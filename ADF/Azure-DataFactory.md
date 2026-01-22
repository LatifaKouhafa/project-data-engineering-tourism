# ETL Pipelines – Azure Data Factory

This folder contains the Azure Data Factory (ADF) pipelines used to orchestrate the end-to-end data ingestion and transformation workflow of the project.

The ETL process integrates heterogeneous data sources and prepares them for analytics using a cloud-based data platform.

---

## Data Sources
Two main data sources are handled by the ETL pipelines:

- **Airbnb data**
  - Source: Azure Blob Storage
  - Format: CSV files

- **Booking.com data**
  - Source: SQL Server on-premise
  - Data collected via web scraping and stored in relational tables

<img width="624" height="340" alt="importation-sqlserver" src="https://github.com/user-attachments/assets/157aca20-f709-4494-ba34-f16bc1285e3f" />

---

## Pipelines Overview

### 1. Copy Pipeline – Airbnb (Blob Storage → ADLS Gen2)
- Copies Airbnb CSV files from Azure Blob Storage
- Stores raw data in the **Bronze** container of Azure Data Lake Storage Gen2
- Acts as the ingestion layer for Airbnb datasets

<img width="527" height="341" alt="adf blob airbnb" src="https://github.com/user-attachments/assets/5ea2685c-3768-49e8-a236-e7d2f2d0d466" />


---

### 2. Copy Pipeline – Booking (SQL Server → ADLS Gen2)
- Extracts Booking.com hotel data from a SQL Server on-premise database
- Copies structured data into the **Bronze** container of Azure Data Lake Storage Gen2
- Enables hybrid (on-premise to cloud) data integration

<img width="512" height="329" alt="adf sql booking" src="https://github.com/user-attachments/assets/d81b487c-a677-41f3-a545-ef644231080f" />

---

### 3. ETL Orchestration Pipeline
This pipeline orchestrates the full transformation process:
1. Executes the Airbnb and Booking copy pipelines
2. Triggers Databricks notebooks:
   - Bronze → Silver (Airbnb)
   - Bronze → Silver (Booking)
   - Silver → Gold (data consolidation)

---

## Transformation Layer
Data transformations are executed using Apache Spark on Azure Databricks, following a **Medallion Architecture**:
- Bronze: raw ingested data
- Silver: cleaned and standardized data
- Gold: curated and analytics-ready datasets

<img width="1648" height="495" alt="ETL-pipeline" src="https://github.com/user-attachments/assets/fa1bc65e-a400-4d90-82dd-a4ae89e44073" />
---

## Scheduling
The ETL pipeline is scheduled to run **once per week (Saturday night)**,
automatically triggering the ingestion and transformation workflow.

<img width="580" height="716" alt="image" src="https://github.com/user-attachments/assets/a58c0f1a-5dd5-4884-a9cd-6a18bf1404f1" />

---
