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

### Stage 1 — Conservative first-pass screening (current planned stage)
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

### Stage 2 — Verify implementation and data (for shortlisted and borderline papers)
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
- [ ] Complete inventory: match all PDF/TXT names, inspect duplicates and extraction quality.
- [ ] First-pass screening of all 41 texts.
- [ ] Build the provisional 15–20-paper shortlist and borderline group.
- [ ] Verify public code and dataset evidence for retained/borderline papers.
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
