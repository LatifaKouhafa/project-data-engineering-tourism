# Tourism Data Platform – Azure

End-to-end **Data Engineering project** designed to analyze tourism trends in Paris using accommodation data from Booking.com and Airbnb.

This project demonstrates the design and implementation of a **cloud-based data platform** covering data collection, ingestion, transformation, analytics and visualization.

---

## 🎯 Project Objectives
- Collect and consolidate heterogeneous tourism data
- Build a scalable **Big Data architecture on the cloud**
- Process data using a **Medallion architecture (Bronze / Silver / Gold)**
- Enable analytical queries and business insights
- Visualize key tourism indicators for decision-making

---

## 🧠 Data Sources
- **Booking**
  - Web scraping using Playwright
  - Hotel prices, ratings, reviews and metadata
- **Airbnb**
  - CSV datasets with accommodation details
    
---

## ☁️ Cloud & Big Data Architecture
The platform is implemented using **Microsoft Azure** services:

- **Azure Data Factory** – Data ingestion & orchestration  
- **Azure Data Lake Storage Gen2** – Scalable storage (Bronze / Silver / Gold)  
- **Azure Databricks (Apache Spark)** – Data transformation & enrichment  
- **Azure Synapse Analytics** – Analytical data warehouse & SQL views  
- **Power BI** – Interactive dashboards  

---

## 🔄 Data Pipeline Overview
1. **Data Collection**
   - Web scraping for Booking.com
   - CSV ingestion for Airbnb
2. **Ingestion**
   - Automated pipelines with Azure Data Factory
   - Hybrid sources (Blob Storage & SQL Server on-premise)
3. **Transformation**
   - Spark processing on Databricks
   - Medallion architecture with Delta Lake
4. **Analytics**
   - SQL views and queries in Azure Synapse
5. **Reporting**
   - Interactive dashboards in Power BI

---

## 📊 Key Insights
- Price distribution across Paris neighborhoods
- Comparison between hotels and Airbnb listings
- Relationship between ratings and pricing
- Identification of highly rated and high-demand areas

---

## 🧩 RNCP Competencies
This project validates **RNCP B1 & B2** competencies:

B1 : Design and develop a data storage architecture

B2: Design, develop, and deploy a big data processing solution

---

<img width="1508" height="982" alt="Capture d&#39;écran 2026-01-23 003431" src="https://github.com/user-attachments/assets/e6d68b07-9cdb-4043-8321-14401316427e" />


