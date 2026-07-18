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


# Solution Architecture

The project follows the Medallion Architecture (Bronze, Silver, Gold) to build a scalable and maintainable Azure Data Engineering pipeline.

<p align="center">
    <img src="Architecture/AzureArchitecture.png" alt="Architecture Diagram" width="900"/>
</p>




# Project Workflow

1. Azure Data Factory connects to the AdventureWorks source datasets through an HTTP Linked Service.
2. Azure Data Factory demonstrates both **static** and **dynamic** data ingestion techniques to load raw CSV files into the **Bronze container** of Azure Data Lake Storage Gen2.
3. The Bronze container stores the raw source data without modification.
4. Azure Databricks authenticates using a Microsoft Entra ID Service Principal and processes the raw data from the Bronze container using PySpark.
5. The data is transformed by creating additional columns, converting data types, and preparing analytics-ready datasets.
6. The transformed datasets are stored as **Parquet** files in the **Silver container** of Azure Data Lake Storage Gen2.
7. Azure Synapse Analytics provides a reporting layer using **OPENROWSET**, **SQL Views**, and **External Tables**.
8. Power BI connects to the Azure Synapse Serverless SQL Endpoint to visualize the curated data.







# Repository Structure

```text
enterprise-azure-data-engineering-platform
│
├── Architecture
│   └── AzureArchitecture.png
│
├── AzureDataFactory
│   ├── Pipelines
│   ├── LinkedServices
│   ├── Datasets
│   └── Factory
│
├── AzureDatabricks
│   └── Silver
│
├── AzureSynapse
│   ├── CreateSchema.sql
│   ├── CreateViews.sql
│   ├── ExternalTables.sql
│   └── OPENROWSET.sql
│
├── Dataset
│
├── Documentation
│
├── PowerBI
│
├── Screenshots
│
└── README.md
```




# Azure Services Used

| Azure Service | Purpose |
|---------------|---------|
| Azure Data Factory | Data ingestion using HTTP Linked Service with static and dynamic pipelines |
| Azure Data Lake Storage Gen2 | Stores Bronze, Silver, and Gold datasets |
| Azure Databricks | Performs data transformation using PySpark |
| Azure Synapse Analytics | Creates Views, OPENROWSET queries, and External Tables |
| Microsoft Entra ID | Authentication and authorization |
| Service Principal | Secure access between Databricks and ADLS Gen2 |
| Power BI | Connects to Synapse Serverless SQL Endpoint for reporting |






# Key Features

- End-to-end Azure Data Engineering pipeline
- HTTP Linked Service integration in Azure Data Factory
- Static and dynamic data ingestion into Azure Data Lake Storage Gen2
- Medallion Architecture (Bronze, Silver, Gold)
- Data transformation using PySpark in Azure Databricks
- Parquet-based storage for optimized analytics
- Azure Synapse Serverless SQL using OPENROWSET, Views, and External Tables
- Power BI integration with Synapse Serverless SQL Endpoint
- Microsoft Entra ID and Service Principal authentication





AzureDataFactory
│
├── Pipelines
│     GitToRaw.json
│     GitToRaw_Dynamic.json
│
├── Datasets
│     ds_git_parameters.json
│     ds_http.json
│     ds_raw.json
│     ds_sink_dynamic.json
│
├── LinkedServices
│     HTTP.json
│     AzureDataLakeStorage.json
│
├── Screenshots
│     ADF_Pipelines.png
│     ADF_Datasets.png
│     ADF_LinkedServices.png
│
└── README.md

# Azure Data Factory

## Overview

Azure Data Factory is responsible for ingesting the AdventureWorks source datasets into Azure Data Lake Storage Gen2.

## Pipelines

### GitToRaw

- Static ingestion pipeline
- Copies source datasets from the HTTP Linked Service into the Bronze container

### GitToRaw_Dynamic

- Dynamic ingestion pipeline
- Uses parameterization to ingest multiple datasets into the Bronze container
- Demonstrates a reusable ingestion pattern

## Datasets

- HTTP Source Dataset
- Bronze Layer Dataset
- Parameter Dataset
- Dynamic Sink Dataset

## Output

Raw CSV files are stored in the Bronze container of Azure Data Lake Storage Gen2.


