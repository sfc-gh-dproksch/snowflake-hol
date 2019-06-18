```
#!/bin/bash
snowsql -u hol_user --prompt << EOF
use role demo_role;
use warehouse demo_warehouse;
use database hol_db;

put file:///tmp/json_0_0_0.json @demo_state/;
copy into load_json_sample
   from @demo_state/
   file_format = ( type = JSON );

select * from load_json_sample limit 22;

EOF
```
