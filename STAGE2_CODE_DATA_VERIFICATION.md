
# Stage 2 — Code, dataset, and ground-truth verification

**Checked:** 2026-10-21  
**Repository under review:** https://github.com/abolfaaazl/data-science  
**Status:** Partial evidence-backed pass; no implementation has been executed.

## Scope and confidence rules

This pass checked public GitHub repository endpoints and visible repository contents for 11 papers with strong direct relevance to Concept Drift detection, benchmarking, or evaluation. A public repository is not proof that code runs or reproduces the paper. Dataset names in a paper are not proof of download access, reuse rights, or exact drift timestamps.

## Findings

| Paper | Code/repository evidence | Dataset and ground-truth evidence | Supervisor assessment |
|---|---|---|---|
| A benchmark and survey of fully unsupervised concept drift detectors | **Confirmed public repository:** https://github.com/DFKI-NI/unsupervised-concept-drift-detection. It contains detectors, data folder, metrics, evaluation code, requirements, tests, and BSD-3-Clause license. | Paper reports 11 real-world streams. Repository instructions require external data acquisition; at least one archive is password-protected and the cited publication gives the password. Real-world streams do not automatically have exact drift timestamps. | Excellent survey/benchmark and metrics reference. Reproduction infrastructure exists, but dataset acquisition is a friction point. |
| WinDrift++ | **Confirmed public repository:** https://github.com/Naureenaqvi/windriftplusplus. Python implementation, requirements, synthetic-data resources, tests, and license are visible; README describes 47 unit tests and a runnable pipeline. | README claims 22 synthetic and 8 real-world datasets. Synthetic generators are promising for controlled experiments; dataset-by-dataset provenance and exact drift annotations still need inspection. | Strong recent method candidate with comparatively practical setup. Tests were not run. |
| Early Concept Drift Detection via Prediction Uncertainty (PUDD) | **Confirmed public repository:** https://github.com/RocStone/PUDD. Python scripts, notebooks, data folder, results CSV, and reproduction commands are present. | README lists sine, SEA variants, mixed, powersupply, elec2, airline, and CIFAR-10. Synthetic streams are useful for controlled experiments; real streams do not guarantee exact drift-time labels. | Strong detection-focused implementation candidate. Start with tabular/synthetic experiments; image experiments add PyTorch/torchvision complexity. |
| A Framework for Evaluating and Benchmarking Concept Drift | **Confirmed public repository:** https://github.com/vcerqueira/experiments-drift_evaluation. Public README, requirements, source, scripts, and results are present; README specifies Python 3.10+ and CapyMOA. | Framework creates controlled drifts with known locations and reports evaluation on seven real-world datasets across four drift types. Exact protocol needs deep reading. | Strong evaluation-methodology reference; likely more complex than implementing one detector. |
| A method to benchmark high-dimensional process drift detection | **Confirmed public repository:** https://github.com/edgarWolf/driftbench. Python package, tests, data, project configuration, benchmark runner, and generator are present; Apache-2.0 license. | Synthetic process curves and drift segments provide controlled ground truth. Paper also links NASA milling-wear data. The scope is specialized industrial/process curves. | Useful controlled-GT and industrial benchmark reference; narrower than general stream detection. |
| Concept Drift Adaptation by Exploiting Drift Type (paper calls method Type-LDA) | The old URL https://github.com/liaub/Type-LDA appears to redirect/move to https://github.com/liaub/Type-LDD, which has Python files and data-generation scripts. | Root inventory suggests generated streams and input data, but exact relationship to the paper's method, dependencies, and ground-truth representation need verification. | Keep for adaptation comparison; do not claim exact reproduction until code-paper correspondence is checked. |
| Unsupervised Concept Drift Detection with a Discriminative Classifier (D3) | **Confirmed public repository:** https://github.com/ogozuacik/d3-discriminative-drift-detector-concept-drift. Python implementation and README are present. | Paper reports eight datasets; dataset access, exact drift-time ground truth, and current environment compatibility remain unverified. | Relevant classical unsupervised baseline; likely useful for comparisons. |
| Drift-Lens: Unsupervised Concept Drift Detection from Deep Learning Representations in Real-Time | **Confirmed public repository:** https://github.com/grecosalvatore/drift-lens. Package structure, requirements, setup file, license, and experiment documentation are present. | Deep-learning representations for unstructured data. Experiments require use-case-specific training/data scripts; some pre-extracted embeddings were described as planned rather than already available. | Important for seminar breadth, but higher implementation and compute cost; not the default easiest thesis base. |
| STUDD: A student–teacher method for unsupervised concept drift detection | The paper-linked URL https://github.com/vcerqueira/studd returns a moved/redirect response; canonical location and setup need confirmation. | Paper text reports 19 benchmark streams. Current data access and run instructions not yet confirmed. | Retain as candidate; do not treat old URL as verified runnable code. |
| Towards Computational Performance Engineering for Unsupervised Drift Detection | The paper's URL https://github.com/elwer/Perf returns 404. A likely matching repository exists at https://github.com/elwer/perf_dd and is described as experiments for the DATA 2024 paper. | Exact paper-to-repository correspondence and environment/data requirements still need verification. | Correct likely URL identified, but keep status as provisional until correspondence is confirmed. |
| LAMDA: A Longitudinal Android Malware Benchmark for Concept Drift Analysis | **Confirmed public repository:** https://github.com/IQSeC-Lab/LAMDA, with code folder, metadata file, README, and dataset link. The paper identifies itself as an ICLR 2026 conference paper. | Longitudinal Android malware data; creation instructions refer to AndroZoo, and APK access may be subject to external access/terms. Public metadata does not prove all raw APKs are freely redistributable. Exact labels and reuse terms need checking. | Strong current benchmark/application candidate, but data access and malware-domain complexity increase implementation risk. |

## Ground-truth distinction that matters

- Class labels are not the same as drift-onset timestamps.
- Drift type labels are not the same as exact onset times.
- Real-world data can be valuable while still lacking an objective event timeline.
- Controlled synthetic streams are the safer foundation for measuring detection delay, missed detections, and false alarms.
- A robust thesis design can combine controlled synthetic streams (known drift positions) with one or more real-world streams for external validity.

## Stage 2 decision

1. Preserve the original 20-paper shortlist. Do not remove papers only because code is difficult to find.
2. The strongest practical candidates for the next reproducibility-focused pass are PUDD, WinDrift++, and the unsupervised benchmark; each offers a different trade-off between a focused method, a recent tested implementation, and broad comparison.
3. Keep the evaluation framework and driftbench as references for metrics, protocols, and controlled ground truth.
4. Keep Drift-Lens and LAMDA for seminar breadth, but treat them as higher-risk implementation options.
5. Confirm Type-LDD, STUDD, and Perf_DD repository correspondence before using them as a reproduction base.

## Not yet completed

- Live code-link checks for the rest of the shortlist and reserve group.
- Running any repository, installing dependencies, downloading datasets, or reproducing paper tables.
- Verifying every publication venue/DOI and dataset license.
- Deep review of algorithms, metrics, baselines, limitations, and thesis-extension potential.

**Next action:** finish Stage 2 checks for remaining shortlist/reserve papers and publication metadata, then compare the top candidates using a structured method/data/reproducibility/extension matrix. MarkIt deep reading should begin only after this candidate set is narrowed.


## Review scope and decision sequence (2026-10-21)

The corpus contains 41 extracted-text files but 39 distinct papers after deduplication. The goal is not to deep-read every paper equally. Finish an auditable first-pass screen of all distinct papers, complete Stage 2 checks on the shortlist and plausible reserve candidates, then deep-read a smaller evidence-selected set (initially about 8–12, adjusted as needed).

The seminar and proposal should be aligned from the start but should not be treated as the same selection problem:
- **Seminar track:** choose a coherent, scientifically credible and complementary 7–10-paper narrative; code is not required for a paper to be valuable here.
- **Thesis-base track:** separately prioritize paper–repository correspondence, reproducibility, accessible data, meaningful ground truth, clear metrics/baselines, manageable implementation, and a testable extension.
- **Synthesis bridge:** derive a candidate research gap from the seminar literature, then validate it against the deeper technical review and related work. Do not claim novelty or promise a contribution before this check.

No full repository execution, dataset download, or baseline reproduction has been completed merely by checking public repository contents. Repository availability is not proof of reproducibility.


## Additional second-pass checks (2026-10-21)

### BenchMFC: A benchmark dataset for trustworthy malware family classification under concept drift (Computers & Security, 2024)

- **Publication evidence:** ScienceDirect identifies this as a Computers & Security article, volume 139 (April 2024), article 103706, DOI `10.1016/j.cose.2024.103706`. The abstract describes 223K samples from 526 families, with family, packer, and timestamp tags.
- **Repository correspondence:** The paper links to, and the public `crowdma/benchmfc` README identifies itself as, the same dataset/paper. README gives install instructions for Python 3.9 to below 3.10 and scripts for training, testing, and drift detection.
- **Data footprint:** README lists the full sample archive at approximately 83 GB; the paper's experiment subset includes an Ember feature archive around 39 MB and sample archive around 7 GB, plus metadata. This suggests the feature-based experimental subset may be much more feasible than handling raw malware binaries, but exact download links, checksums, and the usable subset still need validation.
- **Ground-truth quality:** Timestamps, family labels, and packer labels support temporal and type-specific analyses. “First seen” is an estimate of appearance time, not necessarily the exact causal onset of every drift event. Do not equate timestamp tags with exact drift-onset labels for all evaluation metrics.
- **License/security/complexity:** Repository README says MIT. This is a malware-security application and involves a specialized domain; do not download or execute raw malware. A feature-only analysis could be possible if the relevant precomputed features and protocol are accessible.
- **Assessment:** Strong benchmark/data paper for seminar discussion and evaluation design. Not a default thesis base for this student unless the project is intentionally narrowed to feature-level data and temporal drift; domain complexity and dataset size make it a higher-risk implementation path.

### Unsupervised statistical concept drift detection for behaviour abnormality detection (Applied Intelligence, 2023 issue)

- **Publication evidence:** Springer identifies the paper as published online 10 May 2022 and in Applied Intelligence volume 53 (2023), pages 2527–2537; DOI `10.1007/s10489-022-03611-3`.
- **Method/evaluation clues:** Uses a variational autoencoder (VAE) to estimate parameters for a statistical test; evaluates four artificial drift types and applies the approach to smart-home activity data from 20 older adults.
- **Ground truth/data limitation:** Authors explicitly state the real-world data are not publicly available due to privacy concerns and acknowledge that reliable ground-truth labels were unavailable for most real-world observations. Artificial data have known ground truth.
- **Assessment:** Useful seminar case study for unsupervised detection, synthetic-vs-real validation, privacy, and ground-truth limitations. Poor default thesis base if the plan requires reproducing real-world experiments; VAE and healthcare-specific features also add complexity.

### Concept drift detection and adaptation framework using optimized deep learning and adaptive sliding window (Expert Systems, 2023)

- **Publication evidence:** Wiley identifies the paper as first published 11 July 2023, DOI `10.1111/exsy.13394`.
- **Method clue:** The abstract combines an optimized Deep CNN, an aggressive-hunt optimization procedure for parameter tuning, and an optimized adaptive sliding-window method, reporting strong classification metrics.
- **Code/data status:** No direct paper-matched public implementation or independently verified dataset package was confirmed in this pass. The abstract alone is insufficient to verify benchmark fairness, leakage control, statistical significance, or whether gains can be attributed to the drift method rather than the optimizer/classifier combination.
- **Assessment:** Keep as a method-family comparison and possible critique case for the seminar; do not promote to thesis-base candidate until code, datasets, baseline details, and paper-repository correspondence are independently verified. The combined CNN/metaheuristic design is likely a higher implementation burden.

### A systematic review on detection and adaptation of concept drift in streaming data using machine learning techniques (WIREs Data Mining and Knowledge Discovery, 2024)

- **Publication evidence:** Wiley confirms first publication 19 March 2024, volume 14, issue 4, article e1536, DOI `10.1002/widm.1536`.
- **Assessment:** Strong candidate for seminar foundations because it covers drift types, detection/adaptation approaches, metrics, limitations, and future directions. No code is required for its seminar role. Check overlap against the other surveys before retaining more than one broad review in the final 7–10.

### Machine learning based concept drift detection for predictive maintenance

- **Code/data status:** This search pass did not establish a paper-matched public repository or a clearly accessible dataset/protocol. This is **not** evidence that none exists; the exact source paper and its links must be rechecked from the extracted PDF before any exclusion.
- **Assessment:** Retain provisionally if it contributes a distinct regression/predictive-maintenance angle; do not treat it as an implementation candidate yet.

## Updated second-pass implications

1. Add BenchMFC to the seminar/benchmark candidate pool; its metadata and temporal tags are valuable, but malware-domain and raw-data burdens make it a conditional, not default, thesis route.
2. Retain the VAE smart-home paper for discussion of real-world ground-truth limitations, not as a preferred reproducibility base because its real data are private.
3. Treat the optimized CNN/adaptive-window paper cautiously until its code, data, and comparative protocol are verified.
4. Keep the 2024 WIREs review as a strong broad-review candidate, while avoiding redundant survey-heavy final selection.
5. No repository has been executed and no paper's results have been reproduced during these checks.
