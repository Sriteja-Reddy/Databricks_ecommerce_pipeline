# Databricks_ecommerce_pipeline

An end-to-end data engineering project built on Databricks using 
real Brazilian E-Commerce data from Olist. Implements Medallion 
Architecture with automated pipeline, incremental loading, 
data quality checks and interactive dashboard.



#Architecture

Raw CSV Files (Kaggle)
↓
Bronze Layer — Raw Delta tables (no transformations)
↓
Silver Layer — Cleaned, joined master table
↓
Gold Layer — Business metrics and aggregations
↓
Databricks Dashboard - Interactive visualizations



#Tech Stack

- Platform: Databricks Free Edition
- Language: Python, PySpark, SQL
- Storage: Delta Lake
- Orchestration: Databricks Jobs and Workflows
- Visualization: Databricks SQL Dashboard
- Dataset: Olist Brazilian E-Commerce (100k+ records)




#Project Structure

| Notebook | Layer | Description |
| 01_bronze_incremental | Bronze | Incremental data ingestion with watermark |
| 02_silver_layer | Silver | Data cleaning, deduplication and joins |
| 03_gold_layer | Gold | Business metric aggregations |
| 04_data_quality_checks | Monitoring | Data validation and quality reporting |
| 05_delta_time_travel | Auditing | Version history and time travel queries |



#Key Features

**Medallion Architecture**
- Bronze: Raw data ingested as Delta tables
- Silver: Cleaned and joined master table with 30 columns
- Gold: 5 business metric tables ready for reporting

**Incremental Loading**
- Watermark based incremental loading
- MERGE operation for upserts
- Only processes new data on each run
- Prevents duplicate processing

**Automated Pipeline**
- 3 task workflow: Bronze → Silver → Gold
- Scheduled to run every day at 6am IST
- Email notifications on success and failure
- Task dependencies ensure correct execution order

**Data Quality Checks**
- Row count validation across all layers
- Null checks on critical columns
- Duplicate detection
- Caught real data issue: 3 orders with missing payment values

**Delta Time Travel**
- Full version history of all tables
- Query data at any previous version
- Instant data recovery if corruption occurs




#Dashboard

Built on Databricks SQL Dashboard with:
- Monthly revenue trend (bar chart)
- Top 10 product categories by revenue (bar chart)
- Top 10 states by orders (bar chart)
- Payment type distribution (pie chart)




#Key Insights

- Total orders: 96,478
- Total revenue: R$ 19.7 Million
- Average order value: R$ 204
- Peak month: August (highest revenue)
- Top state: São Paulo (SP)
- Top category: Bed, Bath and Table (cama_mesa_banho)
- Most popular payment: Credit card




#How to Run

1. Sign up for Databricks Free Edition
2. Upload Olist dataset CSVs to a Volume
3. Run notebooks in order:
   - 01_bronze_incremental
   - 02_silver_layer
   - 03_gold_layer
4. Set up Jobs and Pipelines for automation
5. Create SQL Dashboard on Gold tables




# Dataset

Olist Brazilian E-Commerce Public Dataset
- Source: Kaggle
- Records: 100,000+ orders
- Period: 2016 to 2018
- Tables: orders, customers, products, payments, order items



#Author

Sriteja Reddy
- LinkedIn: (www.linkedin.com/in/punnam-sriteja)
- Email: sritejareddy18@gmail.com
