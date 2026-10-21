# Concept Drift — First-Pass Screening of the Paper Collection

**Date:** 2026-10-21  
**Repository:** https://github.com/abolfaaazl/data-science  
**Input folder:** https://github.com/abolfaaazl/data-science/tree/main/extracted_text  
**Purpose:** Conservative first-pass screening, not final paper selection.

## Important interpretation

There are 41 extracted-text files and 41 PDFs. Two paper pairs appear duplicated under different filenames, leaving **39 distinct papers by the initial duplicate audit**. Duplicates count once in the scientific shortlist; original files have not been deleted.

The first-pass assessment used extracted text, especially title/abstract, method/evaluation clues, conclusion/limitations, and URLs appearing in the text. This is not yet a full verification of all formulas, tables, appendices, or linked repositories. A URL mentioned in a paper is not proof that the repository is accessible or runnable. Dataset and ground-truth claims remain provisional.

To minimize false exclusions, uncertain papers are retained in a separate group. “Lower priority” means lower priority for the central seminar set, not necessarily poor scientific quality.

## Initial result

- Provisional shortlist: 20 distinct papers.
- Inspect further / reserve: 11 distinct papers.
- Lower priority for the central set: 8 distinct papers.
- Total distinct papers accounted for: 39.
- Duplicate text/PDF pairs: 2 pairs.

## A. Provisional shortlist — 20 papers

| # | Paper / file identifier | First-pass role and reason to retain | Dataset / ground-truth clues | Code clue in text | Confidence |
|---:|---|---|---|---|---|
| 1 | A benchmark and survey of fully unsupervised concept drift detectors (2025; duplicate copy also present) | Core survey and comparative benchmark of fully unsupervised detectors; highly aligned with detection without online labels; useful for theory, metrics, and research gaps. | Reports 11 real-world streams and seven evaluated algorithms; ground-truth/evaluation assumptions need inspection. | DFKI-NI GitHub URL appears in paper. | High |
| 2 | WinDrift++: A Diversified Detector for Concept Drift (2026) | Recent primary detection method using a committee of statistical tests; directly aligned with detection and compared against baselines. | Reports 22 synthetic and 8 real-world datasets. Synthetic ground truth may be useful; verify generation details. | windriftplusplus GitHub URL appears; paper wording says code/data will be made available, so live status is unconfirmed. | High |
| 3 | Early Concept Drift Detection via Prediction Uncertainty (AAAI-25) | Primary method with a clear question: can predictive uncertainty signal drift earlier than error rate? | Real-world datasets mentioned; exact names, labels, and drift-time ground truth need extraction. | PUDD GitHub URL appears in text. | High |
| 4 | A Framework for Evaluating and Benchmarking Concept Drift (KDD ’26, as indicated in text) | Important evaluation framework addressing inconsistent benchmarks, drift simulation, metrics, and hyperparameter transparency. | Controlled distribution changes and an evaluation window are described; verify exact data and label construction. | experiments-drift_evaluation GitHub URL appears. | High |
| 5 | A method to benchmark high-dimensional process drift detection (2025) | Benchmark/method paper for multivariate process curves; addresses multiple drift segments and an evaluation score. | Synthetic process-curve generation with stated ground truth; useful for reproducible experiments but domain-specific. | driftbench GitHub URL appears. | High |
| 6 | A systematic review on detection and adaptation of concept drift in streaming data (2024) | Broad review of drift types, detection, adaptation, datasets, and metrics; useful for seminar foundations. | Discusses synthetic and real-world datasets; individual dataset suitability needs extraction. | A data-streams GitHub URL appears in references/text, not confirmed as code for this review. | High |
| 7 | A Systematic Literature Review of Concept Drift Mitigation in Time-Series Applications | Relevant review of detection/adaptation in time series; points to a possible regression-focused gap. | Discusses real-world and synthetic data; specific datasets and review protocol need verification. | No clear direct implementation link found in initial scan. | High |
| 8 | An overview of unsupervised drift detection methods | Directly relevant overview; complements the benchmark paper and maps assumptions/failure modes. | Discusses global vs regional drift and false alarms; dataset details need inspection. | No direct code link identified. | High |
| 9 | Concept Drift Adaptation by Exploiting Drift Type | Primary adaptation work with explicit drift-type handling; helps compare detection-only and adaptation thesis paths. | Experiments mention stream datasets such as Poker/Elec; verify complete benchmark and ground truth. | Type-LDA GitHub URL appears. | High |
| 10 | Concept Drift Detection on Unlabeled Data Streams: A Systematic Literature Review | Direct match to the unlabeled/unsupervised branch; useful for taxonomy and research-gap discovery. | Focuses on unlabeled streams; exact datasets and review protocol need checking. | No direct code URL identified. | High |
| 11 | Concept Drift Under Harsh Constraints: A Review of Potential Strategies for IoT Systems | Useful resource-efficiency review; highlights accuracy/adaptability/resource trade-offs. | IoT-focused review, not yet identified as an independent benchmark. | No direct code link identified. | Medium-high |
| 12 | Learning under Concept Drift: A Review | Broad foundational review of detection, understanding, and adaptation; useful for conceptual framework and terminology. | Review; no new benchmark confirmed in initial scan. | No direct code link identified. | High |
| 13 | One or Two Things We Know About Concept Drift — A Survey on Monitoring in Evolving Environments | Conceptual survey on monitoring and unsupervised detection; may help define the problem and avoid evaluation pitfalls. | Discusses multivariate/high-dimensional monitoring; data details need inspection. | No confirmed direct implementation link. | Medium-high |
| 14 | On Learning Guarantees to Unsupervised Concept Drift Detection on Data Streams (2018) | Theoretical paper on learning guarantees and the Plover algorithm; adds depth beyond empirical papers. | Synthetic and real-world scenarios mentioned; inspect assumptions and evaluation protocol. | No direct code link identified. | High for theory |
| 15 | Unsupervised Concept Drift Detection with a Discriminative Classifier (D3) | Directly relevant unsupervised detector and potential baseline; may be a comparatively approachable implementation candidate. | Sliding-window discriminative approach; datasets and ground truth need full-text review. | D3 GitHub URL appears. | High |
| 16 | Unsupervised Concept Drift Detection From Deep Learning Representations in Real-Time (DRIFTLENS; duplicate copy also present) | Recent primary method for unlabeled, unstructured streams; relevant to representation-based detection, though implementation may be harder. | Multiple use cases/streams mentioned; ground-truth construction and compute requirements need verification. | drift-lens GitHub URL appears. | High |
| 17 | A student–teacher method for unsupervised concept drift detection | Primary unsupervised method avoiding online true labels; useful to compare with D3 and DRIFTLENS. | Experiments described; datasets and drift labels need extraction. | studd GitHub URL appears, along with links to related tools. | High |
| 18 | Benchmarking Change Detector Algorithms from Different… | Focused benchmark comparing EDDM, DDM, HDDMW, and HDDMA across abrupt, gradual, and incremental drift. | Compares detection capability/delay; authors note more diverse/larger datasets would improve the findings. | No direct code link confirmed. | Medium-high |
| 19 | Towards Computational Performance Engineering for Unsupervised Drift Detection | Important perspective on runtime and computational cost, not just accuracy; relevant to defensible experimental design. | Initial performance analysis of two detectors; benchmark scope needs review. | Perf GitHub URL appears. | High |
| 20 | LAMDA: A Longitudinal Android Malware Benchmark for Concept Drift Analysis (ICLR 2026 filename) | Potentially valuable longitudinal benchmark/data contribution; data quality can determine thesis feasibility even if it is not a new detector. | Temporal malware/family drift is central; inspect license, availability, labels, splits, and temporal ground truth. | IQSeC-Lab/LAMDA GitHub URL and project page appear. | High for dataset relevance; venue/status to verify |

## B. Inspect further / reserve — 11 papers

These remain in consideration and should not be discarded without further evidence.

| # | Paper / file identifier | Why it remains under consideration | What must be checked |
|---:|---|---|---|
| 21 | A Comprehensive Survey on Concept-Drift-Resilient Network Intrusion Detection Systems (2026) | Recent, substantial survey connecting datasets, detection, adaptation, and dynamic evaluation; useful if security is selected as an application. | Unique contribution vs other reviews; benchmark tables and dataset mapping. |
| 22 | A Systematic Review of Concept Drift Approaches for Anomaly Detection in IoT (2025) | Focused review of drift in IoT anomaly detection and cybersecurity. | Review quality, selection protocol, overlap with NIDS survey, and concrete datasets. |
| 23 | Concept drift detection in image data stream: a survey | Specialized survey for high-dimensional visual data; may inform representation-based detection. | Fit to general seminar scope and whether image data makes thesis too difficult. |
| 24 | Concept drift detection and adaptation framework using optimized deep learning and adaptive… | Primary streaming/deep-learning framework; possible implementation direction. | Complexity, fair baselines, reproducibility, and whether improvement claims are supported. |
| 25 | Machine learning based concept drift detection for predictive maintenance | Industrial application with time-series regression and condition monitoring. | Dataset access, label/drift-time definition, and reproducibility. |
| 26 | Machine learning-based detection of concept drift in business processes | Specialized detection method for event logs and multiple drift types. | Domain-specific data, repository access, complexity, and fit to general scope. |
| 27 | Implementing machine learning model drift detection in fog | Recent distributed/fog application, potentially relevant to resource constraints. | Distinguish data/concept drift from model drift; inspect labels, baselines, and implementation. |
| 28 | Unsupervised Statistical Concept Drift Detection for Behaviour Abnormality Detection | Unsupervised method with sensor/activity data and a real-world use case. | Publication type, data access, novelty, and suitability as a peer-reviewed base paper. |
| 29 | BenchMFC: A Benchmark Dataset for Trustworthy Malware Family Classification | Dataset paper motivated partly by concept drift; may complement LAMDA. | Explicit temporal annotations, public access, license, labels, and overlap with LAMDA. |
| 30 | Benchmarking concept drift adoption strategies for high-speed data stream mining | Broad review/taxonomy of adaptation strategies. | Publication age/venue, rigor, and redundancy with newer systematic reviews. |
| 31 | A review on real-time data stream classification and adapting to various concept drift scenarios | Older overview of streaming classifiers/adaptation; may support foundational context. | Publication date, depth, and redundancy with newer reviews. |

## C. Lower priority for the central seminar set — 8 papers

“Lower priority” is provisional and topic-relative, not a claim that the work is scientifically poor.

| # | Paper / file identifier | Initial reason for lower priority | What could change the decision |
|---:|---|---|---|
| 32 | A Hybrid Recommendation System: A Review | Primarily a recommender-system review; concept drift is one component rather than the central research question. | Reconsider if a recommendation-system application is selected. |
| 33 | A Systematic Review of Machine Learning and Deep Learning Approaches for Credit Card Fraud Detection | Fraud-detection review; the extracted abstract does not show concept drift as its central focus. | Reconsider if full text has a substantive drift section or unique streaming dataset. |
| 34 | A survey about self-adaptive anomaly detection in software-defined systems | Adjacent anomaly/IDS topic; drift is one aspect of a broader adaptive-system review. | Could support an application-focused seminar section if it adds unique taxonomy/evidence. |
| 35 | Development of an Efficient Supervised Machine Learning Model using Concept Drift Analysis: A Review | Initial text appears broad and less specific about a novel method or rigorous benchmark. | Check venue and references before a firm exclusion; retain if it offers unique coverage. |
| 36 | Evolving Strategies in Machine Learning: A Systematic Review | Broad review of evolving strategies, not necessarily narrow enough on drift detection. | Check its review protocol, coverage, and unique recent methods. |
| 37 | SDDObench: A Benchmark for Streaming Data-Driven Optimization | Focuses on streaming data-driven optimization/evolutionary algorithms rather than concept-drift detection itself. | Reconsider only if the thesis moves toward optimization under environmental change. |
| 38 | Online machine learning for proactive DDoS defense | Focuses on proactive DDoS detection/mitigation; drift is not clearly central in the abstract. | Reconsider if full text explicitly evaluates drift or temporal shifts. |
| 39 | Duplicate copy of DRIFTLENS | Same scientific paper as item 16 under a filename variation; not a separate paper. | Retain both files in the integrity audit, but count the paper once. |

## Duplicate and integrity audit

Two duplicate pairs are visible from the file inventory and matching paper contents:

1. “1. A benchmark and survey of fully unsupervised concept drift detectors.txt” and “A benchmark and survey of fully unsupervised concept drift detectors.txt”.
2. “Unsupervised Concept Drift Detection From Deep Learning Representations in Real-Time.txt” and “Unsupervised_Concept_Drift_Detection_From_Deep_Learning_Representations_in_Real-Time.txt”.

These pairs count as two scientific papers, not four. Source files remain untouched. A stricter byte-level comparison and PDF-to-text match should be completed if ambiguity remains.

## Code and data verification status

URLs were extracted from the paper text, but live repository state, code completeness, dependency installation, dataset licensing, and end-to-end reproducibility have **not** yet been confirmed.

- “URL mentioned in paper” is a lead, not proof of accessible/runnable code.
- “Real-world dataset” does not prove that the data are public.
- Synthetic ground truth may be known by construction, but the generator and drift-time labels must be checked.
- Benchmarks may define detection timing differently; metric compatibility must be examined.

Next verification priority: shortlist items 1–5, 9, 15–20, plus reserve items 24, 25, 28, and 29 if their code/data could change the ranking.

## Second-pass advisor audit checklist

Before treating this result as stable, re-check:
1. All 41 text files are accounted for, with duplicate files explicitly marked.
2. The shortlist includes theory, direct detection methods, evaluation/benchmark papers, and feasible implementation candidates.
3. No potentially valuable paper was deprioritized solely because code/data were not immediately found.
4. Code and dataset claims remain marked “mentioned in text” until independently verified.
5. Current-year papers and venue/conference status are verified from primary sources.
6. The shortlist remains provisional until methods, results, limitations, and data/code feasibility are checked.

## Next step

Create a precise inventory of publication metadata and filenames, verify public code and dataset/ground-truth evidence for shortlisted and borderline papers, then re-rank and choose the final seminar set and base-paper candidates.
