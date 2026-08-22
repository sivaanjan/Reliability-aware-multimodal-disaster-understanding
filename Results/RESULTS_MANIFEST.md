# Results Manifest

Every file in `Results/figures/` and `Results/metrics/` traced back to its
source notebook and cell. "Cell index" refers to the 0-indexed cell position
in the notebook's raw `.ipynb` JSON (`nb['cells'][i]`), which you can locate
by opening the notebook and counting cells from the top, or via
`jupyter nbconvert --to script` cell markers.

## Figures

| File | Type | Source Notebook | Cell index | Description |
|---|---|---|---|---|
| `eda_event_type_distribution.png` | Figure | Baseline (01) | 18 | Event Type class distribution, Train/Dev/Test |
| `eda_informativeness_distribution.png` | Figure | Baseline (01) | 18 | Informativeness class distribution, Train/Dev/Test |
| `eda_humanitarian_distribution.png` | Figure | Baseline (01) | 18 | Humanitarian category distribution, Train/Dev/Test |
| `eda_damage_severity_distribution.png` | Figure | Baseline (01) | 18 | Damage Severity distribution, Train/Dev/Test |
| `baseline_b1_uncertainty_by_correctness.png` | Figure | Baseline (01) | 69 | B1 Vanilla EDL: text/image uncertainty boxplots by prediction correctness |
| `baseline_b1_reliability_diagram.png` | Figure | Baseline (01) | 69 | B1 Vanilla EDL: reliability diagram, Humanitarian task |
| `eda_class_distribution.png` | Figure | Proposed (02) | 14 | Multi-task class distribution (Event/Info/Humanitarian/Damage), Train split |
| `eda_random_training_samples.png` | Figure | Proposed (02) | 18 | Random grid of tweet text + image training samples (Section 3) |
| `eda_50_original_images.png` | Figure | Proposed (02) | 27 | 50 original raw images spot-check (Section 3.1) |
| `preprocessed_sample_train.png` | Figure | Proposed (02) | 47 | Preprocessed image sample grid — Train split (Section 3.5) |
| `preprocessed_sample_dev.png` | Figure | Proposed (02) | 47 | Preprocessed image sample grid — Dev split (Section 3.5) |
| `preprocessed_sample_test.png` | Figure | Proposed (02) | 47 | Preprocessed image sample grid — Test split (Section 3.5) |
| `training_curves.png` | Figure | Proposed (02) | 77 | Multi-task loss curve + multi-task avg weighted-F1 curve (Section 15) |
| `evaluation_metrics_summary.png` | Figure | Proposed (02) | 83 | Comprehensive per-task Accuracy/Precision/Recall/F1 bar chart (Section 16.1) |
| `confusion_matrices.png` | Figure | Proposed (02) | 88 | Normalized confusion matrices — Event/Info/Humanitarian/Damage (Section 17) |
| `reliability_analysis.png` | Figure | Proposed (02) | 90 | Reliability distribution, correlation, confidence-by-class, correctness split (Section 18) |
| `gradcam_case_studies.png` | Figure | Proposed (02) | 97 | Grad-CAM heatmap comparison, correct vs. incorrect Humanitarian predictions (Section 19.1) |
| `gradcam_faithfulness_curves.png` | Figure | Proposed (02) | 99 | Grad-CAM deletion/insertion faithfulness curves (Section 19.2) |
| `tsne_embeddings.png` | Figure | Proposed (02) | 102 | t-SNE of shared `H_disaster` representation, colored by Event Type & Damage Severity (Section 20) |
| `ablation_study.png` | Figure | Proposed (02) | 109 | Structural ablation study bar chart — Humanitarian/Damage/4-task avg (Section 21) |
| `erem_uncertainty_spread.png` | Figure | Proposed (02) | 111 | E-REM `u_t`/`u_v` uncertainty spread histograms, diagnostic (Section 21.4) |
| `performance_dashboard.png` | Figure | Proposed (02) | 114 | Combined performance/confidence/reliability/ablation dashboard (Section 22) |
| `gradcam_01.png` – `gradcam_25.png` | Figure | Proposed (02) | 119 | 25 individual single-sample Grad-CAM explanations, "Sample N/25" (Section 19 single-inference demo, cell also covers Section 24) |

## Metrics

| File | Type | Source Notebook | Cell index | Description |
|---|---|---|---|---|
| `baseline_B0_B4_comparison.csv` | Metrics | Baseline (01) | 55 | Per-task + average weighted-F1, B0-B4 (verbatim from notebook's own results table) |
| `baseline_perclass_classification_reports.csv` | Metrics | Baseline (01) | 61 | Precision/recall/F1/support per class — Humanitarian & Damage, all 5 baselines (parsed from printed `classification_report`) |
| `uncertainty_comparison_B1_B4.csv` | Metrics | Baseline (01) | 66 | Mean/std uncertainty, AUROC/AUPRC vs. error, ECE, Brier — B1-B4 (B0 has no uncertainty head) |
| `baseline_b1_qualitative_examples.csv` | Metrics | Baseline (01) | 72 | 3 real test-set qualitative examples with text/image/gt/pred/confidence/uncertainty |
| `baseline_B0_B4_training_epoch_log.csv` | Metrics | Baseline (01) | 48 | Per-epoch train_loss/dev_loss/dev_avg_F1/dev_target_F1, all 5 baselines, parsed from real console log |
| `baseline_B0_B4_console_log.txt` | Metrics (raw log) | Baseline (01) | 48 | Full raw training console log, verbatim |
| `evaluation_metrics_full.csv` | Metrics | Proposed (02) | 83 | Accuracy/Precision/Recall(macro+wtd)/F1(macro+wtd)/Kappa/MCC/ROC-AUC/PR-AUC, all 5 tasks (notebook's own `evaluation_metrics_full.csv` export, reproduced from printed table) |
| `proposed_model_humanitarian_classification_report.csv` | Metrics | Proposed (02) | 121 | Per-class precision/recall/F1/support, Humanitarian head (Section 24.1 demo cell) |
| `ablation_results_structural.csv` | Metrics | Proposed (02) | 109 | Structural ablation table (A): Full / w/o E-REM / w/o UASG / w/o UG-CMA / Text Only / Image Only |
| `ablation_results_posthoc_technique.csv` | Metrics | Proposed (02) | 109 | Post-hoc technique ablation table (B): calibration / TTA / text-cleaning / gating variants |
| `gradcam_faithfulness_metrics.csv` | Metrics | Proposed (02) | 99 | Average Drop %, Average Increase %, Deletion AUC, Insertion AUC (N=100, Humanitarian head) |
| `gradcam_method_comparison.csv` | Metrics | Proposed (02) | 99 | Average Drop % per Grad-CAM method: gradcam / gradcam++ / eigencam |
| `mean_reliability_score_calibrated.csv` | Metrics | Proposed (02) | 92 | Fitted temperatures + raw vs. calibrated Mean Reliability Score with 95% CI (Section 18.1) |
| `statistical_significance_paired_bootstrap.csv` | Metrics | Proposed (02) | 117 | Paired-bootstrap ΔF1, 95% CI, p-value per ablated component (Section 23) |
| `proposed_model_training_epoch_log.csv` | Metrics | Proposed (02) | 72 | Per-epoch train/val loss, 4-task avg F1, per-task val F1, parsed from real 41-epoch console log |
| `proposed_model_console_log.txt` | Metrics (raw log) | Proposed (02) | 72 | Full raw training console log, verbatim |

## Not extracted / not present (documented limitations)

| Item | Reason |
|---|---|
| `Docs/Architecture.png` | No architecture-diagram image exists in either notebook; only ASCII-art text (see `Docs/README.md`). |
| B0-B4 "Figure 1"–"Figure 5" (training-loss/F1 comparison charts) | Cells 50-52, 56-58 of `01_Baseline_Experiments_B0-B4.ipynb` only `print()` a caption string; no image was rendered/saved. Underlying real values were extracted to `baseline_B0_B4_training_epoch_log.csv` instead. |
| Per-baseline confusion matrices (B0, B2-B4) | `plot_confusion(...)` calls in cell 63 are commented out; only a placeholder message was printed. |
| Per-baseline uncertainty/reliability plots (B0, B2-B4) | Only B1's `test_eval` uncertainty arrays were populated in the executed run (cell 69); B0 has no uncertainty head, B2-B4's arrays were not captured in this run. |
| Baseline per-class reports for Event Type, Informativeness, Verification | Cell 61 only computed `classification_report` for Humanitarian and Damage. |
| Proposed-model per-class reports for Event Type, Informativeness, Damage Severity | Only the Humanitarian head's report was printed as text (cell 121); the others were not found printed in any executed cell output. |
| Raw per-sample prediction/probability arrays (`.npz`/`.pkl`) | Referenced by notebook Section 25.1 (cell 125) as saved to the original Kaggle session's local disk (`results/predictions/...`); not embedded in the `.ipynb` JSON itself and therefore not recoverable from the notebook files alone. |
| Model checkpoints (`.pt`) | Deliberately excluded per project scope (not research results). |

## Summary counts

- **Figures extracted:** 47 (6 from Baseline notebook, 41 from Proposed-model notebook, of which 25 are individual Grad-CAM samples)
- **Metric files extracted:** 16 (14 CSV + 2 raw console-log `.txt`)
- **Source notebooks:** 2 (`01_Baseline_Experiments_B0-B4.ipynb`, `02_Proposed_Reliability_Aware_Multimodal_Model.ipynb`)
