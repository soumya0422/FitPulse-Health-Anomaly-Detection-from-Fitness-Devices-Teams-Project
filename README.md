# FitPulse: Health Anomaly Detection System

FitPulse is a health analytics dashboard that processes wearable fitness data (heart rate, steps, sleep), detects anomalies using Machine Learning, and provides AI-based wellness insights.

---

## Input Data

The original dataset was taken from Kaggle:  
https://www.kaggle.com/datasets/arashnic/fitbit

From this dataset, the following files were used:
- minuteSleep_merged.csv  
- heartrate_seconds_merged.csv  
- weightLogInfo_merged.csv  
- dailyActivity_merged.csv  

### Data Preparation Process
1. Preprocessing was first applied on individual files.  
2. An inner join was performed to combine heart rate and steps data, producing:  
   clean_Dataset.csv  
3. A left join was then applied with the remaining datasets (sleep and weight) to generate the final dataset:  
   final_Dataset.csv  

This final_Dataset.csv is used as the main input for the system.

---

## Steps of Implementation

1. Data Upload and Preprocessing  
2. Feature Engineering (rolling statistics)  
3. Anomaly Detection  
   - Rule-based  
   - DBSCAN clustering  
4. Time-Series Forecasting using Prophet  
5. Visualization of trends and distributions  
6. Report generation (CSV and PDF)  
7. AI-based wellness advice  

---

## Tech Stack

Frontend: Streamlit, Plotly  
Backend: FastAPI, Uvicorn  
Data Science: Pandas, NumPy, Scikit-learn, Prophet, Matplotlib  
AI/LLM: OpenAI API  
Utilities: ReportLab, PyNgrok  

---

## Run

Install dependencies:
```bash
pip install fastapi uvicorn pyngrok pandas numpy prophet scikit-learn matplotlib plotly streamlit requests openai reportlab
-------
start backend:
```bash
uvicorn backend:app --port 8003
-------
Start frontend:
```bash
streamlit run app.py
-------
