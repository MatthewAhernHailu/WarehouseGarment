

Overview

This project analyzes a Kaggle dataset on garment worker productivity to identify key drivers of output and create a Power BI dashboard for management insights.

Using Python for data cleaning, aggregation, and machine learning, the pipeline automatically generates CSV outputs that feed into Power BI. The dashboard provides Daily KPIs, team-level performance, and feature importance insights to help managers understand what drives productivity.

Approach to Solving the Problem

The project is designed around three stages:

1. Data Cleaning & KPI Generation

Raw data from Kaggle is cleaned in Python:
Productivity values clipped to valid ranges (0–1).
Conversion of numeric fields to ensure consistency.
Removal of missing/dirty entries.
Daily KPIs are generated per team and department:
Actual vs targeted productivity.
Performance ratio (perf_ratio = actual ÷ target).
Overtime, incentives, SMV, and idle worker metrics.
Results exported to kpi_with_predictions_latest.csv for Power BI.

2. Predictive Modeling & Feature Importance

A Random Forest Regressor predicts actual productivity based on operational factors.
Feature importance analysis highlights key drivers
Results exported as feature_importance.csv for visualization.

3. Automation with Papermill

Papermill executes Jupyter notebooks automatically, generating updated CSVs without manual intervention.
Paired with Windows Task Scheduler for daily runs.
Ensures Power BI dashboards always pull fresh KPIs and predictions.

Technologies Used
Python: Data cleaning, KPI calculation, machine learning.
Pandas / NumPy: Data wrangling and numeric processing.
Scikit-learn: Machine learning
Papermill: Automated notebook execution and reproducibility.
Power BI: Dashboards and interactive reporting.


Getting Started
1. Clone this Repository

2. Install Requirements
pip install -r requirements.txt

3. Run Notebook with Papermill
papermill notebooks/DataCleanKPI.ipynb notebooks/DataCleanKPI_output.ipynb


DATA SOURCED:

Dataset: Kaggle – Productivity Prediction of Garment Employees
https://www.kaggle.com/datasets/ishadss/productivity-prediction-of-garment-employees
