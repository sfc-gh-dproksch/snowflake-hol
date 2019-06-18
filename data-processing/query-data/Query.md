# Query Data

Snowflake support querying data via a wide variety of platforms:
-  Web UI
-  SnowSQL
-  JDBC
-  ODBC
-  Node
-  Spark Connector
-  R
-  Golang

The workshop will focus on running SQL from the Web UI.

1.  Navigate to the *Worksheets* tab
![alt-text](../../images/query/Query-Worksheets-tab.png)

1.  Copy [sample query](./data-processing/query-data/queries/query00.sql) and past into worksheet. 
![alt-text](./images/query/Query-CopyQuery.png)

1.  Set the proper user context
    -  **Role:** DEMO_ROLE
    -  **Warehouse:** DEMO_WAREHOUSE
    -  **Database:** SNOWFLAKE_SAMPLE_DATA
    -  **Schema:** TPCDS_SF10TCL
![alt-text](./images/query/Query-Set-Context.png)

1.  Run the query
![alt-text](./images/query/Query-Select-Run.png)

1.  Review the Results
    1.  Query ID - This is a unique key which identifies an SQL statement across the entire Snowflake deployment
    1.  SQL - Opens a dialogue box with the SQL that was executed
    1.  The duration of the query execution
![alt-text](./images/query/Query-Execution.png)
