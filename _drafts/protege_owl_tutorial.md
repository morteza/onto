---
layout: post
title:  "راهنمای ساخت آنتولوژی OWL با Protégé نسخه ۴"
date:   2014-0-08 12:34:03
date_fa: "۶ آگوست ۲۰۱۴"
date_shamsi: "۱۵ مرداد ۱۳۹۳"
categories: intro tutorial
permalink: /protege_tutorial
---

راهنمای کاربردیِ ساخت آنتولوژی‌های OWL با Protégé نسخه ۴


فصل یک — مقدمه
این راهنما به معرفی نرم‌افزار Protege نسخه ۴ برای ساختن آنتولوژی‌ها به زبان OWL می‌پردازد. فصل سوم یک نمای کلی از زبان آنتولوژی OWL ارائه می‌دهد. در فصل چهار ساخت یک آنتولوژی OWL-DL و استفاده از استنتاج‌گر منتطق توصیفی برای بررسی سازگاریِ آنتولوژی (consistency) و محاسبه‌ی خودکار ساختار سلسله‌مراتبی کلاس‌های آنتولوژی ارائه می‌شود. در فصل ۷ نیز بعضی از ساختارهای OWL مانند محدودیت hasValue و کلاس‌های شمارشی (Enumerated Classes) که به صورت مستقیم در این راهنما استفاده نشده‌اند را بررسی می‌کنیم.

۱.۱. قواعد نوشتاری

نام کلاس، صفت‌ها (Property) و نمونه‌ها () با فونت سنزسریف نوشته شده‌اند، مانند این.
نام نماها و واسط‌های کاربری به این صورت نمایش داده شده‌اند.
وقتی در یک تمرین نیاز به تایپ اطلاعاتی در نرم‌افزار Protege باشد، از فونت دستگاه تایپ مانند این استفاده می‌شود.
تمرین‌ها و قدم‌های لازمِ خودآموز مانند موردِ زیر نمایش داده شده‌اند:
تمرین ۱: این کار را بکنید:
۱. این قدم.
۲. سپس این قدم.
۳. سپس این قدم.

نکته: نکته‌ها و پیش‌نهادهای مربوط به پروتژه ۴ و ساخت آنتولوژی‌ها مانند این نمایش داده می‌شوند.
مفهوم: توصیف یعنی معنای چیزها مانند این نمایش داده می‌شوند.
اخطار: تله‌ها و اخطارهای بالقوه به این صورت نمایش داده می‌شوند.
یادداشت: نکات کلی و یادداشت‌های کمکی به این صورت نمایش داده می‌شوند.
واژگان: توصیف واژگان و نام‌های هم‌معنا و جایگزین به این صورت نمایش داده می‌شوند.


فصل دوم — نیازمندی‌ها

برای ادامه و تعقیب این راهنمای خودآموز شما باید به نرم‌افزار پروتژه ۴ دسترسی داشته باشید. این نرم‌افزار از وب‌سایت پروتژه (protege.stanford.edu) قابل دانلود است. پلاگین‌ها و ابزار کمکیِ این نرم‌افزار نیز از وب‌سایت CO-ODE (www.co-ode.org) قابل دانلود است. هم‌چنین پیشنهاد می‌شود از پلاگین OWLViz استفاده شود (هرچند لازم نیست.) این پلاگین امکان نمایش گرافیکی ساختار سلسله‌مراتبیِ دسته‌بندی‌های استخراجی و استنباطی را می‌دهد. برای قدم‌های مورد نیاز برای نصب این ابزار، به مستندهای هر یک از این موارد مراجعه کنید.

فصل سوم — آنتولوژی OWL چیست؟

آنتولوژی‌ها برای استخراج دانش درباره‌ی یک حوزه‌ی خاص مورد علاقه استفاده می‌شوند. یک آنتولوژی به توصیف مفاهیمِ موجود در یک حوزه و ارتباط‌های بین این مفاهیم می‌پردازد. زبان‌های آنتولوژی مختلف ویژگی‌ها و امکانات مختلفی را به این منظور فراهم می‌سازد. آخرین دستاورد در استنانداردسازی زبان‌های آنتولوژی OWL از کنسرسیوم W3C است. همانند پروتژه، OWL توصیف مفاهیم را امکان می‌سازد و علاوه بر این امکانات جدیدی را نیز فراهم می‌سازد. این زبان مجموعه عمل‌گرهای بزرگتری دارد — مانند اشتراک، اجتماع و نفی. این زبان بر مدل منتطقی متفاوتی بنا شده است که علاوه بر امکان تعریف مفاهیم، امکان توصیف آن‌ها را نیز فراهم می‌سازد. در نتیجه مفاهیم پیچیده می‌توانند به کمک مفاهیم ساده‌تری که تعریف شده‌اند، توصیف شوند. هم‌چنین این مدل منطقی اجازه‌ی استفاده از استنتاج‌گر را می‌دهد، که می‌تواند بررسی کند که آیا عباراتِ یک آنتولوژی با هم سازگار هستند یا خیر. استنتاج‌گر همچنین امکان بررسی اینکه کدام مفاهیم را می‌توان ب چه  توصیفی تعریف نمود را می‌دهد. بنابراین استنتاج‌گر می‌تواند به نگه‌داری و توسعه‌ی صحیحِ یک سلسله‌مراتب کمک کند. این ویژگیِ اسنتاج‌گرها به‌خصوص در زمانی که کلاس‌ها می‌توانند بیشتر از والد داشته باشند، مفید است.

۳.۱. مولفه‌های آنتولوژی‌های OWL

آنتولوژی‌های OWL مولفه‌های مشابه‌ای نسبت به آنتولوژی‌های مبتنی بر فریمِ پروتژه دارند. با این حال کلمات مورد استفاده برای توصیف این مولفه‌ها کمی با آنچه در زبان‌های فریمی استفاده می‌شود، تفاوت دارد. یک آنتولوژی OWL از نمونه‌ها، صفت‌ها و کلاس‌ها تشکیل شده است که به ترتیب معادل Instance، Slot و Class در آنتولوژی‌های مبتنی بر فریم هستند.

۳.۱.۱ نمونه‌ها

نمونه‌ها، نمایش‌گر اشیاء در حوزه‌ی مورد نظر ما هستند. یک تفاوت مهم بین پروتژه و OWL عدم استفاده از فرضِ نامِ یکتا (Unique Name Assumption یا UNA) در OWL است. این تفاوت به معنای این است که دو نام متفاوت می‌توانند در واقع به یک نمونه اشاره کنند. برای مثال «ملکه الیزابت»، «ملکه» و «الیزابت ویندزور» ممکن است همگی به یک نمونه‌ی یکسان اشاره کنند. در OWL باید به صورت مشخص به اینکه نمونه‌هایی یکسان با هم هستند، یا متفاوت از یکدگر هستند اشاره شود — وگرنه آن‌ها ممکن است با یکدیگر یکسان باشند یا ممکن است با یکدیگر متفاوت باشند. شکل ۳.۱ بیان‌گر یک نمایش از چند نمونه در یک حوزه است — در این راهنما، نمونه‌ها در شکل‌ها به صورت لوزی نشان داده می‌شوند.

۳.۱.۲ صفت‌ها