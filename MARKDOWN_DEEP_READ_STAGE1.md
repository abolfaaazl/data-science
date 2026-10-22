# Stage 3 — Deep Reading of the 12 MarkIt Papers (Initial Evidence Report)

**Date:** 2026-10-22  
**Scope:** First deep-reading pass over the 12 Markdown conversions in `markit_concept_drift/`.  
**Status:** Preliminary comparative analysis; **not** the final 7–10 seminar-paper selection and **not** a thesis-base decision. No experiment has been run and no reported result has been independently reproduced.

## Executive findings

1. The 12 expected Markdown files are present. Their shortened filenames are manageable because the titles and bibliographic details can be matched from the document contents.
2. The conversions are generally usable for scientific screening: abstracts or equivalent opening summaries, section structure, method descriptions, experiments and conclusions are recoverable in the files. However, several files contain very large embedded base64 images, and some article layouts have irregular headings/abstract labels. This makes automated reading and file navigation noisier, not necessarily scientifically incomplete.
3. The strongest complementary seminar backbone currently looks like: **the 2024 systematic review**, **the fully unsupervised detector benchmark**, **the KDD 2026 evaluation framework**, and a carefully chosen set of distinct methods such as **PUDD**, **WinDrift++**, **D3/STUDD**, with **Type-LDA** if the seminar needs to explain adaptation rather than detection alone. This is a working direction, not the final list.
4. The clearest initial thesis-base comparison remains **PUDD vs WinDrift++**, but neither should be selected solely from paper claims or repository presence. PUDD has a clear proposed signal and a stated open issue around manually setting the alarm threshold. WinDrift++ has a useful explicit limitation around fixed hierarchical windows and future adaptive windows. Each needs a small reproduction check before deciding.
5. The most important methodological issue across this literature is **ground truth**. Synthetic data give known drift positions but may not represent real streams; real streams often lack verified onset labels. The KDD 2026 framework injects controlled drift into real-world datasets to bridge that gap, while the process-drift benchmark has verified ground truth for its generated process curves. Neither automatically solves ground truth for arbitrary natural streams.
6. No evidence yet justifies selecting one algorithm as “best overall.” The papers use different data, drift definitions, metrics, labeling assumptions, and domains; their headline scores are not directly comparable.

## Conversion quality and reading notes

- Files 1, 2, 5, 11 and 12 include sizeable embedded image payloads. These can dominate file size and interfere with programmatic extraction. Keep the Markdown source; do not manually delete images until the relevant tables/figures have been checked against the original PDF.
- Several converted papers use inconsistent heading styles (for example, “ABSTRACT”, “Abstract”, or a journal-style “a b s t r a c t”). A heading parser may miss a section even when the content is present.
- The systematic review and unsupervised benchmark contain table-like material that should be inspected as tables, not treated as ordinary prose. In particular, the inclusion/search protocol, algorithm comparisons, dataset descriptions and metric definitions matter.
- For final extraction, verify equations and method-defining tables against the original PDF for PUDD, WinDrift++, Type-LDA, Plover, and the KDD evaluation framework. Do not repair minor OCR/formatting noise unless it changes a method, parameter, result or citation.

## Paper-by-paper evidence matrix

### 1. A systematic review on detection and adaptation of concept drift in streaming data using machine learning techniques (2024)
**Role:** Broad survey and seminar orientation; low value as a direct implementation base.

- **Scope/contribution:** Reviews concept drift types, datasets, detection techniques, adaptation approaches, evaluation metrics and future research directions. Its selection process examines literature from 2012–2022.
- **Seminar value:** High for defining the vocabulary and organizing the seminar; useful for separating detection from adaptation and for introducing the main algorithm families.
- **Limitations to keep in view:** It is a survey, not a controlled benchmark. Its literature window ends in 2022, so it cannot be the only source for current methods. The paper itself notes that existing material is scattered; we should still cross-check its taxonomy against newer work.
- **Decision:** Keep as the broad review candidate, but avoid adding multiple broad surveys to the final seminar unless they contribute clearly different taxonomies.

### 2. A benchmark and survey of fully unsupervised concept drift detectors on real-world data streams (online 2024; issue 2025)
**Role:** Key unsupervised-detection survey and benchmark.

- **Scope/contribution:** Reviews 61 publications; identifies 10 algorithms that satisfy the authors’ inclusion criteria for a sufficiently faithful implementation; evaluates 7 of them on 11 real-world data streams.
- **Important implementation/evaluation detail:** Three candidates are not evaluated for practical reasons: some were too slow in the authors’ implementation and one relied too heavily on chance. The paper recommends D3, IBDD and SPLL depending on the target metric, rather than claiming one universal winner.
- **Seminar value:** Very high. It exposes the difference between a paper proposing an algorithm and an algorithm that can be implemented faithfully and run at stream speed.
- **Ground-truth caveat:** Real-world streams are valuable but often do not have exact drift-onset labels. The paper therefore discusses proxy metrics and also checks behavior on synthetic data. Metric definitions and their failure modes must be explained rather than copying headline rankings.
- **Decision:** Keep as a core seminar paper and as an implementation/evaluation reference. Reproducing the full benchmark is likely too much for the first implementation milestone.

### 3. A Framework for Evaluating and Benchmarking Concept Drift Detection Methods (KDD 2026)
**Role:** Evaluation design, drift ground truth and fair comparison.

- **Scope/contribution:** Benchmarks 14 detectors on 7 real-world streams. It injects controlled changes using Monte Carlo trials, considering four drift mechanisms—class-prior changes, label swaps, feature permutations and feature filtering—with abrupt and gradual transitions.
- **Evaluation contributions:** Timing-aware metrics include an F1 detection score, drift recall and false-alarm rate; the framework also proposes leave-one-dataset-out hyperparameter optimization.
- **Seminar value:** Very high because it directly addresses inconsistent protocols and unknown drift points in natural data.
- **Interpretation caveat:** This creates known drift points for the *injected changes*, not verified historical drift labels for the untouched original streams. Results should be described as controlled experiments on real-world data, not proof that every naturally occurring drift in those datasets has ground truth.
- **Decision:** Keep as a core methodology paper. It may be too broad to adopt wholesale as a first thesis implementation, but its protocol can inform a smaller, defensible experiment.

### 4. Early Concept Drift Detection via Prediction Uncertainty (PUDD; AAAI 2025)
**Role:** Main thesis-base candidate, pending reproduction.

- **Core idea:** Uses a Prediction Uncertainty Index (PU-index) instead of relying only on classification error. The paper argues that the prediction-probability/uncertainty distribution can shift before the error rate changes. It uses adaptive PU-index bucketing and a Pearson chi-square test.
- **Evaluation described:** Synthetic streams and real-world streams including airline, electricity (elec2), power supply and image experiments based on CIFAR-10. The image scenario is generated to model changing user interests.
- **Strengths:** Clear hypothesis; meaningful distinction from error-rate detectors; theoretical analysis plus experiments; public repository and a potentially manageable first experiment on synthetic/tabular data.
- **Limitations/research lead:** The conclusion explicitly says alarm-threshold determination remains manual and should be automated. The chunk-based setup and statistical-test assumptions also need to be understood before proposing a change.
- **Risks:** The image/CIFAR branch introduces deep-learning and compute overhead. It should not be the first reproduction target. Theoretical claims and the precise meaning of “early” detection must be checked against the definitions and metrics in the paper.
- **Decision:** High-priority reproduction candidate. First reproduce one small synthetic or tabular result and at least one baseline before committing to an extension.

### 5. WinDrift++: A Diversified Detector for Concept Drift (IEEE Transactions on Artificial Intelligence; 2026 issue)
**Role:** Main thesis-base candidate, pending reproduction.

- **Core idea:** Extends WinDrift with a committee of empirical-CDF-based statistical distance tests (including KS, Cramér–von Mises, Anderson–Darling, Kuiper and EMD) and hierarchical sliding windows at multiple temporal scales.
- **Evaluation described:** 22 synthetic and 8 real-world datasets; comparisons against eight state-of-the-art detectors. The paper reports better detection accuracy and lower false-positive rates; it favors majority voting as a practical trade-off.
- **Strengths:** A concrete statistical detector, broad claimed evaluation, code/data repository and a clear baseline for comparing detector design choices.
- **Explicit limitation:** Fixed hierarchical window sizes can limit adaptation to highly dynamic drift patterns. The authors list adaptive windows (e.g., ADWIN-style adjustment), noisy/irregular data and finer drift-type classification as future directions.
- **Risks:** The number of named datasets does not by itself prove every dataset can be obtained or every result reproduced. We must verify the exact dataset list, drift labels, metric setup, baseline fairness, and whether tests run in our environment.
- **Decision:** High-priority reproduction candidate. Test a small synthetic case first; do not begin with all 30 datasets.

### 6. Unsupervised Concept Drift Detection with a Discriminative Classifier (D3; CIKM 2019)
**Role:** Simple, explainable baseline and a source of a specific limitation.

- **Core idea:** A discriminative classifier (logistic regression in the paper) is trained to distinguish samples from an older window and a newer window. A change in separability is used as an unsupervised drift signal.
- **Evaluation described:** 8 datasets; comparison against commonly used detectors.
- **Strengths:** Relatively simple to explain and implement; useful as a baseline for newer methods and as an example of feature-distribution monitoring without post-deployment labels.
- **Explicit limitation:** The authors state that logistic regression limits detection to linear patterns in P(X), and suggest kernelized/nonlinear classifiers and stream-dependent parameterization as future work.
- **Research caution:** “Replace logistic regression with a nonlinear model” is a plausible experiment, not automatically a novel thesis contribution. It would need a specific hypothesis, fair tuning, and evidence that it improves detection under well-defined nonlinear drifts without unacceptable false alarms/runtime.
- **Decision:** Keep as a key comparison baseline; likely easier than reproducing a complex recent method.

### 7. STUDD: A student–teacher method for unsupervised concept drift detection (2023)
**Role:** Distinct method family and useful seminar comparison.

- **Core idea:** A student model learns to mimic a teacher model. During deployment, changes in the student’s mimic loss are monitored as a drift signal, avoiding the need for continuously available true labels.
- **Evaluation described:** 19 data streams; experiments also analyze label access/delay and algorithm choices.
- **Strengths:** Conceptually distinct from direct distribution-distance tests and error-rate monitoring; helps explain unsupervised detection in the absence of labels.
- **Risks:** The original repository URL was previously found stale. A later performance-engineering repository contains an adapted STUDD implementation, but that is not evidence that the original paper’s full results are reproduced exactly.
- **Decision:** Good seminar candidate. Use the adapted implementation only after documenting what differs from the original algorithm and protocol.

### 8. Concept Drift Adaptation by Exploiting Drift Type (Type-LDA; ACM TKDD 2024)
**Role:** Detection-to-adaptation bridge, not a pure detector comparison.

- **Core idea:** Attempts to determine both *when* drift occurred and *how* it occurred. A drift-type identifier and drift-point locator are used to guide model relearning; it also includes stream-based active learning.
- **Drift types discussed:** Sudden, gradual, incremental and recurring are introduced, but the method’s stated focus is on immediate types and it excludes recurring drift in its setup.
- **Strengths:** Directly clarifies the difference between detecting change and using information about the change to adapt a model. This matters if the seminar title and thesis direction later expand beyond detection.
- **Risks:** More complex than a detector-only method; relies on synthetic data with known drift types for pretraining components. The code path appears to have changed from Type-LDA to Type-LDD, so paper/repository correspondence needs a separate check.
- **Decision:** Include if adaptation is a meaningful seminar section. Do not make it the default thesis base before understanding the training pipeline and reproduction cost.

### 9. On Learning Guarantees to Unsupervised Concept Drift Detection on Data Streams (Plover; 2018)
**Role:** Theory and assumptions.

- **Core idea:** Uses algorithmic stability and concentration inequalities to derive a bound for change detection and proposes the incremental Plover detector with a method for estimating window length.
- **Strengths:** Provides theoretical depth and demonstrates that detector behavior depends on the chosen measure function and application domain.
- **Limitations for this project:** Mathematical density is high relative to the user’s current background; the paper is older and does not appear to be the easiest path to an implementation-based thesis.
- **Decision:** Optional seminar support for theoretical foundations. Do not choose as the first thesis-base paper unless the supervisor explicitly wants a theory-heavy direction.

### 10. Towards Computational Performance Engineering for Unsupervised Concept Drift Detection (DATA 2024)
**Role:** Runtime/memory evaluation and methodological caution.

- **Core idea:** Argues that detector evaluation should include computational complexity and empirical performance, not only detection quality. It discusses complexity for existing detectors and traces two implementations with HPC tools.
- **Strengths:** Adds a dimension missing from accuracy-only comparisons: runtime, memory, scaling and bottlenecks. It also notes that complexity expressions alone do not substitute for empirical measurements.
- **Limitations:** The paper presents an initial performance analysis rather than a complete benchmark of every detector. The tooling and environment may be heavier than needed for a first thesis implementation.
- **Decision:** Valuable as a seminar complement or as a secondary evaluation dimension; not the default base paper.

### 11. A method to benchmark high-dimensional process drift detection (2025)
**Role:** Ground-truth-controlled benchmark for a specialized industrial setting.

- **Core idea:** Generates multivariate process curves with controlled drift segments and introduces temporal AUC (TAUC) to assess whether a detector identifies drift segments with the right temporal consistency.
- **Evidence:** Uses three generated benchmark datasets; the paper reports that methods can struggle when there are multiple drift segments, and that ordinary AUC can disagree with TAUC.
- **Strengths:** A clear example of a dataset with known ground truth and a metric designed around temporal segments.
- **Limitations:** Process curves from manufacturing are not interchangeable with general-purpose data streams. The benchmark is narrow and should not be generalized to all concept-drift tasks.
- **Decision:** Keep as a targeted seminar option if ground truth and industrial/process data deserve a dedicated section. Not a default thesis base unless choosing this domain deliberately.

### 12. Machine learning based concept drift detection for predictive maintenance (2019)
**Role:** Applied industrial case study.

- **Core idea:** Uses multivariate time-series regression and rolling-horizon forecasting to detect and, to some extent, predict drift in condition-monitoring data. It evaluates synthetic streams and a run-to-failure radial-fan case.
- **Strengths:** Shows a real industrial use case and a distinction between detecting a drift after it appears and forecasting it earlier.
- **Limitations:** The real-world study is a specific industrial case; open paper-matched code/data has not been verified. The case data were supplied by an industry partner, so availability and repeatability must not be assumed.
- **Decision:** Useful as an application paper if the final seminar needs predictive maintenance. Lower priority for thesis implementation until data/code access is established.

## Cross-paper comparison: the main distinctions

| Dimension | Papers that best illustrate it | What we can safely say |
|---|---|---|
| Broad taxonomy and terminology | Systematic review (1) | Best for organizing the field, not for comparing raw performance |
| Fully unsupervised detector implementation and benchmark | Unsupervised benchmark (2), D3 (6), STUDD (7) | No continuous true labels are required by these detector approaches, but evaluation may still use labels or synthetic drift positions |
| Controlled evaluation and cross-dataset tuning | KDD framework (3) | Controlled drift injection makes the injected onset known; it does not reveal natural historical onset in untouched real data |
| Uncertainty-based early signal | PUDD (4) | Tests whether prediction uncertainty changes before classification error; alarm threshold remains a research opportunity |
| Distribution tests + multi-scale windows | WinDrift++ (5) | Designed to detect multiple kinds of statistical change; fixed windows are an acknowledged limitation |
| Type-aware adaptation | Type-LDA (8) | Goes beyond “when did drift happen?” to “what kind of drift happened and how should the model relearn?” |
| Formal guarantees | Plover (9) | Provides theoretical assumptions/bounds, but higher mathematical and implementation burden |
| Runtime/memory | Performance engineering (10) | Quality metrics alone are not enough when detectors must run online |
| Controlled process ground truth and temporal score | Process benchmark (11) | Strong within its process-curve domain, not a universal concept-drift benchmark |
| Industrial application | Predictive maintenance (12) | Useful application evidence; dataset/code reproducibility remains unverified |

## Preliminary thesis direction: what to test before deciding

The two strongest current candidates are PUDD and WinDrift++, for different reasons:

- **PUDD:** an identifiable open issue around manual alarm-threshold selection, and a clear first experiment on synthetic/tabular streams.
- **WinDrift++:** an identifiable open issue around fixed window scales and a clear baseline implementation based on statistical tests.

Do not choose between them from the reported accuracy alone. The next gate should be a bounded reproducibility check:
1. Select one synthetic dataset with known drift locations from each repository.
2. Run the authors’ smallest documented example with pinned dependencies.
3. Confirm that the detector produces alarms and that the evaluation script can score them against known drift locations.
4. Reproduce one reported table row or figure as closely as practical.
5. Record runtime, environment, any code/data modifications, and discrepancies.
6. Only then compare a narrowly scoped extension (for example, threshold calibration for PUDD or adaptive window selection for WinDrift++) against the original method and fair baselines.

These are candidate research directions, not novelty claims. A contribution is defensible only after a more targeted literature check confirms that the exact proposed extension is not already solved and after a controlled experiment shows a meaningful benefit.

## Decisions intentionally not made yet

- The final 7–10 seminar papers are not selected here.
- No claim is made that any repository’s tests pass in our environment.
- No dataset is yet declared “easy” solely because a link or filename exists.
- No natural real-world stream is assumed to have exact ground-truth drift timestamps.
- No thesis novelty claim is made from an author’s future-work paragraph alone.

## Next actions

1. Check conversion quality of the method-defining equations, figures and tables in papers 2–5 and 8, against the original PDFs.
2. Inspect exact dataset lists, drift labels, metric definitions, baseline configurations and repository instructions for PUDD and WinDrift++.
3. Run only a minimal reproducibility test for one candidate at a time; do not attempt all 12 papers or every dataset.
4. Use the findings to update the priority matrix and select a complementary final seminar set, separately from the thesis-base decision.
