```
#!/bin/bash

snowsql -u hol_user --prompt << EOF
use role demo_role;
use warehouse demo_warehouse;
use database hol_db;
use schema demo_schema;


copy into @demo_state/load_csv
   from load_sample
   file_format = ( type = CSV );

ls @demo_state;

EOF
```
