# ssms-adls-through controltable
**Project**: Data Movement from SQL Server to Azure SQL Database and ADLS using Control Table in Azure Data Factory

- Designed and implemented an ELT solution to copy data from multiple SQL Server tables to Azure SQL Database and Azure Data Lake Storage (ADLS) using Azure Data Factory (ADF).

Configured Linked Services and Datasets:
- Create Linked Service that connects to ADLS, call it as ls_adls
- Create Linked Service that connects to Azure SQL Database (ls_azure_sql_db)
- Create Linked Service that connects to on-prem SQL server call it as ls_ssms.
- Create a dataset that connect to ADLS, call it as ds_adls
- Create a dataset that that use Azure SQL database call it as ds_azure_sql_db
- Create a dataset that use SQL Server management Studio (SSMS) call it ds_ssms.

- Once after Linked Service & datasets created, create pipeline using the existing Linked Services and datasets.

- Developed pipeline pl_ssms_adls to copy data from OnPrem SQL Server to ADLS.
- Developed another pipeline pl_ssms_azure_sql_db to copy data from SQL Server to Azure SQL Database.
- Created Parent pipeline using activities like, Lookup, ForEach, and If Condition activities to implement dynamic flow based on a control table settings:

- A Control table is used to dynamically change the flow of the pipeline.
- A column called `type` used to deviate the pipeline that it should run.
- For eg: If type=`ssms_storage`, the Parent pipeline runs pl_ssms_adls to load data into ADLS.
- If the type = `ssms_adls`, the parent pipeline runs pipeline pl_ssms_azure_sql_db to load data to Azure SQL Database.

Implemented dynamic execution using the Execute Pipeline activity to automate conditional data movement.

Pushed the solution to Git version control for source code management and collaboration.

Ensured scalable, reusable, and automated data movement with minimal manual intervention, improving data availability for analytics and reporting.

**Technologies used**:
1. Azure Data Factory,
2. SQL Server Management Studio (SSMS),
3. Azure SQL Database,
4. Azure Data Lake Storage (ADLS),
5. Git,
6. ETL,
7. Control Tables
