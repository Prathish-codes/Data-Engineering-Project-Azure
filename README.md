# Data-Engineering-Project-Azure

##  Project Overview  
This project demonstrates data engineering pipelines built on Azure. It uses Azure Data Factory to build pipelines and Databricks (PySpark) for transformations. The pipeline is designed to handle incremental data loads, implement Slowly Changing Dimensions (SCD) Type 1, and organize data in a Star Schema model for analytics.

##  Architecture  


<img width="915" height="756" alt="image" src="https://github.com/user-attachments/assets/16fcfd03-0746-4979-b737-3b7941743821" />


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

**increm_data_pipeline :**
-Implements incremental loading with watermark logic
-Writes Parquet to Bronze layer
-Updates watermark table
-Triggers Databricks notebooks to build Silver and Gold (dimensions and fact table) layer.
