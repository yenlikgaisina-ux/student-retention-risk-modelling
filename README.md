# Student Retention Risk Modelling

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0-orange)
![SHAP](https://img.shields.io/badge/SHAP-0.44-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> **Business Question:** Which student cohorts are at highest risk of non-continuation after Year 1, and what institutional and demographic factors are most predictive of early withdrawal?

---

## Overview

This project builds a machine learning pipeline to identify the institutional and demographic characteristics most strongly associated with non-continuation risk in UK higher education.

The dataset is a **calibrated synthetic dataset** of 2,400 cohort-level records, with non-continuation rates, demographic proportions, and institutional characteristics drawn from published HESA 2021/22 performance indicator figures. HESA does not make cohort-level microdata (provider x subject x tariff x mode) freely available for download — detailed student records require institutional data-sharing agreements. The synthetic data preserves the statistical relationships reported in HESA's aggregate tables while enabling a complete ML pipeline demonstration.

The model assigns a risk score to each cohort profile, produces SHAP-based feature importance rankings, and generates actionable policy recommendations for student support services. The methodology is directly transferable to real institutional data (e.g., from SITS student records systems).

---

## Methods

| Stage | Technique | Purpose |
|-------|-----------|---------|
| Data preparation | Calibrated synthetic cohorts (HESA-structured) | Aggregate cohort-level features |
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
| Cohort profiles scored | 2,400 |
| XGBoost ROC-AUC | See notebook output |
| Logistic Regression AUC (baseline) | See notebook output |
| Top risk factor | Entry tariff band (SHAP rank #1) |
| Data calibration basis | HESA 2021/22 published performance indicators |

All specific metrics (AUC scores, F1, improvement percentages, high-risk segment sizes) are computed from the calibrated synthetic data and reported in the notebook.

---

## Model Performance

The notebook produces ROC curves comparing XGBoost against Logistic Regression baseline, confusion matrices with optimised thresholds, and SHAP feature importance analysis. XGBoost substantially outperforms the Logistic Regression baseline, with entry tariff band as the strongest individual predictor of non-continuation risk.

---

## What a University Would Do With This

A student support team with access to this model's cohort risk scores could act before the end of the first term rather than waiting for early withdrawal data to accumulate. The highest-risk profiles -- typically part-time students at post-92 providers with low entry tariffs -- can be flagged for proactive outreach: targeted induction support, peer mentoring referrals, and early academic skills assessments. Because the model operates at cohort level, it does not require individual student data sharing agreements, which makes it deployable across institutions.

---

## Repository Structure

```
student-retention-risk-modelling/
|-- docs/
|   |-- roc_curve.svg
|   +-- shap_summary.svg
|-- notebook/
|   +-- student_retention_risk_modelling.ipynb
+-- README.md
```

---

## Skills Demonstrated

`Python` `XGBoost` `SHAP` `Scikit-learn` `Logistic Regression` `HESA Data` `Education Analytics` `Feature Engineering` `ROC-AUC` `Cross-Validation` `Pandas` `Matplotlib` `Seaborn`

---

## Author

**Yenlik Gaisina** | Data & Analytics Consultant

[LinkedIn](https://www.linkedin.com/in/yenlik-gaisina/) | Cambridge Data Science with ML & AI Programme
