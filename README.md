# Fintech-CDC Data Integration Pipeline

This project demonstrates a **data integration pipeline** for migrating historical data from an SQL Database into the **Azure Cloud** using various Azure services like **Azure Synapse Analytics**, **Azure Data Lake Storage (ADLS)**, and **Delta Tables**. It also leverages **PySpark** for data transformations. The pipeline is built with a multi-layered architecture following the **Bronze-Silver-Gold** data model.

## Project Overview

The **Fintech-CDC Data Integration Pipeline** efficiently moves historical data from SQL databases into Azure, processes the data using PySpark notebooks, and stores it in **Delta Tables** for real-time analytics and reporting. The pipeline supports **incremental data migration** and transformation across multiple stages of data processing, ensuring reliable and automated workflows.

## Tech Stack

- **Azure Synapse Analytics**
- **Azure SQL Database**
- **Azure Data Lake Storage (ADLS)**
- **Delta Tables**
- **PySpark**
- **Python**

## Pipeline Architecture

### 1. **Data Ingestion:**
   - Historical data from SQL Database tables is moved into **ADLS** in the **Bronze Layer** using an **Azure Synapse Pipeline**.
   - The data ingestion process captures both full-load and incremental changes for efficient data movement.

### 2. **Data Transformation:**
   - **PySpark notebooks** are used for transforming the data across different layers:
     - **Bronze to Silver Transformation**: Raw data is cleaned, transformed, and written to the **Silver Layer** as **Delta Tables**.
     - **Silver to Gold Transformation**: Further transformations and enrichment are done, and the final data is stored in the **Gold Layer**.

### 3. **Automated Pipeline Execution:**
   - The entire process is orchestrated using **Azure Synapse Pipelines** for sequential and automated execution.

## Key Features

- **End-to-End Data Pipeline**: Ingest, transform, and store data using Azure Synapse and Delta Tables.
- **Bronze-Silver-Gold Data Architecture**: A layered approach to data processing for raw, clean, and enriched data.
- **PySpark-Based Data Transformations**: Leverages PySpark for handling large-scale data efficiently.
- **Automated and Incremental Data Loads**: Supports CDC (Change Data Capture) for incremental data loading and automated pipeline execution.
### Synapse Pipeline
![image](https://github.com/user-attachments/assets/cec7de0e-2005-41ba-80cd-4d8a8aa38bb2)

### ADLS Containers
![image](https://github.com/user-attachments/assets/4ecde48a-4a23-44b7-8bc9-09392216cc25)

### SQL Database
![image](https://github.com/user-attachments/assets/29863c0e-219c-4420-a48a-6b016419f2e2)

Before running this pipeline, ensure you have the following:

- **Azure Synapse Analytics Workspace**
- **Azure SQL Database** with pre-loaded historical data
- **Azure Data Lake Storage (ADLS) Gen2** for storing data in different layers
- **PySpark** notebooks for data transformations
- **Azure Active Directory** roles and permissions for managing the pipeline

### 1. Clone the Repository
### 2. Upload Notebooks to Synapse
   - Navigate to your **Azure Synapse Workspace** and upload the notebooks in the `notebooks` folder.
### 3. Set Up Synapse Pipelines
   - Import the **Synapse pipeline JSON** file  to set up the pipeline in Azure Synapse.
   - Ensure you have configured access to your SQL database and ADLS.
### 4. Run the Pipeline
   - Trigger the pipeline for either full data loads or incremental CDC (Change Data Capture) loads.
