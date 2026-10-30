# Customer Churn Prediction and Sales Dashboard

## Project Description

This repository contains a complete end-to-end customer churn prediction and sales analytics project built in Python. It includes data cleaning, feature engineering, machine learning model training, customer segmentation, and a multi-page Streamlit dashboard for business-facing insights.

## Features

- Data cleaning and preprocessing pipeline
- Feature engineering with derived customer metrics
- Machine learning model training with Logistic Regression, Random Forest, and XGBoost
- Automatic model selection based on F1 score
- Customer segmentation using K-Means clustering
- Prediction center for live churn scoring
- Multi-page Streamlit dashboard with KPIs, analytics, sales views, segmentation, model performance, and an interactive data explorer
- Prepared for Streamlit Cloud deployment

## Installation

1. Clone or download this project into the directory `Customer_Churn_Project`.
2. Create a Python environment (recommended):
   ```bash
   python -m venv venv
   .\venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Dataset Information

The project uses the Kaggle dataset `Telco Customer Churn Dataset` with file name `WA_Fn-UseC_-Telco-Customer-Churn.csv`.

### Dataset placement

- Preferred: place the dataset in `data/raw/WA_Fn-UseC_-Telco-Customer-Churn.csv`
- Optional: if Kaggle API is installed and configured, the pipeline will attempt to download the dataset automatically.

## How to Run

### 1. Clean the data

```bash
python src/data_cleaning.py
```

### 2. Prepare features and train models

```bash
python src/train_model.py
```

### 3. Generate customer segmentation

```bash
python src/clustering.py
```

### 4. Launch the dashboard

```bash
streamlit run dashboard/app.py
```

## Streamlit Dashboard Pages

1. Executive Summary
2. Customer Analytics
3. Sales Dashboard
4. Prediction Center
5. Customer Segmentation
6. Model Performance
7. Data Explorer

## Deployment Instructions

- Ensure `requirements.txt` is present
- Verify `dashboard/app.py` runs locally
- For deployment to Streamlit Cloud, push this repository to GitHub and connect the repo to Streamlit Cloud
- Set the startup command: `streamlit run dashboard/app.py`

## Technologies Used

- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- plotly
- streamlit
- streamlit-option-menu
- streamlit-aggrid
- joblib

## GitHub Integration

```bash
git init
git add .
git commit -m "Customer Churn Prediction and Sales Dashboard project"
git branch -M main
git remote add origin REPOSITORY_URL
git push -u origin main
```

> Replace `REPOSITORY_URL` with your GitHub repository URL.

## Model Review and Business Interpretation

Use the same validation strategy when comparing Logistic Regression, Random Forest, and XGBoost. Since churn datasets can be imbalanced, review precision, recall, F1-score, and the confusion matrix rather than selecting a model by accuracy alone. Check that any threshold used for live scoring is appropriate for the business objective.

## Dashboard Validation Checklist

- Verify KPI totals against the source dataset.
- Check filters and segment counts against independently calculated values.
- Test the prediction page with valid, missing, and out-of-range inputs.
- Confirm that the dashboard explains that churn scores are estimates, not guaranteed outcomes.

## Project Development Notes

Track class balance and the decision threshold used for churn alerts. Validate dashboard KPIs against source data and compare models using recall, precision, and F1.

For reproducible updates, record the dataset/source version, environment and dependency versions, preprocessing choices, and actual outputs from each run. Keep sample values clearly labelled and do not publish secrets or private data.

### Technical Deep Dive

Churn modelling should preserve the distinction between a probability score and a business decision. Evaluate candidate models on the same stratified validation strategy, inspect class imbalance, and select the alert threshold based on the relative cost of missed churners and unnecessary retention outreach. Keep clustering features and churn-prediction features conceptually separate unless there is a clear reason to combine them.

Suggested engineering checks: fit preprocessing only on training data, calibrate probabilities if they drive decisions, validate dashboard KPIs against independent aggregations, and test missing/out-of-range form values.
