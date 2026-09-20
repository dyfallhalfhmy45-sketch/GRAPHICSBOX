# Graphics Box — Draw-to-Play Physics Sandbox

**English / العربية**

Draw an object, release your finger or mouse, and watch gravity take over. Graphics Box is a responsive, bilingual 2D physics playground built with HTML Canvas, JavaScript, and a locally bundled Matter.js engine.

## Features

- Freehand strokes, straight lines, rectangles, and circles become collidable bodies.
- Gravity, rotation, friction, and adjustable bounciness.
- Fixed platforms and ramps for building small levels.
- Grab and drag objects, erase, undo the latest object, clear, and reset the demo.
- Pause to build, then play to test.
- Full English / Arabic interface with RTL layout and remembered language preference.
- Mouse, stylus, and touch input; responsive mobile layout.
- Works offline: no API keys, server, accounts, CDN requests, or installation.

## Run

Download and extract the project ZIP, then open **index.html** in a modern browser. Keep `app.js`, `style.css`, and the `vendor` folder beside it. Do not open the HTML from inside the ZIP preview.

If your browser restricts local files, serve this folder with `python3 -m http.server 8000` and open `http://localhost:8000`.

## Controls

| Control | Action |
| --- | --- |
| Freehand / Line / Rectangle / Circle | Drag on the canvas and release to create a body |
| Fixed in place | Make new objects static; useful for ramps |
| Grab | Drag an existing object; paused objects and static platforms can also be moved |
| Erase | Tap an object to remove it |
| Gravity | Change gravity for the whole scene (0–2×) |
| Bounciness / Color | Apply to newly drawn objects |
| Space | Pause / resume (when not focused on a control) |
| Ctrl+Z / Cmd+Z | Remove the most recently added object |
| Reset scene | Restore the sample scene and resume |
| Clear canvas | Remove all user objects and platforms |

Freehand drawings are rigid chains of thick segments. Closed freehand outlines remain hollow; use the rectangle and circle tools for filled solids. The scene uses a fixed 1000 × 650 coordinate system that scales to the available canvas; unused space may appear on narrow screens. Drawings outside its bounds are clamped to its edges.

## Publish with GitHub Pages

1. Create a GitHub repository, for example `graphics-box`.
2. Upload the extracted files with **index.html at the repository root**, preserving the `vendor` folder.
3. In repository **Settings → Pages**, choose **Deploy from a branch**.
4. Select your branch (usually `main`) and **/(root)**, then save.
5. Open the website URL displayed by GitHub after publication completes.

This project does not require a build command. The Pages site is separate from the GitHub repository page. The exact Pages availability depends on your repository and account settings.

Official setup reference: [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Files

```text
index.html                 Interface and metadata
style.css                  Responsive dark theme and RTL layout
app.js                     Drawing, controls, rendering, translations
vendor/matter.min.js       Matter.js 0.20.0, bundled locally
vendor/LICENSE-Matter.txt  Third-party MIT license
README.md                  This bilingual guide
LICENSE                    Project MIT license
.nojekyll                  Serve static assets directly on GitHub Pages
```

## Technical notes and limitations

Matter.js runs at a fixed 60 Hz physics step with a bounded catch-up interval. Canvas rendering uses requestAnimationFrame and a capped pixel ratio. The engine sleeps resting bodies, limits scenes to 150 bodies, and samples at most 90 points per stroke for performance. Complex compound strokes can be expensive on older phones. Very fast or very thin bodies may pass through each other; this is a creative sandbox, not an engineering simulator.

There is no scene persistence/export, scoring, goal system, audio, or backend. Reset/clear and refreshing the page discard drawings. Undo removes the latest body; it does not reverse erasures, motion, or setting changes. Bounciness applies only to newly drawn bodies. Language preference alone is saved locally when browser storage is available.

## License and credits

Project code: MIT; see LICENSE. Physics engine: [Matter.js](https://github.com/liabru/matter-js), version 0.20.0, Copyright (c) Liam Brummitt, MIT. Its original license is included in `vendor`.

---

## العربية

**Graphics Box — صندوق الرسم والفيزياء**

موقع تفاعلي ترسم فيه خطوطًا وأشكالًا، ثم تتحول عند رفع إصبعك أو الماوس إلى أجسام تتأثر بالجاذبية والتصادم والدوران. تستطيع بناء المنحدرات والمنصات وتجربة مشاهد لعب بسيطة مباشرة.

### التشغيل

1. حمّل ملف المشروع المضغوط وفك الضغط عنه.
2. افتح `index.html` في متصفح حديث.
3. أبقِ `app.js` و`style.css` ومجلد `vendor` بجانب ملف الصفحة.

يعمل محليًا دون إنترنت أو حساب أو مفاتيح API. إذا منع المتصفح فتح الملفات المحلية، شغّل `python3 -m http.server 8000` داخل المجلد وافتح `http://localhost:8000`.

### الاستخدام

- اختر الرسم الحر أو الخط أو المستطيل أو الدائرة، واسحب على اللوحة ثم اترك المؤشر.
- فعّل **ثابت في مكانه** لإنشاء منصات ومنحدرات لا تسقط.
- استخدم **تحريك** لسحب الأجسام، و**مسح** لإزالة جسم بالضغط عليه.
- أوقف المحاكاة مؤقتًا لبناء المشهد ثم شغّلها لتجربته.
- الجاذبية تؤثر على المشهد كاملًا. اللون والارتداد يطبّقان على الأجسام الجديدة.
- **تراجع** يزيل آخر جسم أُضيف. **مسح اللوحة** يزيل الأجسام والمنصات. **إعادة المشهد** يستعيد المثال.
- بدّل بين العربية والإنجليزية من أعلى الصفحة.

الرسم الحر يصنع سلسلة صلبة من المقاطع، والأشكال المغلقة المرسومة يدويًا تبقى مجوفة. استخدم الدائرة والمستطيل للحصول على أجسام ممتلئة. قد تمر الأجسام السريعة جدًا أو الرفيعة عبر بعضها؛ المشروع للتجربة والإبداع وليس لمحاكاة هندسية دقيقة. الحد الأقصى 150 جسمًا، ولا يوجد حفظ للمشاهد؛ تحديث الصفحة يفقد الرسومات.

### الرفع على GitHub ونشر الموقع

1. أنشئ مستودعًا جديدًا مثل `graphics-box`.
2. ارفع **محتويات المجلد بعد فك الضغط**، وليس ملف ZIP وحده. ضع `index.html` في جذر المستودع واحتفظ بمجلد `vendor` كاملًا.
3. افتح **Settings → Pages** واختر **Deploy from a branch**.
4. اختر فرع `main` ومجلد **/(root)** ثم احفظ.
5. انتظر اكتمال النشر وافتح رابط الموقع الذي يعرضه GitHub.

ملف المشروع متاح برخصة MIT، ويستخدم محرك Matter.js برخصة MIT المرفقة.
