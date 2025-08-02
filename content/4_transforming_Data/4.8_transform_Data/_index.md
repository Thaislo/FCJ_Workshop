---
title : "Transform Data and Save to Target"
weight : 8
chapter : false
pre : " <b> 4.8 </b> "
---

#### Edit Column Names and Data Types of the Joined Dataset

- Click on the **Transform** icon and select **Change Schema**.
- Specify the following:
  - **Name** – `Change Schema - Joined Data`
  - Edit the **Target key** and **Data type** for the following items:
    - `vendorid` to `vendor_id`
    - `tpep_pickup_datetime` to `pickup_datetime`, `string` to `timestamp`
    - `tpep_dropoff_datetime` to `dropoff_datetime`, `string` to `timestamp`
  - Remove the following **Source keys**:
    - `pulocationid`
    - `dolocationid`
![](../../images/4.transforming/29.png)
- Remember to save your job.
![](../../images/4.transforming/30.png)
#### Save Transformed Data to Amazon S3
- Click on the **Target** tab and select **Amazon S3**.
- Specify the following:
  - **Name** – `Transformed Yellow Trip Data`
  - In the **Data target properties – S3** tab, specify the following:
    - **Format** – `Parquet`
    - **Compression Type** – `Snappy`
    - **S3 Target Location** – `s3://serverlessanalytics-[your-account-id]-transformed/nyc-taxi/yellow-tripdata/`
![](../../images/4.transforming/31.png)
- Remember to save your job.
![](../../images/4.transforming/32.png)