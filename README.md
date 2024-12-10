# AZURE-BASED-DATA-MIGRATION-AND-ANALYTICS

This project demonstrates an end-to-end data engineering pipeline on the Azure platform, including data migration, transformation, and analytics. It highlights key tools and technologies like Azure Data Factory, Azure Data Lake Storage (ADLS) Gen2, Azure Databricks, Azure Synapse Analytics, and Power BI for reporting.

---

## **Project Overview**
The project involves migrating data from an Azure SQL database to Azure Data Lake Storage (ADLS Gen2), transforming it using Databricks, and building a Lakehouse architecture with Bronze, Silver, and Gold layers. The final data is loaded into Azure Synapse Analytics for querying and integrated with Power BI for reporting.

---

## **Architecture**
"D:\PICTURES\Screenshots\Architecture.png"
### **Source: Azure SQL Database**
- Contains **10 tables** as the initial data source.

### **Azure Data Factory (ADF)**
- Used for data ingestion and ETL processes.
- Facilitates the migration of tables from the Azure SQL Database to ADLS Gen2.

### **Azure Data Lake Storage Gen2 (ADLS Gen2)**
- Cost-effective storage solution.
- Data is organized into three layers: Bronze, Silver, and Gold.

### **Azure Databricks**
- Handles data transformation and analytics workloads.
- Implements the **Medallion Architecture** for structured data pipelines:
  - **Bronze Layer**: Stores raw data directly from the source.
  - **Silver Layer**: Applies the first level of transformations (e.g., typecasting, data cleaning).
  - **Gold Layer**: Applies the second level of transformations (e.g.,  column renaming).

### **Azure Synapse Analytics**
- Serves as the data warehouse for the Gold layer data.
- Provides scalable storage and SQL-based querying for analysis and reporting.

### **Power BI**
- Used for creating interactive dashboards and reports from the curated data in Synapse.

### **Security and Governance**
- **Azure Active Directory** for identity and access management.
- **Azure Key Vault** for secure storage of credentials (e.g., database usernames and passwords).

---

## **Implementation Steps**

### **1. Environment Setup**
- Created resource groups and Azure services, including ADF, ADLS, Databricks, Synapse, and Key Vault.

### **2. Data Ingestion**
- Used Auto-resolve Integration Runtime to establish connectivity between ADF and the Azure SQL database.
- Used **Lookup Activity** in ADF to retrieve table metadata.
- Implemented **ForEach Activity** with **Copy Data Activity** to migrate all tables to ADLS Gen2.

### **3. Data Transformation**
- Created a Databricks cluster and notebooks for data transformation.
- Established mount points for Bronze, Silver, and Gold layers in ADLS Gen2.
- Performed transformations:
  - **Bronze to Silver**: Typecasting and data cleaning.
  - **Silver to Gold**: Column renaming

### **4. Data Loading**
- Loaded transformed Gold layer data into Azure Synapse Analytics for centralized storage and querying.

### **5. Reporting**
- Connected Synapse Analytics to Power BI to create insightful reports and dashboards.

---

## **Key Features**
1. **End-to-End Data Migration:** Moved data seamlessly from Azure SQL Database to the cloud (ADLS Gen2).
2. **Medallion Architecture:** Implemented Bronze, Silver, and Gold layers to ensure data quality and efficient processing.
3. **Scalable Analytics:** Leveraged Databricks and Synapse Analytics for high-performance transformations and querying.
4. **Secure Workflow:** Used Azure Key Vault and Azure Active Directory for secure credential management and access control.
5. **Data Visualization:** Integrated with Power BI for dynamic and user-friendly reporting.

---

## **Technologies Used**
- **Azure Data Factory**: Data ingestion and orchestration.
- **Azure Data Lake Storage Gen2**: Scalable and cost-efficient cloud storage.
- **Azure Databricks**: Data transformation and analytics using Python and SQL.
- **Azure Synapse Analytics**: Data warehousing and SQL-based querying.
- **Power BI**: Interactive dashboards and reporting.
- **Azure Active Directory**: Identity and access management.
- **Azure Key Vault**: Secure credential management.

---

