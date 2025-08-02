---
title : "Run SQL queries to explore the data"
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---

- Check number of yellow taxi trip records.

{{< highlight SQL >}}
SELECT COUNT(*) "Count" FROM raw_yellow_tripdata;
{{< /highlight >}}
![](../../images/3.exploring/14.png)

- Explore data categories

{{< highlight SQL >}}
SELECT vendorid, COUNT(*) "Count"
FROM  raw_yellow_tripdata
GROUP BY vendorid
ORDER BY 1;
{{< /highlight >}}
![](../../images/3.exploring/15.png)

{{< highlight SQL >}}
SELECT pulocationid, COUNT(*) "Count"
FROM   raw_yellow_tripdata
GROUP BY pulocationid
ORDER BY 1;
{{< /highlight >}}
![](../../images/3.exploring/16.png)

{{< highlight SQL >}}
SELECT payment_type, COUNT(*) "Count"
FROM   raw_yellow_tripdata
GROUP BY payment_type
ORDER BY 1;
{{< /highlight >}}
![](../../images/3.exploring/17.png)


- Explore records with NULL Vendor ID.

{{< highlight SQL >}}
SELECT * 
FROM   raw_yellow_tripdata
WHERE  vendorid IS NULL
LIMIT 100;
{{< /highlight >}}
![](../../images/3.exploring/18.png)

- Explore records by time period.

{{< highlight SQL >}}
SELECT SUBSTR(tpep_pickup_datetime, 1, 7) "Period", COUNT(*) "Total Records"
FROM   raw_yellow_tripdata
GROUP BY SUBSTR(tpep_pickup_datetime, 1, 7) 
ORDER BY 1;
{{< /highlight >}}
![](../../images/3.exploring/19.png)

- Count records that falls outside of year 2020.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata 
WHERE  SUBSTR(tpep_pickup_datetime, 1, 7) NOT LIKE '2020%';
{{< /highlight >}}
![](../../images/3.exploring/20.png)

- Count records with NULL values (based on Vendor ID) that falls within 2020.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata
WHERE  vendorid IS NULL
AND    SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020%';
{{< /highlight >}}
![](../../images/3.exploring/21.png)

- Count records that falls in the last quarter of 2020, exclude records with missing Vendor ID.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata
WHERE  vendorid IS NOT NULL
AND    SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020-1%';
{{< /highlight >}}
![](../../images/3.exploring/22.png)

- Join taxi trips data with taxi zone look up table.

{{< highlight SQL >}}
SELECT td.*, pu.*, do.*
FROM   raw_yellow_tripdata td, 
       raw_taxi_zone_lookup pu, 
       raw_taxi_zone_lookup do 
WHERE  td.pulocationid = pu.locationid AND
       td.pulocationid = do.locationid AND
       vendorid IS NOT NULL AND
       SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020-1%'
LIMIT 100;
{{< /highlight >}}
![](../../images/3.exploring/23.png)

- Count total joined records for the last quarter of 2020.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata td, 
       raw_taxi_zone_lookup pu, 
       raw_taxi_zone_lookup do 
WHERE  td.pulocationid = pu.locationid AND
       td.pulocationid = do.locationid AND
       vendorid IS NOT NULL AND
       SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020-1%';
{{< /highlight >}}
![](../../images/3.exploring/24.png)
