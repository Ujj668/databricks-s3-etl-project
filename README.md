**Databricks + AWS S3 ETL Pipeline**

**#Project Overview**
An end-to-end ETL (Extract, Transform, Load) pipeline built using
Databricks and AWS S3, processing NYC Taxi Zone data with 
PySpark and Pandas, storing results as Delta tables.

**#Architecture**
AWS S3 (Raw CSV)
↓
Databricks (PySpark - Read)
↓
Pandas (Clean & Transform)
↓
Delta Tables (Load)
↓
SQL Queries (Analysis

**#Tech Stack**
| Tool | Purpose |
|------|---------|
| AWS S3 | Raw data storage |
| Databricks Community Edition | Cloud compute platform |
| PySpark | Data ingestion from S3 |
| Pandas | Data cleaning & transformation |
| Delta Lake | ACID compliant final storage |
| SQL | Data querying & analysis |

## ETL Steps

### Extract
- Stored raw CSV in AWS S3 bucket
- Connected Databricks to S3 using IAM credentials
- Read data into Databricks using PySpark

### Transform
- Removed invalid Borough values (`N/A`, `Unknown`)
- Removed duplicates and null values
- Standardized text columns to consistent format
- Added `is_yellow_zone` flag (Yes/No)
- Added `is_airport_zone` flag (Yes/No)
- Added `borough_category` (Core / Outer / Other)
- Created aggregated summary by Borough + Service Zone

### Load
- Saved cleaned data as Delta table `taxi_zones_clean`
- Saved aggregated data as Delta table `taxi_zones_summary`
- Queried tables using Spark SQL

- ## Key Learnings
- Connecting AWS S3 to Databricks using IAM Access Keys
- Difference between PySpark and Pandas DataFrames
- Converting between Spark ↔ Pandas DataFrames
- Writing and querying Delta tables
- Real-world data quality issues (string nulls, inconsistent values)



## Author
**Ujjwal Tyagi**  
Data Engineer  
[GitHub](https://github.com/Ujj668) | [LinkedIn](https://www.linkedin.com/in/ujjwal-tyagi-758004148/)
