# 🗳️ Forecasting Election Outcomes in Contemporary Democracies

**Predicting whether governments will change after elections using machine learning, instead of opinion polls.**

This project was developed as part of the Data Science Group Project module at the University of Birmingham.

---

## 📌 Quick Summary

- **Goal:** Predict government change (yes/no) based on a country's social, economic, and political indicators
- **Data:** 38 OECD countries, using over 50 indicators from sources like World Bank, OECD, UNDP, and IDEA
- **Models Used:** Logistic Regression, Random Forest, XGBoost
- **Best Accuracy:** 82% (Random Forest, cluster-based)
- **Innovation:** No polling data used; predictions based on structural features alone

---

## 📈 Project Motivation

Polling has failed to predict key political events (e.g., Brexit, 2016 US election). We wanted to build a more reliable, data-driven alternative using machine learning and publicly available index data — especially useful in countries where polling is unreliable or unavailable.

---

## 🛠️ Methodology Overview

### 1. Data Collection

- **Dependent variable:** Whether the incumbent government stayed in power (ParlGov, web-scraped election results)
- **Independent variables:** Social, economic, and political indicators from over 10 global databases  
- All datasets were either open-source or freely accessible under academic licenses

### 2. Data Processing

- Cleaned and unified ~50 features across countries and years
- Imputed missing values using regression and nearest-neighbour methods
- Standardized feature names and formats across sources

### 3. Feature Engineering

- Applied PCA to reduce dimensionality and multicollinearity
- Created two key composite features:
  - `Political-Social Index` (e.g., freedom of media, gender equality)
  - `Economic Stability Index` (e.g., GDP, Gini coefficient)

### 4. Clustering

- Used hierarchical clustering to group countries into 4 similar clusters
- Built separate models per cluster for improved performance

### 5. Modelling

- Algorithms used: Logistic Regression, Random Forest, XGBoost
- Random Forest performed best in most clusters
- Feature importance was evaluated using permutation and Gini importance

---

## 🧪 Results

| Model               | Full Dataset | Best Cluster (C3) |
|---------------------|--------------|-------------------|
| Logistic Regression | 52%          | 82%               |
| Random Forest       | 66%          | 82%               |
| XGBoost             | 61%          | 66%               |

- Political-Social and Economic Stability indices were the most informative features
- Our models **outperformed polling in more than half of the tested countries**
- Particularly strong results in Poland, Ireland, France, and Sweden

---

## 🌍 Real-World Implications

- **Poll-free election forecasting** for countries with limited infrastructure
- Can be used by election observers, political risk analysts, and NGOs
- Flexible and scalable — just needs publicly available indicator data

---

## 📁 Project Structure

```
election-forecasting-ml/
├── data/            # Raw and processed datasets
├── notebooks/       # Jupyter notebooks (EDA, modelling, evaluation)
├── report.pdf       # Final project report
├── proposal.pdf     # Project proposal and data documentation
└── README.md        # This file!
```
---

## 👥 Authors

> University of Birmingham - Msc Data Science Group Project
Connor Boyd-Lyon, Evelina Ivanova, Matthew Randall, Yarkın Yorulmaz, **Yeni Jung**, Zehn-Ul-Abideen Sharif

---

## 📜 License & Data Sources

All datasets used in this project are publicly licensed under open data policies (e.g., CC BY 4.0, CC0).  
For full citations, refer to the Appendix section of the final report.

---

## 🔮 Future Work

- Include coalition dynamics and election types (e.g., presidential vs parliamentary)
- Incorporate psychological or technological factors (e.g., internet usage, misinformation)
- Explore deep learning models or automated feature selection pipelines
