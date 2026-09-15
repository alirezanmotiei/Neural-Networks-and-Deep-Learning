# HW06: Unsupervised Representation Learning & Domain Adaptation

This module investigates unsupervised representation learning across two critical paradigms: Domain-Adversarial Neural Networks (DANN) for cross-domain transfer, and Variational Autoencoders (EndoVAE) for endoscopic colonoscopy polyp reconstruction.

---

## Assigned Questions & Implementation Architecture

### 1. Unsupervised Domain Adaptation via DANN (`NNDL_HW06_Q1_Domain_Adaptation.ipynb`)
- **Distribution Shift**: Transfer from clean grayscale MNIST digits (source) to colored, textured MNIST-M digits (target) with zero target labels.
- **Gradient Reversal Layer (GRL)**: Minimax optimization coupling a task label predictor and domain discriminator with inverted gradient flow ($- \lambda \mathbf{I}$).
- **Performance**: Evaluates the domain gap: $98.98\%$ on clean source MNIST versus $56.63\%$ direct transfer on colored MNIST-M ($42.35\%$ drop).

### 2. EndoVAE: Endoscopic Polyp Reconstruction (`NNDL_HW06_Q2_EndoVAE_Polyp.ipynb`)
- **Probabilistic Formulation**: Variational inference maximizing the Evidence Lower Bound (ELBO) with KL divergence regularization and the reparameterization trick.
- **Medical Reconstruction**: Preserves fine mucosal surface geometry, achieving Mean PSNR of $17.38\text{ dB}$ and Mean SSIM of $0.482$ across 50 test frames.
- **Latent Manifold**: Smooth interpolations across polyp shapes and successful downstream lesion classification achieving $98.75\%$ test accuracy and $0.9962$ AUC on the latent representation.

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
