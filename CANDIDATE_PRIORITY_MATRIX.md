# Candidate Priority Matrix — Before MarkIt Deep Reading

**Date:** 2026-10-21  
**Purpose:** Narrow the 39 distinct papers to a manageable set for Markdown conversion and deep reading. This is **not** the final 7–10-paper seminar selection and does not lock the thesis topic.

## Decision rule

Prioritize papers that are likely to change one of these decisions:
1. How we explain the field in the seminar.
2. Which detection-method families we compare.
3. Which data/ground-truth/evaluation protocol is defensible.
4. Which paper could be reproduced and extended for the thesis.

Use separate judgments for seminar value and thesis-base value. Public code is not a prerequisite for seminar value; it is only one requirement for thesis feasibility. Do not treat a GitHub README as proof of reproducibility.

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

## What this matrix means

- **12 papers are prioritized for Markdown conversion/deep reading**, not selected as the final seminar set.
- After reading these, we may replace some with Priority B papers; the final 7–10 should be complementary, not simply the first seven rows.
- Thesis-base selection will remain a separate decision, likely centered first on PUDD versus WinDrift++, with D3/STUDD as simpler comparative baselines and the benchmark papers informing evaluation.
- The next useful action after conversion is a focused extraction of each priority paper's: research question, method, assumptions, data, ground truth, metrics, baselines, reported limitations, reproducibility steps, and plausible but unclaimed extension.
- No implementation or result reproduction has been completed at this stage.
