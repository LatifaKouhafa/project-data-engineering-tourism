# Azure Resource Group

This project is deployed within a dedicated Azure Resource Group that centralizes all cloud resources required for the data engineering platform.

The resource group provides a logical container to manage, monitor and control access to the services used throughout the data pipeline.

---

## Purpose
The Azure Resource Group was created to:
- Group all project resources in a single environment
- Simplify resource management and monitoring
- Apply consistent access control and permissions
- Support cost tracking and governance

---

## Resources Included
The resource group contains the following Azure services:
- Azure Data Factory (data ingestion and orchestration)
- Azure Data Lake Storage Gen2 (Bronze, Silver, Gold layers)
- Azure Databricks (Apache Spark data processing)
- Azure Synapse Analytics (data warehouse and SQL analytics)
- Power BI (data visualization and reporting)

---

## Security & Access
Due to Azure Student subscription limitations:
- Databricks was assigned the **Storage Blob Contributor** role directly
- RBAC was used to control access between services

In a production environment, authentication would rely on:
- Azure Active Directory App Registration
- Azure Key Vault for secure secret management

---

## Monitoring
The resource group enables centralized monitoring through:
- Azure Data Factory pipeline monitoring
- Azure Metrics for performance tracking
- Diagnostic logs for execution and failure analysis

---


<img width="741" height="385" alt="rg-azure" src="https://github.com/user-attachments/assets/88aece82-47bd-4104-9a12-6a4c1f51dc17" />
