# Query Semi-Structured Data

Snowflake natively supports the storage and querying of:
-  JSON
-  XML
-  Parquet
-  Avro
-  ORC

The workshop will focus on how to convert an existing table into JSON, and how to convert a query using that table into a join between structured and JSON data.

## Convert Tabular to JSON

1.  Navigate to the *Worksheet* tab
![alt-text](../../images/query/Query-Worksheets-tab.png)

1.  Copy the SQL and place it in the worksheet
**Note:** 65M rows will be used.
```
USE DATABASE HOL_DB;
USE SCHEMA DEMO_SCHEMA;
CREATE OR REPLACE TABLE CUSTOMER (V VARIANT);

INSERT INTO CUSTOMER
SELECT OBJECT_CONSTRUCT(*) FROM (
    SELECT 
        * 
    FROM
        SNOWFLAKE_SAMPLE_DATA.TPCDS_SF10TCL.CUSTOMER
);

SELECT * FROM CUSTOMER LIMIT 22;
```
