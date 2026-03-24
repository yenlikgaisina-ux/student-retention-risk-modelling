# Student Retention Risk Modelling

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python) ![XGBoost](https://img.shields.io/badge/XGBoost-2.0-orange) ![SHAP](https://img.shields.io/badge/SHAP-0.44-green) ![License](https://img.shields.io/badge/License-MIT-lightgrey)

> **Business Question:** Which student cohorts are at highest risk of non-continuation after Year 1, and what institutional and demographic factors are most predictive of early withdrawal?

---

## Overview

Using publicly available HESA (Higher Education Statistics Agency) aggregate data on UK student continuation rates, this project builds a machine learning pipeline to identify the institutional and demographic characteristics most strongly associated with non-continuation risk. The model produces risk scores by cohort profile, SHAP-based feature importance, and actionable policy recommendations for student support services.

---

## Methods

| Stage | Technique | Purpose |
|-------|-----------|---------|
| Data preparation | HESA Table 10 continuation rates | Aggregate cohort-level features |
| Feature engineering | Subject area, entry tariff band, mode of study, provider type | Risk factor construction |
| Baseline model | Logistic Regression | Interpretable benchmark |
| Main model | XGBoost Classifier | Non-linear risk prediction |
| Explainability | SHAP TreeExplainer | Feature importance and cohort drivers |
| Threshold tuning | Precision-Recall curve, F1 optimisation | Operational decision boundary |
| Validation | Stratified 5-fold cross-validation, ROC-AUC | Generalisation testing |

---

## Key Findings

| Metric | Value |
|--------|-------|
| XGBoost ROC-AUC | 0.847 |
| Logistic Regression AUC (baseline) | 0.761 |
| Improvement over baseline | +11.3% AUC |
| Top risk factor | Entry tariff band (SHAP rank #1) |
| High-risk cohort non-continuation rate | 18.4% vs 4.1% low-risk |
| Students in high-risk segment | ~23% of enrolments |

---

## Repository Structure

```
student-retention-risk-modelling/
+-- notebook/
|   +-- student_retention_risk_modelling.ipynb
+-- README.md
+-- .gitignore
```

---

## Skills Demonstrated

`Python` `XGBoost` `SHAP` `Scikit-learn` `Logistic Regression` `HESA Data` `Education Analytics` `Feature Engineering` `ROC-AUC` `Cross-Validation` `Pandas` `Matplotlib` `Seaborn`

---

## Author

**Yenlik Gaisina** | Data & Analytics Consultant  
[LinkedIn](https://linkedin.com/in/yenlikgaisina) | Cambridge Data Science with ML & AI Programme
