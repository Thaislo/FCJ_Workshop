---
title : "Add another Data source"
weight : 5
chapter : false
pre : " <b> 4.5 </b> "
---

#### Add Taxi Pickup Zone Lookup Table
- Go back to the **Visual** tab.
- Click on the **Source** tab and select **S3**.
- In the **Data source – S3 bucket** node, specify the following:
  - **Name** – `Pickup Zone Lookup`
  - **Database** – `nyctaxi_db`
  - **Table** – `raw_taxi_zone_lookup`

![](/images/4.transforming/17.png)

Remember to save your job.

![](/images/4.transforming/18.png)

#### Edit Column Names for Pickup Taxi Zone Lookup Table
- Ensure the **Amazon S3 - Pickup Zone Lookup** node is selected.
- Click on the **Transform** tab and select **Change Schema**.
- Specify the following:
  - **Name** – `Change Schema - Pickup Zone Lookup`
  - Edit **target key**:
    - `locationid` to `pu_location_id`
    - `borough` to `pu_borough`
    - `zone` to `pu_zone`
    - `service_zone` to `pu_service_zone`

![](/images/4.transforming/19.png)

- Remember to save your job.

![](/images/4.transforming/20.png)
