# 🏦 Credit Risk Oversight System

> **A dual-stream analytics platform combining descriptive BI (Power BI) and predictive AI (Streamlit) to optimize loan approval decisions.**

![Dashboard Preview](assets/dashboard_screenshot_main.png)
*(Note: Add your dashboard screenshot in an 'assets' folder)*

## 📌 Executive Summary
Managing a $3.2M subprime lending portfolio requires balancing risk with opportunity. Traditional manual reviews led to a **30% default rate**. This project deploys a two-stage solution:
1.  **Strategic Oversight (Power BI):** A dashboard to identify high-risk segments (e.g., "Skilled Workers") and simulate profitability scenarios.
2.  **Operational Action (Streamlit):** A machine learning web app allowing loan officers to score new applicants in real-time with **77% accuracy**.

---

## 🛠 System Architecture

The project is structured into two distinct pipelines:

### 1. The Analytics Pipeline (Business Intelligence)
* **Goal:** Root cause analysis of historical defaults.
* **Tech:** Python (Pandas) $\rightarrow$ Power BI (DAX, Decomposition Trees).
* **Key Output:** Discovered that **Skilled Workers** carry a 2x higher default risk than Unskilled labor, contradicting traditional credit assumptions.

### 2. The Predictive Pipeline (Machine Learning)
* **Goal:** Real-time risk scoring for new applicants.
* **Tech:** Scikit-Learn (Extra Trees Classifier) $\rightarrow$ Streamlit.
* **Performance:** The **Random Forest** model achieved the highest stability, while **Extra Trees** was selected for production speed.

| Model | Accuracy | Status |
|-------|----------|--------|
| **Random Forest** | **77.0%** | 🏆 Best Performer |
| Extra Trees | 74.5% | ⚡ Deployed (Low Latency) |
| XGBoost | 73.5% | |
| Decision Tree | 70.5% | Baseline |

---

## 📂 Repository Structure

```text
CreditRisk/
├── data/
│   ├── raw/german_credit_data.csv       # Original Kaggle dataset
│   └── processed/                       # ETL output for Power BI
├── notebooks/
│   ├── 01_powerbi_data_prep.ipynb       # ETL Pipeline (Cleaning & Logic)
│   └── 02_analysis_model.ipynb          # ML Training & EDA
├── models/
│   ├── extra_trees_credit_model.pkl     # Serialized Model
│   └── *_encoder.pkl                    # Categorical Encoders
├── dashboard/
│   └── Credit_Risk_Dashboard.pbix       # The Power BI File
├── app/
│   └── app.py                           # Streamlit Web Application
└── README.md
