# 🏥 Hospital Resource Allocation — End-to-End Data Analytics Project

![Power BI Dashboard](dashboard/page1_executive_summary.png)

## 📌 Project Overview
This project analyzes hospital resource allocation patterns across 13 departments 
using 3 years of patient admission data (2021–2024). The goal is to identify 
resource bottlenecks, predict patient readmission risk, and forecast future 
admission demand to help hospital administrators make data-driven decisions.

---

## 🎯 Business Questions Answered
1. Which departments are over/under-utilizing resources?
2. Can we predict which patients are at high readmission risk?
3. What admission patterns exist across time and departments?

---

## 📊 Key Findings
- **Neurology** is the busiest department with 181 admissions
- **Orthopedics** has the longest average stay at 17.5 days
- **Oncology** is the most expensive department at ₹60,345 avg bill
- **19.6%** of patients are at high readmission risk
- High risk patients cost **50% more** (₹14.34K vs ₹9.54K avg)
- **Endocrinology (Diabetes)** has highest readmission rate at 52%
- Admissions peak in **2023** with 348 total admissions

---

## 🗂️ Dataset
- **Source:** Kaggle — Hospital Patient Records 2021–2024
- **Size:** 974 patients, 21 features after engineering
- **Period:** July 2021 — July 2024

---

## 🛠️ Tech Stack
| Tool | Purpose |
|---|---|
| Python (pandas, numpy) | Data cleaning & feature engineering |
| Matplotlib, Seaborn | Exploratory data analysis |
| Scikit-learn, XGBoost | Machine learning models |
| Facebook Prophet | Admission forecasting |
| Power BI | Interactive dashboard |
| Jupyter Notebook | Analysis environment |

---

## 📁 Project Structure
```
hospital-resource-allocation/
├── data/                   # Raw and cleaned datasets
├── notebooks/              # Jupyter notebook (full analysis)
├── dashboard/              # Power BI file + screenshots
├── reports/                # Data dictionary
└── README.md
```

---

## 🤖 Machine Learning Models

### Track A — Admission Forecasting
- Model: Linear Regression (baseline)
- Forecast: 26 admissions/month stable trend
- Metrics: MAE, RMSE

### Track B — Readmission Risk Classification
- Model: Random Forest Classifier
- Accuracy: 82% | AUC-ROC: 0.604
- Top predictor: Bill Amount
- Challenge identified: Class imbalance (783 vs 191)
- Solution applied: SMOTE oversampling

### Track C — Department Clustering
- Model: K-Means Clustering
- Result: 2 clusters identified
- Cluster 0: High volume, moderate cost departments
- Cluster 1: Low volume, very high cost (Oncology, Nephrology)

---

## 📈 Dashboard Pages
| Page | Description |
|---|---|
| Executive Summary | KPI cards — total patients, avg LOS, avg bill, readmission rate |
| Department Analysis | LOS, billing and resource profile by department |
| Admission Trends | Monthly trends, day of week patterns, year filter |
| Patient Risk Analysis | Readmission risk by condition, high risk patient list |

### Dashboard Screenshots
**Page 1 — Executive Summary**
![Page 1](dashboard/page1_executive_summary.png)

**Page 2 — Department Analysis**
![Page 2](dashboard/page2_department_analysis.png)

**Page 3 — Admission Trends**
![Page 3](dashboard/page3_admission_trends.png)

**Page 4 — Patient Risk Analysis**
![Page 4](dashboard/page4_patient_risk_analysis.png)

---

## 🚀 How to Run
1. Clone this repo
```bash
git clone https://github.com/YOURUSERNAME/hospital-resource-allocation.git
```
2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
```
3. Open Jupyter Notebook
```bash
jupyter notebook notebooks/hospital_analysis.ipynb
```
4. Open dashboard in Power BI Desktop
```
dashboard/Hospital_Resource_Allocation_Dashboard.pbix
```

---

## 💡 Key Learnings
- Real hospital datasets often lack repeat visit data — domain knowledge 
  used to engineer a medically logical readmission risk flag
- Class imbalance is a critical challenge in healthcare ML — addressed 
  using SMOTE oversampling
- Oncology drives highest cost but not highest volume — resource planning 
  must consider cost per patient not just headcount

---

## 👤 Author
**Akhil Tomar**
- LinkedIn: https://www.linkedin.com/in/akhil-tomar-a06300257
- GitHub: github.com/akhiltomar0000

---
⭐ If you found this project useful, please star the repo!