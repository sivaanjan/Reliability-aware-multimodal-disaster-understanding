# Results/figures

47 image files, all extracted verbatim (byte-for-byte decoded from the
notebook's embedded `image/png` output) from the two source notebooks —
none were redrawn, regenerated, or fabricated. See `../RESULTS_MANIFEST.md`
for the full source-notebook / cell mapping of every file.

## Contents

**From `01_Baseline_Experiments_B0-B4.ipynb` (6 figures):**
- `eda_event_type_distribution.png`, `eda_informativeness_distribution.png`,
  `eda_humanitarian_distribution.png`, `eda_damage_severity_distribution.png`
  — Train/Dev/Test class-distribution bar charts.
- `baseline_b1_uncertainty_by_correctness.png` — B1 (Vanilla EDL) text/image
  uncertainty boxplots, split by prediction correctness.
- `baseline_b1_reliability_diagram.png` — B1 (Vanilla EDL) reliability
  diagram (Humanitarian task).

**From `02_Proposed_Reliability_Aware_Multimodal_Model.ipynb` (41 figures):**
- `eda_class_distribution.png`, `eda_random_training_samples.png`,
  `eda_50_original_images.png` — dataset EDA / spot-check visuals.
- `preprocessed_sample_train.png`, `preprocessed_sample_dev.png`,
  `preprocessed_sample_test.png` — preprocessed image-sample grids per split.
- `training_curves.png` — multi-task loss and weighted-F1 curves.
- `evaluation_metrics_summary.png` — per-task Accuracy/Precision/Recall/F1 bars.
- `confusion_matrices.png` — normalized confusion matrices, 4 tasks.
- `reliability_analysis.png` — E-REM reliability-score distributions/correlation.
- `gradcam_case_studies.png` — Grad-CAM comparison grid (Section 19.1).
- `gradcam_faithfulness_curves.png` — Grad-CAM deletion/insertion faithfulness curves.
- `tsne_embeddings.png` — t-SNE of `H_disaster`, colored by Event Type / Damage Severity.
- `ablation_study.png` — structural ablation bar chart (Humanitarian/Damage/4-task avg).
- `erem_uncertainty_spread.png` — E-REM `u_t` / `u_v` histograms (diagnostic, Section 21.4).
- `performance_dashboard.png` — combined performance/confidence/reliability/ablation dashboard.
- `gradcam_01.png` ... `gradcam_25.png` — 25 individual single-sample Grad-CAM
  explanations (Section 19, "Sample N/25").

## Not included (checked, not present in the notebooks)

- Per-baseline (B0/B2/B3/B4) uncertainty/reliability plots — only B1's were
  rendered in the executed run; the code paths for the others exist but
  their `test_eval` uncertainty arrays were not populated in this run
  (see `01_Baseline_Experiments_B0-B4.ipynb`, Section 15 markdown note).
- "Figure 1"-"Figure 5" (B0-B4 training-loss/F1 comparison charts) referenced
  in `01_Baseline_Experiments_B0-B4.ipynb` Sections 7-8 — these cells only
  `print()` a figure caption placeholder; no image was actually rendered or
  saved in the executed notebook. The underlying numeric values are real and
  were extracted to `Results/metrics/baseline_B0_B4_training_epoch_log.csv`
  instead of being redrawn as a chart.
- Per-baseline (B0/B2-B4) confusion matrices — the `plot_confusion(...)` calls
  in `01_Baseline_Experiments_B0-B4.ipynb` Section 8.2 are commented out in
  the source; no confusion-matrix image was rendered for the baselines.
