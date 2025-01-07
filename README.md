# Azure Data Engineering Project E2E-ADF-ADB-Unity Catalog
## Business Scenerio
The project demonstrated the design and implementation of a robust, production-ready data pipeline using Azure’s Medallion Architecture. It utilized a sample car sales dataset from the Tableau Server Guru website, which was uploaded to my GitHub repository. By leveraging Azure services, the pipeline ensured seamless data ingestion, transformation, and storage, adhering to contemporary data governance and quality standards. The goal was to provide analytics-ready data for business insights.

## Business Requirements
Ingest car sales data from my GitHub repository into Azure SQL Database.

Transform raw data to meet analytics requirements by structuring it into fact and dimension tables.

Implement Medallion Architecture to ensure traceability, quality, and scalability.

Store the final transformed data in optimized formats for analysis.

Visualize key metrics like sales trends and revenue performance using Power BI.

## Deliverables
Python Scripts: For data transformation and storage.

Processed Data: High-quality datasets in Parquet and Delta formats.

Power BI Dashboards: Insights into sales trends and revenue.

## Specifications
Dataset: Car sales data with attributes such as Branch ID, Dealer ID, Model ID, Revenue, Units Sold, and Date ID.
![image alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/data%20description.png?raw=true)

## Project Architecture
The project followed the Medallion Architecture with distinct Bronze, Silver, and Gold layers, ensuring traceability and analytics-readiness. Pipeline Logic: Integrated incremental loading with parameterized SQL queries and dynamic configurations.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/Project%20flows.png?raw=true)

## Steps to complete the project
### 1. Environment Setup
Created a Resource Group in Azure for project resources.

Configured Azure Data Lake Storage Gen2 with a hierarchical namespace for data organization.

Established Azure SQL Database as the central processing hub and secured it with firewall rules.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/project%20resources.png?raw=true)
### 2. Data Ingestion
Extracted sales data from the GitHub repository.

Loaded the data into Azure SQL Database using Azure Data Factory’s Copy Activity.

Utilized dynamic datasets and parameterized configurations for flexibility.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/adf_pl_2.png?raw=true)
### 3. Medallion Architechture
Bronze Layer: Stored raw data as-is for traceability.

Silver Layer: Cleaned and standardized data for analytical use.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/adb-data-analytics.png?raw=true)
Gold Layer: Aggregated data into a star schema for efficient querying.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/gold%20layer.png?raw=true)
### 4. Incremental Loading
Created a watermark table in Azure SQL Database to track the last processed date.

Implemented pipeline logic with:

Lookup Activity: Retrieved the last processed date.

Parameterized SQL Queries: Fetched only new or updated records.

Stored Procedure Activity: Dynamically updated the watermark table post-pipeline execution.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/adf_pl_succeeded.png?raw=true)
### Data Transformation
Split data into fact and dimension tables using Azure Databricks.

Implemented Slowly Changing Dimensions (SCD Type 1) for effective data updates.

Converted data into Parquet and Delta formats for optimized storage and querying.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/adb_pl_data_model.png?raw=true)
### 7. Data Governance
Managed governance policies and role-based access control with Unity Catalog.

Incorporated data validation and audit mechanisms to ensure integrity.
![image_alt](https://github.com/sumitrawall/Car-Sales-End-to-End-data-pipeline/blob/main/Extras/adb_unity_catalog.png?raw=true)
### 8. Visusalization
Integrated Gold Layer data with Power BI for dashboards.

Delivered insights into sales trends and revenue performance.

Key Takeaways

Tool Proficiency: Gained expertise with Azure Data Factory, Databricks, and SQL Database.

Scalable Pipelines: Designed automated workflows to minimize manual intervention.

Dimensional Modeling: Implemented a star schema and handled slowly changing dimensions effectively.

Visualization: Created interactive dashboards in Power BI.

This project underscores my ability to independently design and implement scalable data engineering workflows, showcasing my readiness for dynamic and challenging roles in the industry.




