# Customer Churn Prediction and Sales Dashboard

An end-to-end analytics project combining customer churn modelling, customer segmentation and business-focused dashboard reporting.

## Key capabilities
- Data cleaning and feature preparation
- Churn classification and model comparison
- Customer grouping with K-Means clustering
- Interactive Streamlit views for analytics and exploration
- Prediction workflow for estimating churn risk

## Technology
Python · Pandas · Scikit-learn · Streamlit · K-Means · Data Visualization

## Dataset
The project README identifies the Telco Customer Churn dataset. Place the CSV where the data pipeline expects it (the documented default is `data/raw/WA_Fn-UseC_-Telco-Customer-Churn.csv`). Confirm the source and licence before redistributing data.

## Setup
```bash
git clone https://github.com/Ravi506051/Customer-Churn-prediction-and-sales-dashboard-main.git
cd Customer-Churn-prediction-and-sales-dashboard-main
python -m venv .venv
# Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
```

Run the data preparation, model training and dashboard commands documented in the project scripts. The current README describes `src/data_cleaning.py`, `src/train_model.py`, `src/clustering.py` and a Streamlit dashboard entry point; check the repository for the exact dashboard filename.

## Evaluation
Use a held-out test set and report precision, recall, F1-score, ROC-AUC and a confusion matrix when appropriate. Churn scores are estimates, not certainty; review class imbalance and false negatives before business use.

## Responsible use
Avoid exposing customer-level data in public dashboards. Document data provenance, access controls and retention policies.

## Maintainer
**Ravi Kumar Rao** · [GitHub](https://github.com/Ravi506051)

## Skills Demonstrated

- Customer churn analysis
- customer segmentation
- K-Means clustering
- Streamlit dashboarding
- classification metrics.

## Portfolio Context

This project is part of my hands-on learning portfolio. The repository documents the workflow and implementation; results should be reproduced from the included code and data before being used in reports or professional claims.
