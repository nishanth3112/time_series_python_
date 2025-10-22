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

The architecture connects **data ingestion → processing → model training → forecast visualization**.

