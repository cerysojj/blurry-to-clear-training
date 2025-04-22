# blurry-to-clear-training

**Curriculum-based CNN training to study blur robustness across faces vs. objects and instance vs. category classification.**  

This repository accompanies our paper submitted to ICDL 2025, currently under review:

**_“Learning from Faces and Favourite Toys: Effects of Domain and Classification Level on Robustness”_**  
*(Jenkins, Sanyal, Michelson & Kunda, 2025 — under submission)*

We train CNNs with a blurry-to-clear schedule, inspired by early human visual development, and examine how domain (faces vs. objects) and classification level (instance vs. category) impact blur robustness and receptive field properties.

---

## Overview

We evaluate the effect of blurry-to-clear training on five datasets:
- **Faces** (FaceScrub) – Instance-level
- **Toybox (Instance-level)** – Object individuation
- **Toybox (Category-level)** – Object categorisation
- **ImageNet-12** – Compact category-level benchmark
- **ImageNet-100** – Broader category-level dataset

For each dataset, we train three models:
1. **Clear-only**
2. **Blurry-only (σ = 8)**
3. **Blurry-to-clear curriculum** (σ = 8 → 0 across 100 epochs)

---

## How to Run

All training and evaluation is handled through Jupyter notebooks.

### Model Training

`notebooks/models/` corresponds to a dataset and trains all three model variants. Example:
- `faces_training.ipynb` — trains clear-only, blurry-only, and blurry-to-clear models on FaceScrub

### Recreate Paper Figures

`notebooks/figures/` generates:
- Accuracy vs. blur level plots
- Accuracy ratio comparisons
- Receptive field size analyses

Example:
- `fig4_accuracy_vs_blur.ipynb`
- `fig5_training_stage_accuracy.ipynb`

---

## Datasets

FaceScrub: https://github.com/happynear/facescrub

Toybox: https://github.com/maithilee/toybox

ImageNet-12: Subsets curated from ImageNet and MS-COCO

ImageNet-100: 

Details and preprocessing steps are handled in `src/datasets.py`.

---

## Results Summary
Key findings include:

- Instance-level training leads to better robustness under blur than category-level training
- Face-trained models are most robust, likely due to domain-specific processing
- Blurry-to-clear training promotes broader spatial integration (measured via receptive field size)

---

For questions, feel free to reach out: c.o.j.jenkins@sms.ed.ac.uk
