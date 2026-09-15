# HWE: Advanced Topics in Deep Learning

This capstone module explores advanced adversarial attack dynamics across neural architectures and constructs an end-to-end multimodal deep learning pipeline for Persian Image Captioning.

---

## Assigned Questions & Implementation Architecture

### 1. Adversarial Robustness: ResNet vs. Vision Transformer (`NNDL_HWE_Q1_Adversarial_Attacks.ipynb`)
- **Threat Models**: White-box $L_\infty$-bounded single-step FGSM and multi-step iterative PGD attacks evaluated across CIFAR-100 and Oxford Flowers-102.
- **Architectural Comparison**: Original ResNet-18 clean accuracy is $55.18\%$ (dropping to $0.54\%$ under PGD, improved to $18.16\%$ with defense), while Fine-Tuned ViT clean accuracy is $86.40\%$ (dropping to $0.00\%$ under PGD, improved to $25.40\%$ with defense).

### 2. End-to-End Persian Image Captioning (`NNDL_HWE_Q2_Persian_Captioning.ipynb`)
- **Linguistic Preprocessing**:
  - Hazm morphological normalization and tokenization.
  - `arabic_reshaper` and `python-bidi` for right-to-left Persian text rendering.
  - Custom vocabulary builder ($V = 6,842$ tokens) handling compound Persian verbs and zero-width non-joiners.
- **Deep Architecture**: Pretrained CNN visual encoder paired with a 2-layer LSTM decoder trained with teacher forcing.
- **Evaluation**: Baseline model achieves Greedy BLEU-1 of $0.2445$ and Beam Search BLEU-4 of $0.0461$, outperforming Scheduled Sampling ($0.1924$) and Dot-Product Attention ($0.2268$).

---

## Directory Structure

```text
HWE-Adversarial-Robustness-and-Multimodal-Captioning/
├── README.md
├── notebooks/
│   ├── NNDL_HWE_Q1_Adversarial_Attacks.ipynb
│   └── NNDL_HWE_Q2_Persian_Captioning.ipynb
└── report/
    ├── HWE_Report.tex
    └── figures/
```
