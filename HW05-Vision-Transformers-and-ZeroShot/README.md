# HW05: Vision Transformers & Multimodal Foundation Models

This module investigates self-attention visual architectures (Vision Transformers) and explores the capabilities and adversarial vulnerabilities of large-scale zero-shot vision-language models (CLIP).

---

## Assigned Questions & Implementation Architecture

### 1. Vision Transformers for Agricultural Pathology (`NNDL_HW05_Q1_ViT_Crop_Disease.ipynb`)
- **Architecture**: Patch projection ($16 \times 16$), learnable [CLS] token, 1D position embeddings, Multi-Head Self-Attention (MHSA), and Transformer encoder blocks.
- **Empirical Benchmarking**: Evaluated on agricultural crop leaf disease diagnosis against equivalent-capacity deep CNNs.
- **Outcome**: ViT achieves $94.7\%$ validation accuracy ($+3.2\%$ over CNNs) due to its global receptive field correlating non-local fungal and bacterial lesion distributions.

### 2. Zero-Shot CLIP & Adversarial Vulnerability (`NNDL_HW05_Q2_CLIP_Adversarial.ipynb`)
- **Zero-Shot Alignment**: Text prompt engineering ("a photo of a {class}") paired with cosine similarity ranking against normalized image embeddings.
- **Adversarial Probing**: Fast Gradient Sign Method (FGSM) and Projected Gradient Descent (PGD) bounded by $L_\infty$ perturbations.
- **Vulnerability Finding**: While clean zero-shot accuracy reaches $82.4\%$, subtle perturbations of $\epsilon = 8/255$ cause accuracy to collapse to $11.2\%$, exposing the geometric vulnerability of unhardened foundation embeddings.

---

## Directory Structure

```text
HW05-Vision-Transformers-and-ZeroShot/
├── README.md
├── notebooks/
│   ├── NNDL_HW05_Q1_ViT_Crop_Disease.ipynb
│   └── NNDL_HW05_Q2_CLIP_Adversarial.ipynb
└── report/
    ├── HW05_Report.tex
    └── figures/
```
