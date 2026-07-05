# 🏢 AtliQ FMCG Data Engineering Pipeline

## 📌 Project Overview

This project demonstrates an end-to-end Data Engineering pipeline built using **Databricks**, **PySpark**, **Delta Lake**, and the **Medallion Architecture (Bronze → Silver → Gold)**.

The pipeline ingests raw FMCG sales data, performs data cleansing and transformation, and creates analytics-ready dimension tables for reporting and business intelligence.

---

## 🛠 Tech Stack

- Databricks
- PySpark
- Python
- SQL
- Delta Lake
- Unity Catalog
- Delta Change Data Feed (CDF)
- Git & GitHub

---

## 📂 Project Architecture

```
                Source CSV Files
                       │
                       ▼
              Bronze Layer (Raw Data)
                       │
        Data Validation & Profiling
                       │
                       ▼
          Silver Layer (Clean Data)
        - Remove Duplicates
        - Handle Null Values
        - Correct Data Errors
        - Standardize Formats
        - Generate Business Columns
                       │
                       ▼
          Gold Layer (Business Model)
        - Dimension Tables
        - Fact Tables
        - Analytics Ready Data
```

---

## 📁 Project Structure

```
AtliQ-Data-Engineering/
│
├── notebooks/
│   ├── 01_setup.py
│   ├── 02_bronze.py
│   ├── 03_silver_customers.py
│   ├── 04_silver_products.py
│   ├── 05_gold_customers.py
│   ├── 06_gold_products.py
│   └── utilities.py
│
├── sample_data/
│   ├── customers.csv
│   ├── products.csv
│   ├── sales.csv
│   └── stores.csv
│
├── images/
│   └── architecture.png
│
└── README.md
```

---

## 🚀 Data Pipeline

### Bronze Layer

- Ingest raw CSV files into Delta tables
- Enable Delta Change Data Feed (CDF)
- Preserve original data without modification
- Capture metadata such as:
  - File Name
  - File Size
  - Ingestion Timestamp

---

### Silver Layer

Performed data cleansing and standardization:

- Removed duplicate customer records
- Trimmed unnecessary spaces
- Corrected spelling mistakes
- Standardized city names
- Handled null values
- Generated customer business keys
- Extracted product variants using Regular Expressions
- Created derived business attributes

Example:

```
Customer Name + City
↓

John-Bengaluru
```

---

### Gold Layer

Created analytics-ready dimension tables:

- Customer Dimension
- Product Dimension

Used Delta Lake **MERGE** operations for incremental loading.

Example:

- Update existing customers/products
- Insert new customers/products

---

## ✨ Key Features

- Delta Lake Tables
- Change Data Feed (CDF)
- MERGE (Upsert)
- Incremental Processing
- Data Validation
- Duplicate Removal
- Null Handling
- Regex-based Data Cleaning
- Unity Catalog
- Medallion Architecture

---

## 📊 Sample Transformations

### Customer Data

Before

| customer_name | city |
|---------------|------|
| John | Bengaluru |
| Alice | NULL |

After

| customer |
|----------|
| John-Bengaluru |
| Alice-Unknown |

---

### Product Data

Before

```
Whey Protien (Chocolate)
```

After

```
Product : Whey Protein

Variant : Chocolate
```

---

## 📈 Business Outcome

The pipeline prepares clean, reliable, and analytics-ready datasets that can be consumed by reporting tools such as Power BI, Tableau, or downstream machine learning applications.

---

## ▶️ How to Run

1. Create Unity Catalog and Schemas.
2. Upload sample CSV files into Databricks Volumes.
3. Execute notebooks in the following order:

```
01_setup

↓

02_bronze

↓

03_silver_customers

↓

04_silver_products

↓

05_gold_customers

↓

06_gold_products
```

---

## 📌 Skills Demonstrated

- Data Engineering
- ETL Pipeline Development
- PySpark
- SQL
- Delta Lake
- Databricks
- Data Cleaning
- Data Quality
- Incremental Loading
- Git Version Control

---

## 📷 Screenshots

Add screenshots here:

- Unity Catalog
- Databricks Workflow
- Bronze Tables
- Silver Tables
- Gold Tables
- Delta History
- CDF Enabled Table
- MERGE Operation

---

## 👩‍💻 Author

**Shivangi Vaish**

Data Engineer | Python | SQL | PySpark | AWS | Databricks

GitHub: https://github.com/<your-github-username>

LinkedIn: https://linkedin.com/in/<your-linkedin-profile>
