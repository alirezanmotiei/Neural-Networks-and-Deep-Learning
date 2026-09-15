# HWE: Advanced Topics in Deep Learning

This capstone module explores advanced adversarial attack dynamics across neural architectures and constructs an end-to-end multimodal deep learning pipeline for Persian Image Captioning.

---

## Assigned Questions & Implementation Architecture

### 1. Adversarial Robustness: ResNet vs. Vision Transformer (`NNDL_HWE_Q1_Adversarial_Attacks.ipynb`)
- **Threat Models**: White-box $L_\infty$-bounded single-step FGSM and multi-step iterative PGD attacks evaluated across CIFAR-100 and Oxford Flowers-102.
- **Architectural Comparison**: ResNet-18 exhibits rapid accuracy drops under small perturbations, whereas Vision Transformers demonstrate higher residual robustness in the low-perturbation regime (retaining $33.4\%$ accuracy vs. $24.1\%$ for ResNet at $\epsilon = 8/255$).

### 2. End-to-End Persian Image Captioning (`NNDL_HWE_Q2_Persian_Captioning.ipynb`)
- **Linguistic Preprocessing**:
  - Hazm morphological normalization and tokenization.
  - `arabic_reshaper` and `python-bidi` for right-to-left Persian text rendering.
  - Custom vocabulary builder ($V = 6,842$ tokens) handling compound Persian verbs and zero-width non-joiners.
- **Deep Architecture**: Pretrained CNN visual encoder paired with a 2-layer LSTM decoder trained with teacher forcing.
- **Evaluation**: Smoothed BLEU-1 score of $0.548$ and BLEU-4 of $0.182$, generating culturally and grammatically sound Persian captions.

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
