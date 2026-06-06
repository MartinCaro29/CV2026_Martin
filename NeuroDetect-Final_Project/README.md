# NeuroDetect — Brain Tumor Detection with Deep Learning

**Course:** Computer Vision | Christian Mata, PhD  
**Group members:** Martin Çaro, Edison Zyberaj  
**Dataset:** [LGG Brain MRI Segmentation](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation) (Kaggle — mateuszbuda)

---

## Overview

NeuroDetect is a deep learning pipeline for brain tumor detection in MRI scans, covering three tasks: binary classification via transfer learning (MobileNetV2), pixel-level segmentation with a U-Net, and Grad-CAM interpretability. For a full write-up of the theory, results, and discussion, open [`REPORT.html`](REPORT.html) in a browser.

---

## Project Structure

```
NeuroDetect-Final_Project/
├── demo/
│   └── demo.ipynb              # Detects tumor presence based on an input image
├── notebooks/
│   ├── 00_setup.ipynb           # Dataset download and TIF → PNG conversion
│   ├── 01_train_test.ipynb      # Train/test split and label derivation
│   ├── 02_classification_TL.ipynb  # Transfer learning classifier (MobileNetV2)
│   ├── 03_segmentation.ipynb       # U-Net pixel-wise segmentation
│   └── 04_heatmap.ipynb            # Grad-CAM interpretability heatmaps
├── models/
│   ├── brain_tumor_classifier.h5
│   └── brain_tumor_segmenter.h5
├── results/                        # Generated plots and visualizations
└── REPORT.html                     # Theory, results, and discussion
```

---

## Installation & Setup

The notebooks run on **Google Colab** with **Google Drive** as persistent storage.

### Prerequisites

- A Google account with Google Drive
- A Kaggle account with an API token (`kaggle.json`)

### Step 1 — Upload notebooks to Drive

Upload the `notebooks/` folder to your Google Drive, then open each notebook in Google Colab.

### Step 2 — Configure the Kaggle API

1. Go to kaggle.com → Account → **Create New Token** to download `kaggle.json`
2. Upload `kaggle.json` when prompted by `00_setup.ipynb`

### Step 3 — Run notebooks in order

| # | Notebook                     | What it does |
|---|------------------------------|---|
| 1 | `00_setup.ipynb`             | Download dataset, convert TIF → PNG |
| 2 | `01_train_test.ipynb`        | Split data and derive labels |
| 3 | `02_classification_TL.ipynb` | Train MobileNetV2 transfer learning classifier |
| 4 | `03_segmentation.ipynb`      | Train and evaluate the U-Net segmenter |
| 5 | `04_heatmap.ipynb`           | Generate Grad-CAM heatmaps |
| 6 | `demo.ipynb`                 | Detects tumor presence based on an input image |

Each notebook reads from and writes back to Google Drive. Run them sequentially.
