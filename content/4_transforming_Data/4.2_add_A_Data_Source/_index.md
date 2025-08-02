---
title : "Add a Data source"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

#### Add Yellow Trips Data from Amazon S3
- Click on the **Source** tab and select **S3**.
![](/images/4.transforming/5.png)
- In the **Data source – S3 bucket**, specify the following:
  - **Name** – `Yellow Trip Data`
  - **Database** – `nyctaxi_db`
  - **Table** – `raw_yellow_tripdata`
![](/images/4.transforming/6.png)
- Click **Save**. Remember to save your job as you proceed with building the data transformation steps.
#### View Data Schema and Preview Data
- Go to the **Output schema** tab to review the data schema.
![](/images/4.transforming/7.png)
- Go to the **Data preview** tab to inspect a sample dataset while editing your job.
![](/images/4.transforming/8.png)