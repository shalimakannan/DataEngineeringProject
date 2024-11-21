
#Azure-Data Engineering  Project

This project demonstrates an end-to-end data engineering solution on Microsoft Azure, designed to handle the ingestion, transformation, and analysis of data from an on-premises SQL Server database to a comprehensive reporting platform in Power BI. The solution uses Azure Data Lake Storage Gen2, Azure Data Factory, Databricks, and Azure Synapse Analytics, with added security managed through Azure Key Vault.

![Project Pipeline Diagram](/screenshot/Ingestion.png)

# Project Overview

## Pipeline Components

1. **Self-Hosted Integration Runtime (SHIR)**:
   - Used for secure data transfer from the on-premises SQL Server to Azure. The SHIR facilitates connectivity between the on-prem environment and Azure Data Factory.

2. **Azure Data Factory (ADF)**:
   - Orchestrates the data pipeline by moving data from the on-premises SQL Server to Azure Data Lake Storage Gen2 via SHIR.
   - Performs data ingestion, using various activities to manage data flow and ensure seamless pipeline execution.

3. **Azure Data Lake Storage Gen2**:
   - Stores ingested data in Bronze, Silver, and Gold layers to manage raw, cleansed, and curated datasets, respectively.

4. **Databricks**:
   - Transforms data from the Silver layer to the Gold layer. 
   - Handles complex transformations, cleansing, and data preparation for downstream analytics.

5. **Azure Synapse Analytics**:
   - Acts as the data warehouse, loading curated data from the Gold layer for advanced analytics.
   - Enables efficient query processing and serves as the source for Power BI reporting.

6. **Azure Key Vault**:
   - Manages and secures sensitive information such as database connection strings and API keys used throughout the pipeline.

7. **Power BI**:
   - Connects to Azure Synapse Analytics for data visualization and reporting, enabling insights and analysis of the ingested and transformed data.

## Workflow

1. **Data Ingestion**:
   - Data is ingested from an on-premises SQL Server database using SHIR and ADF, moving data securely to Azure Data Lake Storage Gen2.

2. **Data Transformation**:
   - Data in the Bronze layer is cleansed and transformed into the Silver layer.
   - Databricks processes the Silver data and produces a refined dataset in the Gold layer.

3. **Data Loading and Analytics**:
   - The transformed data from the Gold layer is loaded into Azure Synapse Analytics.
   - Power BI accesses the data from Synapse to create interactive reports and visualizations.

## Security

- **Azure Key Vault** ensures the security of sensitive credentials used in the pipeline, such as database passwords and access keys.

## Conclusion

This project demonstrates how to build a scalable and secure data engineering solution on Azure, using best practices in data storage, transformation, and analytics. It leverages SHIR for secure on-premises connectivity, data layer separation in Azure Data Lake, and integration with powerful analytics and visualization tools like Azure Synapse and Power BI.

Many thanks to [Mr K. Talks Tech ](https://www.youtube.com/@mr.ktalkstech) for one of the best tutorials about data engineering on Azure that I have Found.

## Screenshots

Include relevant screenshots here to illustrate Azure workspace.

![SHIR](/screenshot/shir.png) 

![ADF](/screenshot/CaptureWholePipeline.PNG)

![Az Synapse](/screenshot/CaptureSynapse.PNG)

![Az Databricks](/screenshot/CaptureDatabricks.PNG)

![run pipeline](/screenshot/CapturePipeline.PNG)

![Azure Service](/screenshot/CaptureServices.PNG)

