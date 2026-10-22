# Stage 5 — Minimal Reproduction Gate (PUDD)

**Date:** 2026-10-22  
**Purpose:** Define the smallest honest test before committing to PUDD as the thesis base.  
**Status:** Source inspection only; upstream code has not been executed.

## 1. Exact official starting command

The repository README's Table 1 example is:

```bash
python main.py --threshold -1 --continual True --dataset_name sine --classifier_name GNB
```

The README lists `sine`, `sea0`, `sea10`, `sea20`, `mixed`, `powersupply`, `elec2`, `airline`, and `cifar10` as datasets; `GNB`, `DNN`, and `hoeffding` as classifier options; and threshold values `-1`, `-3`, and `-5`. CIFAR-10 requires preprocessing and is not appropriate for the first gate.

## 2. Important source-level findings

- The synthetic SINE generator changes the selected classification function every 10 chunks (`i % 10 == 0`), so the intended transition schedule is controlled by the generator structure.
- However, `load_dataset_with_drift(..., seed, drift_every_k_chunks)` currently does not use either argument. The synthetic variant selection uses NumPy random choice, and reproducibility therefore depends on the global RNG state set elsewhere.
- The official `main.py` loops over 100 episodes and saves aggregate classification accuracy, configuration, and runtime to `result.csv`. This output alone does **not** provide a complete per-drift event table with detection delay and false-alarm counts.
- The code's action/reset events can be observed in the console, but they must be aligned to the known synthetic transition schedule before standard event-level metrics can be calculated.
- The minimal official command is not necessarily a quick detector-only test: it runs the full experimental loop and requires PyTorch, River, NumPy, torchvision, tqdm, and related classifier dependencies.

## 3. Gate procedure

### Gate A — Environment and smoke test
1. Use a fresh Python virtual environment (do not alter a working global Anaconda environment).
2. Install dependencies as specified by the repository; record Python and package versions.
3. Run the official SINE/GNB command once.
4. Save the terminal output and generated `result.csv`; note runtime, warnings, and errors.

**Pass:** command finishes and writes a new result row.  
**Fail:** dependency or runtime errors cannot be resolved with a bounded amount of work.

### Gate B — Verify the detector signal
1. Inspect the saved/console output to determine exactly which event means a drift alarm/reset.
2. Confirm the transition indices implied by the generator and document the index convention (zero- or one-based; chunk index vs sample index).
3. Run a small number of repeated trials with explicit seeds. Record whether outputs are reproducible; if not, identify the uncontrolled random sources.
4. Do not treat the overall accuracy in `result.csv` as detection precision/recall.

**Pass:** each trial has a traceable alarm sequence and an explicit known transition schedule.  
**Fail:** alarms cannot be extracted or aligned without invasive changes to the original code.

### Gate C — Evaluation feasibility
For each known transition, calculate:
- detection delay in chunks;
- missed transitions;
- false alarms in no-drift intervals;
- optional precision/recall/F1 only after defining a defensible event-matching tolerance.

Use the same generated stream and transition labels for PUDD and a simple baseline. Report means and variability across repeated seeds, not only the best run.

**Pass:** the protocol can evaluate detection behavior separately from downstream predictive accuracy.  
**Fail:** published claims cannot be checked without substantial reconstruction.

## 4. Decision rule

PUDD becomes the provisional thesis base only if Gates A–C pass with bounded effort and the method-defining equations/results are checked against the paper PDF. If Gate A passes but B/C fail, keep PUDD as a seminar paper and compare against a simpler detector with clearer event-level evaluation. Do not claim reproduction based on a successful command alone.

## 5. Execution limitation in this review

The current review environment could retrieve public source files through the GitHub connector, but outbound DNS/network access from its local shell was unavailable, so the upstream repository could not be cloned and executed here. This is a tooling limitation, not evidence that the project fails on the user's Windows system. No results have been reproduced.
