# QuFeX - Quantum Feature Extractor with Y-Net for Brain Tumor Classification

A hybrid quantum-classical deep learning framework that integrates a **Quantum Feature Extractor (QuFeX)** into a **Y-Net autoencoder** architecture for multi-class brain tumor classification from MRI scans.

---

## Overview

This project explores the use of parameterized quantum circuits as a bottleneck feature extractor inside a U-Net-style encoder-decoder network. The quantum layer replaces the classical bottleneck, processing spatial image patches through amplitude embedding and entangling gates, then feeding the resulting quantum measurements into a classical classifier head.

Two architectural configurations are evaluated:

| Mode | Architecture | Loss |
|------|-------------|------|
| `classifier` | U-Net Encoder + QuFeX + Classifier Head | Cross Entropy only |
| `full` | U-Net Encoder + QuFeX + Classifier Head + U-Net Decoder | Cross Entropy + MSE (α=1) |

---

## Dataset

The model is trained and evaluated on the [Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset), which contains four classes:

- Glioma
- Meningioma
- Pituitary Tumor
- No Tumor

Images are converted to grayscale and resized to **64 × 64** pixels.

**Expected folder structure on Google Drive:**
```
brain-tumor-data/
├── Training/
│   ├── glioma/
│   ├── meningioma/
│   ├── pituitary/
│   └── notumor/
└── Testing/
    ├── glioma/
    ├── meningioma/
    ├── pituitary/
    └── notumor/
```

---
