# Robust CIFAR-10 Image Classification

Investigating generalization and robustness in image classification using a lightweight, Inception-inspired Convolutional Neural Network (CNN).

## Overview

This project explores how architectural design, data augmentation, and regularization affect the performance of image classification models under limited training data and distribution shifts.

A compact CNN inspired by the Inception architecture is trained on CIFAR-10. Multiple training configurations are evaluated to understand their impact on classification accuracy, generalization, and robustness to image corruptions.

## Objectives

- Develop a lightweight CNN for multi-class image classification.
- Investigate generalization when training data is limited.
- Evaluate geometric and photometric data augmentation strategies.
- Study regularization techniques and their effects on model performance.
- Analyze robustness under distribution shifts using controlled experiments.
- Compare training configurations through systematic ablation studies.

## Dataset

**CIFAR-10** is a benchmark image classification dataset containing 60,000 color images of size 32 × 32 pixels across 10 classes.

The classes are:

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

The experimental workflow uses a limited, balanced subset of the training data, divided into training and validation sets. The clean test set is reserved for final evaluation.

Distribution-shift experiments use synthetically transformed images to investigate robustness to changes in image appearance.

> **Note:** Synthetic distribution shifts are experimental proxies and should not be interpreted as results from an official corrupted or shifted test benchmark.

## Model Architecture

The project uses a lightweight, Inception-inspired CNN designed for image classification under a constrained parameter budget.

The architecture explores parallel convolutional feature extraction at different receptive-field sizes, followed by feature aggregation and classification.

Key design considerations include:

- Compact model capacity
- Multi-scale feature extraction
- Computational efficiency
- Generalization under limited training data

## Experimental Methodology

Experiments investigate the effects of different training strategies:

| Configuration | Purpose |
|---|---|
| Baseline | Establish performance without data augmentation |
| Geometric augmentation | Evaluate transformations such as rotations and flips |
| Photometric augmentation | Study brightness, contrast, and related appearance changes |
| Combined augmentation | Evaluate geometric and photometric transformations together |
| Cutout / Random Erasing | Investigate robustness to partial occlusion |
| Mixup / CutMix and label smoothing | Explore additional regularization strategies |
| Final configuration | Evaluate the selected combination of techniques |

Each configuration is compared using consistent evaluation procedures. Where applicable, experiments are repeated across multiple random seeds to measure variability.

## Evaluation Metrics

The experiments consider:

- Training and validation accuracy
- Training and validation loss
- Clean test accuracy
- Accuracy under synthetic distribution shifts
- Per-class classification accuracy
- Normalized confusion matrix
- Misclassified image analysis

Results should be interpreted alongside the experimental configuration and evaluation protocol.

## Repository Structure

```text
robust-cifar10-classification/
├── README.md
├── requirements.txt
├── notebooks/
│   └── cifar10_robust_classification.ipynb
└── results/
    └── figures/
```

*The structure above is a suggested organization; adjust it to match the files actually present in the repository.*

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/robust-cifar10-classification.git
cd robust-cifar10-classification
```

### 2. Install dependencies

Create a Python environment and install the required packages:

```bash
pip install -r requirements.txt
```

The exact dependencies should match those imported by the notebook.

### 3. Run the experiments

Open the notebook in Jupyter or Google Colab and execute the cells in order.

For GPU-based execution, select a compatible GPU runtime where available. The notebook should record the random seeds, configuration, and evaluation metrics required to reproduce the experiments.

## Results

Results are reported for the baseline and subsequent experimental configurations.

The final report should include clean test accuracy, shifted-proxy accuracy, variability across random seeds, and the configuration selected for the final model.

**Results summary:** Add the verified experimental results here after running the complete notebook.

## Limitations

- Training uses a limited subset of the available training data.
- Synthetic distribution shifts do not represent every real-world domain shift.
- Results depend on the selected architecture, hyperparameters, random seeds, and training environment.
- Reproducibility requires consistent data splits, preprocessing, and evaluation procedures.

## Future Improvements

- Evaluate on established image-corruption benchmarks.
- Investigate calibration and confidence under distribution shifts.
- Explore alternative compact CNN architectures.
- Compare augmentation strategies across additional datasets.
- Analyze the trade-off between clean accuracy and robustness.

## License

A license has not yet been specified. Add an appropriate license before redistributing or reusing this repository's code.
