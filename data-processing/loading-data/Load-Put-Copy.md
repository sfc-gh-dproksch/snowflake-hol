# Loading Data with PUT and COPY

The Snowflake UI is useful for loading data where the files are less than 50MB.  When the data volumes grow, it is useful to use the [PUT](https://docs.snowflake.net/manuals/sql-reference/sql/put.html) and [COPY](https://docs.snowflake.net/manuals/sql-reference/sql/copy-into-table.html) commands.  PUT can be replaced with the Cloud Provider's mechanism for placing data into Object Storage, as PUT only works with Snowflake managed internal storage.

1.  Connect to Snowflake using [SnowSQL](https://docs.snowflake.net/manuals/user-guide/snowsql.html).

1.  Execute the following script: 
```
#!/bin/bash

snowsql -u hol_user --prompt << EOF
use role demo_role;
use warehouse demo_warehouse;
use database hol_db;
use schema demo_schema;

remove @demo_state/json_0_0_0.json.gz;

put file:///tmp/samp.json_0_0_0.json @demo_state/;

copy into load_json_sample
   from @demo_state/
   file_format = ( type = JSON );

select * from load_json_sample limit 22;

EOF
```
