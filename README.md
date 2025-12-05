# E‑commerce Data Pipeline on Databricks

Welcome to the **E‑commerce Data Pipeline on Databricks** repository. 🚀
This project implements an end‑to‑end data engineering workflow on Databricks, using the Medallion Architecture (Bronze → Silver → Gold) to build an analytics‑ready dataset for an online retail business.

---
## 🏗️ Data Architecture

The data architecture for this project follows Medallion Architecture **Bronze**, **Silver**, and **Gold** layers:
<img width="17234" height="7528" alt="databricks_architecture" src="https://github.com/user-attachments/assets/6c6226bc-ff8e-484f-a6f4-42df4e5c5023" />
<img width="18554" height="7390" alt="legacy_architecture" src="https://github.com/user-attachments/assets/71176b23-5945-4c26-9c66-de59ae6fb43c" />


1. **Bronze Layer**: Ingests raw CSV files (orders, customers, products, brands, categories, dates) into Delta tables with minimal transformation, preserving the original data.
2. **Silver Layer**: Cleans, standardizes, and models data into dimension tables (customers, products, brands, categories, dates) with business‑friendly column names and data types.
3. **Gold Layer**: Builds fact tables for e‑commerce orders and denormalized views that are optimized for reporting, Genie queries, and dashboarding.

---
## 📖 Project Overview

This project demonstrates how to go from raw files to business insights using Databricks Free Edition.

### Key objectives:
1. Design and implement a Medallion‑style lakehouse for an e‑commerce use case.​
2. Build incremental data processing notebooks for dimension and fact tables using Spark and Delta Lake.​​
3. Expose curated data for self‑service analytics through Genie and simple BI dashboards.

🎯 This repository is suitable to showcase skills in:
- Databricks & Spark data engineering
- Medallion architecture and Delta Lake
- ETL / ELT pipeline development 
- Data modeling for analytics (dimensions and facts) 
- SQL‑based analysis and dashboarding  

---

## 🛠️ Tech Stack & Tools

- **Platform:** Databricks Free Edition (Unity Catalog, Workflows)
- **Processing:** PySpark / Spark SQL, Delta Lake tables
- **Storage format:** Delta (Bronze, Silver, Gold tables)
- **Analytics:** Databricks SQL, Genie, Databricks dashboards

---

## 🚀 Project Requirements

High‑level business requirement: build a reliable analytics layer for an e‑commerce company’s order data so stakeholders can analyze customers, products, and sales performance.

#### Main engineering requirements:

1. Ingest order data from CSV files into Databricks using the Bronze layer.​​
2. Clean and standardize data, resolving data‑quality issues (nulls, types, basic validation) in the Silver layer.​
3. Model Gold‑layer fact and dimension tables to support reporting on customers, products, brands, categories, and daily sales.​​
4. Provide a denormalized table or view for Genie and dashboard queries.

#### Analytics requirements:

1. Analyze customer behavior (order counts, revenue, repeat customers).​​
2. Evaluate product and brand performance (top sellers, revenue, discount impact).​​
3. Track sales trends over time using the date dimension (daily, monthly, seasonal views).

---

## 📂 Repository Structure
```
databricks-ecommerce-medallion/
│
├── 0_data/                               # Raw input data files
│   └── order_items/
│       ├── brands.csv
│       ├── category.csv
│       ├── customers.csv
│       ├── date.csv
│       └── products.csv
│
├── 1_codes/                              # Databricks notebooks (exported as .ipynb)
│   ├── 1_setup/
│   │   └── setup_catalog.ipynb           # Catalog, schemas, and initial configuration
│   │
│   ├── 2_medallion_processing_dim/
│   │   ├── 1_dim_bronze.ipynb            # Load raw dimension data into Bronze tables
│   │   ├── 2_dim_silver.ipynb            # Clean and standardize dimension data (Silver)
│   │   └── 3_dim_gold.ipynb              # Create dimension tables for analytics (Gold)
│   │
│   ├── 3_medallion_processing_fact/
│        ├── 1_fact_bronze.ipynb           # Load raw order/fact data into Bronze
│        ├── 2_fact_silver.ipynb           # Transform and join for clean fact tables (Silver)
│        └── 3_fact_gold.ipynb             # Final fact tables and denormalized views (Gold)
│   
│── 2_genie_exploration/
│       └── questions.txt                 # Sample Genie prompts and business questions
│
├── 3_dashboard/
│   ├── dashboard.png                     # Screenshot of Databricks dashboard
│   └── denormalise_table_query.sql       # SQL query used for the dashboard / Genie
│
├── LICENSE                               # Project license
├── README.md                             # Project overview and usage instructions
└── databricks_architecture.png
└── legacy_architecture.png

```
---

## 🛡️ License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and share this project with proper attribution.

## 🌟 About Me

Hi! This project is maintained by **Er. Srijan Khadka**, an aspiring data engineer building end‑to‑end cloud data projects with Databricks, SQL, and modern data architecture.
