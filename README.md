# CervixViT 🔬
### DualPathCervixNet: A Hybrid CNN-Transformer Architecture for Cervical Cell Classification

<p align="left">
  <img src="https://img.shields.io/badge/Accuracy-98.68%25-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Macro_AUC-0.9988-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Macro_F1-0.9869-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Dataset-SIPaKMeD-purple?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Classes-5-red?style=for-the-badge" />
</p>

<p align="left">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/Kaggle-20BEFF?style=flat-square&logo=kaggle&logoColor=white" />
</p>

---

## 📌 Overview

**CervixViT** presents **DualPathCervixNet** — a novel hybrid architecture that fuses a CNN backbone with a Vision Transformer (ViT) encoder via a cross-attention mechanism for multi-class cervical cell classification from Pap smear images.

Cervical cancer is one of the most preventable cancers when detected early. Automated, high-accuracy classification of cervical cells from Pap smear imagery can assist cytologists and clinicians in screening workflows. This project explores a deep learning approach that combines the local feature extraction strength of CNNs with the global context modelling of transformers.

---

## 🧠 Architecture: DualPathCervixNet

The model follows a dual-path design:

- **CNN Path** — Extracts fine-grained local texture and morphological features from cell images
- **Transformer Path** — Captures long-range spatial dependencies and global structural patterns using Vision Transformer blocks
- **Cross-Attention Fusion** — A custom cross-attention module fuses representations from both paths, allowing each stream to attend to the other's features before final classification

This architecture is designed to overcome the limitations of pure CNNs (limited global context) and pure ViTs (insufficient local inductive bias for small medical datasets).

---

## 📊 Results

Evaluated on **608 test images** from the SIPaKMeD dataset:

| Metric | Score |
|---|---|
| **Accuracy** | **98.68%** |
| **Macro F1-Score** | **0.9869** |
| **Macro AUC (OvR)** | **0.9988** |

### Per-Class Performance

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| Dyskeratotic | 0.9677 | 0.9836 | 0.9756 | 122 |
| Koilocytotic | 0.9835 | 0.9597 | 0.9714 | 124 |
| Metaplastic | 0.9917 | 1.0000 | 0.9958 | 119 |
| Parabasal | 1.0000 | 0.9915 | 0.9957 | 118 |
| Superficial-Intermediate | 0.9921 | 1.0000 | 0.9960 | 125 |

---

## 📁 Repository Structure

```
CervixViT/
│
├── cervixvit-data-preprocessing-eda.ipynb      # Dataset loading, EDA, augmentation pipeline
├── cervixvit-novel-architecture-training.ipynb # DualPathCervixNet architecture + training loop
└── cervixvit-results-v0.ipynb                  # Evaluation metrics, Grad-CAM visualizations
```

---

## 🗂️ Dataset

**SIPaKMeD** (Single-cell Image Database for Pap smear Microscopy)

- 4,049 Pap smear cell images
- 5 cell classes: Dyskeratotic, Koilocytotic, Metaplastic, Parabasal, Superficial-Intermediate
- Publicly available on [Kaggle](https://www.kaggle.com/datasets/prahladmehandiratta/cervical-cancer-largest-dataset-sipakmed)

---

## ⚙️ Setup & Usage

### Requirements

```bash
pip install torch torchvision timm grad-cam pandas numpy matplotlib scikit-learn
```

### Run Notebooks (in order)

```bash
# 1. Data Preprocessing & EDA
jupyter notebook cervixvit-data-preprocessing-eda.ipynb

# 2. Model Architecture & Training
jupyter notebook cervixvit-novel-architecture-training.ipynb

# 3. Results & Visualisation
jupyter notebook cervixvit-results-v0.ipynb
```

> **Note:** Training was done on a GPU (CUDA). Adjust batch size and device settings accordingly.

---

## 🔬 Key Techniques

- **Dual-path CNN + ViT fusion** with cross-attention
- **Grad-CAM** visualisations for model interpretability
- **Class-balanced training** to handle dataset distribution
- **Augmentation pipeline** tailored for Pap smear imagery

---

## 👤 Author

**Soumyaranjan Sahoo**
BTech, Electronics & Telecommunication Engineering — VSSUT Burla

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/soumyaranjan--sahoo)
[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=flat-square&logo=firefox&logoColor=white)](https://www.soumyaranjan.tech/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SOUMYA-soumya)

---

## ⚠️ Disclaimer

This project is for academic and research purposes only. It is not intended for clinical use or medical diagnosis.

---

*If you find this project interesting, feel free to ⭐ star the repo!*
