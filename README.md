# Reliability-Aware Multimodal Disaster Understanding

<p align="center">
  <b>Reliability-Aware Multimodal Disaster Understanding Through Evidential Reliability Estimation and Uncertainty-Aware Cross-Modal Attention</b>
</p>

<p align="center">
  A multimodal deep learning framework for disaster-related social media understanding using textual and visual information.
</p>

---

## Overview

Social media provides valuable information during natural disasters through
user-generated text and images. However, such content can be noisy,
incomplete, ambiguous, or unreliable.

This project develops a reliability-aware multimodal framework that jointly
processes textual and visual information while estimating the reliability of
each modality.

The framework integrates:

- DeBERTa-v3 for text representation
- CLIP ViT-B/32 for image representation
- Quality-based reliability features
- Evidential Reliability Estimation Model (E-REM)
- Uncertainty-Aware Semantic Gating (UASG)
- InfoNCE-based cross-modal alignment
- Uncertainty Gating–Cross-Modal Attention (UG-CMA)
- Multi-task prediction
- Grad-CAM-based visual explanation

---

## Proposed Architecture

<p align="center">
  <img src="Docs/Architecture.png" width="1000">
</p>

<p align="center">
  <b>Figure 1.</b> Overview of the proposed reliability-aware multimodal disaster understanding framework.
</p>

---

## Methodology

### Text and Image Encoding

Textual information is encoded using **DeBERTa-v3**, while visual
information is encoded using **CLIP ViT-B/32**.

### Reliability Estimation

Quality features from the text and image modalities are combined with their
learned representations and processed using the **Evidential Reliability
Estimation Model (E-REM)** to estimate modality-specific reliability and
uncertainty.

### Uncertainty-Aware Semantic Gating

The estimated reliability values are used by **Uncertainty-Aware Semantic
Gating (UASG)** to regulate the contribution of each modality.

### Contrastive Alignment

**InfoNCE** is used to improve semantic alignment between corresponding
textual and visual representations.

### Cross-Modal Attention

The gated representations are processed using **Uncertainty
Gating–Cross-Modal Attention (UG-CMA)** to enable interaction between the
textual and visual modalities while considering their reliability.

### Multi-Task Learning

The shared multimodal representation is used for multiple prediction tasks:

- Event Type
- Informativeness
- Humanitarian Category
- Damage Severity
- Disaster Verification
- Uncertainty Estimation

### Explainability

**Grad-CAM** is used to generate visual explanations and highlight image
regions contributing to model predictions.

---

## Baseline Experiments

The baseline notebook evaluates the following configurations:

| Experiment | Description |
|---|---|
| **B0** | Conventional Fusion |
| **B1** | Vanilla EDL |
| **B2** | EDL + UASG |
| **B3** | E-REM + UASG |
| **B4** | E-REM + Conventional Attention |

These experiments are used to study the contribution of the reliability and
attention components.

---

## Notebooks

### Baseline Experiments

[`01_Baseline_Experiments_B0-B4.ipynb`](Notebooks/01_Baseline_Experiments_B0-B4.ipynb)

Contains the baseline experiments B0-B4 and their evaluation.

### Proposed Model

[`02_Proposed_Reliability_Aware_Multimodal_Model.ipynb`](Notebooks/02_Proposed_Reliability_Aware_Multimodal_Model.ipynb)

Contains the proposed reliability-aware multimodal framework, including
E-REM, UASG, InfoNCE, UG-CMA, multi-task learning, and Grad-CAM.

---

## Results

### Figures

The generated experimental figures are available in:

[`Results/figures/`](Results/figures/)

These include training and evaluation plots, confusion matrices, ablation
visualizations, uncertainty/reliability visualizations, embedding
visualizations, and Grad-CAM outputs.

### Metrics

Numerical experimental results are available in:

[`Results/metrics/`](Results/metrics/)

---

## Dataset

The project uses multimodal disaster-related social media data containing
textual and visual information.

The dataset is **not included in this repository**. Users should obtain the
dataset from its original source and follow its applicable terms of use.

Dataset paths should be configured in the notebooks before execution.

---

## Requirements

The main dependencies include:

```text
numpy
pandas
scipy
matplotlib
seaborn
Pillow
opencv-python
scikit-learn
tqdm
torch
torchvision
transformers
open_clip_torch
jupyter
ipykernel
```

The complete dependency list is provided in `requirements.txt`.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/sivaanjan/Reliability-aware-multimodal-disaster-understanding.git
cd Reliability-aware-multimodal-disaster-understanding
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter:

```bash
jupyter notebook
```

---

## Repository Structure

```text
reliability-aware-multimodal-disaster-understanding/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── Notebooks/
│   ├── 01_Baseline_Experiments_B0-B4.ipynb
│   └── 02_Proposed_Reliability_Aware_Multimodal_Model.ipynb
│
├── Docs/
│   └── Architecture.png
│
├── Results/
│   ├── figures/
│   └── metrics/
│
└── src/
```

---

## Author

**Siva Anjan Kumar Thota**  
M.Tech Data Science  
SRM University-AP
