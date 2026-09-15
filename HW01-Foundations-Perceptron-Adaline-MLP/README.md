# HW01: Foundations of Neural Networks

This module investigates the foundational mechanics of artificial neural networks, progressing from single-layer threshold units to continuous gradient optimization, deep Multi-Layer Perceptrons (MLPs), and self-supervised bottleneck representation learning.

---

## Assigned Questions & Implementation Architecture

### 1. Credit Card Fraud Detection with Deep MLP (`NNDL_HW01_Q1_Fraud_Detection.ipynb`)
- **Problem Formulation**: Extreme class imbalance on financial transaction data ($284,807$ instances, $492$ fraudulent cases $pprox 0.172\%$).
- **Methodology**: 
  - PCA-transformed feature normalization.
  - Weighted Binary Cross-Entropy loss with inverse class frequency weights.
  - Dynamic decision threshold calibration targeting maximum Precision-Recall AUC (PR-AUC).
- **Key Metrics**: Achieves test accuracy of $94.93\%$, precision of $100.0\%$, recall of $89.86\%$, and F1-score of $94.66\%$.

### 2. Concrete Compressive Strength Regression (`NNDL_HW01_Q2_Concrete_MLP.ipynb`)
- **Problem Formulation**: High-dimensional nonlinear regression modeling civil engineering concrete strength from constituent ingredients (cement, slag, ash, water, superplasticizer, coarse/fine aggregate, age).
- **Architecture**: 3-layer deep MLP ($8 	o 128 	o 64 	o 32 	o 1$) with ELU activations and $L_2$ weight regularization.
- **Results**: Achieves test MAE of $7.61\text{ MPa}$ and MSE of $91.46\text{ MPa}^2$ (RMSE $= 9.56\text{ MPa}$).

### 3. Adaptive Linear Neuron (Adaline) on IRIS (`NNDL_HW01_Q3_Adaline_Iris.ipynb`)
- **Theory**: Continuous quadratic objective minimization via the Widrow-Hoff Delta rule ($\Delta \mathbf{w} = \eta \sum_i (y_i - \mathbf{w}^T \mathbf{x}_i) \mathbf{x}_i$).
- **Comparison**: Contrasted directly against Rosenblatt's Perceptron to show smooth gradient descent convergence on overlapping feature distributions.

### 4. MNIST Autoencoder & Downstream Classification (`NNDL_HW01_Q4_MNIST_Autoencoder.ipynb`)
- **Self-Supervised Pretraining**: Symmetric bottleneck autoencoder compressing $784$-dim digit vectors into $64$-dim latent representations.
- **Encoder Freezing**: Freezing encoder weights and training a linear classification layer yields $81.50\%$ test accuracy ($75.97\%$ for 16-dim bottleneck), proving the expressive compactness of the learned latent manifold.

---

## Directory Structure

```text
HW01-Foundations-Perceptron-Adaline-MLP/
├── README.md
├── notebooks/
│   ├── NNDL_HW01_Q1_Fraud_Detection.ipynb
│   ├── NNDL_HW01_Q2_Concrete_MLP.ipynb
│   ├── NNDL_HW01_Q3_Adaline_Iris.ipynb
│   └── NNDL_HW01_Q4_MNIST_Autoencoder.ipynb
└── report/
    ├── HW01_Report.tex
    └── figures/
```
