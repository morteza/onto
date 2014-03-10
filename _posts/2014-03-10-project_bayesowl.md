---
layout: post
title:  "BayesOWL: عدم‌قطعیت و آنتولوژی"
date:   2014-03-10 14:53:38
date_fa: "۱۰ مارچ ۲۰۱۴"
date_shamsi: "۱۹ اسفند ۱۳۹۲"
categories: review blog
permalink: /blog/review/project_bayesowl
---
بعد از دست‌آوردهای عصب‌شناسان در اینکه ساختار نئوکورتکس مغز انسان، به عنوان یک شبکه‌ی فیدفوروارد، در روشِ کار شباهت زیادی به شبکه‌های بِیزیَن دارد، در هوش‌مصنوعی به خصوص در یادگیری ماشین بحث‌ها و مطالعات زیادی به سمت این شبکه‌ها حرکت نمود. امروزه مطالعات با پسوند آماری مانند تشخیص الگوی آماری، پردازش زبان طبیعیِ آماری و یادگیریِ آماری اغلب اشاره به استفاده از این الگوریتم‌ها دارند. حتی می‌توان گفت محدود به استفاده از شبکه‌های بِیز می‌شوند. از ابزاری که از هر دوی این مسیرها (محتوا-محور و مکانیزم-محور) عبور می‌کند، کتابخانه‌ی BayesOWL برای زبان جاوا است. هدف از این پروژه، ارائه‌ی راه‌حلی برای تزریق عدم‌اطمینان در آنتولوژی‌ها است.

این ابزار در حقیقت با استفاده از تکنیک‌های مورد استفاده در شبکه‌های بِیزیَن، برای مسائل اصلی در حیطه‌ی آنتولوژی مانند مدل‌سازی حوزه‌ی خاص، استنتاج مبتنی بر آنتولوژی یا نگاشت آنتولوژی‌ها راه‌حل ارائه می‌دهد. این کتابخانه در [سایت پروژه](http://www.csee.umbc.edu/~ypeng/BayesOWL/index.html)‌ قابل دسترس است.

ابزار اشاره‌شده از بخش‌های زیر تشکیل شده است:

- پارسرِ رده‌بندی (T-Parser) که وظیفه‌ی تجزیه و تحلیل فایل‌های آنتولوژی مانند OWL یا RDF را دارد. خروجی این ماژول رده‌بندی‌های موجود در آنتولوژی ورودی هستند.

- پارسر احتمال (P-Parser) برای استخراج دانشِ نامطمئن و غیرقطعی به صورت احتمال در فرمتی خاص استفاده می‌شود.

- سازنده‌ی ساختار (Structure-Constructure) بخشی است که رده‌بنده‌ها را به شبکه‌های بِیزیَن تبدیل می‌سازد. جزییات قواعد مورد استفاده برای نگاشت این دو ساختار متفاوت در منابع اشاره شده در پایین آمده است.

- سازنده‌ی CPT که وظیفه‌ی تزریق دانش و یکپارچه‌سازی آن با شبکه‌های بِیزیَن را دارد. این دانش توسط پارسر احتمال استخراج شده است.

شکل زیر نمای کلی ماژول‌های این ابزار را نشان می‌دهد.

![معماری ابزار BayesOWL](/images/bayesowl_arch.jpg)

برخی از منابع آکادمیک قابل دسترس، هرچند قدیمی ولی قابل تاملِ این پروژه شامل موارد زیر می‌شود:


- [Ding, Z., Peng, Y. et al. **"A Bayesian Approach to Uncertainty Modeling in OWL Ontology"**, Proceedings of the International Conference on Advances in Intelligent Systems Theory and Applications, November 2004, Luxembourg.](http://www.csee.umbc.edu/~ypeng/BayesOWL/papers/ICAISTA04.pdf)

- [Peng, Y. and Ding, Z.: **"Modifying Bayesian Networks by Probability Constraints"**, in Proceedings of 21st Conference on Uncertainty in Artificial Intelligence (UAI-2005), Edinburgh, Scotland, July 26-29, 2005.](http://www.csee.umbc.edu/~ypeng/BayesOWL/papers/UAI05.pdf)

- [Ding, Z., **BayesOWL: Uncertainty Modeling in Semantic Web Ontologies**, PhD thesis, 2005.](http://www.csee.umbc.edu/~ypeng/BayesOWL/papers/Ding_Thesis.pdf)
