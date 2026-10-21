
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
