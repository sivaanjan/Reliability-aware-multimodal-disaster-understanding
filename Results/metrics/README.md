# Results/metrics

16 files. Every numeric value in these files was either (a) copied verbatim
from a `.to_csv(...)`/printed table that the notebook itself produced, or
(b) losslessly extracted/parsed from the notebook's real, executed console
text output (e.g. per-epoch training logs, `classification_report` text).
Nothing here was estimated, interpolated, or invented. See
`../RESULTS_MANIFEST.md` for the full source-notebook / cell mapping.

## From `01_Baseline_Experiments_B0-B4.ipynb`
- `baseline_B0_B4_comparison.csv` — per-task + average weighted-F1 for B0-B4.
- `baseline_perclass_classification_reports.csv` — precision/recall/F1/support
  per class, Humanitarian & Damage Severity tasks, all 5 baselines.
- `uncertainty_comparison_B1_B4.csv` — mean/std uncertainty, AUROC/AUPRC vs.
  error, ECE, Brier score. **B0 excluded** — it has no uncertainty head by
  design (not a missing value; B0 is architecturally EDL-free).
- `baseline_b1_qualitative_examples.csv` — the 3 real test-set qualitative
  examples (correct / difficult / incorrect) with text, image path, ground
  truth, prediction, confidence, and text uncertainty.
- `baseline_B0_B4_training_epoch_log.csv` — per-epoch train/dev loss and F1,
  parsed from the real training console log, all 5 baselines.
- `baseline_B0_B4_console_log.txt` — the full raw training console log
  (verbatim), source for the CSV above.

## From `02_Proposed_Reliability_Aware_Multimodal_Model.ipynb`
- `evaluation_metrics_full.csv` — Accuracy, Precision/Recall (macro & wtd),
  F1 (macro & wtd), Cohen's Kappa, MCC, ROC-AUC, PR-AUC, all 5 tasks
  (Section 16.1, notebook's own `evaluation_metrics_full.csv` export).
- `proposed_model_humanitarian_classification_report.csv` — per-class
  precision/recall/F1/support for the Humanitarian head (Section 24.1 demo).
- `ablation_results_structural.csv` — structural ablation (Full / w/o E-REM /
  w/o UASG / w/o UG-CMA / Text Only / Image Only), per-task weighted-F1.
- `ablation_results_posthoc_technique.csv` — post-hoc technique ablation
  (calibration / TTA / text-cleaning / hierarchical gating variants).
- `gradcam_faithfulness_metrics.csv` — Average Drop %, Average Increase %,
  Deletion AUC, Insertion AUC (Humanitarian head, N=100 test samples).
- `gradcam_method_comparison.csv` — Average Drop % for gradcam / gradcam++ /
  eigencam.
- `mean_reliability_score_calibrated.csv` — fitted per-modality temperatures
  and raw vs. temperature-calibrated Mean Reliability Score with 95% CI
  (Section 18.1).
- `statistical_significance_paired_bootstrap.csv` — paired-bootstrap ΔF1,
  95% CI, and p-value per ablated component, Humanitarian & Damage tasks
  (Section 23).
- `proposed_model_training_epoch_log.csv` — per-epoch train/val loss, 4-task
  avg F1, and per-task val F1 (event/info/human/damage), parsed from the
  real 41-epoch training console log.
- `proposed_model_console_log.txt` — the full raw training console log
  (verbatim), source for the CSV above.

## Explicitly not extracted (checked, not available)

- Per-class classification reports for Event Type, Informativeness, and
  Damage Severity (proposed model) — only the Humanitarian head's report was
  printed as text in the executed notebook (Section 24.1 demo cell); the
  other three heads' `classification_report` calls were not found printed
  anywhere in the executed outputs.
- Raw per-sample prediction/probability arrays (`all_preds`, `all_probs`,
  `all_trues`) — these live only as in-memory Python objects / `.npz`/`.pkl`
  exports on the original Kaggle session disk (see notebook Section 25.1);
  they are not embedded in the notebook JSON itself and so cannot be
  recovered from the `.ipynb` files alone.
- Baseline (B0-B4) per-class reports for Event Type, Informativeness, and
  Verification — Section 8.1 of `01_Baseline_Experiments_B0-B4.ipynb` only
  produced `classification_report` text for Humanitarian and Damage.
