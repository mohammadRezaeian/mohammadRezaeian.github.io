---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: Cheet Sheet Math Part 1
title: "باهم ریاضی بخونیم و لذت ببریم"

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Mohammad
# multiple category is not supported
category: Math
# multiple tag entries are possible
tags: [Math]
# thumbnail image for post
img: ":Math.webp"
# disable comments on this page
comments_disable: false

# publish date
date: 2026-11-01 12:00:00 +0900

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

# 📜 چیت‌شیت جامع و کامل ریاضیات پایه (همراه با مثال)

## بخش ۱: حساب پایه، اعداد و اولویت‌ها
* **قانون علامت‌ها (جمع و تفریق):** هم‌علامت‌ها جمع می‌شوند و علامت می‌ماند؛ غیرهم‌علامت‌ها از هم کم می‌شوند و علامت عدد بزرگ‌تر می‌نشیند.
  * مثال: $-3 - 2 = -5$ | $-5 + 3 = -2$
* **قانون علامت‌ها (ضرب و تقسیم):** هم‌علامت $\rightarrow$ مثبت، غیرهم‌علامت $\rightarrow$ منفی.
  * مثال: $(-3) \times (-2) = +6$ | $(+4) \times (-2) = -8$
* **اولویت عملیات (PEMDAS):** پرانتز $\rightarrow$ توان/رادیکال $\rightarrow$ ضرب/تقسیم $\rightarrow$ جمع/تفریق.
  * مثال: $2 + 3 \times 4 = 2 + 12 = 14$
* **کسرها (جمع و تفریق):** نیاز به مخرج مشترک.
  * مثال: $\frac{1}{2} + \frac{1}{3} = \frac{3 + 2}{6} = \frac{5}{6}$
* **کسرها (ضرب و تقسیم):** ضرب صورت در صورت و مخرج در مخرج / تقسیم = ضرب در معکوس کسر دوم.
  * مثال: $\frac{2}{3} \times \frac{3}{4} = \frac{6}{12} = \frac{1}{2}$
* **تناسب (طرفین وسطین):**
  * مثال: $\frac{2}{3} = \frac{4}{x} \rightarrow 2x = 12 \rightarrow x = 6$

---

## بخش ۲: توان، جذر و رادیکال‌ها
* **توان:** ضرب تکراری یک عدد در خودش.
  * مثال: $2^3 = 2 \times 2 \times 2 = 8$
* **جذر (رادیکال):** معکوس توان دو.
  * مثال: $\sqrt{25} = 5$
* **ساده‌سازی رادیکال‌های غیرمربع کامل:** شکستن به حاصل‌ضرب مربع کامل.
  * مثال: $\sqrt{18} = \sqrt{9 \times 2} = 3\sqrt{2}$
* **جمع و تفریق رادیکال‌های متشابه:**
  * مثال: $3\sqrt{2} + 5\sqrt{2} = 8\sqrt{2}$

---

## بخش ۳: جبر مقدماتی، اتحادها و معادلات
* **مربع دو جمله‌ای:** $(a \pm b)^2 = a^2 \pm 2ab + b^2$ (جمله آخر همیشه مثبت است).
  * مثال: $(x + 3)^2 = x^2 + 6x + 9$
* **اتحاد مزدوج:** $(a - b)(a + b) = a^2 - b^2$ *(برای تجزیه: $x^2 - 16 = (x-4)(x+4)$)*
  * مثال: $(x - 5)(x + 5) = x^2 - 25$
* **اتحاد جمله مشترک:** $(x + a)(x + b) = x^2 + (a + b)x + ab$
  * مثال: $(x + 2)(x + 3) = x^2 + 5x + 6$
* **معادلات درجه دو (ویژگی صفر):**
  * مثال: $(x - 3)(x + 2) = 0 \rightarrow x = 3, x = -2$

---

## بخش ۴: هندسه و اندازه‌گیری
* **محیط:** مجموع طول تمامی اضلاع بیرونی.
  * مثال: مستطیل با طول ۵ و عرض ۳ $\rightarrow \text{محیط} = 5 + 5 + 3 + 3 = 16$
* **مساحت:** طول $\times$ عرض.
  * مثال: مستطیل با طول ۵ و عرض ۳ $\rightarrow \text{مساحت} = 5 \times 3 = 15$
* **قضیه فیثاغورس (مثلث قائم‌الزاویه):** $(\text{وتر})^2 = (\text{ضلع}_1)^2 + (\text{ضلع}_2)^2$
  * پیدا کردن وتر: اضلاع ۳ و ۴ $\rightarrow \text{وتر} = \sqrt{3^2 + 4^2} = \sqrt{25} = 5$
  * پیدا کردن ضلع مجهول: وتر ۱۰، ضلع ۶ $\rightarrow \text{ضلع} = \sqrt{10^2 - 6^2} = \sqrt{64} = 8$

---

## بخش ۵: مختصات و توابع
* **مختصات $(x, y)$:** $x$ افقی، $y$ عمودی.
  * مثال: نقطه $(-4, 3)$ یعنی ۴ واحد چپ و ۳ واحد بالا.
* **ماشین تابع:** ورودی $x$ $\rightarrow$ قانون $\rightarrow$ خروجی $y$.
  * مثال: $y = 2x + 3$ با ورودی $x = 5 \rightarrow y = 2(5) + 3 = 13$
* **معادله خط ($y = mx + b$):** $m$ شیب خط، $b$ عرض از مبدأ.
  * مثال: در خط $y = -2x + 7$، شیب خط $m = -2$ (سرپایینی) و عرض از مبدأ $b = 7$ است.

---

## بخش ۶: نامعادلات
* **قانون طلایی علامت منفی:** ضرب یا تقسیم طرفین نامعادله در عدد منفی، جهت علامت را برعکس می‌کند.
  * مثال: $-2x \le 8 \rightarrow x \ge -4$ (جهت علامت برگشت).
# 📜 چیت‌شیت جامع و کامل ریاضیات پایه (همراه با مثال)

## بخش ۱: حساب پایه، اعداد و اولویت‌ها
* **قانون علامت‌ها (جمع و تفریق):** هم‌علامت‌ها جمع می‌شوند و علامت می‌ماند؛ غیرهم‌علامت‌ها از هم کم می‌شوند و علامت عدد بزرگ‌تر می‌نشیند.
  * مثال: $-3 - 2 = -5$ | $-5 + 3 = -2$
* **قانون علامت‌ها (ضرب و تقسیم):** هم‌علامت $\rightarrow$ مثبت، غیرهم‌علامت $\rightarrow$ منفی.
  * مثال: $(-3) \times (-2) = +6$ | $(+4) \times (-2) = -8$
* **اولویت عملیات (PEMDAS):** پرانتز $\rightarrow$ توان/رادیکال $\rightarrow$ ضرب/تقسیم $\rightarrow$ جمع/تفریق.
  * مثال: $2 + 3 \times 4 = 2 + 12 = 14$
* **کسرها (جمع و تفریق):** نیاز به مخرج مشترک.
  * مثال: $\frac{1}{2} + \frac{1}{3} = \frac{3 + 2}{6} = \frac{5}{6}$
* **کسرها (ضرب و تقسیم):** ضرب صورت در صورت و مخرج در مخرج / تقسیم = ضرب در معکوس کسر دوم.
  * مثال: $\frac{2}{3} \times \frac{3}{4} = \frac{6}{12} = \frac{1}{2}$
* **تناسب (طرفین وسطین):**
  * مثال: $\frac{2}{3} = \frac{4}{x} \rightarrow 2x = 12 \rightarrow x = 6$

---

## بخش ۲: توان، جذر و رادیکال‌ها
* **توان:** ضرب تکراری یک عدد در خودش.
  * مثال: $2^3 = 2 \times 2 \times 2 = 8$
* **جذر (رادیکال):** معکوس توان دو.
  * مثال: $\sqrt{25} = 5$
* **ساده‌سازی رادیکال‌های غیرمربع کامل:** شکستن به حاصل‌ضرب مربع کامل.
  * مثال: $\sqrt{18} = \sqrt{9 \times 2} = 3\sqrt{2}$
* **جمع و تفریق رادیکال‌های متشابه:**
  * مثال: $3\sqrt{2} + 5\sqrt{2} = 8\sqrt{2}$

---

## بخش ۳: جبر مقدماتی، اتحادها و معادلات
* **مربع دو جمله‌ای:** $(a \pm b)^2 = a^2 \pm 2ab + b^2$ (جمله آخر همیشه مثبت است).
  * مثال: $(x + 3)^2 = x^2 + 6x + 9$
* **اتحاد مزدوج:** $(a - b)(a + b) = a^2 - b^2$ *(برای تجزیه: $x^2 - 16 = (x-4)(x+4)$)*
  * مثال: $(x - 5)(x + 5) = x^2 - 25$
* **اتحاد جمله مشترک:** $(x + a)(x + b) = x^2 + (a + b)x + ab$
  * مثال: $(x + 2)(x + 3) = x^2 + 5x + 6$
* **معادلات درجه دو (ویژگی صفر):**
  * مثال: $(x - 3)(x + 2) = 0 \rightarrow x = 3, x = -2$

---

## بخش ۴: هندسه و اندازه‌گیری
* **محیط:** مجموع طول تمامی اضلاع بیرونی.
  * مثال: مستطیل با طول ۵ و عرض ۳ $\rightarrow \text{محیط} = 5 + 5 + 3 + 3 = 16$
* **مساحت:** طول $\times$ عرض.
  * مثال: مستطیل با طول ۵ و عرض ۳ $\rightarrow \text{مساحت} = 5 \times 3 = 15$
* **قضیه فیثاغورس (مثلث قائم‌الزاویه):** $(\text{وتر})^2 = (\text{ضلع}_1)^2 + (\text{ضلع}_2)^2$
  * پیدا کردن وتر: اضلاع ۳ و ۴ $\rightarrow \text{وتر} = \sqrt{3^2 + 4^2} = \sqrt{25} = 5$
  * پیدا کردن ضلع مجهول: وتر ۱۰، ضلع ۶ $\rightarrow \text{ضلع} = \sqrt{10^2 - 6^2} = \sqrt{64} = 8$

---

## بخش ۵: مختصات و توابع
* **مختصات $(x, y)$:** $x$ افقی، $y$ عمودی.
  * مثال: نقطه $(-4, 3)$ یعنی ۴ واحد چپ و ۳ واحد بالا.
* **ماشین تابع:** ورودی $x$ $\rightarrow$ قانون $\rightarrow$ خروجی $y$.
  * مثال: $y = 2x + 3$ با ورودی $x = 5 \rightarrow y = 2(5) + 3 = 13$
* **معادله خط ($y = mx + b$):** $m$ شیب خط، $b$ عرض از مبدأ.
  * مثال: در خط $y = -2x + 7$، شیب خط $m = -2$ (سرپایینی) و عرض از مبدأ $b = 7$ است.

---

## بخش ۶: نامعادلات
* **قانون طلایی علامت منفی:** ضرب یا تقسیم طرفین نامعادله در عدد منفی، جهت علامت را برعکس می‌کند.
  * مثال: $-2x \le 8 \rightarrow x \ge -4$ (جهت علامت برگشت).

  <!-- KaTeX Stylesheet & Script for rendering math formulas -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.css" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.js" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/contrib/auto-render.min.js" crossorigin="anonymous"
    onload="renderMathInElement(document.body, {
      delimiters: [
        {left: '$$', right: '$$', display: true},
        {left: '$', right: '$', display: false}
      ]
    });"></script>



<style>
  /* راست‌چین کردن کل محتوای پست‌های وبلاگ */
  body, .post-content, .content {
    direction: rtl;
    text-align: right;
  }
  /* مرتب‌سازی لیست‌ها و بولت‌ها برای حالت راست‌چین */
  .post-content ul, .post-content ol {
    padding-right: 20px;
    padding-left: 0;
  }
</style>