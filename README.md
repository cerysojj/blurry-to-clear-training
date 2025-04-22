# Learning from Faces and Favourite Toys: Effects of Domain and Classification Level on Robustness

This repository contains code for our paper (submitted to ICDL 2025):

**_“Learning from Faces and Favourite Toys: Effects of Domain and Classification Level on Robustness”_**  
*Jenkins, Sanyal, Michelson & Kunda (2025 — under submission)*

---

## Overview

Inspired by infant visual development, this project explores how early exposure to blur and instance-level learning affect robustness to blur in convolutional neural networks (CNNs).  
We evaluate a **blurry-to-clear training curriculum** across five datasets that vary in domain and classification level:

- **Faces** (instance-level)
- **Toybox (Instance-level)**
- **Toybox (Category-level)**
- **ImageNet-12** (category-level)
- **ImageNet-100** (category-level)

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

- **Blurry-to-clear training improves robustness to blur**, especially for **faces** and **object instances**.
- **Instance-level learning** is more effective than category-level learning for developing blur-invariant representations.
- **Face-trained models** show the strongest robustness, suggesting a mix of instance-level and domain-specific effects.
- **Receptive field analysis** shows increased spatial integration under blurry-to-clear training, especially in instance-level tasks.

---

For questions or collaboration, feel free to get in touch:  
c.o.j.jenkins@sms.ed.ac.uk
