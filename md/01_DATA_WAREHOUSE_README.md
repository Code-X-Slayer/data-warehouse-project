# 📊 Project 1: SQL Data Warehouse (Medallion Architecture)

> **Building a Production-Grade Data Warehouse with Layered ETL Pipelines**

---

# 🎯 Project Overview

This project implements a **Medallion Architecture** data warehouse pattern using SQL Server. It demonstrates enterprise-level ETL pipelines, layered transformations, and analytics-ready dimensional modeling.

The warehouse follows a structured three-layer architecture:

- 🥉 Bronze → Raw ingestion
- 🥈 Silver → Cleansed & transformed data
- 🥇 Gold → Business-ready analytical models

---

# 🏗️ Repository Structure

├── 📄 [LICENSE](../LICENSE)  
├── 📄 [README_MAIN.md](../README_MAIN.md)  

├── 📁 [datasets](../datasets)  
│   ├── 📁 [source_crm](../datasets/source_crm)  
│   │   ├── 📄 [cust_info.csv](../datasets/source_crm/cust_info.csv)  
│   │   ├── 📄 [prd_info.csv](../datasets/source_crm/prd_info.csv)  
│   │   └── 📄 [sales_details.csv](../datasets/source_crm/sales_details.csv)  
│   │
│   └── 📁 [source_erp](../datasets/source_erp)  
│       ├── 📄 [CUST_AZ12.csv](../datasets/source_erp/CUST_AZ12.csv)  
│       ├── 📄 [LOC_A101.csv](../datasets/source_erp/LOC_A101.csv)  
│       └── 📄 [PX_CAT_G1V2.csv](../datasets/source_erp/PX_CAT_G1V2.csv)  

├── 📁 [docs](../docs)  
│   ├── 📄 [data_catalog.md](../docs/data_catalog.md)  
│   ├── 🖼️ [data_flow.png](../docs/data_flow.png)  
│   ├── 🖼️ [data_model.png](../docs/data_model.png)  
│   ├── 🖼️ [dw_architecture.png](../docs/dw_architecture.png)  
│   ├── 🖼️ [integration_model.png](../docs/integration_model.png)  
│   ├── 📄 [master.drawio](../docs/master.drawio)  
│   └── 📄 [naming_conventions.md](../docs/naming_conventions.md)  

├── 📁 [md](../md)  
│   ├── 📄 [01_DATA_WAREHOUSE_README.md](../md/01_DATA_WAREHOUSE_README.md)  
│   ├── 📄 [02_EDA_README.md](../md/02_EDA_README.md)  
│   └── 📄 [03_ADVANCED_ANALYTICS_README.md](../md/03_ADVANCED_ANALYTICS_README.md)  

└── 📁 [scripts](../scripts)  
    ├── 📁 [01_data_warehouse](../scripts/01_data_warehouse)  
    │   ├── 📁 [bronze](../scripts/01_data_warehouse/bronze)  
    │   │   ├── 📄 [ddl_bronze.sql](../scripts/01_data_warehouse/bronze/ddl_bronze.sql)  
    │   │   └── 📄 [proc_load_bronze.sql](../scripts/01_data_warehouse/bronze/proc_load_bronze.sql)  
    │   │
    │   ├── 📁 [silver](../scripts/01_data_warehouse/silver)  
    │   │   ├── 📄 [ddl_silver.sql](../scripts/01_data_warehouse/silver/ddl_silver.sql)  
    │   │   └── 📄 [proc_load_silver.sql](../scripts/01_data_warehouse/silver/proc_load_silver.sql)  
    │   │
    │   ├── 📁 [gold](../scripts/01_data_warehouse/gold)  
    │   │   └── 📄 [ddl_gold.sql](../scripts/01_data_warehouse/gold/ddl_gold.sql)  
    │   │
    │   ├── 📁 [tests](../scripts/01_data_warehouse/tests)  
    │   │   ├── 📄 [quality_checks_gold.sql](../scripts/01_data_warehouse/tests/quality_checks_gold.sql)  
    │   │   └── 📄 [quality_checks_silver.sql](../scripts/01_data_warehouse/tests/quality_checks_silver.sql)  
    │   │
    │   ├── 📄 [init_database.sql](../scripts/01_data_warehouse/init_database.sql)  
    │   └── 📁 [raw_practice](../scripts/01_data_warehouse/raw_practice)  
    │
    ├── 📁 [02_eda](../scripts/02_eda)  
    │   ├── 📄 [00_init_database.sql](../scripts/02_eda/00_init_database.sql)  
    │   ├── 📄 [01_database_exploration.sql](../scripts/02_eda/01_database_exploration.sql)  
    │   ├── 📄 [02_dimensions_exploration.sql](../scripts/02_eda/02_dimensions_exploration.sql)  
    │   ├── 📄 [03_date_range_exploration.sql](../scripts/02_eda/03_date_range_exploration.sql)  
    │   ├── 📄 [04_measures_exploration.sql](../scripts/02_eda/04_measures_exploration.sql)  
    │   ├── 📄 [05_magnitude_analysis.sql](../scripts/02_eda/05_magnitude_analysis.sql)  
    │   └── 📄 [06_ranking_analysis.sql](../scripts/02_eda/06_ranking_analysis.sql)  
    │
    ├── 📁 [03_advaced_analytics](../scripts/03_advaced_analytics)  
    │   ├── 📄 [07_change_over_time_analysis.sql](../scripts/03_advaced_analytics/07_change_over_time_analysis.sql)  
    │   ├── 📄 [08_cumulative_analysis.sql](../scripts/03_advaced_analytics/08_cumulative_analysis.sql)  
    │   ├── 📄 [09_performance_analysis.sql](../scripts/03_advaced_analytics/09_performance_analysis.sql)  
    │   ├── 📄 [10_part_to_whole_analysis.sql](../scripts/03_advaced_analytics/10_part_to_whole_analysis.sql)  
    │   └── 📄 [11_data_segmentation.sql](../scripts/03_advaced_analytics/11_data_segmentation.sql)  
    │
    ├── 📁 [04_reports](../scripts/04_reports)  
    │   ├── 📄 [12_customer_report.sql](../scripts/04_reports/12_customer_report.sql)  
    │   └── 📄 [13_product_report.sql](../scripts/04_reports/13_product_report.sql)  
    │
    └── 📁 [raw_practice](../scripts/raw_practice)  
        ├── 📄 [adv_eda.sql](../scripts/raw_practice/adv_eda.sql)  
        ├── 📄 [cust_report.sql](../scripts/raw_practice/cust_report.sql)  
        ├── 📄 [eda.sql](../scripts/raw_practice/eda.sql)  
        ├── 📄 [gold_dim_products.sql](../scripts/raw_practice/gold_dim_products.sql)  
        ├── 📄 [prod_report.sql](../scripts/raw_practice/prod_report.sql)  
        ├── 📄 [silver_crm_cust_info.sql](../scripts/raw_practice/silver_crm_cust_info.sql)  
        ├── 📄 [silver_crm_prd_info.sql](../scripts/raw_practice/silver_crm_prd_info.sql)  
        ├── 📄 [silver_crm_sales_detials.sql](../scripts/raw_practice/silver_crm_sales_detials.sql)  
        ├── 📄 [silver_erp_cust_az12.sql](../scripts/raw_practice/silver_erp_cust_az12.sql)  
        ├── 📄 [silver_erp_loc_a101.sql](../scripts/raw_practice/silver_erp_loc_a101.sql)  
        └── 📄 [silver_erp_px_cat_g1v2.sql](../scripts/raw_practice/silver_erp_px_cat_g1v2.sql)  

---

# 🏗️ Architecture: Visual Overview

## 📐 Architecture Diagram

![Data Warehouse Architecture Flow](../docs/dw_architecture.png)

The Medallion Architecture consists of three layers:

- 🥉 Bronze → Raw Data
- 🥈 Silver → Cleansed Data
- 🥇 Gold → Analytics Models

---

## 🔗 Integration Model

![Integration Model](../docs/integration_model.png)

Shows how CRM and ERP systems are integrated into a unified warehouse.

---

## ⭐ Data Model (Star Schema)

![Data Model Diagram](../docs/data_model.png)

### Core Components

### Fact Table
- `gold.fact_sales`

### Dimension Tables
- `gold.dim_customers`
- `gold.dim_products`
- `gold.dim_dates`

The star schema improves analytical query performance and reporting efficiency.

---

## 🔄 Data Flow Diagram

![Data Flow Diagram](../docs/data_flow.png)

Illustrates the ETL pipeline from ingestion to analytics-ready reporting models.

---

# 🥉 Bronze Layer — Raw Ingestion

## Purpose
Store raw source-system data exactly as received.

## Responsibilities
- Raw CSV ingestion
- Audit preservation
- Data lineage tracking
- Source fidelity

## Scripts

- 📄 [ddl_bronze.sql](../scripts/01_data_warehouse/bronze/ddl_bronze.sql)
- 📄 [proc_load_bronze.sql](../scripts/01_data_warehouse/bronze/proc_load_bronze.sql)

## Source Tables
- `bronze.cust_info`
- `bronze.prd_info`
- `bronze.sales_details`

---

# 🥈 Silver Layer — Cleansing & Transformation

## Purpose
Apply transformations, validations, and business rules.

## Responsibilities
- Null handling
- Deduplication
- Standardization
- Type conversion
- Validation

## Scripts

- 📄 [ddl_silver.sql](../scripts/01_data_warehouse/silver/ddl_silver.sql)
- 📄 [proc_load_silver.sql](../scripts/01_data_warehouse/silver/proc_load_silver.sql)

## Quality Rules

- Customer key cannot be NULL
- Sales amount > 0
- No duplicate records
- Valid order dates

---

# 🥇 Gold Layer — Analytics Models

## Purpose
Deliver business-ready dimensional models.

## Responsibilities
- Star schema design
- Fact/dimension modeling
- Reporting optimization
- Business metrics

## Scripts

- 📄 [ddl_gold.sql](../scripts/01_data_warehouse/gold/ddl_gold.sql)

## Core Tables

### Fact Table
- `gold.fact_sales`

### Dimensions
- `gold.dim_customers`
- `gold.dim_products`
- `gold.dim_dates`

---

# 🚀 Setup & Execution

## Step 1 — Initialize Database

```sql
:r ../scripts/01_data_warehouse/init_database.sql
```

---

## Step 2 — Load Bronze Layer

```sql
:r ../scripts/01_data_warehouse/bronze/ddl_bronze.sql
:r ../scripts/01_data_warehouse/bronze/proc_load_bronze.sql
EXEC bronze.load_bronze;
```

---

## Step 3 — Load Silver Layer

```sql
:r ../scripts/01_data_warehouse/silver/ddl_silver.sql
:r ../scripts/01_data_warehouse/silver/proc_load_silver.sql
EXEC silver.load_silver;
```

---

## Step 4 — Create Gold Layer

```sql
:r ../scripts/01_data_warehouse/gold/ddl_gold.sql
```

---

## Step 5 — Run Quality Checks

```sql
:r ../scripts/01_data_warehouse/tests/quality_checks_silver.sql
:r ../scripts/01_data_warehouse/tests/quality_checks_gold.sql
```

---

# 📊 Data Sources

## CRM Source

📁 [source_crm](../datasets/source_crm)

- 📄 [cust_info.csv](../datasets/source_crm/cust_info.csv)
- 📄 [prd_info.csv](../datasets/source_crm/prd_info.csv)
- 📄 [sales_details.csv](../datasets/source_crm/sales_details.csv)

---

## ERP Source

📁 [source_erp](../datasets/source_erp)

- 📄 [CUST_AZ12.csv](../datasets/source_erp/CUST_AZ12.csv)
- 📄 [LOC_A101.csv](../datasets/source_erp/LOC_A101.csv)
- 📄 [PX_CAT_G1V2.csv](../datasets/source_erp/PX_CAT_G1V2.csv)

---

# 🧪 Data Quality Framework

## Quality Check Scripts

- 📄 [quality_checks_silver.sql](../scripts/01_data_warehouse/tests/quality_checks_silver.sql)
- 📄 [quality_checks_gold.sql](../scripts/01_data_warehouse/tests/quality_checks_gold.sql)

---

# 🔗 Related Documentation

- 🖼️ [Architecture Diagram](../docs/dw_architecture.png)
- 🖼️ [Data Model](../docs/data_model.png)
- 🖼️ [Data Flow](../docs/data_flow.png)
- 📄 [Data Catalog](../docs/data_catalog.md)
- 📄 [Naming Conventions](../docs/naming_conventions.md)

---

# 🎓 Credits

This project is inspired by the SQL Master Class created by :contentReference[oaicite:0]{index=0}.

Happy Learning 🚀