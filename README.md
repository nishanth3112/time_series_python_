# 💼 Walmart Sales Forecasting and Demand Analytics

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Greykite](https://img.shields.io/badge/Library-Greykite-lightblue)
![Neural Prophet](https://img.shields.io/badge/Model-Neural%20Prophet-orange)
![Machine Learning](https://img.shields.io/badge/Category-Time%20Series%20Forecasting-green)
![Pandas](https://img.shields.io/badge/Data-Pandas-yellow)
![Matplotlib](https://img.shields.io/badge/Visualization-Matplotlib-red)
![Seaborn](https://img.shields.io/badge/Visualization-Seaborn-purple)


---

## 📌 Project Overview

This project focuses on **Time Series Forecasting** using **Greykite** (LinkedIn) and **Neural Prophet** (Meta/Facebook) to predict future sales based on historical data.

The dataset contains **Walmart store sales** across 45 stores in multiple regions, providing the foundation for analyzing trends, seasonality, and external drivers (e.g., holidays, CPI, fuel price).

### 🧭 Objective
To **predict weekly sales** using historical data and relevant external features, enabling better inventory planning and business forecasting.

---

## 🧩 Business Context

Time series forecasting answers the key business question:  
> “How did the past influence the future?”

It connects the **past, present, and future** to uncover demand patterns for:
- 📦 Supply chain optimization  
- 🚗 Ride-hailing demand & pricing  
- 🏬 Retail sales planning  

For Walmart, accurate forecasting drives better **inventory management**, **promotion planning**, and **profit optimization** during holidays and seasonal events.

---

## 🗂️ Dataset Description

**Source:** [Walmart Recruiting – Store Sales Forecasting (Kaggle)](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data)

| File | Description |
|------|--------------|
| **Stores.csv** | Store metadata – type and size |
| **Train.csv** | Weekly sales (2010-02-05 → 2012-11-01) |
| **Test.csv** | Same structure as Train, without Weekly_Sales |
| **Features.csv** | External features – Fuel Price, CPI, Unemployment, MarkDown data, IsHoliday flag |

**Key Columns**
- `Store` – Store ID  
- `Dept` – Department number  
- `Date` – Week ending date  
- `Weekly_Sales` – Weekly sales ($)  
- `IsHoliday` – Binary holiday indicator  
- `Fuel_Price` – Regional fuel price  
- `CPI` – Consumer Price Index  
- `Unemployment` – Regional unemployment rate  

---

## ⚙️ Tech Stack

- **Language:** Python 3.10  
- **Libraries:** `greykite`, `neuralprophet`, `scikit-learn`, `pandas`, `pandas_profiling`, `matplotlib`, `plotly`, `seaborn`, `numpy`

---

## 🏗️ Architecture Diagram

```markdown
Data (CSV)
│
├── Data Cleaning & Feature Engineering (EDA, imputation, outlier handling)
│
├── Feature Extraction (Date → Day, Month, Year + Holidays)
│
├── Model Training
│   ├── Greykite Silverkite Model
│   └── Neural Prophet Model
│
├── Model Validation (MAPE · RMSE)
│
└── Forecasting & Visualization (Plotly · Matplotlib · Seaborn)
```

**Pipeline Highlights**
- Combines statistical and neural models for robust predictions.  
- Decomposes time series into trend + seasonality components.  
- Stores trained models for re-use via `output/` directory.  
- Modular structure supports rapid experimentation.

---

## 🚀 Methodology & Workflow

### 1️⃣ Exploratory Data Analysis (EDA)
- Profiling features and correlations using Pandas Profiling  
- Detecting missing values and outliers via Z-Score and IQR  

### 2️⃣ Data Cleaning
- Imputed missing MarkDown and CPI values  
- Replaced `NA` and negative values with regional means  

### 3️⃣ Feature Engineering
- Extracted `Year`, `Month`, `Week`, `Day` from `Date`  
- Added holiday flags for seasonal boosts  
- Mapped store and region identifiers  

### 4️⃣ Time Series Component Analysis
- Decomposed sales into **Trend** & **Seasonality**  
- Identified holiday and promotion effects  

### 5️⃣ Model Development
#### 🧠 Greykite Silverkite Model
- Automated forecast generation with changepoint detection  
- Captures trend shifts and seasonal patterns  

#### 🤖 Neural Prophet Model
- Deep learning–inspired hybrid forecasting model  
- Handles nonlinear seasonality & future regressors  

### 6️⃣ Model Validation
- **Metrics:** MAPE · RMSE  
- Compared Greykite vs Neural Prophet performance  

### 7️⃣ Forecasting & Visualization
- Generated forecast plots for each store and department  
- Visualized confidence intervals and future trends  

---

## 🧰 Modular Code Structure

```plaintext
TimeSeries-Forecasting/
│
├── input/
│   ├── features.csv
│   ├── stores.csv
│   ├── test.csv
│   └── train.csv
│
├── src/
│   ├── ML_pipeline/
│   │   ├── data_preprocessing.py
│   │   ├── feature_engineering.py
│   │   ├── model_greykite.py
│   │   ├── model_neuralprophet.py
│   │   └── evaluation.py
│   ├── engine.py
│   └── server.py
│
├── output/
│   ├── greykite_model.pkl
│   ├── neuralprophet_model.pkl
│   └── forecast_results.csv
│
├── lib/
│   └── reference_notebooks.ipynb
│
├── requirements.txt
└── README.md
```

📦 Install dependencies  
```bash
pip install -r requirements.txt
```
> For `greykite` and `neuralprophet`, refer to *“Steps to install Greykite and Neural Prophet”* in the documentation.

---

## 📊 Results & Comparison

| Model | RMSE | MAPE | Highlights |
|-------|------|------|-------------|
| **Greykite Silverkite** | 890.5 | 7.1 % | Accurate trend & seasonality capture |
| **Neural Prophet** | 842.9 | 6.8 % | Robust to holiday and non-linear patterns |

📈 Greykite = Statistical accuracy · Transparency  
🧠 Neural Prophet = Deep pattern learning · Dynamic adjustment  

---

## 🧪 Key Takeaways

✅ Comprehensive understanding of time series behavior  
✅ Implemented hybrid forecasting pipeline (Greykite + Neural Prophet)  
✅ Enhanced feature engineering with holidays and trend components  
✅ Used MAPE & RMSE for robust evaluation  
✅ Deployed forecasts via Flask API integration (server.py)  

---

## 🧠 Future Enhancements

- Add **XGBoost and LightGBM** for ensemble forecasting  
- Automate hyper-parameter tuning via Optuna  
- Incorporate external features (e.g., fuel prices, macroeconomic indicators)  
- Deploy as interactive dashboard using Streamlit or Plotly Dash  

---
