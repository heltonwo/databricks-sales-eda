# 📊 Databricks Sales & Customer Insights EDA

An End-to-End Exploratory Data Analysis (EDA) project built natively on the 
Databricks Lakehouse platform using SQL and Delta Lake architecture.

![Sales & Customer Insights Dashboard](03_images/Databricks-Dashboard-01.png)

## 📌 Project Overview

This project transforms raw transactional sales data into structured, 
analytics-ready tables to evaluate company health, product category behavior, 
and customer demographics. The entire pipeline follows data engineering best 
practices, including an isolated catalog, layered data architecture, syntax 
troubleshooting, and an executive-ready dashboard.

## 🏗️ Data Architecture (Medallion Structure)

Instead of using shared course environments, a fully isolated catalog named 
`sales_project_db` was deployed to manage the data lifecycle across two 
explicit layers:

1. **Bronze Layer** (`sales_project_db.bronze`): Raw, ingestion-level table 
   replicas directly mirroring historical event data.
2. **Silver Layer** (`sales_project_db.silver`): Fully cleaned, decoupled 
   dimensional schemas with standardized data types, concatenated attributes 
   (e.g., customer full names), and verified foreign keys ready for consumption.

## 📂 Repository Structure

```
databricks-sales-eda/
├── 00_data/                         # Raw source CSV files
├── 01_data_engineering/             # Bronze & Silver layer creation scripts
├── 02_analytics_eda/                # EDA notebooks (D1, D2, D3) + Dashboard.md
├── 03_images/                       # Dashboard and chart exports
├── Documentation-EDA-D1-D2-D3.ipynb # Full technical documentation
└── README.md
```

## 🔍 Key Insights Tracked

- **Sales Performance:** historical revenue tracking and average ticket growth.
- **Product Catalog:** identification of high-value categories vs. high-volume items.
- **Customer Demographics:** customer purchasing behavior segmented by age group.

## 📈 Executive Summary & Business Insights

1. **Revenue Growth Trend** — historical data shows consistent, long-term 
   revenue growth, with notable cyclical seasonal spikes toward the end of 
   each fiscal year.
2. **Product Performance Discrepancy**
   - *Bikes* is the primary revenue engine, generating over $20M in total sales.
   - *Accessories* dominates operational volume, with over 30,000 individual 
     transactions recorded.
3. **Target Demographics** — the highest-value customer segments are 
   concentrated in older age groups (50-59 and 60+), each generating over 
   $10M in total revenue.

## 🛠️ Tech Stack

- **Platform:** Databricks Lakehouse
- **Language:** SQL
- **Storage Format:** Delta Lake
- **Architecture:** Medallion (Bronze / Silver)
- **Visualization:** Databricks SQL Dashboards

## 🧠 Skills Demonstrated

- Multi-table joins (`LEFT JOIN`, `INNER JOIN`) with clean alias conventions
- `CREATE TABLE AS SELECT` (CTAS) for persistent table creation
- Unity Catalog isolation and schema management
- Medallion architecture implementation in a Lakehouse environment
- Data cleaning, type standardization, and dimensional modeling
- SQL debugging (syntax errors, delimiter handling, execution context switching)

## 📁 Data Source

The dataset used in this project was sourced from **DataWithBaraa** 


## 🚀 How to Reproduce

1. Clone this repository into a Databricks Repo.
2. Run the scripts in `01_data_engineering` in order (Step 1 → Step 2 → Step 3) 
   to create the Bronze and Silver layers.
3. Run the notebooks in `02_analytics_eda` (D1 → D2 → D3) to generate the 
   analytical tables and visualizations.
4. Publish the dashboard from the queries in D1–D3, or explore the pre-built 
   one referenced in `02_analytics_eda/Dashboard.md`.
