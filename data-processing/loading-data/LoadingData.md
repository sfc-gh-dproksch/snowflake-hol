# Snowflake Data Loading

Snowflake handles loading [structured](#rectangle) and [semi-structured](#semi) data without the need for pre-processing or shredding.  Snowflake provides several ways to ingest data:
-  Via the [Web UI](#web-ui)
-  Via the [CLI](#put-and-copy) or a programming language
 
<a name="web-ui"></a>
<a name="rectangle"></a>
## Loading Rectangular Data

Snowflake has the ability to ingest data at very high speeds, both in batch mode and in near real-time.  This portion of the workshop is focusing on batch mode data ingestion.

### Ingest Data
*  Obtain the [sample data](./data/samp.csv.gz)
*  Command to create the sample table DDL:
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

### Ingest Data
*  Obtain the [sample data](./data/samp.json.gz)
*  Command to create sample table DDL:
<a name="sample_json_ddl"></a>
```
CREATE OR REPLACE TABLE LOAD_JSON_SAMPLE (
  col1 variant
);
```

<a name="json_file_format"></a>
*  Command to create a JSON File Format
```
CREATE OR REPLACD FILE FORMAT HOL_DB.DEMO_SCHEMA.DEMO_JSON_FILE_FORMAT 
TYPE = 'JSON' COMPRESSION = 'AUTO' ENABLE_OCTAL = FALSE 
ALLOW_DUPLICATE = FALSE STRIP_OUTER_ARRAY = TRUE 
STRIP_NULL_VALUES = FALSE 
IGNORE_UTF8_ERRORS = FALSE 
COMMENT = 'Demonstration JSON File Format';
```
1.  Navigate to the *Worksheets* tab. (Further discussion of how to use the worksheet will occur in the Query section.
![alt-text](../../images/dataloading/DataLoading-Worksheet.png)

1.  Configure the current user context
    1.  Select the HOL_DB database
    1.  Select the DEMO_SCHEMA schema 
![alt-text](../../images/dataloading/DataLoading-SQLContext.png)
![alt-text](../../images/dataloading/DataLoading-SQLContext-FIlled.png)

1. Copy and Run the [sample JSON command](#json_file_format), pasting it in the worksheet
![alt-text](../../images/dataloading/DataLoading-JSON-CreateFileFormat.png)

1.  Copy and Run the [sample table](#sample_json_ddl), pasting it in the worksheet
![alt-text](../../images/dataloading/DataLoading-JSON-CreateTable.png)

1.  Navigate to the *Databases* page
![alt-text](../../images/dataloading/DataLoading-Databases.png)

1.  Select the *HOL_DB* database
![alt-text](../../images/dataloading/DataLoading-DatabaseSelected.png)

1.  Select the *LOAD_JSON_SAMPLE* table
![alt-text](../../images/dataloading/DataLoading-JSON-TableSelected.png)

1.  Choose the *Load Tables* option
![alt-text](../../images/dataloading/DataLoading-JSON-TableLoad.png)

1.  The data loading wizard will appear.  Choose the warehouse which will process the ingestion request.  Choose *Next*.
![alt-text](../../images/dataloading/DataLoading-Wizard-Warehouse.png)
  
1.  Select where the source file(s) are located.  Choose *Next*.
![alt-text](../../images/dataloading/DataLoading-JSON-Wizard-Files.png)

1.  Select the correct file format.  Choose **Load**.
![alt-text](../../images/dataloading/DataLoading-JSON-Wizard-FileFormat.png)

![alt-text](../../images/dataloading/DataLoading-JSON-Wizard-Loaded.png)
Click *OK* to return to the table details page.

<a name="put-and-copy"></a>
## [Using PUT and COPY](./Load-Put-Copy.md)

