# Demo data
Data used for demo purpose.

## Post
Post request body with a valid cell id. This can be used to test against the crawler.
```json
{"cell_id": "9289026679689183232"}
```

## IAM
```
User: pkgo-0
access key id: AKIAIDE74HHXDXSKUQXQ (deactivated)
secret access key: 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 (deactivated)
```

## Relation Database
AWS rds information
```
DB instance indentifier: pkgo-0
master username: pkgo0
pw: mypkgo-0 (deactivated)
```

Command to login PostgreSQL
```bash
psql -h pkgo-0.c8yops2lyqcp.us-west-2.rds.amazonaws.com -p 5432 -U pkgo0
```

Command to create a table in database.
```sql
CREATE TABLE POKEMON_MAP (
    encounter_id    DOUBLE PRECISION,
    expire          DOUBLE PRECISION,
    pokemon_id      INT,
    latitude        DOUBLE PRECISION,
    longitude       DOUBLE PRECISION,
    PRIMARY KEY (encounter_id)
);


CREATE INDEX expire_idx ON POKEMON_MAP (expire);
CREATE INDEX pokemon_id_idx ON POKEMON_MAP (pokemon_id);
CREATE INDEX longitude_idx ON POKEMON_MAP (longitude);
CREATE INDEX latitude_idx ON POKEMON_MAP (latitude);
```

Command to insert data into the table above.
```sql
INSERT INTO pokemon_map VALUES (1, 1, 1, 1, 1) ON CONFLICT (encounter_id) DO NOTHING;
select * from pokemon_map;
```


## Front End Project
- [Microsoft Bing Map SDK](https://www.bing.com/api/maps/sdkrelease/mapcontrol/isdk#overview)
- [Getting a Bing Map Key](https://msdn.microsoft.com/en-us/library/ff428642.aspx)


## Web Server
Valid geographical locations information used to test against the query web server.
```
-----> north bound: 34.42472445909278
-----> south bound: 34.41761769460624
-----> east bound: -119.70132859036184
-----> west bound: -119.70697195812917
```


## Data format
Sample Pokemon data.
```json
[  
   {  
      "pokemon_id":182,
      "expiration_timestamp_ms":1492660198000,
      "longitude":-119.84137910168162,
      "latitude":34.4483324347305,
      "spawn_point_id":"9289026679353638912",
      "encounter_id":9289026680846299110
   },
   {  
      "pokemon_id":165,
      "expiration_timestamp_ms":1492660085000,
      "longitude":-119.84137910168162,
      "latitude":34.44770108163997,
      "spawn_point_id":"9289026679219421184",
      "encounter_id":9289026680712081269
   },
   {  
      "pokemon_id":316,
      "expiration_timestamp_ms":1492660122000,
      "longitude":-119.84137910168162,
      "latitude":34.44770108163997,
      "spawn_point_id":"9289026679219421184",
      "encounter_id":9289026680712081306
   },
   {  
      "pokemon_id":396,
      "expiration_timestamp_ms":1492660281000,
      "longitude":-119.84282583393119,
      "latitude":34.44731393583173,
      "spawn_point_id":"9289026679756292096",
      "encounter_id":9289026681248952377
   },
   {  
      "pokemon_id":339,
      "expiration_timestamp_ms":1492660337000,
      "longitude":-119.84210246969995,
      "latitude":34.44624479502537,
      "spawn_point_id":"9289026678816768000",
      "encounter_id":9289026680309428337
   }
]
```