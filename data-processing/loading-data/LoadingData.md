# Snowflake Data Loading

## Loading Rectangular Data

Snowflake has the ability to ingest data at very high speeds, both in batch mode and in near real-time.  This portion of the workshop is focusing on batch mode data ingestion.

### Ingest Data
1.  Obtain the [sample data](./data/samp.csv.gz)
1.  Copy the sample table DDL:
```
CREATE OR REPLACE TABLE LOAD_SAMPLE (
  salutation char(20),
  first_name varchar(50),
  last_name  varchar(50),
  birthdate  date  
);
```

## Loading Semi-Structured Data
