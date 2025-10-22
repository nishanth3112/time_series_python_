# 💼 Walmart Sales Forecasting and Demand Analytics

![Tableau](https://img.shields.io/badge/Tool-Tableau-blue)
![AWS RDS](https://img.shields.io/badge/Cloud-AWS%20RDS-orange)
![SQL Server](https://img.shields.io/badge/Database-SQL%20Server-lightgrey)
![SQL](https://img.shields.io/badge/Language-SQL-green)
![Data Visualization](https://img.shields.io/badge/Focus-Data%20Visualization-purple)
![Finance Analytics](https://img.shields.io/badge/Domain-Financial%20Analytics-yellow)
![License](https://img.shields.io/badge/License-Educational-success)

🛠️ **Tech Stack:** Tableau · AWS RDS (SQL Server) · SQL · Data Visualization  
---

## 📌 Overview

This project presents an **end-to-end financial analytics solution** built on **Tableau** to analyze and visualize **Accounts Receivable (AR)** and **Accounts Payable (AP)** data.  
By connecting Tableau directly to **AWS RDS (SQL Server)**, it computes and visualizes **key working-capital metrics** — **DSO (Days Sales Outstanding)** and **DPO (Days Payable Outstanding)** — helping enterprises improve liquidity, cash-flow visibility, and operational efficiency.

---

## 🎯 Objectives

- Enable real-time monitoring of receivables and payables through Tableau dashboards.  
- Identify inefficiencies and risks in customer payments and supplier management.  
- Apply **DSO/DPO metrics** and **Aging Buckets (0–30, 31–60, 61–90, 90+)** for financial benchmarking.  
- Enhance working-capital decision-making via interactive, KPI-driven dashboards.  

---

## 🏗️ Architecture

### 🔹 Architecture Summary

The project architecture integrates **cloud-based data storage, SQL data transformation, and Tableau visualization** into a unified pipeline:

1. **Data Source Layer (AWS RDS – SQL Server)**  
   - Stores transactional AR/AP data (invoices, payments, customers, suppliers).  
   - Queries executed to extract and aggregate key metrics.

2. **Data Preparation Layer (SQL Scripts)**  
   - SQL joins and transformations calculate:
     - Days Sales Outstanding (DSO)
     - Days Payable Outstanding (DPO)
     - Aging buckets (0–30, 31–60, 61–90, 90+ days)
   - Cleaned and structured datasets exported for Tableau.

3. **Visualization Layer (Tableau)**  
   - Two dashboards:  
     - **Accounts Receivable Dashboard** → customer collections, overdue invoices.  
     - **Accounts Payable Dashboard** → supplier payment cycles and optimization.

4. **Insights & Decision Layer**  
   - Tableau KPIs highlight top overdue accounts, supplier dependencies, and late-payment risks.

---

## ⚙️ Data Source & Integration

- **Cloud:** AWS RDS (SQL Server)  
- **Tables:** Customers, Suppliers, Invoices, Payments, Credit Limits  
- **Integration:** Tableau live connection to SQL Server using AWS credentials  

**SQL Extract Example:**
```sql
SELECT 
    CustomerID,
    InvoiceID,
    DATEDIFF(day, InvoiceDate, PaymentDate) AS DaysOutstanding,
    CASE 
        WHEN DATEDIFF(day, InvoiceDate, PaymentDate) <= 30 THEN '0–30 Days'
        WHEN DATEDIFF(day, InvoiceDate, PaymentDate) <= 60 THEN '31–60 Days'
        WHEN DATEDIFF(day, InvoiceDate, PaymentDate) <= 90 THEN '61–90 Days'
        ELSE '90+ Days'
    END AS AgingBucket,
    InvoiceAmount,
    PaymentAmount
FROM Receivables
WHERE InvoiceStatus = 'Open' OR InvoiceStatus = 'Paid';
