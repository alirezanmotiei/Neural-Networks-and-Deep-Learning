# HW03: Urban Scene Semantic Segmentation on CamVid

This module implements a lightweight, computationally efficient encoder-decoder semantic segmentation network engineered with Depthwise Separable Convolutions, evaluated on the Cambridge-driving Labeled Video Database (CamVid) benchmark.

---

## Technical Highlights

### 1. Depthwise Separable Convolutions
- **Factorization**: Decomposing standard $3 \times 3$ convolutions into depthwise spatial filtering ($D_K \times D_K \times M$) followed by $1 \times 1$ pointwise channel projection ($M \times N$).
- **Computational Efficiency**: Achieves an $8.2\times$ reduction in floating-point Multiply-Accumulate operations (MACs), making the network suitable for real-time edge robotics.

### 2. U-Net Topology & Multi-Scale Features
- 4 downsampling stages contracting spatial resolution while expanding feature channels ($32 \to 64 \to 128 \to 256$).
- Dilated bottleneck ($d=2$) expanding the receptive field without resolution degradation.
- Symmetrical upsampling decoder with cross-hierarchy skip connections to preserve high-frequency boundary contours.

### 3. Training & Evaluation
- **Dataset**: CamVid 12-class urban driving scenes (Road, Building, Car, Pedestrian, Tree, Sky, etc.).
- **Schedule**: Optimized over an extensive 100-epoch regimen with cosine learning rate scheduling and inverse frequency class weighting.
- **Results**: Mean Intersection over Union (mIoU) of $62.8\%$ and global pixel accuracy of $88.3\%$.

---

## Directory Structure

```text
HW03-CamVid-Semantic-Segmentation/
├── README.md
├── notebooks/
│   └── NNDL_HW03_CamVid_Segmentation.ipynb
└── report/
    ├── HW03_Report.tex
    └── figures/
```
