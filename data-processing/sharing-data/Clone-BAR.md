# Using Zero-Copy Clone

Cloning, also referred to as “zero-copy cloning,” creates a copy of a database, schema or table. A snapshot of data present in the source object is taken when the clone is created, and is made available to the cloned object. The cloned object is writable, and is independent of the clone source. That is, changes made to either the source object or the clone object are not part of the other. Cloning a database will clone all the schemas and tables within that database. Cloning a schema will clone all the tables in that schema. 

## Development - Test - Exploration Environments

Copy the SQL into a Worksheet, set the proper context, and Run each statement individually, exploring the results
```
    CREATE TABLE customer_clone CLONE customer;
    SELECT * FROM CUSTOMER_CLONE; 
    CREATE DATABASE hol_db_clone CLONE hol_db;
```
## BAR

### UNDROP Objects
Copy the SQL into a Worksheet, set the proper context, and Run each statement individually, exploring the results
```
    DESCRIBE TABLE CUSTOMER;
    DROP TABLE CUSTOMER;
    DESCRIBE TABLE CUSTOMER;
    UNDROP TABLE CUSTOMER;
    DESCRIBE TABLE CUSTOMER;
```
**Note:**  UNDROP is available for:
- TABLE
- SCHEMA
- DATABASE

### Recover from Data Corruption
Copy the SQL into a Worksheet, set the proper context, and Run each statement individually, exploring the results
```
    UPDATE CUSTOMER SET V = NULL;
    SELECT * FROM CUSTOMER LIMIT 22;
    CREATE OR REPLACE TABLE CUSTOMER_CLONE 
        CLONE CUSTOMER BEFORE (STATEMENT => ''); -- get queryID of ALTER
    SELECT * FROM CUSTOMER_CLONE LIMIT 22;
    ALTER TABLE CUSTOMER_CLONE SWAP WITH CUSTOMER;
    SELECT * FROM CUSTOMER_CLONE LIMIT 22;
```
