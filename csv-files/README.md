# CSV Data Description

This folder contains the original and intermediate CSV files used during the
data collection and preprocessing phases of the project.

These files represent different stages of the data lifecycle before being
ingested into the Azure-based data platform (Data Lake, Databricks, Synapse).

---

## 📄 File Descriptions

### `airbnb-listings.csv`
- Airbnb accommodation listings for **year 2023**
- Raw source dataset before cloud ingestion
- Contains prices, ratings, reviews, location and listing metadata
- Used as input for the *Bronze → Silver (Airbnb 2023)* transformation

---

### `airbnb-listings-2024.csv`
- Airbnb accommodation listings for **year 2024**
- Raw source dataset used for year-over-year analysis
- Ingested into the Bronze layer and processed with Spark

---

### `airbnb_listings_structurees.csv`
- Cleaned and structured Airbnb dataset
- Columns renamed and normalized
- Represents an **intermediate cleaned version** (pre-cloud / pre-Silver)
- Used mainly for validation and exploratory analysis

---

### `filtered_airbnb_listings.csv`
- Filtered Airbnb dataset
- Contains a subset of listings (e.g. Paris only, valid prices, selected features)
- Used for analytical testing and business exploration

---

### `hotel-booking.csv`
- Hotel data collected from **:contentReference[oaicite:0]{index=0}**
- Generated via web scraping using Playwright
- Contains hotel prices, ratings, reviews and hotel characteristics
- Initially stored in a SQL Server on-premise database, then ingested into Azure Data Lake

---

## ⚠️ Important Note
These CSV files are **not used directly in production analytics**.

In the final architecture:
- Data is stored in **Azure Data Lake Storage Gen2**
- Transformed using **Apache Spark on Databricks**
- Saved in **Parquet / Delta Lake format**
- Modeled and queried via **Azure Synapse Analytics**

This folder is kept for **documentation, traceability and reproducibility purposes**.
