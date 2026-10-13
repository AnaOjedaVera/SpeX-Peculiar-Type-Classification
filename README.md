# SpeX Peculiar-Type Classification

[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-8A2BE2)
![SPIE 2026](https://img.shields.io/badge/SPIE-2026-0077B5)
[![DOI](https://img.shields.io/badge/DOI-10.1117%2F12.3116063-B31B1B)](https://doi.org/10.1117/12.3116063)

Machine-learning framework for the simultaneous classification of **spectral type** and **peculiar class** in low-mass stars and brown dwarfs using low-resolution near-infrared SpeX spectra.

This repository accompanies the manuscript:

> **A comparative machine learning framework for stellar subdwarf classification using spectral metrics and feature engineering**

**Ana V. Ojeda, Christopher A. Theissen, C. A. Guerrero, Juan J. Tapia, and T. Zhou**

Published in *Applications of Machine Learning 2026*, Proceedings of SPIE, Vol. 14218, Article 1421815 (2026).

**DOI:** https://doi.org/10.1117/12.3116063

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
```

---

## Contact

**Ana V. Ojeda Vera**  
Doctoral Student in Data Science  
CITEDI – Instituto Politécnico Nacional (IPN), Mexico  
Email: **anaojedavera@gmail.com**

[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:anaojedavera@gmail.com)
[![ORCID](https://img.shields.io/badge/ORCID-A6CE39?style=flat&logo=orcid&logoColor=white)](https://orcid.org/0009-0002-0748-9630)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-4285F4?style=flat&logo=googlescholar&logoColor=white)](https://scholar.google.com/citations?user=HO17QvAAAAAJ&hl=es)
[![ResearchGate](https://img.shields.io/badge/ResearchGate-00CCBB?style=flat&logo=researchgate&logoColor=white)](https://www.researchgate.net/profile/Ana-V-Ojeda)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anaojedavera/)
