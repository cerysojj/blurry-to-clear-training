# blurry-to-clear-training

We train CNNs with a blurry-to-clear curriculum, inspired by early human visual development, and examine how domain (faces vs. objects) and classification level (instance vs. category) impact blur robustness and receptive field properties.

This repository accompanies our paper submitted to ICDL 2025, currently under review:

**_“Learning from Faces and Favourite Toys: Effects of Domain and Classification Level on Robustness”_**  
*(Jenkins, Sanyal, Michelson & Kunda, 2025 — under submission)*

---

## Overview

We evaluate the effect of blurry-to-clear training on five datasets:
- **Faces**
- **Toybox (Instance-level)**
- **Toybox (Category-level)**
- **ImageNet-12**
- **ImageNet-100**

For each dataset, we train three models:
1. **Clear-only**
2. **Blurry-only (σ = 8)**
3. **Blurry-to-clear curriculum** (σ = 8 → 0 across 100 epochs)

---

## How to Run

All training and evaluation is handled via Jupyter notebooks, organized into two folders: `models/` for training and `figures/` for generating results. All notebooks are designed to run in Google Colab with A100 GPUs.

### Model Training

`notebooks/models/` corresponds to a dataset and trains all three model variants. Example:
- `faces_training.ipynb` — trains clear-only, blurry-only, and blurry-to-clear models on FaceScrub

### Recreate Paper Figures

`notebooks/figures/` generates figures for:
- Test accuracy results
- Test accuracy across training stages
- Receptive field size analyses
- Spatial frequency analysis

---

## Datasets

Toybox: https://aivaslab.github.io/toybox/

FaceScrub: https://exposing.ai/face_scrub/

ImageNet-12: Category matched to Toybox, curated from ImageNet and MS-COCO

ImageNet-100: https://www.kaggle.com/datasets/ambityga/imagenet100

Details and preprocessing steps are handled in `src/datasets.py`.

---

## Results Summary

- We disentangle the effects of **domain (faces vs. objects)** and **classification level (instance vs. category)** using 5 datasets.
- **Instance-level training** with blurry-to-clear progression yields better robustness to blur than category-level training.
- **Face-trained models** show the highest robustness, suggesting domain-specific specialization.
- **Blurry-to-clear training** increases spatial integration, as seen in receptive field size growth.

---

For questions, feel free to reach out: c.o.j.jenkins@sms.ed.ac.uk
