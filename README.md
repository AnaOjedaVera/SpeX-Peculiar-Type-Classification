# SpeX Peculiar-Type Classification

Machine-learning framework for the simultaneous classification of **spectral type** and **peculiar class** in low-mass stars and brown dwarfs using low-resolution near-infrared SpeX spectra.

This repository accompanies the manuscript:

> **A comparative machine learning framework for stellar subdwarf classification using spectral metrics and feature engineering**

**Ana V. Ojeda, Christopher A. Theissen, C. A. Guerrero, Juan J. Tapia, and T. Zhou**

Presented as a poster at **SPIE Optics + Photonics 2026**, San Diego, California.

---

## Overview

This work extends previous machine-learning approaches for the automated classification of M0–T9 dwarfs observed with the SpeX prism spectrograph.

Two classification tasks are considered:

- **Spectral type:** M0–T9
- **Peculiar class:** field, β, γ, d/sd, sd, and esd

The proposed representation combines spectral, photometric, and physically motivated engineered features to improve the identification of gravity- and metallicity-sensitive peculiar classes.

Four supervised-learning models are evaluated:

- Random Forest (RF)
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- Convolutional Neural Network (CNN)

Model selection prioritizes **peculiar-class balanced accuracy (BAcc)** to account for class imbalance.

---

## Input Features

Each spectrum is represented by a **90-dimensional feature vector** containing:

- 67 normalized spectral-flux bins
- 16 targeted spectral slopes
- Apparent $J$- and $H$-band magnitudes
- 5 field-referenced residual features:
  - $A_i$
  - $Y_i$
  - $H_i$
  - $K_i$
  - $D_i$

The field-referenced features quantify deviations from the field spectral standard of the same spectral type.

---

## Dataset

The analysis uses low-resolution near-infrared spectra obtained with the **SpeX spectrograph** at the NASA Infrared Telescope Facility (IRTF).

The final datasets contain:

| Dataset | Samples | Description |
|---|---:|---|
| Training | 66,000 | Synthetic spectra generated from spectral standards |
| Validation | 396 | Observed and synthetic spectra used for model selection |
| Test | 1,300 | Independent observed spectra |

The independent test set is not used during training or hyperparameter selection.

---

## Main Results

Among the evaluated classifiers, **KNN achieved the strongest overall performance** on the independent test set:

| Metric | KNN |
|---|---:|
| Peculiar-class BAcc | **89.84%** |
| Peculiar-class accuracy | **88.08%** |
| Spectral type within ±1 | **96.85%** |
| Spectral type within ±3 | **99.54%** |

Random Forest additionally provides feature-importance estimates, identifying the field-referenced features $D_i$ and $A_i$, the apparent $J$- and $H$-band magnitudes, selected near-infrared slopes, and spectral bins near 0.89–0.99 μm among the most informative variables for peculiar-class classification.

---

## Repository Structure

```text
SpeX-Peculiar-Type-Classification/
│
├── Figures/
│   └── Figures used in and generated for the manuscript
│
├── data and models/
│   ├── Classification_Models.ipynb
│   ├── classes_meta.csv
│   ├── test.csv
│   ├── testval_meta.csv
│   ├── train_meta.csv
│   └── val.csv
│
├── SPIE_Manuscript.pdf
├── SPIE_Poster_36x42in.pdf
└── README.md
