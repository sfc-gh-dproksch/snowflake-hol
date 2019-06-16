# Snowflake Data Organization

Snowflake organizes data into a heirarchy of artifcats.  If you are famiiar with heritage RDBMS platforms, these concepts will be familiar.  The **DATABASE** object is at the top level.  A database contains one or more **SCHEMAS**. With in a schema, **TABLES**, **VIEWS**, **FILE FORMATS**, **STAGES**, and **SEQUENCES** are contained.  

In order to create these artifacts, navigate to the Databases icon in the Snowflake UI.  ![alt-text](./images/Database-Tab.png)

## Creating a Database
Once the Databases page is presented, choose Create ![alt-text](./images/Create-Database.png)

A dialogue box ![alt-text](./images/Create-Database-Dialoge.png) will be presented, and fill out the following information:
  1.  **Name:**  This is the name of the database
  1.  **Comment:**  This is an optional meta-data field ![alt-text](./images/Create-Database-Dialoge-Filled.png)
  1.  **Show SQL:**  This link will show the SQL used to create the database.  **NOTE** Almost every aspect of the Snowflake UI will offer to show the SQL.  This is a great opportunity to learn the commands and helps understand how to interact with Snowflake from the various tools and utilities that are part of the Snowflake ecosystem. ![alt-text](./images/Create-Database-Dialoge-Filled-ShowSQL.png)
  1.  **Finish:**  Submit the request to have Snowflake create the requested database.  

## Creating a Schema
## Creating a Table
## Creating a View
## Creating a File Format
## Creating a Stage
