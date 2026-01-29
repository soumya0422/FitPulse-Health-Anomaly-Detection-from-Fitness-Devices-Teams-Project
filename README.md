FitPulse: Health Anomaly Detection System

FitPulse is a health analytics dashboard that processes wearable fitness data (heart rate, steps, sleep), detects anomalies using Machine Learning, and provides AI-based wellness insights.

Input Data

The original dataset was taken from Kaggle:
https://www.kaggle.com/datasets/arashnic/fitbit

From this dataset, the following files were used:

minuteSleep_merged.csv

heartrate_seconds_merged.csv

weightLogInfo_merged.csv

dailyActivity_merged.csv

Data Preparation Process

Preprocessing was first applied on individual files.

An inner join was performed to combine heart rate and steps data, producing:
clean_Dataset.csv

A left join was then applied with the remaining datasets (sleep and weight) to generate the final dataset:
final_Dataset.csv

This final_Dataset.csv is used as the main input for the system.

Steps of Implementation

Data Upload and Preprocessing

Feature Engineering (rolling statistics)

Anomaly Detection

Rule-based

DBSCAN clustering

Time-Series Forecasting using Prophet

Visualization of trends and distributions

Report generation (CSV and PDF)

AI-based wellness advice

Tech Stack

Frontend: Streamlit, Plotly
Backend: FastAPI, Uvicorn
Data Science: Pandas, NumPy, Scikit-learn, Prophet, Matplotlib
AI / LLM: OpenAI API
Utilities: ReportLab, PyNgrok

Run
Install Dependencies

pip install fastapi uvicorn pyngrok pandas numpy prophet scikit-learn matplotlib plotly streamlit requests openai reportlab

Start Backend

uvicorn backend:app --port 8003

Start Frontend

streamlit run app.py

Screenshots

The repository includes screenshots to visually demonstrate the working of the system and each major module.

Screenshots cover:

Data upload and preprocessing results

Feature extraction and rolling statistics

Health trend forecasting (Prophet graphs)

Anomaly detection results

User health dashboard (raw vs rolling charts, health score)

DBSCAN clustering visualizations

Download and report generation screens

These screenshots help reviewers quickly understand the UI flow, analytics, and outputs without running the application.

Output Reports

FitPulse generates downloadable reports in both CSV and PDF formats.

CSV Reports

Detailed anomaly records per user

Includes:

Date

Metric affected

Severity level

AI-generated recommendation

PDF Reports

Two types of PDF reports are generated.

Full Dashboard Report

Dataset overview

Sample records

Anomaly summary

Visual analytics

Health insights

Personalized User Report

User-specific health trends

Health score breakdown

Detected anomalies

Personalized AI-based wellness advice

All generated reports are included in the repository as sample outputs to validate system functionality.
