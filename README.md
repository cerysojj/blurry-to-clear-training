# Learning from Faces and Favourite Toys: Effects of Domain and Classification Level on Robustness

This repository contains code for our paper (submitted to ICDL 2025):

**_“Learning from Faces and Favourite Toys: Effects of Domain and Classification Level on Robustness”_**  
*Jenkins, Sanyal, Michelson & Kunda (2025 — under submission)*

---

## Overview

Inspired by infant visual development, this project explores how early exposure to blur and instance-level learning affect robustness to blur in convolutional neural networks (CNNs).  
We evaluate a **blurry-to-clear training curriculum** across five datasets that vary in domain and classification level:

- **Faces**
- **Toybox (Instance-level)**
- **Toybox (Category-level)**
- **ImageNet-12**
- **ImageNet-100**

Each dataset is used to train three models:
1. **Clear-only**
2. **Blurry-only** (σ = 8)
3. **Blurry-to-clear** (σ = 8 → 0 over 100 epochs)

---

## Repository Structure

- `notebooks/models/`: Jupyter notebooks for training models on each dataset.
- `notebooks/figures/`: Notebooks to generate results and paper figures.
- `src/`: Core scripts for dataset loading, model definitions, and utility functions.

All notebooks are designed to run in **Google Colab** with **A100 GPUs**. No installation required.

---

## How to Use

To train models or recreate figures:
1. Open any notebook in `notebooks/models/` (e.g. `faces_training.ipynb`)
2. Run cells in order — all required code is included.
3. To generate results/plots, use the matching notebook in `notebooks/figures/`.

---

## Datasets

- **Toybox**: https://aivaslab.github.io/toybox/  
- **FaceScrub**: https://exposing.ai/face_scrub/  
- **ImageNet-12**: Curated from ImageNet and MS-COCO  
- **ImageNet-100**: https://www.kaggle.com/datasets/ambityga/imagenet100

Preprocessing is handled in `src/datasets.py`.

---

## Key Findings

- We replicate and extend the findings of Jang & Tong (2021), using five datasets to disentangle the effects of **domain (faces vs. objects)** and **classification level (instance vs. category)** on blur robustness under a blurry-to-clear training curriculum.
- **Instance-level training**, combined with a **blurry-to-clear curriculum**, substantially improves CNN **robustness to blur** compared to category-level training.
- **Face-trained models** achieve the highest robustness overall, suggesting combined effects from domain-specific face training and general instance-level training.
- **Receptive field analyses** reveal that blurry-to-clear training promotes broader spatial integration, especially in face and instance-level models — a potential mechanism for enhanced blur robustness.

---

If you have any question feel free to send me an email at c.o.j.jenkins@sms.ed.ac.uk.
