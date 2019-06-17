# Snowflake Data Loading

Snowflake handles loading [structured](#rectangle) and [semi-structured](#semi) data without the need for pre-processing or shredding.
 
<a name="rectangle"></a>
## Loading Rectangular Data

Snowflake has the ability to ingest data at very high speeds, both in batch mode and in near real-time.  This portion of the workshop is focusing on batch mode data ingestion.

### Ingest Data
1.  Obtain the [sample data](./data/samp.csv.gz)
1.  Copy the sample table DDL:
<a name="sample_ddl"></a>
```
CREATE OR REPLACE TABLE LOAD_SAMPLE (
  salutation char(20),
  first_name varchar(50),
  last_name  varchar(50),
  email      varchar(100),
  birthdate  date  
);
```
1.  Navigate to the *Worksheets* tab. (Further discussion of how to use the worksheet will occur in the Query section.
![alt-text](../../images/dataloading/DataLoading-Worksheet.png)

1.  Configure the current user context
    1.  Select the HOL_DB database
    1.  Select the DEMO_SCHEMA schema 
![alt-text](../../images/dataloading/DataLoading-SQLContext.png)
![alt-text](../../images/dataloading/DataLoading-SQLContext-FIlled.png)

1.  Copy the [sample DDL](#sample_ddl) and paste into the worksheet
![alt-text](../../images/dataloading/DataLoading-DDL-Coppied.png)

1.  *Run* the DDL by pressing the *Run* button.
![alt-text](../../images/dataloading/DataLoading-RunButton.png)

1.  Verify the DDL ran correctly
![alt-text](../../images/dataloading/DataLoading-TableCreation.png)

1.  Navigate to the *Databases* page
![alt-text](../../images/dataloading/DataLoading-Databases.png)

1.  Select the *HOL_DB* database
![alt-text](../../images/dataloading/DataLoading-DatabaseSelected.png)

1.  Select the *LOAD_SAMPLE* table
![alt-text](../../images/dataloading/DataLoading-TableSelected.png)

1.  Choose the *Load Tables* option
![alt-text](../../images/dataloading/DataLoading-TableLoad.png)

1.  The data loading wizard will appear.  Choose the warehouse which will process the ingestion request.  Choose *Next*.
![alt-text](../../images/dataloading/DataLoading-Wizard-Warehouse.png)
  
1.  Select where the source file(s) are located.  Choose *Next*.
![alt-text](../../images/dataloading/DataLoading-Wizard-Files.png)

1.  Select the correct file format.  Choose **Load**.
![alt-text](../../images/dataloading/DataLoading-Wizard-FileFormat.png)

![alt-text](../../images/dataloading/DataLoading-Wizard-Loaded.png)

<a name="semi"></a>
## Loading Semi-Structured Data
