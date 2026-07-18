
# Azure Databricks

## Overview

Azure Databricks is used to transform raw AdventureWorks datasets stored in the Bronze layer of Azure Data Lake Storage Gen2 into curated datasets stored in the Silver layer.

## Authentication

Databricks authenticates with Azure Data Lake Storage Gen2 using a Microsoft Entra ID Service Principal.

## Transformations Performed

- Read CSV files from the Bronze layer
- Converted date columns into Date data type
- Created Month and Year columns
- Performed basic aggregations
- Stored transformed datasets in Parquet format
- Wrote curated data into the Silver layer

## Technologies

- PySpark
- Azure Data Lake Storage Gen2
- Microsoft Entra ID
- Service Principal
- Parquet
