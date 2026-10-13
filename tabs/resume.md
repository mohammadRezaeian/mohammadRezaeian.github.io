---
layout: links
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_links

# publish date (used for seo)
# if not specified, site.time will be used.
#date: 2022-03-03 12:32:00 +0000

# for override items in _data/lang/[language].yml
#title: My title
#button_name: "My button"
# for override side_and_top_nav_buttons in _data/conf/main.yml
#icon: "fa fa-bath"

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-03-03 12:32:00 +0000
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
#published: false


# you can always move this content to _data/content/ folder
# just create new file at _data/content/links/[language].yml and move content below.
###########################################################
#                Links Page Data
###########################################################
page_data:
  main:
    header: "Resume"
    info: " "

  # To change order of the Categories, simply change order. (you don't need to change list order.)
  category:
    - title: "Educations"
      type: id_educations
      color: "gray"

    - title: "Experience"
      type: id_experience
      color: "#F4A273"

    - title: "Skills"
      type: id_Skills
      color: "#62b462"

    - title: "Favorites"
      type: id_Favorites
      color: "gray"

    - title: "Projects"
      type: id_projects
      color: "#F4A273"
      
  list:
    # id_educations
    - type: id_educations
      title: "B.S"
      url: "https://garmsar.iau.ir"
      info:  "Computer Engineering-Software <b>B.S</b> IAU Garmsar Branch  <b style=\"float: right;\">2015-2019</b>"

    # Experience
    - type: id_experience
      title: "<a href=https://www.yaasie.com>Yaas Arghavani</a>"
      info:  "<b>Embedded linux Software Developer </b> <b style=\"float: right;\">2024-2026</b><br><br>
      My responsibilities included developing software for <b>embedded Linux devices</b> using C/C++. I was responsible for maintaining and optimizing embedded boards, which involved <b>modifying communication protocols</b>, </b>resolving security vulnerabilities</b>, and implementing new features. Additionally, I utilized the Qt framework to develop applications for cashless kiosk systems.

  
    - type: id_experience
      title: "<a href=http://www.ehyadarman.com>Ehya Darman Pishrafte</a>"
      info:  "<b>Embedded linux Software Developer </b> <b style=\"float: right;\">2022-2024</b><br><br>
      My responsibilities included developing programs in Linux For <b>Embedded Linux Devices</b> using C/C++ Languages, and solve problem embedded boards like ready Framework Qt for build <b>cross platform</b> or <b>custom  build Qt </b> for Board advantech  RSB4710   to give best performance like build and change driver GPU, we Are 3 Developer and we work with  Various Framework Such as Qt, QML and sometimes STL Library"

    - type: id_experience
      title: "<a href=https://Unalink.net>Unalink</a>"
      info:  "<b>C/C++ Developer and SysAdmin</b> <b style=\"float: right;\">2021-2022</b><br></br>
      My responsibilities included developing programs in <b>Linux</b> and <b>Embedded C </b>mostly for <b>ESP32</b>  microcontrollers using <b>IDF</b> In addition to that, implementing hardware and internet protocols were among my tasks."

    - type: id_experience
      title: "<a href=https://hanasystemsco.com/>HANA</a>"
      info:  "<b>C/C++ Developer, DB Designer and SysAdmin</b> <b style=\"float: right;\">2020-2021</b><br><br/<b>Linux</b> and <b>Windows</b> development for Management UAV(Drone) Use-cases with the aid of <b>C++11</b>, <b>Qt</b>, <b>QML</b>, various <b>Database</b> technologies"

    - type: id_Skills
      title: "C/C++"
      info:  "<i>Proficient in:</i> Standard <b>Standard C++1, Qt, Felgo Framework with the usage of QML in order to develop User Interface, and usage of IDF for firmware development.</b> <br> <i>Familiar with:</i> <b>Multi-threading under C++11 thread library</b>"

    - type: id_Skills
      title: "DB"
      info:  "<i>Experienced with:</i>Experienced with: Database design through hand-written queries."

    - type: id_Skills
      title: "GNU/Linux SysAdmin"
      info:  "<i>Experienced with:</i> IPtables , DNS , Docker, Podman , Hardening Linux"

    #Favorites    
    
    - type: id_Favorites
      title: "Embedded Linux"
      info: "I love working with Embedded Linux devices"

    - type: id_Favorites
      title: "IDF"
      info: "Doing activities that few people are interested in attracts me, one of which is development using IDF"

    - type: id_Favorites
      title: "C++"
      info: "Being busy with C/C++ is one of my main hobbies"

    - type: id_Favorites
      title: "GNU/Linux"
      info: "One of my main interests is working with GNU/Linux in any situation"

    - type: id_Favorites
      title: "Reading Book"
      info: "Before starting any of my tasks, I would love to read books and prepare my mind"
      
    
# id_projects
    - type: id_projects
      title: "<b>DK Apadana</b>"
      info: "Khoshe android application"

    - type: id_projects
      title: "<b>HANA</b>"
      info: "<b>System Automation</b> and create other project For <b>Management UAV(Drone)</b> and write <b>Messenger</b>   for local network into company."

    - type: id_projects
      title: "<b>Personal(Qt)</b>"
      info: "First Mirror Finder For Project Fedora (is Distribution Gnu/Linux)"

    - type: id_projects
      title: "<b>Personal(Qt)</b>"
      info: "Music player"
    
    - type: id_projects
      title: "<b>Personal(BASH)</b>"
      info: "Script Music Finder for Distribution Gnu/Linux"

    - type: id_projects
      title: "<b>Personal(Fedora)</b>"
      info: "Script For Install Package and Many configuration for Fedora"

---
