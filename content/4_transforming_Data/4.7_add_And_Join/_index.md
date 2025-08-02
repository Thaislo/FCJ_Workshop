---
title : "Add and Join another Dataset"
weight : 7
chapter : false
pre : " <b> 4.7 </b> "
---

#### Add Drop-off Zone Lookup Table
- Click on the **Source** icon and select **S3**.
- In the **Data source – S3 bucket node**, specify the following:
  - **Name** – `Dropoff Zone Lookup`
  - **Database** – `nyctaxi_db`
  - **Table** – `raw_taxi_zone_lookup`
![](../../images/4.transforming/23.png)
- Remember to save your job.
![](../../images/4.transforming/24.png)
#### Edit Column Names for Drop-off Taxi Zone Lookup Table
- Ensure that the **Amazon S3 - Dropoff Zone Lookup** node is selected.
- Click on the **Transform** icon and select **Change Schema**.
- Specify the following:
  - **Name** – `Change Schema - Dropoff Zone Lookup`
  - Edit the **target key** for the following columns:
    - `locationid` to `do_location_id`
    - `borough` to `do_borough`
    - `zone` to `do_zone`
    - `service_zone` to `do_service_zone`
![](../../images/4.transforming/25.png)
- Remember to save your job.
![](../../images/4.transforming/26.png)
#### Join Yellow Trips Data with Drop-off Zone Lookup Data
- Click on the **Transform** icon and select **Join**.
- Specify the following:
  - **Name** – `Yellow Trip Data + Pickup Zone Lookup + Drop-off Zone Lookup`
  - **Node Parents**:
    - `Yellow Trip Data + Pickup Zone Lookup`
    - `Change Schema - Dropoff Zone Lookup`
  - Under **Join conditions**, select the following keys:
    - `Change Schema - Dropoff Zone Lookup` – `do_location_id`
    - `Filter - Yellow Trip Data + Pickup Zone Lookup` – `pulocationid`
![](../../images/4.transforming/27.png)