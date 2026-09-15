# HW04: Sequence Modeling & Multimodal Deep Learning

This module addresses sequential credit assignment across two disparate domains: multimodal image captioning with convolutional-recurrent architectures, and multivariate clinical time-series forecasting for Intensive Care Unit (ICU) patient telemetry.

---

## Assigned Questions & Implementation Architecture

### 1. Multimodal Image Captioning on Flickr8k (`NNDL_HW04_Q1_Image_Captioning.ipynb`)
- **Encoder-Decoder Architecture**:
  - Vision Encoder: Pretrained ResNet-50 extracting $2048$-dimensional spatial feature vectors.
  - Language Decoder: Word embedding projection followed by deep LSTM units with teacher forcing.
- **Inference & Scoring**: Greedy decoding and beam search evaluated with BLEU-1 through BLEU-4 metrics: Greedy BLEU-1: $0.1889$, BLEU-4: $0.2963$; Beam Search ($k=5$) BLEU-1: $0.2139$, BLEU-4: $0.4152$.

### 2. Clinical ICU Time-Series Modeling (`NNDL_HW04_Q2_Clinical_TimeSeries.ipynb`)
- **Statistical Preprocessing**:
  - Augmented Dickey-Fuller (ADF) hypothesis testing verifying stationarity after differencing.
  - Autocorrelation (ACF) and Partial Autocorrelation (PACF) determining effective temporal memory lag ($T_{\text{in}} = 24$ hours).
- **Recurrent Forecasting**:
  - Stacked Gated Recurrent Units (GRU) predicting future physiological trajectories ($T_{\text{out}} = 6$ hours).
  - Heteroscedastic Maximum Log-Likelihood estimation with channel-weighted Mean Squared Error.

---

## Directory Structure

```text
HW04-Sequence-Modeling-and-Clinical-NLP/
├── README.md
├── notebooks/
│   ├── NNDL_HW04_Q1_Image_Captioning.ipynb
│   └── NNDL_HW04_Q2_Clinical_TimeSeries.ipynb
└── report/
    ├── HW04_Report.tex
    └── figures/
```
