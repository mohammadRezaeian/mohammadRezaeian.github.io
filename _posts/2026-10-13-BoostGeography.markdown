---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: Route Planning and Geometric Calculations.
title: "Route Planning and Geometric Calculations"

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Mohammad
# multiple category is not supported
category: c++
# multiple tag entries are possible
tags: [Linux, Developing, General, C++]
# thumbnail image for post
img: ":Geometric.jpg"
# disable comments on this page
comments_disable: false

# publish date
date: 2026-10-18 15:00:00 +0900

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-01-01 10:04:30 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
published: true
---


# Route Planning and Geometric Calculations

☕ Before reading, make yourself a cup of coffee or tea. You're going to need it! 😄

## 1. Introduction

The purpose of this document is to explain how to calculate a route between a starting point and a destination, generate waypoints, and check whether a route is allowed or forbidden.

The system can be used for humans, drones, robots, and other machines that need to move from one location to another.

The main goal is to calculate a suitable route while avoiding forbidden areas and respecting allowed areas when required.

The system uses the following tools:

- **Qt `QGeoCoordinate`** for geographic coordinates, distances, bearings, and calculating new positions.
- **Boost.Geometry** for geometric operations, such as checking whether a route intersects or enters a polygon.
- **Waypoints** to represent the points that a human or machine can follow along the route.

## 2. Understanding Waypoints

A waypoint is a point along a route that tells a human or machine where to go next.

Before generating waypoints, we must decide how far apart they should be. For example, we can generate a new waypoint every 1 meter, 10 meters, or 100 meters, depending on the requirements of the system.

The distance between waypoints can depend on the total route distance, the type of machine, and the required accuracy.

For example:

- A short route may need only a few waypoints.
- A long route may need more waypoints.
- A route near a forbidden area may require additional waypoints to describe a safe detour.

The distance between waypoints should be selected according to the requirements of the system. Using a smaller distance creates more waypoints, but it does not automatically guarantee a safer route.

## 3. Calculating the Distance to the Destination

Qt provides the `QGeoCoordinate::distanceTo()` function to calculate the distance between two geographic coordinates.

Example:

```cpp
double distance = startGeo.distanceTo(destinationGeo);
```

Here:

- `startGeo` represents the starting coordinate.
- `destinationGeo` represents the destination coordinate.
- `distance` represents the distance between the two coordinates in meters.

This distance helps us understand how far we must travel to reach the destination.

However, `distanceTo()` calculates the geographic distance between two points. It does not calculate the length of a route that avoids obstacles or forbidden areas.

If the route must go around an obstacle, the actual route distance will be greater than the direct distance between the start and destination.

## 4. Calculating the Next Waypoint

Qt provides the `QGeoCoordinate::atDistanceAndAzimuth()` function to calculate a new geographic coordinate from an existing coordinate.

```cpp
QGeoCoordinate nextGeo =
    curretRoute.atDistanceAndAzimuth(
        distance,
        angle,
        altitude
    );
```

The function uses three parameters:

- `distance`: The distance to travel from the current coordinate, in meters.
- `angle`: The azimuth or bearing, in degrees, measured clockwise from true north.
- `altitude`: The altitude assigned to the resulting coordinate, in meters.

For example, an azimuth of 0 degrees points north, 90 degrees points east, 180 degrees points south, and 270 degrees points west.

This function helps us calculate the next waypoint in a specified direction.

We can repeat this process to generate waypoints along a route. However, each new waypoint must be checked against the route constraints before it is accepted.

**Important:** The altitude parameter specifies the altitude of the resulting coordinate. It does not mean that the machine moves vertically by that amount.

## 5. Understanding Allowed and Forbidden Areas

The system may contain two types of geographic areas:

### 5.1. Allow Areas

An Allow area represents a region where movement is permitted or, depending on the routing rules, required.

The routing algorithm must determine how the Allow area affects the route. For example, the route may be required to enter the area, remain inside it, or pass through it before continuing to the destination.

These rules must be defined before calculating the route.

### 5.2. Disallow Areas (Worker Areas)

A Disallow area represents a region that the route must not enter.

For example, if a polygon represents a forbidden area, the routing algorithm must check whether the next waypoint or the segment connecting the current waypoint to the next waypoint enters or crosses that polygon.

If the proposed segment violates the routing rules, the algorithm must search for an alternative route.

Checking only the next waypoint is not sufficient. Both endpoints can be outside a forbidden polygon while the segment between them crosses the polygon.

## 6. Using Boost.Geometry

Boost.Geometry provides functions for checking relationships between geometric objects.

Before performing these operations, we must define our points and polygons correctly.

For example, if we use `boost::geometry::model::d2::point_xy<double>`, the coordinates are stored in the order `(longitude, latitude)` when using geographic longitude and latitude values.

This is different from the usual constructor order of `QGeoCoordinate`, which is `(latitude, longitude)`.

We must be careful when converting between these coordinate types.

### 6.1. The `bg::correct()` Function

The `bg::correct()` function corrects the structural conventions of a supported geometry, such as polygon ring orientation and closure.

Example:

```cpp
bg::correct(workerPolygon);
```

A polygon must follow the conventions expected by the selected Boost.Geometry model and algorithms.

However, `bg::correct()` does not repair every possible geometry problem. It does not automatically make a self-intersecting or otherwise invalid polygon valid.

For more complex cases, we should also validate the polygon before using it.

### 6.2. The `bg::covered_by()` Function

The `bg::covered_by()` function checks whether one geometry is completely covered by another geometry.

For example:

```cpp
bool insideOrOnBoundary =
    bg::covered_by(point, workerPolygon);
```

This checks whether the point is inside the polygon or on its boundary.

It is useful when we need to determine whether a waypoint belongs to a forbidden area or whether a point lies within an allowed region.

The result must be interpreted according to the routing rules. A point on the boundary may need to be treated as forbidden if the route must remain strictly outside the area.

We can also use `covered_by()` with other supported geometry combinations, such as checking whether an entire route segment is contained within a polygon.

### 6.3. The `bg::intersects()` Function

The `bg::intersects()` function checks whether two geometries have any point in common.

For example:

```cpp
bool collision =
    bg::intersects(routeSegment, polygon);
```

This checks whether the route segment and the forbidden polygon intersect.

An intersection can occur when the segment crosses the polygon boundary, touches it, or lies inside the polygon.

Therefore, this function is useful for detecting potential conflicts between a proposed route segment and a forbidden area.

If an intersection is detected, the algorithm must decide whether the segment violates the routing rules and, if necessary, search for an alternative route.

### 6.4. Understanding the Difference

The functions serve different purposes:

- `bg::covered_by()`: Checks whether a geometry is completely covered by another geometry.
- `bg::intersects()`: Checks whether two geometries have any point in common.
- `bg::correct()`: Corrects polygon conventions, including ring orientation and closure.

These functions should not be treated as interchangeable. We must choose the appropriate function according to the question we want to answer.

## 7. Checking the Route Segment

When calculating a route, we must check not only individual waypoints but also the segments connecting them.

For example, let `startGeo` be the current waypoint and `nextGeo` be the proposed next waypoint.

The algorithm can follow these steps:

1. Calculate the next waypoint.
2. Convert the current and next coordinates into the appropriate Boost.Geometry point type.
3. Create a segment between these points.
4. Check whether the segment intersects a forbidden polygon.
5. Reject the segment if it violates the routing rules.
6. Search for another direction or waypoint.
7. Repeat the checks until a valid segment is found or the search limit is reached.

This process helps prevent the route from passing through a forbidden polygon even when both endpoints are outside it.

The same principle applies to Allow areas, but the exact check depends on whether the route must enter the area, cross it, or remain entirely inside it.

## 8. Coordinate Systems and Distance Calculations

One important consideration is the coordinate system used by Boost.Geometry.

If a polygon uses longitude and latitude stored in a Cartesian `point_xy<double>` model, Boost.Geometry may interpret those values as planar coordinates rather than geographic coordinates.

For example, a distance calculated directly from longitude and latitude values may be expressed in angular coordinate units, not meters.

Therefore, we must not assume that `bg::distance()` returns meters when working directly with longitude and latitude in a Cartesian geometry model.

If the algorithm requires distances in meters, we should use an appropriate geographic calculation strategy or transform the coordinates into a suitable projected coordinate system.

Qt's `QGeoCoordinate::distanceTo()` and Boost.Geometry's `bg::distance()` may therefore produce values with different meanings, depending on the coordinate systems and strategies used.

The coordinate system and units must be consistent throughout the route-planning algorithm.

## 9. The Complete Route-Planning Process

The route-planning algorithm can be divided into the following stages:

1. **Receive the input:** Get the starting coordinate, destination coordinate, Allow areas, and forbidden areas.
2. **Validate the polygons:** Check the polygon structures and correct their orientation and closure where necessary.
3. **Calculate the direct distance:** Use `distanceTo()` to calculate the geographic distance between the start and destination.
4. **Determine waypoint spacing:** Select a suitable distance between consecutive waypoints.
5. **Generate the next waypoint:** Use `atDistanceAndAzimuth()` to calculate a candidate coordinate.
6. **Check the candidate route segment:** Use the appropriate Boost.Geometry operations to detect intersections with forbidden areas and verify any Allow-area requirements.
7. **Find an alternative:** If the candidate segment violates the rules, try another direction or search for a detour.
8. **Repeat the process:** Continue until the destination is reached or the algorithm determines that no valid route can be found.
9. **Validate the complete route:** Check all route segments and confirm that the generated route satisfies the defined constraints.

The algorithm must also define a maximum search distance, a maximum number of attempts, or another stopping condition to avoid an endless search when no valid route can be found.

## 10. Important Limitations

The route-planning algorithm must consider several limitations:

- A valid waypoint does not guarantee that the segment leading to it is valid.
- A polygon must be valid for the geometric operations to produce reliable results.
- A direct geographic distance is not necessarily the actual distance of a route around obstacles.
- Coordinate order and units must be consistent between Qt and Boost.Geometry.
- A two-dimensional polygon check does not consider altitude. If altitude affects whether a route is safe, it must be checked separately.
- A mathematically valid route does not automatically guarantee real-world safety. Additional margins and safety constraints may be required.

## Conclusion

The main purpose of this system is to generate waypoints and calculate a route while respecting geographic constraints.

Qt provides the functions needed to calculate geographic distances and new coordinates. Boost.Geometry provides the functions needed to check the relationships between route segments and allowed or forbidden areas.

By combining these operations, we can generate a route, evaluate each proposed segment, and search for an alternative when a segment violates the defined rules.

The most important principle is to validate the geometry and coordinate system before performing geometric calculations, and to check the complete route rather than relying only on individual waypoints.


*Thank you for reading this post. I wish you to have a great time.*