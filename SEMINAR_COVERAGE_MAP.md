# نقشه پوشش علمی سمینار Concept Drift و برنامه جست‌وجوی ادبیات

**تاریخ تهیه:** ۲۲ اکتبر ۲۰۲۶  
**عنوان مصوب سمینار:** استفاده از الگوریتم‌های یادگیری ماشین در تشخیص تغییر الگو در داده‌های پویا  
**هدف این سند:** مشخص‌کردن بخش‌هایی که برای پوشش علمی سمینار باید فهمیده شوند، وضعیت منابع فعلی، خلأهای اولیه و عبارت‌های دقیق برای جست‌وجوی مقالات.  
**وضعیت:** نقشه کاری اولیه؛ پس از جست‌وجوهای بعدی قابل به‌روزرسانی است. این سند ادعا نمی‌کند که کل ادبیات جهان را پوشش داده است.

## 1. اصل راهنما و محدوده سمینار

تمرکز دو ماه آینده روی فهم علمی حوزه و نگارش سمینار است؛ انتخاب قطعی مقاله مبنا و تدوین پروپوزال برای ماه پس از آن در نظر گرفته شده است. بنابراین نامزدهای فعلی، از جمله PUDD و WinDrift++، فقط گزینه‌های موقت‌اند. جست‌وجوهای جدید می‌توانند منابع یا روش‌های مهم‌تری پیدا کنند و فهرست را تغییر دهند.

عنوان سمینار حول **تشخیص Concept Drift با روش‌های Machine Learning در داده‌های پویا و جریانی** است. از نظر علمی، همه تشخیص‌دهنده‌های تغییر الزاماً الگوریتم یادگیری ماشین نیستند؛ روش‌های آماری مانند آزمون‌های تغییر نیز بخش مهمی از زمینه و خط‌پایه‌ها هستند. سمینار باید آن‌ها را برای مقایسه و توضیح خانواده روش‌ها پوشش دهد، سپس روشن کند یادگیری ماشین در کدام روش‌ها نقش اصلی یا کمکی دارد.

این سمینار نیاز ندارد هر کاربرد تخصصی (مالی، امنیت، صنعت، تصویر، IoT و غیره) را با عمق یکسان بررسی کند. هدف، پوشش خانواده‌های اصلی روش‌ها و مسائل ارزیابی است؛ کاربردها نمونه‌هایی برای نشان‌دادن تفاوت شرایط مسئله خواهند بود. Detection موضوع اصلی است؛ Adaptation برای توضیح ارتباط مفهومی و مرز مسئله پوشش داده می‌شود، اما نباید بی‌دلیل به موضوع غالب تبدیل شود.

## 2. نقشه پوشش موضوع و وضعیت فعلی منابع

| بخش علمی | پرسش‌هایی که باید بتوانی پاسخ بدهی | منابع فعلی و نقش آن‌ها | وضعیت اولیه / کار لازم |
|---|---|---|---|
| 1. تعریف و صورت‌بندی مسئله | Concept Drift چیست؟ چه چیزی در طول زمان تغییر می‌کند؟ تفاوت آن با Data Drift، Model Drift، Out-of-Distribution و Anomaly Detection چیست؟ | مرور نظام‌مند ۲۰۲۴ در مجموعه ۱۲تایی؛ مقاله «One or two things we know about concept drift… Part A: detecting concept drift» در مخزن موجود است؛ مرور تصویر ۲۰۲۵ تفاوت‌های اصطلاحی را هم مطرح می‌کند. | **پوشش پایه موجود است، اما باید تعریف‌ها و واژگان را یکدست کنیم.** در گزارش سمینار تعریف کاری خودمان را صریح بنویس و اشاره کن که اصطلاحات در برخی مقاله‌ها یکسان استفاده نمی‌شوند. |
| 2. انواع و شکل تغییر | تغییر ناگهانی (abrupt)، تدریجی (gradual)، افزایشی/آهسته (incremental)، تکرارشونده (recurring) چیست؟ شدت، سرعت و هم‌زمانی تغییر چه اثری دارند؟ Real/virtual drift یا تغییر گروهی (group drift) چه معنایی دارند؟ | مرور نظام‌مند ۲۰۲۴، Type-LDA و بنچمارک‌های کنترل‌شده؛ مرور ۲۰۲۶ «A survey of processing methods for different types of concept drift» برای انواع پیچیده و group drift یافته شده است. | **پوشش پایه موجود، اما طبقه‌بندی تکمیلی لازم است.** مرور جدید را ارزیابی کن تا ببینیم آیا واقعاً بخش مهمی به دسته‌بندی موجود اضافه می‌کند. |
| 3. تنظیمات یادگیری و دسترسی به برچسب | روش نظارت‌شده، بدون‌ناظر و نیمه‌نظارتی چه تفاوتی دارند؟ اگر برچسب دیر برسد یا هرگز برای برخی نمونه‌ها موجود نباشد، چه می‌شود؟ | بنچمارک/مرور روش‌های کاملاً بدون‌ناظر؛ D3؛ STUDD؛ مقاله جدید «Concept drift detection in delayed and partially labeled data streams: An experimental survey» (اکتبر ۲۰۲۶) یافت شده است. | **خلأ اولویت‌دار:** روش‌های delayed/partially labeled در ۱۲ مقاله مطالعه عمیق‌شده نماینده مستقیمی ندارند. مقاله جدید را از نظر روش، پروتکل آزمایش و کد/داده بررسی کن. |
| 4. خانواده‌های الگوریتم تشخیص | روش‌ها بر اساس سیگنال تشخیص چگونه دسته‌بندی می‌شوند و هر کدام چه فرض و محدودیتی دارند؟ | PUDD، WinDrift++، D3، STUDD، Plover؛ مرور بدون‌ناظر ۲۰۲۴؛ مرور عملکردمحور «From concept drift to model degradation». | **پوشش متنوعی وجود دارد، ولی باید taxonomy واحد ساخته شود.** هر روش را بر مبنای سیگنال آن دسته‌بندی کن، نه صرفاً ترتیب زمانی انتشار. دسته‌ها کاملاً مانعةالجمع نیستند. |
| 4-الف. عملکرد و خطای مدل | افت accuracy، error rate، loss یا residual چگونه به سیگنال تغییر تبدیل می‌شود؟ روش در چه شرایطی به برچسب نیاز دارد؟ | DDM/EDDM و روش‌های پایش عملکرد در مرورها؛ PUDD برای مقایسه عدم‌قطعیت با خطا. | توضیح بده که افت عملکرد یک پیامد قابل مشاهده است، اما ممکن است با تأخیر رخ دهد و برای همه تنظیمات مناسب نباشد. |
| 4-ب. توزیع و آزمون آماری | چگونه پنجره قدیم و جدید مقایسه می‌شوند؟ از آزمون‌های دو نمونه، distance، histogram یا توزیع ویژگی چه استفاده‌ای می‌شود؟ | WinDrift++، unsupervised benchmark، KDD 2026 evaluation framework. | **پوشش خوب در مجموعه فعلی.** یک مقایسه ساده از فرض‌ها، حساسیت، سرعت و محدودیت‌ها بساز. |
| 4-ج. تشخیص مبتنی بر طبقه‌بند یا قابلیت تفکیک | آیا می‌توان مدل را برای تفکیک نمونه‌های پنجره قدیم و جدید آموزش داد؟ | D3؛ مطالعه مقاله اصلی برای فهم محدودیت مدل خطی. | یک نمونه قابل‌فهم برای نشان‌دادن نقش ML در خود تشخیص است. |
| 4-د. عدم‌قطعیت پیش‌بینی | آیا توزیع اعتماد/عدم‌قطعیت پیش‌بینی قبل از افت آشکار عملکرد تغییر می‌کند؟ | PUDD، مبنای آن PU-index و آزمون آماری. | پوشش فعلی خوب؛ برای سمینار مفهوم و فرض اصلی مهم‌تر از ورود به جزئیات کد است. |
| 4-هـ. مدل‌های عمیق و نمایش ویژگی | در داده‌های تصویری یا با ابعاد بالا، تغییر در embedding/representation چگونه شناسایی می‌شود؟ هزینه محاسباتی و وابستگی به مدل چه هستند؟ | Drift-Lens در مجموعه اولیه؛ مرور تخصصی تصویر در IEEE/Springer-style literature با عنوان «Concept drift detection in image data stream…» در مخزن PDF موجود است. | **این حوزه تخصصی است.** به اندازه‌ای پوشش بده که خانواده روش‌ها و هزینه‌ها روشن شود؛ وارد جزییات بینایی ماشین نشو مگر اینکه منابع عمومی نشان دهند برای عنوان سمینار لازم است. |
| 4-و. آنتروپی، ویژگی‌های شرطی و تبیین‌پذیری | آیا آنتروپی یا رابطه شرطی می‌تواند تغییر ظریف را نشان دهد؟ آیا علاوه بر زمان تغییر می‌توان علت/ویژگی‌های تغییر را توضیح داد؟ | منبع جدید ۲۰۲۶ درباره تشخیص تبیین‌پذیر با Partial Dependence Profiles (PDPs) و مرورهای مرتبط یافت شده‌اند. | **خلأ تازه و بالقوه مهم:** دست‌کم مقاله PDD مبتنی بر PDP را غربال کن. لازم نیست فعلاً شاخه‌ای مستقل در سمینار شود؛ ابتدا ارزش آن برای نقشه کلی را بسنج. |
| 5. Detection در برابر Adaptation | تشخیص می‌گوید «چه زمانی احتمالاً تغییر رخ داده؟»؛ Adaptation می‌پرسد «بعد از تغییر چه کنیم تا مدل سازگار شود؟» | Type-LDA، مرور نظام‌مند ۲۰۲۴ و مقاله «Anticipating to Change…» (۲۰۲۵)؛ Interformer (۲۰۲۶) نمونه‌ای از کار متمرکز بر adaptation در پیش‌بینی سری زمانی است. | **برای جلوگیری از انحراف عنوان، مختصر و روشن پوشش بده.** روش‌های adaptation را فقط برای توضیح زنجیره detection → response و تفکیک ادبیات بررسی کن. |
| 6. داده‌ها و Ground Truth | کدام داده‌ها تغییر زمان‌دار معلوم دارند؟ چه تفاوتی بین داده مصنوعی، drift تزریق‌شده به داده واقعی و داده طبیعی واقعی وجود دارد؟ | KDD 2026 framework، unsupervised benchmark، process-drift benchmark و داده‌های PUDD/WinDrift++. | **یکی از حیاتی‌ترین بخش‌ها.** برچسب کلاس با زمان دقیق شروع drift یکی نیست. در جریان طبیعی واقعی ممکن است onset تأییدشده در دسترس نباشد؛ تزریق کنترل‌شده این مشکل را برای همان تغییر تزریق‌شده حل می‌کند، نه برای همه تغییرهای تاریخی داده. |
| 7. معیارهای ارزیابی و مقایسه منصفانه | تأخیر تشخیص، هشدار کاذب، drift ازدست‌رفته، precision/recall/F1 و هزینه اجرا چگونه محاسبه می‌شوند؟ روش‌ها تحت چه پروتکلی مقایسه می‌شوند؟ | KDD 2026 framework، unsupervised benchmark، process benchmark و performance engineering. | **پوشش موجود قوی است، ولی باید به زبان خودت جمع‌بندی شود.** accuracy طبقه‌بند را با کیفیت detector یکی نگیر. معیارها به تعریف رویداد، بازه تطبیق، تنظیم پارامتر و زمان اجرا وابسته‌اند. |
| 8. کارایی، محدودیت و اعتبار نتایج | روش آنلاین است؟ حافظه و زمان اجرا چه‌قدر مهم‌اند؟ آزمایش‌ها منصفانه‌اند؟ حساسیت به پارامتر، نویز، تغییر تدریجی و عدم توازن چه اثری دارد؟ | Performance Engineering 2024، benchmark بدون‌ناظر، KDD 2026 و گزارش‌های روش‌های PUDD/WinDrift++. | برای ارزیابی علمی لازم است؛ مقایسه اعداد مقاله‌های مختلف بدون یکسان‌بودن داده، drift، معیار و پروتکل درست نیست. |
| 9. کاربردها و روندهای جدید | روش‌ها در صنعت، نگهداری پیش‌بینانه، تصویر، امنیت، IoT یا چند جریان داده چه تفاوت‌هایی دارند؟ روندهای جدید چه مسئله‌ای را هدف می‌گیرند؟ | Predictive maintenance و process benchmark؛ مقالات تخصصی موجود در مخزن؛ منابع تازه درباره labels، group drift و explainability. | چند نمونه مکمل کافی است. کاربردهای تخصصی را به‌عنوان شواهد تنوع مسئله استفاده کن، نه اینکه سمینار را به مرور همه حوزه‌های کاربردی تبدیل کنی. |

## 3. جمع‌بندی پوشش فعلی و خلأهای واقعی

### پوشش فعلی در نقطه شروع مناسب است
مجموعه ۱۲ مقاله فعلی برای شروع، چند نقش متفاوت را پوشش می‌دهد: مرور عمومی، بنچمارک و ارزیابی، روش‌های مبتنی بر uncertainty و statistical tests، classifier-based detection، student–teacher، مبانی نظری، کارایی محاسباتی و دو زمینه کاربردی. بنابراین نیاز نیست جست‌وجو را از صفر شروع کنیم.

### اما هنوز نمی‌توان گفت پوشش سمینار کامل است
پس از مطالعه اولیه، این محورهای تکمیلی بیشترین اولویت را دارند:

1. **مرور به‌روز تا ۲۰۲۶:** مرور ۲۰۲۴ موجود بازه‌ای را تا سال ۲۰۲۲ بررسی کرده است؛ باید مقاله‌های جدیدتر و روش‌های اخیر را کنترل کنیم.
2. **Delayed / partially labeled streams:** یک مرور تجربی منتشرشده در اکتبر ۲۰۲۶ مستقیماً این مسئله را بررسی می‌کند؛ آن را غربال کن.
3. **طبقه‌بندی انواع و group/multistream drift:** مرور ژانویه ۲۰۲۶ می‌تواند بخش انواع drift را تکمیل کند؛ ارزش افزوده‌اش نسبت به مرورهای قبلی باید سنجیده شود.
4. **Explainable concept drift detection:** مقاله «From XAI to MLOps: Explainable concept drift detection with the partial dependence profiles-based approach» در سال ۲۰۲۶ یک روش مبتنی بر PDP معرفی می‌کند؛ برای پوشش روش‌های جدید و تبیین علت تغییر ارزش بررسی دارد.
5. **مرزبندی Detection / Adaptation / Data Drift:** تعریف و اصطلاحات در مقالات همیشه یکسان نیستند؛ سمینار باید واژگان کاری مشخص و مرزهای روشن داشته باشد.

«خلأ» در این سند یعنی بخشی که در ۱۲ مقاله مطالعه عمیق‌شده نماینده کافی ندارد؛ نه اینکه حتماً از مجموعه ۳۹ مقاله اولیه یا کل مخزن غایب باشد. پیش از اضافه‌کردن فایل تازه، فهرست موجود را برای عنوان و نسخه تکراری بررسی کن.

## 4. مقالات جدیدی که در جست‌وجوی مقدماتی وب پیدا شدند

این فهرست یک غربال اولیه تا تاریخ ۲۲ اکتبر ۲۰۲۶ است؛ **همه این منابع هنوز به‌صورت کامل مطالعه و ارزیابی نشده‌اند.**

| اولویت بررسی | عنوان اصلی و انتشار | چرا باید بررسی شود؟ | اقدام |
|---|---|---|---|
| بالا | [Concept drift detection in delayed and partially labeled data streams: An experimental survey](https://doi.org/10.1016/j.dsp.2026.106325) — Digital Signal Processing, 15 October 2026 | مرور تجربی جدید درباره تأخیر و کمبود برچسب، taxonomy روش‌ها، ارزیابی و داده/کد | چکیده، روش جست‌وجو، تقسیم‌بندی روش‌ها و پروتکل آزمایش را بخوان؛ اگر نقش مکمل دارد به مخزن اضافه کن. |
| بالا | [A survey of processing methods for different types of concept drift](https://doi.org/10.1016/j.datak.2025.102525) — Data & Knowledge Engineering, January 2026 | طبقه‌بندی روش‌ها بر اساس drift منفرد، انواع ترکیبی و group drift؛ تمایز real و virtual drift | با مرور ۲۰۲۴ و taxonomy فعلی مقایسه کن؛ فقط ارزش افزوده مستقل را نگه دار. |
| بالا | [From XAI to MLOps: Explainable concept drift detection with the partial dependence profiles-based approach](https://doi.org/10.1016/j.future.2026.108586) — Future Generation Computer Systems, October 2026 | روش Profile Drift Detection (PDD) با Partial Dependence Profiles؛ علاوه بر تشخیص، به تبیین تغییر می‌پردازد | بررسی کن آیا روش جدید و قابل توضیحی برای پوشش ML-based detection اضافه می‌کند؛ ادعای عملکرد مقاله را بدون بازبینی تجربی قطعی تلقی نکن. |
| متوسط، بر اساس دامنه سمینار | [Concept drift detection in image data stream: a survey on current literature, limitations and future directions](https://doi.org/10.1007/s10462-025-11428-y) — Published 11 December 2025 | مرور تخصصی تشخیص در جریان تصویر با taxonomy بر مبنای ویژگی‌های تصویر، راهبرد تشخیص و ارزیابی | فایل مربوطه از قبل در مجموعه PDFهای مخزن دیده شده؛ قبل از دانلود دوباره، آن را با فهرست موجود تطبیق بده و فقط در صورت نیاز مطالعه عمیق کن. |
| متوسط و بیشتر برای مرزبندی | [Anticipating to Change: A Proactive Approach for Concept Drift Adaptation in Data Streams](https://doi.org/10.1007/s10994-025-06945-4) — Published 14 December 2025 | نمونه‌ای از سازگاری پیش‌دستانه به‌جای واکنش صرفاً پس از تغییر | برای توضیح Detection در برابر Adaptation بررسی شود؛ مقاله اصلی سمینار درباره تشخیص را جایگزین نمی‌کند. |
| مرجع مهم موجود در مجموعه ۱۲تایی | [A Framework for Evaluating and Benchmarking Concept Drift Detection Methods](https://doi.org/10.1145/3770855.3819070) — KDD 2026 | ۱۴ روش را روی ۷ مجموعه‌داده واقعی با driftهای کنترل‌شده و چهار سازوکار تغییر مقایسه می‌کند | دوباره جست‌وجو نکن؛ در مطالعه عمیق آن، تعریف onset، معیارهای timing-aware و پروتکل تنظیم hyperparameter را استخراج کن. |
| مرجع مهم موجود در مخزن، خارج از ۱۲ مقاله تبدیل‌شده | [One or two things we know about concept drift—a survey on monitoring in evolving environments. Part A: detecting concept drift](https://doi.org/10.3389/frai.2024.1330257) — Frontiers in Artificial Intelligence, 2024 | طبقه‌بندی روش‌های بدون‌ناظر را بر اساس دو نمونه، meta-statistics و راهبردهای block-based بررسی می‌کند | PDF آن در مخزن فعلی موجود است؛ برای ساختن taxonomy مستقل و مقایسه با مرورهای دیگر استفاده کن. |

منابع فوق از صفحات ناشر یا صفحه رسمی انتشار بررسی اولیه شده‌اند. مرحله بعد باید نسخه کامل، روش مرور، جداول مقایسه و ارجاعات هر منبع را بررسی کند؛ صرف عنوان و چکیده برای پذیرش نهایی کافی نیست.

## 5. عبارت‌های پیشنهادی برای جست‌وجو

عبارت‌ها را دقیقاً به انگلیسی جست‌وجو کن. اول از جست‌وجوی عمومی شروع کن، سپس بر اساس دسته‌بندی‌های زیر جست‌وجو را تخصصی کن.

### A. تعریف مسئله و مرورهای کلی
- "concept drift detection" AND "machine learning"
- "concept drift detection" AND (survey OR "systematic review" OR taxonomy)
- "concept drift" AND "data streams" AND "state of the art"
- "non-stationary data streams" AND "drift detection"
- "concept drift" AND "data drift" AND "model drift" AND taxonomy
- "real concept drift" AND "virtual drift"

### B. روش‌های اصلی یادگیری ماشین برای تشخیص
- "machine learning based concept drift detection methods"
- "online concept drift detection algorithms" AND "data streams"
- "classifier-based concept drift detection"
- "performance-based concept drift detection" AND "streaming data"
- "distribution-based concept drift detection" AND "two-sample test"
- "unsupervised concept drift detection" AND "data streams"
- "semi-supervised concept drift detection" AND "streaming data"
- "ensemble concept drift detection" AND "online learning"
- "concept drift detection" AND ("prediction uncertainty" OR "model confidence")
- "concept drift detection" AND ("information entropy" OR "conditional entropy")
- "concept drift detection" AND ("adaptive window" OR "sliding window")
- "deep learning representations" AND "concept drift detection"
- "explainable concept drift detection" OR "interpretable drift detection"

### C. انواع تغییر و شرایط دشوار
- "concept drift" AND (abrupt OR gradual OR incremental OR recurring)
- "concept drift detection" AND "drift magnitude" AND "drift rate"
- "concept drift detection" AND ("delayed labels" OR "delayed labeling")
- "concept drift detection" AND ("partially labeled" OR "label scarcity")
- "concept drift" AND ("group drift" OR "multistream" OR "multiple data streams")
- "concept drift detection" AND ("class imbalance" OR noise OR "new classes")

### D. ارزیابی، Ground Truth و مقایسه الگوریتم‌ها
- "concept drift detection benchmark" AND evaluation
- "concept drift detection" AND "ground truth" AND "real-world data streams"
- "concept drift detection" AND ("detection delay" OR "false alarm rate")
- "concept drift detector evaluation metrics" AND benchmark
- "controlled drift injection" AND "concept drift detection"
- "synthetic data streams" AND "concept drift" AND evaluation protocol
- "concept drift detection" AND reproducibility AND baselines
- "concept drift detection" AND "hyperparameter optimization" AND benchmark

### E. تشخیص در برابر سازگاری مدل
- "concept drift detection vs adaptation"
- "concept drift adaptation" AND "online learning" AND survey
- "proactive concept drift adaptation" AND "data streams"
- "drift detection and model adaptation" AND evaluation
- "concept drift" AND ("reactive adaptation" OR "proactive adaptation")

### F. روش‌ها و منابع بسیار جدید
برای هر دسته از عبارت‌ها، فیلتر سال را روی **۲۰۲۴–۲۰۲۶** بگذار و نتایج را بر اساس تاریخ جدیدتر هم بررسی کن. برای مرورهای جدید، از عبارت‌های زیر هم استفاده کن:

- "concept drift detection" survey 2026
- "concept drift detection" benchmark 2026
- "machine learning" "concept drift detection" 2025
- "concept drift detection" "partial labels" 2026
- "explainable concept drift detection" 2026
- "concept drift" "group drift" survey 2026

## 6. در کدام پایگاه‌ها جست‌وجو کنی؟

| منبع | استفاده پیشنهادی |
|---|---|
| Google Scholar | جست‌وجوی گسترده اولیه، یافتن نسخه‌های گوناگون یک مقاله و دنبال‌کردن Cited by |
| IEEE Xplore | روش‌های ML، پایش مدل، سامانه‌های آنلاین، کاربردهای صنعتی و IoT |
| ACM Digital Library | مقالات کنفرانسی داده‌کاوی، یادگیری ماشین و ارزیابی الگوریتم‌ها |
| SpringerLink | مرورها، روش‌های concept drift و منابع Machine Learning |
| ScienceDirect | مرورها و روش‌های جدید در مجلات Elsevier، به‌خصوص مقاله‌های ۲۰۲۵ و ۲۰۲۶ |
| Scopus یا Web of Science، در صورت دسترسی | جست‌وجوی قابل ثبت، محدودسازی نوع مدرک و سال، تحلیل استنادی و یافتن منابع جاافتاده |
| arXiv | کشف پیش‌چاپ‌های تازه؛ برای استناد نهایی وضعیت انتشار رسمی را جداگانه بررسی کن |

فقط به کلمات جست‌وجو اکتفا نکن: منابع مرورهای کلیدی را بررسی کن و از هر مقاله مهم، بخش References و Cited by را نیز دنبال کن. گاهی مقاله کلیدی با واژه‌های متفاوتی نام‌گذاری شده و جست‌وجوی یک عبارت آن را پیدا نمی‌کند.

## 7. روش ثبت هر دور جست‌وجو و معیار توقف

هر نوبت جست‌وجو را با این قالب در فایل CONCEPT_DRIFT_RESEARCH_LOG.md ثبت کن:

- **تاریخ جست‌وجو:**
- **پرسش علمی یا خلأ مورد بررسی:**
- **پایگاه‌ها/ناشران و فیلتر سال:**
- **عبارت‌های دقیق استفاده‌شده:**
- **مقاله‌های مهم پیدا‌شده (عنوان، سال، محل انتشار، DOI/پیوند):**
- **ارتباط مستقیم با عنوان سمینار:**
- **محتوای جدیدی که به نقشه پوشش اضافه می‌کنند:**
- **تصمیم:** اضافه به فهرست مطالعه عمیق / نگهداری برای بخش خاص / عدم انتخاب، با دلیل
- **گام بعد:**

### قواعد توقف

1. هدف، «دانستن نام همه مقاله‌های منتشرشده» نیست؛ هدف، پوشش علمی قابل‌دفاع برای سمینار است.
2. مقاله جدید وقتی ارزش مطالعه عمیق دارد که یک خانواده روش، شرایط داده/برچسب، پروتکل ارزیابی یا روند پژوهشی مهم را اضافه کند؛ صرف جدیدبودن کافی نیست.
3. مرورهای مشابه را تنها وقتی هر دو نگه دار که پروتکل مرور، دامنه یا taxonomy متفاوت و مفیدی داشته باشند.
4. برای روش جدید، فقط Future Work مقاله را به‌عنوان نوآوری پایان‌نامه قبول نکن؛ بعداً باید مقالات مرتبط و کارهای جدیدتر جست‌وجو و ادعا را بررسی کنی.
5. جست‌وجو را در پایان هر دور موقتاً ببند، اما در صورت انتشار مقاله مهم یا مشاهده خلأ واقعی، در نوبت جدید باز کن.
6. عنوان، چکیده و صفحه ناشر برای غربالگری اولیه مناسب‌اند؛ برای ادعاهای روش‌شناختی، جدول‌ها، ارزیابی و محدودیت‌ها، متن کامل مقاله لازم است.

## 8. منابع مرجع بررسی‌شده در این نسخه

- [One or two things we know about concept drift — Part A: detecting concept drift (Frontiers, 2024)](https://doi.org/10.3389/frai.2024.1330257)
- [A benchmark and survey of fully unsupervised concept drift detectors on real-world data streams (Springer, online 2024 / issue 2025)](https://doi.org/10.1007/s41060-024-00620-y)
- [A Framework for Evaluating and Benchmarking Concept Drift Detection Methods (KDD 2026)](https://doi.org/10.1145/3770855.3819070)
- [Concept drift detection in image data stream: a survey on current literature, limitations and future directions (published 2025; volume 2026)](https://doi.org/10.1007/s10462-025-11428-y)
- [A survey of processing methods for different types of concept drift (Data & Knowledge Engineering, 2026)](https://doi.org/10.1016/j.datak.2025.102525)
- [Concept drift detection in delayed and partially labeled data streams: An experimental survey (Digital Signal Processing, 15 October 2026)](https://doi.org/10.1016/j.dsp.2026.106325)
- [From XAI to MLOps: Explainable concept drift detection with the partial dependence profiles-based approach (Future Generation Computer Systems, 2026)](https://doi.org/10.1016/j.future.2026.108586)
- [Anticipating to Change: A Proactive Approach for Concept Drift Adaptation in Data Streams (Machine Learning, online 2025 / volume 2026)](https://doi.org/10.1007/s10994-025-06945-4)

این فهرست منابعی برای شروع نقشه پوشش است، نه فهرست نهایی سمینار. منابع جدید باید از نظر روش مرور، کیفیت علمی، ارتباط با عنوان و ارزش افزوده نسبت به منابع قبلی ارزیابی شوند.
