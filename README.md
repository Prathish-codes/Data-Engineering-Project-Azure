# Data-Engineering-Project-Azure

##  Project Overview  
This project demonstrates data engineering pipelines built on Azure. It uses Azure Data Factory to build pipelines and Databricks (PySpark) for transformations. The pipeline is designed to handle incremental data loads, implement Slowly Changing Dimensions (SCD) Type 1, and organize data in a Star Schema model for analytics.

##  Architecture  


<img width="915" height="756" alt="image" src="https://github.com/user-attachments/assets/16fcfd03-0746-4979-b737-3b7941743821" />

<img width="1078" height="601" alt="image" src="https://github.com/user-attachments/assets/b9446e3a-e3e1-4200-8a26-404cd1f14e78" />



- **Data Ingestion:** Raw data ingested into Raw Container of Azure Data Lake Storage (ADLS)
- **Data Orchestration:** Pipeline built in Azure Data Factory (ADF)
- **Data Transformation:** Data transformed using Azure Databricks (PySpark)
- **Storage:** Transformed data stored in the Silver layer of ADLS
- **Incremental Loading:** Implemented incremental loading logic
- **SCD Type 1:** Applied SCD Type 1 for dimension tables
- **Star Schema:** Created fact and dimension tables
- **Gold Layer:** Final curated data stored in the Gold layer of ADLS


##  Azure Data Factory Pipelines

**source_prep :** Ingests raw CSV data into Azure SQL Database (source_data table) using Copy activity with column mappings.







## Tech Stack

- **SQL Server** – Source database
- **Azure Data Factory (ADF)** – Pipeline orchestration and data ingestion
- **Azure Data Lake Storage Gen2 (ADLS)** – Bronze, Silver, and Gold storage layers
- **Azure Databricks (PySpark)** – Data transformation and business logic
- **Delta Lake** – ACID transactions and optimized storage
- **Star Schema** – Analytics data model

## Pipeline: increm_data_pipeline

- Reads only new and updated records using **watermark-based incremental loading**
- Extracts data from SQL Server
- Writes raw data as **Parquet** files to the **Bronze** layer
- Updates the watermark table after successful ingestion
- Triggers Databricks notebooks for Silver and Gold processing
- Creates dimension and fact tables in the Gold layer
-Triggers Databricks notebooks to build Silver and Gold (dimensions and fact table) layer.
