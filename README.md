# Reliability-Aware Multimodal Disaster Understanding

### Reliability-Aware Multimodal Disaster Understanding Through Evidential Reliability Estimation and Uncertainty-Aware Cross-Modal Attention

<p align="center">
  <img src="Docs/Architecture.png" width="1000">
</p>

<p align="center">
  <i>Overview of the proposed reliability-aware multimodal disaster understanding framework.</i>
</p>

## Overview

This repository contains the implementation of a reliability-aware
multimodal disaster understanding framework for analyzing disaster-related
social media posts using textual and visual information.

The proposed architecture integrates DeBERTa-v3 for text representation,
CLIP ViT-B/32 for visual representation, Evidential Reliability Estimation
Model (E-REM), Uncertainty-Aware Semantic Gating (UASG), InfoNCE-based
alignment, Uncertainty Gating–Cross-Modal Attention (UG-CMA), multi-task
prediction heads, and Grad-CAM-based visual explanation.

## Proposed Architecture

The framework consists of:

1. DeBERTa-v3 text encoder
2. CLIP ViT-B/32 image encoder
3. Quality feature extraction
4. Evidential Reliability Estimation Model (E-REM)
5. Uncertainty-Aware Semantic Gating (UASG)
6. InfoNCE contrastive alignment
7. Uncertainty Gating–Cross-Modal Attention (UG-CMA)
8. Shared multimodal representation
9. Multi-task prediction heads
10. Grad-CAM explainability

## Repository Structure

```text
reliability-aware-multimodal-disaster-understanding/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   ├── 01_Baseline_Disaster_Classification.ipynb
│   └── 02_Reliability_Aware_Multimodal_Disaster_Understanding.ipynb
│
├── docs/
│   └── architecture.png
│
├── results/
│   ├── figures/
│   └── metrics/
│
└── src/