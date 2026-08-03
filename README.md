# Data-Engineering-Project-Azure

##  Project Overview  
This project demonstrates data engineering pipelines built on Azure. It uses Azure Data Factory to build pipelines and Databricks (PySpark) for transformations. The pipeline is designed to handle incremental data loads, implement Slowly Changing Dimensions (SCD) Type 1, and organize data in a Star Schema model for analytics.

##  Architecture  


<img width="915" height="756" alt="image" src="https://github.com/user-attachments/assets/16fcfd03-0746-4979-b737-3b7941743821" />


Data Ingestion: Raw data ingested into Raw Container of Azure Data Lake Storage (ADLS)
Data Orchestration: Pipeline built in Azure Data Factory (ADF)
Data Transformation:
Data transformed using Azure Databricks (PySpark)
Transformed Data stored into Silver layer of ADLS
Implemented incremental loading logic
Applied SCD Type 1 for dimension tables
Created star schema fact & dimension tables
Data Storage: Final curated data stored in the Gold Layer of ADLS
