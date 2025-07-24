# Vanguard A/B Test Analysis

[🇪🇸 Versión en Español](./README.es.md)

![Python](https://img.shields.io/badge/python-3.10-blue.svg)
![Platform](https://img.shields.io/badge/platform-Jupyter%20%7C%20Pandas%20%7C%20Scikit--Learn%20%7C%20Seaborn-lightgrey)
![Last Commit](https://img.shields.io/github/last-commit/fran-eliot/vanguard-ab-test)
![Repo Size](https://img.shields.io/github/repo-size/fran-eliot/vanguard-ab-test)
![License: Educational](https://img.shields.io/badge/license-Educational-informational)

## 📊 Project Overview

This repository contains an exploratory data analysis (EDA), metric validation and hypothesis testing of an A/B test experiment for a tech company. The goal is to identify how user behavior and conversions are affected by a new experimental experience.

## 📁 Notebooks

- `01_eda.ipynb`: Exploratory data analysis and feature engineering.
- `02_metrics_test.ipynb`: Metrics selection, sanity checks, hypothesis testing.

## 🧪 Summary of Findings and Hypothesis Testing

### ✔️ Metrics Validated

- **Click Through Rate (CTR)** and **Conversion Rate (CVR)** were selected as primary metrics.
- Sanity checks (randomization, sample size, normality) were passed, justifying the use of parametric hypothesis tests.

### 📌 Hypotheses Tested

#### 1. CTR Hypothesis

- **H₀ (null hypothesis):** The new experience does **not** increase the click-through rate.
- **H₁ (alternative hypothesis):** The new experience **does** increase the click-through rate.
- ✅ **Result**: The t-test showed a **statistically significant improvement** in CTR for the treatment group. **H₀ was rejected**.

#### 2. Conversion Rate Hypothesis

- **H₀:** The new experience does **not** increase conversion.
- **H₁:** The new experience **does** increase conversion.
- ❌ **Result**: The difference in conversion rates was **not statistically significant**. **H₀ could not be rejected**.

### 📌 Conclusion

- The new experience successfully improved **CTR** but **did not significantly affect conversion**.
- While more users are engaging with the interface, this doesn’t necessarily lead to more final conversions. Further investigation or follow-up tests are recommended.

## 📚 License

This project is published under an **Educational Use License**. It is intended for learning, teaching, and academic evaluation. Commercial use is not permitted without explicit consent.

---

Made with ❤️ by Fran Eliot