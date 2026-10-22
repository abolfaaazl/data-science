# ماتریس اولویت‌بندی مقالات کاندید — مرحله اولیه انتخاب برای MarkIt

**تاریخ شروع:** ۲۱ اکتبر ۲۰۲۶  
**هدف اولیه:** محدودکردن مجموعه حدود ۳۹ مقاله متمایز به گروهی قابل‌مدیریت برای تبدیل به Markdown و مطالعه عمیق. این فایل **فهرست نهایی ۷ تا ۱۰ مقاله سمینار نیست** و موضوع پایان‌نامه را قطعی نمی‌کند.

## راهنمای استفاده و اولویت فعلی

این ماتریس سابقه تصمیم‌گیری است: نشان می‌دهد هر مقاله چرا برای مطالعه زودتر انتخاب شده و هنگام مطالعه چه نکاتی باید بررسی شوند. این اولویت‌ها برای مدیریت زمان بوده‌اند، نه حکم قطعی درباره برتری علمی مقاله‌ها.

طبق برنامه فعلی، در دو ماه آینده اولویت اصلی فهم حوزه و نگارش سمینار است؛ جست‌وجوی علمی تکمیلی در پایگاه‌های معتبر و صفحات ناشران نیز می‌تواند تکرار شود تا خلأهای پوشش موضوع پیدا شوند. ۱۲ مقاله این ماتریس فقط نامزدهای فعلی‌اند و ممکن است با شواهد تازه تغییر کنند. انتخاب مقاله مبنای پروپوزال در ماه بعد از سمینار و با معیارهای جداگانه انجام می‌شود.

## معیار اولویت‌بندی

مقاله‌ها بر اساس احتمال تأثیرگذاری بر این تصمیم‌ها اولویت گرفته‌اند:
1. چطور حوزه Concept Drift را در سمینار توضیح بدهیم و سازمان‌دهی کنیم.
2. کدام خانواده‌های روش تشخیص باید با هم مقایسه شوند.
3. چه پروتکل داده، Ground Truth و ارزیابی برای یک مقایسه علمی قابل‌دفاع است.
4. کدام مقاله ممکن است در آینده قابلیت بازتولید و توسعه برای پایان‌نامه داشته باشد.

ارزش مقاله برای سمینار را از ارزش آن برای مقاله مبنای پایان‌نامه جدا ارزیابی کن. برای سمینار داشتن کد عمومی ضروری نیست؛ برای پایان‌نامه وجود کد فقط یکی از عوامل امکان‌پذیری است. وجود README در GitHub اثبات نمی‌کند که کد اجرا می‌شود یا نتایج مقاله قابل‌بازتولیدند.

## Priority A — Convert to Markdown and deep-read first

| Priority | Paper | Seminar value | Thesis-base value | Why it earns early attention | Main check during deep read |
|---:|---|---|---|---|---|
| A1 | A systematic review on detection and adaptation of concept drift in streaming data using machine learning techniques (2024) | Very high | Low | Broad taxonomy and a current overview of detection/adaptation, metrics, limitations, and future directions | Review protocol, overlap with other surveys, whether it identifies concrete gaps rather than generic future work |
| A2 | A benchmark and survey of fully unsupervised concept drift detectors (online 2024 / issue 2025) | Very high | Medium-low for full benchmark | Closely aligned with unsupervised detection; connects method taxonomy, real-world benchmark, and evaluation pitfalls | Detector taxonomy, benchmark fairness, dataset provenance, metric definitions, limitations |
| A3 | A Framework for Evaluating and Benchmarking Concept Drift Detection Methods (KDD 2026) | Very high | Medium | Recent evaluation-focused work; controlled drift and explicit evaluation protocol can anchor our experimental design | Exact drift generation/onset labels, metric protocol, baselines, statistical comparisons |
| A4 | Early Concept Drift Detection via Prediction Uncertainty (PUDD; AAAI 2025) | High | High relative to current pool | Clear detection signal and public code with synthetic/tabular entry points | Method assumptions, thresholding, detection delay/false alarms, exact reproduction commands, dependency compatibility |
| A5 | WinDrift++ (IEEE Transactions on Artificial Intelligence, 2026 issue) | High | High relative to current pool | Recent direct detector with public implementation and claimed tests; a serious comparison candidate to PUDD | Component ablations, baseline fairness, synthetic drift generator, real dataset access, whether README tests actually pass |
| A6 | Unsupervised Concept Drift Detection with a Discriminative Classifier (D3; CIKM 2019) | High | Medium-high | A comparatively classical unsupervised baseline; paper itself identifies linear-pattern limitations that can motivate careful comparison | Logistic-regression assumption, dataset setup, code/data compatibility, whether known drift locations are available |
| A7 | STUDD: A student–teacher method for unsupervised concept drift detection (Machine Learning, 2023) | High | Medium | Contrasting unsupervised signal: student–teacher mimic loss; reports 19 data streams | The original repository URL appears stale, but the later Perf_DD repository includes an adapted STUDD implementation; establish exactly what can be reproduced |
| A8 | Concept Drift Adaptation by Exploiting Drift Type (Type-LDA; ACM TKDD 2024) | Medium-high | Medium | Helps explain the boundary between detecting a drift and using drift type to adapt a model | Distinguish detection from adaptation; verify current Type-LDA/Type-LDD code correspondence and synthetic drift-type labels |
| A9 | On Learning Guarantees to Unsupervised Concept Drift Detection on Data Streams (2018) | High for theory | Low-medium | Adds theoretical foundations and assumptions, preventing the seminar from being only a catalogue of algorithms | Formal assumptions, guarantee scope, whether they are relevant to the methods and evaluation used in the project |
| A10 | Towards Computational Performance Engineering for Unsupervised Concept Drift Detection (DATA 2024) | High for evaluation | Medium-low as first base | Complements accuracy-oriented papers with runtime/space complexity and performance measurement; public experiment repository found | Which comparisons are fair, runtime environment, complexity assumptions, hardware-specific limitations |
| A11 | A method to benchmark high-dimensional process drift detection (Journal of Intelligent Manufacturing, 2025) | Medium-high | Medium for a process-data thesis only | Provides controlled synthetic process curves and a tailored temporal-AUC score; useful for discussing ground truth and domain-specific benchmarks | Ensure its process-curve problem is not incorrectly generalized to all time-series concept drift; understand score and synthetic generator |
| A12 | Machine learning based concept drift detection for predictive maintenance (Computers & Industrial Engineering, 2019) | Medium-high | Medium-low | Distinct real industrial case: radial-fan run-to-failure, alongside synthetic tests; adds application evidence beyond benchmark streams | Dataset availability, code/proprietary dependencies, how the real-world drift event is defined, limits of one case study |

## Priority B — Keep as targeted alternatives, not automatic MarkIt conversions

| Paper | Reason to keep in reserve | Promote if… |
|---|---|---|
| Learning under Concept Drift: A Review | Broad foundational survey | A1 is too application-heavy or lacks a useful taxonomy for the seminar |
| An overview of unsupervised drift detection methods | Could complement the unsupervised benchmark | It adds a distinct method taxonomy rather than duplicating A1/A2 |
| Concept Drift Detection on Unlabeled Data Streams: A Systematic Literature Review | Closely aligned with no-label detection | It has a stronger review protocol or more distinct methods than the other reviews |
| A Systematic Literature Review of Concept Drift Mitigation in Time-Series Applications | Regression/time-series emphasis | The thesis direction shifts toward time-series regression rather than general data streams |
| Concept drift detection and adaptation framework using optimized deep learning and adaptive sliding window | Complex CNN + optimization + window method; code/data not verified | Code, data, baselines, and paper-repository correspondence become credible |
| Machine learning-based detection of concept drift in business processes (CV4CDD-4D, 2025) | Recent method identifies sudden, gradual, incremental, recurring drifts, but event-log/computer-vision domain is specialized | The user chooses process mining/event logs as an application or the repository/data setup proves unusually accessible |
| LAMDA (ICLR 2026) and BenchMFC (Computers & Security 2024) | Valuable longitudinal malware benchmarks but specialized domain and extra data/security burden | A malware application is explicitly selected; do not keep both merely to fill a benchmark slot |
| Drift-Lens | Covers deep representations and unstructured streams | Representation-based detection becomes a required seminar comparison; avoid as default implementation due to compute/embedding burden |
| Implementing machine learning model drift detection in fog | Could cover distributed/resource-constrained deployment | It clearly studies concept drift rather than generic model drift and offers a distinct contribution |

## Priority C — Do not spend MarkIt conversion time yet

Papers currently in the lower-priority group or those whose central contribution is adjacent to concept-drift detection should remain searchable in the repository. Reopen them only if the higher-priority set fails to cover a necessary role or new evidence changes the ranking. This is a time-allocation decision, not a declaration that those papers are poor.

## معنی این ماتریس و وضعیت فعلی

- **۱۲ مقاله برای تبدیل MarkIt و مطالعه عمیق‌تر اولویت گرفته‌اند**؛ این به‌معنای انتخاب نهایی سمینار نیست.
- پس از مطالعه این گروه، می‌توان بعضی مقاله‌های اولویت B را جایگزین کرد. فهرست نهایی باید مقاله‌های مکمل را پوشش دهد، نه اینکه صرفاً هفت ردیف اول انتخاب شوند.
- انتخاب مقاله مبنای پایان‌نامه تصمیم جداگانه‌ای است. PUDD و WinDrift++ دو نامزد فعلی‌اند، اما نامزدهای دیگری که در جست‌وجوی تازه پیدا شوند نیز می‌توانند وارد مقایسه شوند. D3 و STUDD ممکن است برای مقایسه روش‌ها مفید باشند و مقاله‌های بنچمارک به طراحی ارزیابی کمک کنند.
- مطالعه عمیق اولیه ۱۲ مقاله در [MARKDOWN_DEEP_READ_STAGE1.md](MARKDOWN_DEEP_READ_STAGE1.md) ثبت شده است. هنوز هیچ نتیجه‌ای به‌صورت مستقل بازتولید نشده است.

## به‌روزرسانی اولویت پژوهش — ۲۲ اکتبر ۲۰۲۶

**تمرکز اصلی دو ماه آینده، پوشش علمی و نگارش سمینار است.** هدف، رسیدن به نقشه‌ای منسجم از مفهوم Concept Drift، انواع تغییر، خانواده روش‌های تشخیص، رابطه Detection و Adaptation، دیتاست‌ها، Ground Truth، معیارهای ارزیابی، محدودیت‌ها و جهت‌های پژوهشی است. مرورهای جدید و مقاله‌های مهم ۲۰۲۴ تا زمان جست‌وجو نیز باید به‌صورت هدفمند در منابع معتبر و سایت‌های ناشران بررسی شوند؛ به‌ویژه اگر بتوانند دسته‌ای از روش‌ها یا خلأیی را روشن کنند که در مجموعه فعلی پوشش کافی ندارد.

هنگام هر جست‌وجوی تازه، پرسش جست‌وجو، پایگاه/ناشر، تاریخ، منابع مهم پیدا‌شده و دلیل اثرگذاری آن‌ها را در [CONCEPT_DRIFT_RESEARCH_LOG.md](CONCEPT_DRIFT_RESEARCH_LOG.md) ثبت کن. اگر منبع جدیدی پوشش علمی را بهتر می‌کند، ماتریس قابل‌تغییر است. از بازبینی کامل مجموعه قبلی بدون دلیل مشخص خودداری کن، اما خود را به همان مجموعه هم محدود نکن.

در ماه بعد از تکمیل سمینار، نامزدهای مقاله مبنا بر اساس قابلیت اجرا و بازتولید، دسترسی به داده، Ground Truth، کیفیت خط‌پایه‌ها، هزینه پیاده‌سازی و ظرفیت توسعه دوباره ارزیابی می‌شوند. هر اشاره به PUDD یا WinDrift++ در این فایل یک **فرضیه کاری موقت** است، نه انتخاب قطعی یا ادعای نوآوری.
