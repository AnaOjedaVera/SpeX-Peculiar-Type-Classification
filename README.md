# SpeX Peculiar-Type Classification

This repository contains the data products, analysis code, model outputs, and reproducibility materials associated with the automated classification of M0--T9 low-mass stars and brown dwarfs using SpeX prism spectra.

The study evaluates Random Forest, Support Vector Machine, K-Nearest Neighbors, and one-dimensional Convolutional Neural Network classifiers for the simultaneous prediction of spectral type and peculiar type. Model selection prioritizes dwarf-type balanced accuracy across the field, beta, gamma, d/sd, sd, and esd categories.

The repository includes:

- processed 90-feature data tables;
- training, validation, and independent test-set identifiers;
- hyperparameter-search results and selected configurations;
- RF, SVM, KNN, and CNN training and evaluation code;
- model predictions and performance metrics;
- peculiar-type and spectral-type confusion matrices;
- RF feature-importance results; and
- scripts used to generate the figures reported in the manuscript.
