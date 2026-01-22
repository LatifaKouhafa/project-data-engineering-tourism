# Azure Data Lake Storage – Bronze / Silver / Gold

This project uses Azure Data Lake Storage Gen2 as the central storage layer for all raw, processed and curated datasets.

The storage account is organized following the **Medallion Architecture** to ensure data quality, traceability and scalability.

---

## Container Structure

### Bronze
- Stores raw and unmodified data
- Contains CSV and Parquet files ingested from:
  - Booking.com web scraping
  - Airbnb source datasets
- Acts as the immutable data ingestion layer

---

### Silver
- Stores cleaned and standardized datasets
- Data is processed using Apache Spark on Azure Databricks
- Includes:
  - Deduplication
  - Handling of missing values
  - Column normalization
- Data is stored in Delta Lake format

---

### Gold
- Stores curated and analytics-ready datasets
- Contains enriched and aggregated data
- Optimized for querying via Azure Synapse Analytics and Power BI
- Represents the single source of truth for reporting

---

## Access & Security
Access to the storage account is controlled using Azure RBAC.

Due to Azure Student subscription limitations, Databricks was granted direct
access via the **Storage Blob Contributor** role.

In a production environment, access would be secured using:
- Azure Active Directory App Registration
- Azure Key Vault for secret management


<img width="959" height="312" alt="storageaccount - containers" src="https://github.com/user-attachments/assets/e2b05eb5-ed7e-4711-9abe-1bbbfbd02a49" />

<img width="278" height="242" alt="blob" src="https://github.com/user-attachments/assets/c66ba326-6e10-4702-8e3f-4d5197d6ec13" />

<img width="331" height="256" alt="bronze" src="https://github.com/user-attachments/assets/a88de23f-6c00-4ccb-bc26-acc0d0b3e3f4" />

<img width="374" height="335" alt="silver" src="https://github.com/user-attachments/assets/1dab9456-37f2-4754-afc5-e4d769eee403" />

