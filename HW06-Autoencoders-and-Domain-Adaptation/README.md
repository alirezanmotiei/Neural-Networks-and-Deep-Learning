# HW06: Unsupervised Representation Learning & Domain Adaptation

This module investigates unsupervised representation learning across two critical paradigms: Domain-Adversarial Neural Networks (DANN) for cross-domain transfer, and Variational Autoencoders (EndoVAE) for endoscopic colonoscopy polyp reconstruction.

---

## Assigned Questions & Implementation Architecture

### 1. Unsupervised Domain Adaptation via DANN (`NNDL_HW06_Q1_Domain_Adaptation.ipynb`)
- **Distribution Shift**: Transfer from clean grayscale MNIST digits (source) to colored, textured MNIST-M digits (target) with zero target labels.
- **Gradient Reversal Layer (GRL)**: Minimax optimization coupling a task label predictor and domain discriminator with inverted gradient flow ($- \lambda \mathbf{I}$).
- **Performance**: Boosts target domain classification accuracy from $54.2\%$ (source-only) to $82.6\%$.

### 2. EndoVAE: Endoscopic Polyp Reconstruction (`NNDL_HW06_Q2_EndoVAE_Polyp.ipynb`)
- **Probabilistic Formulation**: Variational inference maximizing the Evidence Lower Bound (ELBO) with KL divergence regularization and the reparameterization trick.
- **Medical Reconstruction**: Preserves fine mucosal surface geometry, achieving SSIM $= 0.871$ and MSE $= 0.012$.
- **Latent Manifold**: Smooth interpolations across polyp shapes and successful downstream lesion classification on the frozen $32$-dimensional latent bottleneck.

---

## Directory Structure

```text
HW06-Autoencoders-and-Domain-Adaptation/
├── README.md
├── notebooks/
│   ├── NNDL_HW06_Q1_Domain_Adaptation.ipynb
│   └── NNDL_HW06_Q2_EndoVAE_Polyp.ipynb
└── report/
    ├── HW06_Report.tex
    └── figures/
```
