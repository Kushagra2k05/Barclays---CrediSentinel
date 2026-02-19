📌 CrediSentinel — AI-Driven Pre-Delinquency Risk Prediction
🚀 Overview

CrediSentinel is an AI/ML-based system designed to predict pre-delinquency risk for loan customers before they miss EMIs.
The system leverages customer financial behavior, repayment history, and usage patterns to generate a risk score and early warning signals for lenders.

This helps in:

Early identification of high-risk customers

Reducing NPAs (Non-Performing Assets)

Enabling proactive intervention (reminders, restructuring, support)

🎯 Problem Statement

Traditional delinquency detection systems act after a missed EMI occurs.
However, by the time a customer misses payments, the probability of default is already high.

CrediSentinel aims to predict delinquency before it happens, using behavioral + financial signals.

✅ Objectives

Predict the probability of a customer becoming delinquent in the next 7/15/30 days

Generate a risk score for each customer

Provide explainability (feature impact) using SHAP

Create an end-to-end architecture including ingestion, feature store, scoring, monitoring, and alerting

🧠 Key Features Used
Income & Employment

income_monthly

employment_status

job_type

income_stability

Credit & Loan Behavior

credit_utilization

missed_emi_count

repayment_ratio

loan_tenure

loan_amount

Time-Based Features

data_period

rolling averages

payment trend features

delinquency recency

🏗️ System Architecture (High Level)

The architecture follows a modern ML pipeline approach:

Data Sources → Kafka → PostgreSQL → Feature Store (Feast) → Model Training → Risk Scoring → Explainability → Serving → Dashboard → Alerts → Orchestration

Components Used

Streaming / Ingestion: Apache Kafka

Storage: PostgreSQL

Feature Store: Feast

Training & Scoring: ML/DL models (classification)

Explainability: SHAP

Serving: BentoML + FastAPI

Dashboard: Plotly Dash

Orchestration: Apache Airflow

Alerts: Email/SMS Stub (can be integrated with Twilio etc.)

🔁 Workflow (Pipeline)

Loan & customer events are ingested daily/real-time

Data is stored in PostgreSQL

Feature computation is performed (batch + streaming)

Features are stored in Feast

Model training runs weekly/monthly

Batch scoring runs daily

Risk score + explanations are generated

Results are served via API and visualized in dashboard

Alerts are triggered for high-risk customers

Monitoring logs pipeline health and model drift

📊 Model Output

The system outputs:

Risk Probability (0–1)

Risk Category

Low

Medium

High

Top Contributing Factors (via SHAP)

🧪 Evaluation Metrics

The system can be evaluated using:

Accuracy

Precision / Recall

F1-score

ROC-AUC

Confusion Matrix

Calibration (optional)

📁 Project Structure (Suggested)
CrediSentinel/
│
├── README.md
├── docs/
│   ├── architecture.png
│   ├── feature_graph.png
│   ├── dataset_schema.pdf
│
├── data/
│   ├── sample_dataset.csv
│
├── notebooks/
│   ├── model_training.ipynb
│
├── src/
│   ├── ingestion/
│   ├── feature_engineering/
│   ├── training/
│   ├── scoring/
│   ├── serving/
│
└── requirements.txt

🛠️ Tech Stack
Layer	Technology
Data Ingestion	Apache Kafka
Storage	PostgreSQL
Feature Store	Feast
Orchestration	Apache Airflow
ML Modeling	Scikit-learn / XGBoost / DL Models
Explainability	SHAP
Serving	FastAPI + BentoML
Dashboard	Plotly Dash
Alerts	Email/SMS Stub
🔒 Notes

This submission is intended as a system design + ML architecture prototype, as per instructions that a working prototype is not required for this round.

The architecture is scalable and can be productionized with minimal changes.

👨‍💻 Authors

Team Name: CrediSentinel
Project Domain: AI/ML + FinTech (Loan Risk Prediction)
