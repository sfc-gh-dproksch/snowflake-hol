# Snowflake Data Loading

## Loading Rectangular Data

Obtain the [sample data](./data/samp.csv.gz)
Use the sample table DDL:
```
CREATE OR REPLACE TABLE LOAD_SAMPLE (
  salutation char(20),
  first_name varchar(50),
  last_name  varchar(50),
  birthdate  date  
);
```

## Loading Semi-Structured Data
