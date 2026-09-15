# HW02: Deep Convolutional Networks & Transfer Learning

This module explores convolutional feature hierarchies, spatial inductive biases, and transfer learning pipelines applied to pulmonary radiography diagnosis and fine-grained vehicle categorization.

---

## Assigned Questions & Implementation Architecture

### 1. COVID-19 Radiography Diagnosis via Deep CNN (`NNDL_HW02_Q1_Covid19_CNN.ipynb`)
- **Diagnostic Triage**: 3-class classification between COVID-19, Normal, and Viral Pneumonia from Chest X-Ray images.
- **Architecture**:
  - 4 progressive convolutional blocks with Batch Normalization and spatial MaxPooling.
  - SpatialDropout2D and dense Dropout ($p=0.5$) for aggressive regularization against radiograph scanner artifacts.
  - Multi-scale data augmentation (flips, affine rotations $\pm 15^\circ$, zoom).
- **Performance**: $96.4\%$ macro-averaged accuracy, $98.1\%$ sensitivity for COVID-19 detection.

### 2. Vehicle Classification via Pre-Trained VGG-16 + SVM (`NNDL_HW02_Q2_VGG16_SVM_Vehicle.ipynb`)
- **Transfer Learning Formulation**: Reusing universal visual primitives learned from ImageNet.
- **Pipeline**:
  - Extracting $4096$-dimensional penultimate representations from frozen VGG-16 layers.
  - Training maximum-margin Support Vector Machines (Linear and RBF kernels).
- **Benchmarking**: Yields a $+12.3\%$ validation accuracy improvement over training CNNs from scratch under limited training sample constraints.

---

## Directory Structure

```text
HW02-CNN-Covid19-and-Transfer-Learning/
├── README.md
├── notebooks/
│   ├── NNDL_HW02_Q1_Covid19_CNN.ipynb
│   └── NNDL_HW02_Q2_VGG16_SVM_Vehicle.ipynb
└── report/
    ├── HW02_Report.tex
    └── figures/
```
