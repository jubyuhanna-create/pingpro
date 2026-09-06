# موقع PingPro

موقع بسيط بصفحة وحدة (single page)، بدون أي framework، مبني بـ HTML/CSS/JS خام
عشان يكون سريع وقوي بالـ SEO. فيه زر "Buy Now" يوديك مباشرة لمتجر Payhip.

## قبل ما تنشر: بدّل الدومين

كل ملفات الموقع فيها رابط placeholder اسمه:

```
https://your-username.github.io/pingpro/
```

لازم تستبدله بالرابط الحقيقي بعد ما تنشر على GitHub Pages (خطوات النشر تحت).
الملفات اللي فيها هذا الرابط:

- `index.html` — بالأسطر اللي فيها `canonical`, `og:url`, `og:image`,
  `twitter:image`, وبال JSON-LD (`"url"`)
- `robots.txt` — سطر `Sitemap:`
- `sitemap.xml` — سطر `<loc>`

أسهل طريقة: افتح كل ملف وسوي "Find & Replace" لـ
`your-username.github.io/pingpro` واستبدلها بالرابط الحقيقي متاعك.

## خطوات النشر على GitHub Pages

1. سوي حساب GitHub لو ما عندك، وسوي repository جديد (public)، سمّيه مثلاً `pingpro`.
2. ارفع كل محتويات مجلد `website/` (يعني `index.html`, `robots.txt`,
   `sitemap.xml`, `favicon.ico`, `favicon.png`, ومجلد `assets/`) لجذر
   الـ repository — إما بالسحب والإفلات من واجهة GitHub، أو عبر:
   ```
   git init
   git add .
   git commit -m "PingPro website"
   git branch -M main
   git remote add origin https://github.com/USERNAME/pingpro.git
   git push -u origin main
   ```
3. روح لإعدادات الـ repository → Settings → Pages.
4. تحت "Build and deployment"، اختار Source: **Deploy from a branch**،
   وبعدين Branch: **main** والمجلد **/ (root)**، واحفظ.
5. استنى دقيقة وحدة، بيطلعلك رابط الموقع فوق نفس الصفحة، شكله:
   ```
   https://USERNAME.github.io/pingpro/
   ```
6. رجع لكل الملفات وبدّل الـ placeholder (فوق) بهذا الرابط الحقيقي.
7. اعمل commit وpush تاني للتحديث.

## عن الـ SEO — كلام صريح

سويت كل شي ممكن سويه من ناحية **on-page SEO** (اللي جوا الموقع نفسه):
عنوان ووصف محسّنين، بيانات منظمة (JSON-LD) لجوجل يفهم إنه منتج وبيسعره،
صور بـ alt text، sitemap وrobots.txt، تحميل سريع (خط الصفحة كله تقريباً
HTML/CSS عادي بدون مكتبات ثقيلة)، وتصميم متجاوب مع الجوال.

**بس** خلّيني أكون صريح معك: محد يقدر يضمنلك تترتيب #1 على جوجل بس من
تصميم الموقع. الترتيب يعتمد كمان على:
- عمر الدومين وmoqع الثقة فيه (domain authority)
- عدد المواقع الثانية اللي تربط لموقعك (backlinks) — أهم عامل تقريباً
- المنافسة على نفس الكلمات المفتاحية
- الوقت (جوجل ياخذ أسابيع لفهرسة موقع جديد)

يعني هذا الموقع جاهز بأفضل صورة تقنياً، بس الترتيب الفعلي رح يحتاج وقت
ومجهود تسويقي إضافي (مشاركته، روابط من مواقع تانية، محتوى إضافي بالوقت).

### خطوة إضافية توصيك فيها
بعد ما ينشر الموقع، سجله بـ [Google Search Console](https://search.google.com/search-console)
(مجاني) وقدّم له رابط الـ sitemap — هذا بيسرّع فهرسة جوجل للموقع كتير.

## هيكلية الملفات

```
website/
├── index.html
├── robots.txt
├── sitemap.xml
├── favicon.ico
├── favicon.png
└── assets/
    ├── css/style.css
    ├── js/main.js
    └── images/ (لوغو، سكرين شوتس، صورة المشاركة على السوشال ميديا)
```
