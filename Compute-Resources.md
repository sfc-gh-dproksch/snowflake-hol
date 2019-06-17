# Snowflake Compute Resources

A virtual warehouse, often referred to simply as a “warehouse”, is a cluster of compute resources in Snowflake. A warehouse provides the required resources, such as CPU, memory, and temporary storage, to perform the following operations in a Snowflake session:

- Executing SQL SELECT statements that require compute resources (e.g. retrieving rows from tables and views).
- Performing DML operations, such as:
  - Updating rows in tables (DELETE , INSERT , UPDATE).
  - Loading data into tables (COPY INTO <table>).
  - Unloading data from tables (COPY INTO <location>).
