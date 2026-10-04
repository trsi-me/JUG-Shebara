# JUG Shebara

## 1. ما هو المشروع؟

صفحة واحدة بعنوان `JUG Shebara` عن منتجع Shebara. فيها قائمة جانبية، صورة بطل، ومعرض صور أفقي يفتح في صندوق إضاءة عند النقر.

## 2. لماذا يوجد هذا المشروع؟

استنتاج من الكود: الصفحة واجهة عرض بصرية لاسم Shebara مع روابط إلى صفحات أخرى.

## 3. من يستخدمه؟

الزائر. رابط القائمة يقول Login / Sign Up ويشير إلى `login.html`. صفحة تسجيل داخل هذا المجلد غير موجودة.

## 4. ماذا يستطيع النظام أن يفعل؟

زر ☰ يستدعي `openMenu` ويفتح `#sidebar`. النقر على `#overlay` يستدعي `closeMenu`. المعرض يعرض أربع صور من `assets`. النقر على صورة يفتح `#lightbox`. روابط القائمة: `login.html` و`resorts.html` و`experiences.html` و`map.html`. رابط الرجوع: `resorts.html`.

## 5. كيف يعمل النظام؟

ملف HTML واحد فيه CSS وJavaScript داخليان. القائمة تبدأ عند `left: -320px` وتتحرك إلى 0. صندوق الإضاءة `display: none` ثم `flex` عند النقر، ويُغلق بالنقر على الخلفية.

## 6. أمثلة واقعية

فتح الصفحة يظهر عنوان Shebara فوق صورة البطل `nn.jpg`. سحب المعرض يعرض rr.jpg وaa.jpg وff.jpg وss.jpg. نقر بطاقة يكبّر الصورة. نقر ☰ يظهر JUG وروابط القائمة.

## 7. رحلة المستخدم

فتح `JUG Shebara.html`. استخدام القائمة أو المعرض. صفحات Login وResorts وExperiences وMap غير موجودة في المجلد، لذلك تلك الروابط بلا هدف محلي.

## 8. الوحدات والأقسام

| الجزء | المكان |
| --- | --- |
| القائمة | #sidebar و openMenu/closeMenu |
| البطل | header.hero |
| المعرض | section.gallery |
| التكبير | #lightbox |

## 9. الشركات والكيانات

اسم العلامة الظاهر في الصفحة: JUG، وعنوان البطل: Shebara. هيكل شركات أو فروع متعدد غير موجود في الملفات الحالية.

## 10. الصلاحيات

رابط Login / Sign Up موجود كنص. صفحة وآلية صلاحيات غير موجودتين في هذا المجلد.

## 11. الأتمتة وWorkflows

غير موجود في الملفات الحالية.

## 12. التكامل بين الوحدات

القائمة والمعرض وصندوق الإضاءة في الملف نفسه. صور البطاقات من `assets`. صورة البطل مسارها `nn.jpg` في جذر الصفحة.

## 13. المصطلحات

| المصطلح | المعنى |
| --- | --- |
| JUG | النص في .logo |
| Shebara | عنوان البطل |
| lightbox | طبقة تكبير الصورة |

## 14. الأسئلة الشائعة

**هل تسجيل الدخول يعمل؟** الرابط `login.html` موجود. الملف غير موجود في المجلد.

**هل nn.jpg موجودة؟** الوسم يشير إليها. ملف بهذا الاسم غير موجود في المجلد. الموجود صور `assets/aa.jpg` و`ff.jpg` و`rr.jpg` و`ss.jpg`.

## 15. Architecture

```
Browser
  -> JUG Shebara.html
  -> CSS داخلي + Playfair Display من Google Fonts
  -> JS داخلي للقائمة والمعرض
  -> صور assets و nn.jpg
```

## 16. Tech Stack

HTML مع CSS وJavaScript مضمّنين. الخط Playfair Display بوزنين 400 و600 من Google Fonts. `lang="en"` و`dir="ltr"`.

## 17. Project Structure

```
JUG Shebara/
  JUG Shebara.html
  assets/aa.jpg
  assets/ff.jpg
  assets/rr.jpg
  assets/ss.jpg
```

## 18. Frontend

صفحة واحدة. المعرض تمرير أفقي `scroll-snap`. عند `max-width: 768px` يصغر عنوان البطل إلى 1.2rem والبطاقة إلى 250x350. صورة البطل `object-fit: cover` و`brightness(65%)`.

## 19. Backend

غير موجود في الملفات الحالية.

## 20. Request Flow

```
Open HTML
  -> paint hero + gallery
Click menu
  -> sidebar left = 0
Click card img
  -> lightbox display flex
  -> lightbox img src = clicked src
```

## 21. Database

غير موجود في الملفات الحالية.

## 22. API

غير موجود في الملفات الحالية.

## 23. Authentication & Authorization

رابط واجهة دخول فقط. تحقق أو جلسة غير موجودين في الملفات الحالية.

## 24. Security

صندوق الإضاءة يعرض `img.src` من صور الصفحة نفسها. تعقيم أو خادم غير موجود. أيقونة تبويب غير موجودة. شريط التمرير في المعرض مخفي بقاعدة webkit.

## 25. Configuration

الألوان في `:root`: `--primary-color` #007c7c و`--text-dark` #1a1a1a و`--bg-light` #ffffff. ملفات بيئة غير موجودة.

## 26. Integrations

Google Fonts لخط Playfair Display.

## 27. Scheduled Jobs

غير موجود في الملفات الحالية.

## 28. File Storage

صور المعرض الأربع داخل `assets`. `nn.jpg` مشار إليها وغير موجودة في المجلد.

## 29. Logging & Monitoring

غير موجود في الملفات الحالية.

## 30. Installation

افتح `JUG Shebara.html`. المعرض يعمل بالصور الأربع الموجودة. صورة البطل والصفحات المرتبطة تحتاج ملفاتها بجانب HTML.

## 31. Development Guide

أضف بطاقة `.card` بصورة جديدة داخل `section.gallery`. روابط القائمة عناصر `a` في الشريط. الدالتان `openMenu` و`closeMenu` في أسفل الملف.

## 32. Deployment

غير موجود في الملفات الحالية.

## 33. Backup & Recovery

غير موجود في الملفات الحالية.

## 34. Troubleshooting

| العرض | السبب |
| --- | --- |
| البطل بلا صورة | nn.jpg غير موجودة |
| Login يفتح 404 على الخادم | login.html غير موجودة |
| Map وResorts وExperiences | الملفات المذكورة في الروابط غير موجودة |

## 35. Dependencies

Playfair Display من Google Fonts. إصدار الخط غير موثق سوى الوزنين 400 و600.

## 36. Known Limitations

الصفحات المرتبطة وصورة البطل غير موجودة في المجلد. تسجيل الدخول نص رابط فقط. أيقونة تبويب غير موجودة. CSS وJS غير منفصلين عن HTML.

## 37. Current System State

| الحالة | التفصيل |
| --- | --- |
| موجود | قائمة ومعرض وأربع صور وتكبير |
| روابط بلا ملفات | login وresorts وexperiences وmap وnn.jpg |
| غير موثق | وصف المنتجع ونصوص المرافق |

## 38. Architecture Decisions

استنتاج من الكود: ملف واحد يكفي لعرض الصفحة. القائمة ثابتة الموضع بعرض 300px وتدخل من اليسار.

## 39. سجل التغييرات

سجل إصدارات غير موجود في الملفات الحالية.

## System Overview

```
الزائر
  -> JUG Shebara.html
  -> قائمة جانبية
  -> بطل Shebara
  -> معرض assets
  -> lightbox
```

## Quick Reference

| الجزء | التقنية | الموقع | الوظيفة |
| --- | --- | --- | --- |
| الصفحة | HTML+CSS+JS | JUG Shebara.html | عرض Shebara |
| الصور | JPG | assets/ | أربع صور معرض |
| الخط | Google Fonts | Playfair Display | عناوين |

## Quick Start

افتح `JUG Shebara.html`.

## For Non-Technical Users

صفحة عرض باسم Shebara، فيها قائمة ومعرض صور.

## For Developers

كل الواجهة في ملف HTML واحد. الصور المستخدمة في المعرض تحت `assets`.
