# Enterprise Azure Data Engineering Platform using Azure Data Factory, Azure Databricks, Azure Synapse Analytics & Power BI

![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Azure Data Factory](https://img.shields.io/badge/Azure%20Data%20Factory-FF6F00?style=for-the-badge)
![Azure Databricks](https://img.shields.io/badge/Azure%20Databricks-EF3E42?style=for-the-badge&logo=databricks&logoColor=white)
![Azure Synapse](https://img.shields.io/badge/Azure%20Synapse-0078D4?style=for-the-badge)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)

---

# Project Overview

This project demonstrates an end-to-end Azure Data Engineering solution built using the Medallion Architecture (Bronze, Silver, Gold). It ingests raw sales data, transforms it with PySpark in Azure Databricks, serves curated datasets through Azure Synapse Analytics, and visualizes business insights with Power BI.

The project showcases how modern Azure services can be combined to build a scalable analytics platform suitable for reporting and decision-making.

---

# Business Problem

Organizations often receive raw business data from multiple operational systems. Raw files cannot be used directly for analytics because they may contain inconsistent formats and require transformation.

This project builds an automated Azure data pipeline that:

- Ingests raw datasets into Azure Data Lake Storage Gen2
- Cleans and transforms the data using Azure Databricks (PySpark)
- Stores curated datasets using the Medallion Architecture
- Exposes data through Azure Synapse Analytics
- Connects Power BI to Azure Synapse Analytics using the Serverless SQL Endpoint to create business reports


  # Technology Stack

| Category | Technologies |
|----------|--------------|
| Cloud Platform | Microsoft Azure |
| Data Ingestion | Azure Data Factory |
| Storage | Azure Data Lake Storage Gen2 |
| Data Processing | Azure Databricks |
| Language | Python, PySpark |
| Data Warehouse | Azure Synapse Analytics (Serverless SQL Pool) |
| Data Format | CSV, Parquet |
| Authentication | Microsoft Entra ID, Service Principal |
| Query Engine | OPENROWSET, External Tables, SQL Views |
| Reporting | Power BI |
| Version Control | GitHub |
