---
title : "Join data"
weight : 6
chapter : false
pre : " <b> 4.6 </b> "
---

#### Join Yellow Trips Data with Pickup Taxi Zone Lookup Data
- Click on the **Transform** icon and select **Join**.
- Specify the following:
  - **Name** – `Yellow Trips Data + Pickup Zone Lookup`
  - **Node Parents**:
    - `Change Schema - Pickup Zone Lookup`
    - `Filter - Yellow Trip Data`
  - Under **Join conditions**, select the following keys:
    - `Change Schema - Pickup Zone Lookup` – `pu_location_id`
    - `Filter - Yellow Trip Data` – `pulocationid`
![](../../images/4.transforming/21.png)
- Remember to save your job.
![](../../images/4.transforming/22.png)