# Concept Drift Research — Roadmap and Decision Log

**Project:** Master's seminar and thesis preparation  
**Approved seminar topic:** Using machine-learning algorithms to detect pattern changes in dynamic data (Concept Drift)  
**Repository:** `abolfaaazl/data-science`  
**Working language:** Persian for analysis and planning; retain original English paper titles and technical terms.  
**Last updated:** 2026-10-21

## 1. Purpose of this file

This is the persistent project log for the literature-screening workflow. At the beginning of a later session, read this file before proposing a new plan. Update it after each meaningful stage with completed actions, evidence, decisions, unresolved questions, and the next step. Do not restart from scratch or silently change the agreed workflow.

This file records the workflow and decisions; it is not itself evidence that a screening stage has been completed.

## 2. Research objective

From the current collection of 41 extracted-text files (corresponding to 41 PDFs), identify a **provisional shortlist of about 15–20 papers** for the seminar. This is a conservative first-pass screen, not the final selection. Later, assess the shortlist in depth and select the strongest seminar set and one or more defensible base-paper candidates for the thesis proposal.

The central topic is Concept Drift in evolving/dynamic data streams. Papers on detection, adaptation, detection-and-adaptation frameworks, benchmarks, evaluation, and relevant applications may all be useful, but their role and relevance must be explicitly classified.

## 3. Conservative screening policy

Avoid false exclusions. A paper must not be rejected solely because its title/abstract is less compelling, its method is unfamiliar, or public code was not immediately found.

Use three first-pass outcomes:

1. **Provisional shortlist** — enough evidence of relevance or value to retain.
2. **Needs further inspection** — evidence is incomplete, ambiguous, or potentially important. Keep it in consideration.
3. **Lower priority / likely out of scope** — initial evidence suggests weaker fit. Record a specific reason; do not silently delete it.

Treat unknown code, dataset, ground-truth, or reproducibility status as **unknown / not yet verified**, not as “unavailable.” A score is for ordering work, not an automatic inclusion/exclusion threshold. Borderline papers should be retained until the deeper pass.

## 4. Screening workflow

### Stage 0 — Inventory and integrity audit
- Enumerate all PDFs and extracted-text files.
- Match text files to PDFs; identify duplicates and naming variations.
- Check extraction quality, missing pages, broken characters, and incomplete sections.
- Preserve the original files; do not delete or overwrite source papers.

**Outputs:** inventory, duplicate pairs, unmatched files, extraction warnings.

### Stage 1 — Conservative first-pass screening (completed provisionally; see FIRST_PASS_SCREENING.md)
For every paper, inspect available title, abstract, keywords, publication year/venue, research question, method category, evaluation summary, and conclusion/limitations where available.

Record at least:
- Exact title and year; paper type (survey/review, method, benchmark, application, theoretical work).
- Relationship to Concept Drift and to the approved seminar topic.
- Primary role: detection, adaptation, both, evaluation/benchmark, application, theory.
- Main method/algorithm and claimed contribution.
- Datasets and whether synthetic or real-world; whether drift labels/ground truth are available or how evaluation is defined.
- Code/repository evidence, if visible in the paper text; mark unverified when not checked.
- Initial strengths, risks, relevance, and confidence in the assessment.
- Screening status and a short evidence-based reason.

**Output target:** retain approximately 15–20 papers, with a separate “needs further inspection” group if necessary. Do not force the shortlist to exactly 15–20 by prematurely excluding ambiguous papers.

### Stage 2 — Verify implementation and data (in progress; see STAGE2_CODE_DATA_VERIFICATION.md)
- Search the paper itself for code/data links and inspect the linked public repository when feasible.
- Verify whether a repository exists, whether it matches the paper, what language/framework it uses, whether instructions and dependencies exist, and whether results appear reproducible.
- Verify dataset names, access conditions, labels/ground truth, drift types, data format, and evaluation metrics.
- Distinguish “code link mentioned,” “repository located,” and “implementation appears runnable”; these are not equivalent.

**Output:** evidence-backed code/data/reproducibility notes, with dates and URLs where checked.

### Stage 3 — Deep reading of the shortlist
Read methods, experimental design, results, limitations, assumptions, figures/tables, and appendices as needed. Check whether comparisons are fair, baselines are suitable, metrics are appropriate, and claims follow from results.

### Stage 4 — Research and thesis potential
For the strongest candidates, assess:
- Theoretical contribution and suitability for explaining the seminar topic.
- Experimental feasibility for a Master's student with a software-engineering background and limited prior ML experience.
- Dataset availability and ground-truth challenges.
- Implementation effort, mathematical prerequisites, and compute requirements.
- Specific limitations and evidence-supported opportunities for extension.
- Whether a plausible thesis contribution would be detection-focused, adaptation-focused, or hybrid. Do not assume adaptation is inherently better than detection.

### Stage 5 — Final selection and study plan
Produce a final, justified seminar reading set; rank base-paper candidates; define a feasible reproduction plan; then formulate research questions and possible thesis extensions. The final decision must follow evidence from the deeper review, not the first-pass score alone.

## 5. Assessment dimensions

Use these dimensions when relevant:
- Direct relevance to the approved topic.
- Scientific contribution and credibility of venue/method.
- Value for seminar theory and conceptual coverage.
- Method clarity and quality of experimental evaluation.
- Dataset suitability and ground-truth/evaluation quality.
- Code availability and practical reproducibility.
- Potential for a defensible thesis extension.
- Implementation difficulty, mathematical prerequisites, and fit to available resources.

No dimension should be treated as a hard exclusion rule in the initial pass. Record uncertainty explicitly.

## 6. Expected deliverables

1. Complete file inventory and duplicate/extraction audit.
2. A first-pass comparison table covering all papers, including uncertain ones.
3. A conservative provisional shortlist of about 15–20 papers, plus a clearly separated borderline group if needed.
4. A record of why lower-priority papers were deprioritized.
5. After verification: evidence-backed code, dataset, ground-truth, and reproducibility assessment.
6. After deep reading: ranked recommendations for seminar theory, practical implementation, and thesis base paper.
7. A running decision log with completed work, findings, changes, open questions, and the next action.

## 7. Current state (2026-10-21)

- [x] User reports that PDFs were converted to readable text files locally and uploaded to `extracted_text/`.
- [x] GitHub tree was checked: 41 `.txt` files are present in `extracted_text/`.
- [x] The repository contains the source PDF collection as well.
- [x] Initial inventory: 41 extracted-text files confirmed; two duplicate pairs identified from matching titles/content, leaving 39 distinct papers.
- [x] First-pass text screening performed across the collection using titles/abstracts, methods/evaluation clues, conclusions/limitations, and in-text URLs.
- [x] Provisional shortlist and reserve/lower-priority groups drafted; shortlist is intentionally conservative and not final.
- [ ] Second-pass verification of publication metadata, public code, datasets, ground truth, and reproducibility.
- [ ] Deep-read and rank final candidates.

No full 41-paper screening is claimed complete at the time this file was created.

## 8. Decision log

### 2026-10-21 — Agreed screening principle
The first stage is deliberately conservative: first identify approximately twice the number of papers likely to be needed for the seminar (around 15–20), then scrutinize the retained papers in greater depth. The priority is to avoid incorrectly excluding strong papers. Uncertain papers remain in a “needs further inspection” category, and every lower-priority decision should have a recorded reason.

## 9. Update template for future sessions

For each work session, append:
- **Date:**
- **Stage:**
- **Files/papers examined:**
- **Actions completed:**
- **Evidence and findings:**
- **Decisions made and reasons:**
- **Uncertainties / items to verify:**
- **Changes to shortlist:**
- **Next concrete action:**

## 10. Source collection

- Extracted text files: https://github.com/abolfaaazl/data-science/tree/main/extracted_text
- PDF collection: https://github.com/abolfaaazl/data-science

When referring to a paper, use its exact filename/title to avoid confusing similarly named versions. Treat identical PDF/TXT duplicates as one paper for scientific counting, but retain an audit record of both files.


### 2026-10-21 — First-pass screening completed (provisional)
- Added `FIRST_PASS_SCREENING.md` with a provisional 20-paper shortlist, 12 papers to inspect further, and 7 distinct lower-priority papers; a duplicate DRIFTLENS file is separately listed for audit, so there are 40 category rows for 39 distinct papers.
- Two duplicate pairs identified: the two differently named copies of the unsupervised benchmark survey, and the two differently named copies of DRIFTLENS.
- The review is based on extracted text and URL mentions; live code repositories, licenses, dataset accessibility, venue status, and end-to-end reproducibility remain unverified.
- An advisor-style audit found and corrected an initially omitted industrial-process drift review in the reserve group.
- Next action: verify source metadata and code/data/ground-truth evidence for shortlisted and borderline papers before making final seminar selections.


## Stage 2 update — 2026-10-21 (partial verification pass)

A live public-repository check was completed for 11 implementation/benchmark candidates. The evidence and caveats are documented in [STAGE2_CODE_DATA_VERIFICATION.md](STAGE2_CODE_DATA_VERIFICATION.md).

Public repositories were confirmed for the unsupervised benchmark, WinDrift++, PUDD, the evaluation framework, driftbench, D3, Drift-Lens, and LAMDA. The Type-LDA URL appears to have moved to Type-LDD; the paper-linked STUDD URL returns a moved/redirect response; and the old Perf URL returns 404 while a likely matching Perf_DD repository exists. These last three require paper-to-repository correspondence checks.

No code was executed, no dependencies installed, no datasets downloaded, and no result tables reproduced. Real-world streams generally do not guarantee exact drift timestamps, while controlled synthetic streams can. The original 20-paper shortlist is preserved. Practical candidates for the next reproducibility pass are PUDD, WinDrift++, and the unsupervised benchmark, but no base paper has been selected.

**Next step:** verify the remaining shortlist/reserve papers and publication metadata, then conduct a structured comparison of methods, metrics, baselines, ground truth, limitations, and thesis-extension potential. Use MarkIt only after the candidate set narrows.


## 2026-10-21 — Seminar-to-thesis selection principle (user clarification)

The selection objective is not simply to find the 7–10 individually strongest papers. The final set should work as a coherent literature narrative and also support choosing one feasible thesis-base paper.

### Seminar paper set (7–10 papers)
Select complementary roles rather than seven to ten papers that all do the same thing:
1. One or two foundational/survey papers that define Concept Drift, its types, and the main detection/adaptation families.
2. Two or three direct detection-method papers representing meaningfully different approaches.
3. One or two evaluation/benchmark papers that clarify datasets, metrics, and limitations.
4. One or two papers that expose an important unresolved challenge or a promising application, without letting the seminar drift away from the approved general topic.
5. Ensure the chosen base paper is included and can be explained in the overall narrative.

The exact allocation is flexible; paper quality and complementarity take priority over filling fixed slots.

### Thesis-base paper selection
A candidate should be judged on:
- clear and defensible research problem;
- accessible implementation and understandable method;
- dataset access and well-defined ground truth, preferably with controlled synthetic streams for detection-timing metrics;
- baseline methods and evaluation metrics that can be reproduced;
- a concrete limitation or research gap that could be tested, not merely claimed;
- realistic complexity for a master's student with limited prior ML experience;
- a credible route from reproduction → one bounded improvement → fair comparative evaluation;
- publication quality and enough novelty to support a defensible proposal.

Having GitHub code is useful but not sufficient. The code must correspond to the paper, dependencies and data must be obtainable, and the baseline must be reproducible before proposing a modification. An improvement is not guaranteed to be publishable simply because it changes a parameter or replaces a component.

### Decision policy
Keep two related but distinct rankings:
- **Seminar value:** explanatory coverage, scientific credibility, diversity of approaches, recency where relevant, and usefulness to the narrative.
- **Thesis-base value:** reproducibility, data/ground-truth feasibility, implementation complexity, measurable limitations, and extension potential.

Do not remove an excellent explanatory/survey paper merely because it has no code. Do not select a base paper merely because it has a repository. The final 7–10-paper set should be chosen after the deeper review, and the base paper should be selected by a separate explicit decision matrix.


### 2026-10-21 — Review scope and seminar/proposal alignment

#### Decision: do not deep-read all 41 files equally
The repository contains 41 extracted-text files but 39 distinct papers after identifying two duplicate pairs. We should preserve an auditable first-pass decision for every distinct paper, but **we do not need to conduct a full, equally detailed review of all 39**.

Use a funnel:
1. **Inventory and deduplicate all 41 files**; map each file to its paper and record duplicates.
2. **First-pass screen all 39 distinct papers** using title, abstract, research question, method, evaluation clues, conclusion, publication details, and code/data links. Record a reason for deprioritization rather than silently dropping papers.
3. **Stage 2 verification** for the provisional shortlist and any reserve papers that could plausibly change the ranking: check paper–repository correspondence, code contents and run instructions, data access, ground truth, metrics, dependencies, license/terms, and publication metadata.
4. **Deep-read a smaller candidate set** (initially about 8–12 papers, adjusted to the evidence) with MarkIt: method, assumptions, baselines, experiments, limitations, threats to validity, and possible research gaps.
5. Select the final **7–10 seminar papers** based on complementarity and scientific value, and choose the thesis-base paper using a separate reproducibility/extension matrix.

Reopen a deprioritized paper if new evidence indicates that it fills a missing role, has a substantially better reproducibility path, or challenges the current ranking. This avoids both extremes: overlooking the corpus and wasting time deeply reviewing every paper.

#### Decision: seminar and thesis proposal should be aligned from the start, but not collapsed into one task
The seminar should establish the conceptual map of concept drift, compare credible approaches, explain evaluation/data/ground-truth issues, and synthesize a defensible research gap. In parallel, maintain a **thesis-candidate track** that checks code, data, reproducibility, and extension feasibility. The seminar's research-gap synthesis should inform the proposal, while the thesis-base choice must still be validated by deeper technical review and a baseline reproduction attempt.

The intended chain is:
**corpus screening → seminar literature narrative → evidence-based research gap → candidate problem statement → baseline reproduction → bounded improvement and evaluation → proposal/thesis plan.**

Do not promise a thesis contribution before the gap is checked against related work. The seminar topic is approved, but the exact thesis problem, method change, dataset/protocol, and contribution remain provisional until evidence supports them.


### 2026-10-21 — Stage 2 continuation and advisor audit

Additional primary-source/public-repository checks were recorded in `STAGE2_CODE_DATA_VERIFICATION.md` and reflected in `FIRST_PASS_SCREENING.md`.

Key evidence updates:
- BenchMFC is a verified 2024 Computers & Security dataset/benchmark paper with a matching public repository, temporal/family/packer metadata, and precomputed feature options. Full raw sample archives are large (README lists ~83 GB); treat it as a strong seminar benchmark candidate but a higher-risk thesis route due to malware-domain complexity.
- The Applied Intelligence smart-home VAE detector uses controlled artificial drifts, but the authors state the real-world data are not public and reliable real-world ground truth is mostly unavailable. Keep it for evaluation-limitations discussion rather than a default reproduction base.
- The optimized CNN/adaptive-window paper's publication metadata is confirmed, but paper-matched code and transparent reproducible data/protocol remain unverified. Do not rank it highly as a thesis base based on reported accuracy alone.
- The 2024 WIREs systematic review is a strong broad-review candidate, subject to overlap checks with other surveys.
- The predictive-maintenance candidate remains unresolved; lack of a confirmed code/data link in this pass is not proof that none exists.

#### Advisor-style audit against project goals

1. **Seminar breadth:** still supported by the current pool—surveys, direct detection methods, theory, benchmark/evaluation papers, and application-specific work are represented. The final set must avoid redundant surveys and must not be dominated by code availability.
2. **Thesis feasibility:** there are several plausible implementation directions (including PUDD, WinDrift++, D3, and possibly the unsupervised benchmark), but none is yet proven reproducible because no code has been executed and no paper results have been reproduced.
3. **Data and ground truth:** the concern is real, not hypothetical. Real-world streams may lack exact drift-onset labels; synthetic controlled data and clearly documented drift positions should be part of any defensible detection experiment. Real-world datasets can be supplementary rather than the sole evaluation basis.
4. **Novelty:** no thesis improvement is approved at this stage. Candidate gaps must be derived from limitations and related work, then tested for novelty and feasibility after baseline reproduction.
5. **Workflow efficiency:** the review funnel is appropriate: first-pass screen all 39 distinct papers, continue targeted Stage 2 checks, then deep-read a smaller evidence-selected set rather than treating all papers equally.
6. **Current outcome:** progress is aligned with the user's goals, but selection is not complete. Next, finish remaining high-impact code/data and venue checks, create a comparison matrix for seminar value and thesis-base value separately, then use MarkIt for deep reading of the strongest candidates.

Do not report this stage as implementation or reproduction. It is a source-checked documentary verification pass only.


### 2026-10-21 — Lead-candidate publication checks and interim comparison

Primary publication metadata was checked for the leading candidates and recorded in Stage 2:
- PUDD is confirmed as an AAAI 2025 paper (DOI 10.1609/aaai.v39i18.34105) with a public repository and explicit experiment commands.
- WinDrift++ is confirmed in IEEE Transactions on Artificial Intelligence, 2026 issue (DOI 10.1109/TAI.2025.3619461); its public repository includes test instructions and claims 47 passing tests, but this has not been independently run.
- The evaluation framework is listed on the official KDD 2026 papers page and has DOI 10.1145/3770855.3819070.
- The fully unsupervised survey/benchmark is confirmed in the International Journal of Data Science and Analytics, online 2024 / issue 2025 (DOI 10.1007/s41060-024-00620-y).

#### Interim supervisor comparison

PUDD and WinDrift++ are currently the strongest practical thesis-base candidates in the checked pool, with different trade-offs. PUDD has a clearly articulated uncertainty-based detection signal and synthetic/tabular entry points; WinDrift++ has a diversified statistical-test approach and a repository that claims a test suite. Neither is yet proven reproducible. The broad unsupervised survey/benchmark and the KDD evaluation framework are particularly valuable for the seminar's scientific framing and evaluation protocol. BenchMFC strengthens benchmark/application coverage but carries greater domain and data-size burden.

#### Audit against the user's stated objectives

- **Seminar:** The candidate pool is broad enough to construct a complementary 7–10-paper story, but the final selection still requires overlap checks among surveys and deep reading of the methods/results.
- **Thesis:** We have plausible, code-backed candidates; we have not yet earned the right to promise a specific improvement because no baseline has been executed or reproduced.
- **Ground truth:** The concern remains central. Use controlled synthetic streams with known drift positions as the core detection-timing evaluation, then add real-world streams where appropriate while clearly stating label/onset limitations.
- **Implementation burden:** Avoid making deep learning or malware analysis the default path. Start with one tractable baseline and a small controlled dataset.
- **Novelty and academic quality:** Any proposed improvement must be justified by a documented limitation, compared with related work, and evaluated against fair baselines; do not assume a gap from a paper's own conclusion alone.
- **Efficiency:** Continue the Stage 2 funnel only where additional evidence could change candidate ranking. Then deep-read a smaller group with MarkIt.

**Next action:** finish high-impact repository/data checks for the remaining shortlist and a small number of reserve papers, then create a comparative decision matrix with two independent scores: seminar value and thesis-base value. The present ranking is interim, not final.


### 2026-10-21 — Candidate narrowing for faster MarkIt workflow

To avoid prolonging Stage 2 indefinitely, created `CANDIDATE_PRIORITY_MATRIX.md` to identify a focused set for Markdown conversion and deep reading. It prioritizes 12 papers across surveys, direct detectors, evaluation/benchmarking, theory, computational performance, and one real industrial application. Priority is not final seminar selection.

Key new clarifications:
- STUDD is a published 2023 method reporting 19 data streams. The paper-linked repository URL is stale, but the public `elwer/perf_dd` repository contains an adapted STUDD implementation as part of the DATA 2024 performance experiments. This supports keeping STUDD for deep reading, while exact reproduction correspondence still needs checking.
- D3 explicitly states that its logistic-regression version is limited to linear patterns in P(X), and lists nonlinear classifiers as future work. This is a possible comparison axis, not a novelty claim: related work must be checked before proposing a nonlinear replacement.
- The predictive-maintenance paper (Computers & Industrial Engineering, 2019) has a real radial-fan run-to-failure case alongside synthetic experiments. It offers useful application context, but data/code availability and event-ground-truth definitions remain uncertain.
- CV4CDD-4D (Process Science, 2025) is a recent supervised computer-vision approach for event logs and four drift types. It is a reserve candidate because its process-mining/event-log framing is specialized and may not fit the general seminar as well as the prioritized papers.
- LAMDA and BenchMFC are retained as alternatives, not both required: malware-domain depth is only warranted if an application focus is chosen.

#### Advisor audit of the accelerated plan

The user clarified that final 7–10 selection comes **after Markdown conversion**. Therefore the current deliverable is a prioritized conversion/deep-reading set, not a premature final seminar selection. This reduces the initial pool from 39 distinct papers to 12 high-information candidates while preserving a reserve list for substitutions.

The plan still matches the original goals: field coverage, complementary method families, honest ground-truth discussion, and a separate code/data/reproducibility test for the thesis-base paper. PUDD and WinDrift++ remain the leading implementation candidates, not final choices. The next stage should start MarkIt conversion for the 12 priority papers, then extract comparable evidence rather than continue open-ended repository browsing.


### 2026-10-22 — Stage 3: first deep-reading pass over the 12 MarkIt papers

The user uploaded all 12 prioritized Markdown conversions to `markit_concept_drift/`. The folder contains 12 paper files plus `readme.md`, which maps the shortened/numbered filenames to the full paper titles. The initial comparative evidence report is saved at [`MARKDOWN_DEEP_READ_STAGE1.md`](MARKDOWN_DEEP_READ_STAGE1.md).

#### Main evidence-based conclusions
- The current pool has complementary roles: one broad 2024 systematic review; one benchmark/survey of fully unsupervised detectors; the KDD 2026 evaluation framework; detector families represented by PUDD, WinDrift++, D3, STUDD and Plover; Type-LDA for the detection/adaptation boundary; performance engineering; a process-curve benchmark with controlled labels; and a predictive-maintenance case study.
- The most defensible current seminar backbone is the broad review + unsupervised benchmark + KDD evaluation framework, supplemented by distinct methods rather than redundant surveys. The final 7–10 papers remain unselected until method/table checks and overlap review are complete.
- PUDD and WinDrift++ remain the leading thesis-base candidates for a small reproducibility gate, not final choices. PUDD's manual alarm-threshold setting is a concrete research lead; WinDrift++'s fixed hierarchical window scales are another. Neither is a novelty claim until related work is checked and an original baseline is reproduced.
- D3 is a useful classical baseline: the paper explicitly says its logistic-regression version is limited to linear patterns in P(X). This is a plausible experimental axis, but replacing the classifier alone is not assumed novel.
- The ground-truth concern is confirmed as central. Synthetic or injected drift supports known onset evaluation; natural real-world streams generally do not provide verified historical onset timestamps. The KDD framework evaluates controlled injected changes on real-world datasets, while the process-curve benchmark generates drift segments with known labels.
- STUDD is useful as a distinct unsupervised signal based on student–teacher mimic loss, but the adapted implementation in the performance-engineering repository must not be treated as an exact reproduction of the original paper.
- Type-LDA is primarily a drift-type-aware adaptation framework, so include it in the seminar only if it adds a useful explanation of the detection/adaptation boundary. It is not required for a detection-focused thesis.
- The predictive-maintenance paper adds a useful industrial case, but its real radial-fan data and paper-matched code have not been verified as publicly reproducible. The high-dimensional process-drift benchmark is better for explaining controlled ground truth, but it is a specialized process-curve setting.

#### Conversion-quality note
The folder listing confirms all 12 files are present. Some conversions include large embedded image payloads and inconsistent abstract/heading formats. Before using method-defining formulas, results tables, or figure-based claims, compare those specific items with the original PDFs. This is a targeted quality check, not a reason to redo all conversions.

#### Status and next action
This is a documentary deep-reading pass only. **No code has been run, no dataset has been downloaded, and no reported result has been independently reproduced.** Next, perform targeted PDF verification of the most decision-relevant tables/formulas and inspect the PUDD and WinDrift++ repositories' smallest runnable examples. Then select one small baseline reproduction path. Keep seminar-paper selection and thesis-base selection as separate decisions.


### Stage 5 — Minimal PUDD reproduction gate defined (2026-10-22)

- Inspected the official PUDD README, `main.py`, `main_ensemble.py`, and `load_dataset.py`. Official first command for the tabular/synthetic Table 1 path is `python main.py --threshold -1 --continual True --dataset_name sine --classifier_name GNB`; avoid CIFAR-10 at the first step.
- Source-level finding: SINE variants are changed every 10 chunks by the generator structure, but `load_dataset_with_drift(..., seed, drift_every_k_chunks)` does not use either argument. Seed control must be verified rather than assumed.
- The main script saves aggregate predictive accuracy/configuration/runtime to `result.csv`; this alone is not an event-level detection evaluation. Alarm/reset traces must be aligned with known transition indices to calculate delay, misses, and false alarms.
- Added `STAGE5_PUDD_MINIMAL_REPRODUCTION_GATE.md` with exact command, environment/smoke-test gate, alarm-trace gate, evaluation gate, pass/fail criteria, and decision rule.
- Execution status: source inspection only. Local shell could not resolve GitHub DNS, so the upstream repository could not be cloned/run in this environment. This does not establish failure on the user's Windows machine. No reproduction is claimed.
- Decision: PUDD remains a provisional candidate, not the final thesis base. Next evidence needed is a single successful SINE/GNB run plus an interpretable alarm trace and event-level evaluation. If that requires substantial reconstruction, pivot to a simpler detector/baseline with clearer ground-truth metrics.
