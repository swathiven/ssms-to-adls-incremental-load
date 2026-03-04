# ssms-adls-through controltable
Project: Data Movement from SQL Server to Azure SQL Database and ADLS using Control Table in Azure Data Factory

Designed and implemented an ETL solution to copy data from multiple SQL Server tables to Azure SQL Database and Azure Data Lake Storage (ADLS) using Azure Data Factory (ADF).

Configured Linked Services and Datasets:

Source: SQL Server (on-prem) (ls_ssms, ds_ssms)

Sink: ADLS (ls_adls, ds_adls) and Azure SQL Database (ls_azure_sql_db, ds_azure_sql_db)

Developed pipeline1 (pl_ssms_adls) to move data from SQL Server to ADLS.

Developed pipeline2 (pl_ssms_azure_sql_db) to move data from SQL Server to Azure SQL Database.

Created pipeline3 using Lookup, ForEach, and If Condition activities to implement dynamic control based on a control table:

If type='ssms_storage', the pipeline triggers pipeline1 to load data into ADLS.

If the type is different, the pipeline triggers pipeline2 to load data into Azure SQL Database.

Implemented dynamic execution using the Execute Pipeline activity to automate conditional data movement.

Maintained the solution under Git version control for source code management and collaboration.

Ensured scalable, reusable, and automated data movement with minimal manual intervention, improving data availability for analytics and reporting.

Technologies used:
Azure Data Factory, SQL Server Management Studio (SSMS), Azure SQL Database, Azure Data Lake Storage (ADLS), Git, ETL, Control Tables
