# IDS-Africa-ML
### Machine Learning-Based Intrusion Detection for Sub-Saharan African Networks
#### A Comparative Study of ML Models with Explainability and Edge Deployment Analysis
## Overview

This repository contains the full research pipeline for a comparative analysis of machine learning models applied to network intrusion detection, with a specific focus on deployment feasibility in Sub-Saharan African network environments.

This work addresses a critical gap in existing literature: while ML-based Intrusion Detection Systems (IDS) have been extensively studied in high-resource settings, their applicability to the resource-constrained, infrastructure-limited networks common across Sub-Saharan Africa remains largely unexplored.
**Research Domain:** Cybersecurity · Machine Learning · Network Security · African ICT

---

## Research Questions

1. How do Random Forest, XGBoost, and Neural Network models compare in detecting modern network intrusions on the CICIDS-2017 dataset?
2. How does class imbalance affect model performance, and can SMOTE-based resampling improve detection of minority attack types?
3. Which features most strongly drive intrusion detection decisions, and do they align with known network security principles? (SHAP analysis)
4. Which model offers the best trade-off between accuracy and computational cost for deployment in low-resource African network environments?

---
## Dataset

**CICIDS-2017** — Canadian Institute for Cybersecurity Intrusion Detection Evaluation Dataset 2017

- **Source:** [University of New Brunswick](https://www.unb.ca/cic/datasets/ids-2017.html)
- **Size:** ~2.8 million network flow records
- **Features:** 78 network traffic features
- **Classes:** BENIGN + 14 attack categories including DDoS, PortScan, Botnet, Web Attacks, Infiltration
- **Why CICIDS-2017:** Contains modern attack types not present in older benchmarks (e.g., NSL-KDD from 1999), making it significantly more relevant to current threat landscapes

> Note: The dataset is not included in this repository due to size. See `data/README.md` for download instructions.

## Models Compared

| Model | Type | Key Strength |
|---|---|---|
| Random Forest | Ensemble (Supervised) | Handles imbalance well, interpretable |
| XGBoost | Gradient Boosting (Supervised) | High performance, fast inference |
| Neural Network | Deep Learning (Supervised) | Learns complex patterns |

---

## Methodology Summary

```
Raw CICIDS-2017 Data
        │
        ▼
Data Cleaning (remove inf/null, strip whitespace)
        │
        ▼
Feature Encoding + Standard Scaling
        │
        ▼
SMOTE Resampling (handle class imbalance)
        │
        ▼
Train/Test Split (80/20)
        │
        ├──► Random Forest
        ├──► XGBoost          ──► Evaluation (Accuracy, F1, Precision, Recall)
        └──► Neural Network
                │
                ▼
        SHAP Explainability Analysis
                │
                ▼
        Edge Deployment Feasibility Assessment
        (Model size · Inference time · RAM usage)
                │
                ▼
        Discussion: Sub-Saharan Africa Context
```

---

## Evaluation Metrics

- **Accuracy** — Overall correct classifications
- **F1 Score (weighted)** — Balances precision and recall across imbalanced classes
- **Precision & Recall** — Per-class detection performance
- **ROC-AUC** — Discrimination ability across thresholds
- **Training Time** — Computational cost
- **Model Size (MB)** — Storage footprint for edge deployment
- **Inference Latency (ms)** — Real-time detection capability

---

## Sub-Saharan Africa Context

A key contribution of this work is situating the findings within the realities of African network infrastructure:

- Internet penetration in Sub-Saharan Africa averages ~36% (ITU, 2023), with rapid growth increasing exposure to cyber threats
- INTERPOL's African Cyberthreat Assessment reports a significant rise in network intrusions targeting financial and government institutions
- Edge routers and network devices in the region often operate under RAM and processing constraints that make heavy deep learning models impractical
- This study explicitly evaluates which model offers the best **accuracy-to-resource trade-off** for realistic deployment

---






## Research Paper

**Title:** Comparative Analysis of Machine Learning Models for Intrusion Detection on Modern Network Traffic: A Study on Class Imbalance, Explainability, and Edge Deployment Feasibility in Sub-Saharan Africa


**Author:** Maxwell Gitahi 
---

*This research is conducted as part of an effort to bridge the gap between ML security research and practical deployment in African network environments.*
