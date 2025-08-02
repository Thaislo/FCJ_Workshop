---
title : "Clean up"
weight : 8
chapter : false
pre : " <b> 8. </b> "
---
1. Delete Data from S3
- Choose each bucket to **Empty**, type `permanently delete` to confirm deletion and then choose each bucket to **Delete**
![](../images/7.clean/2.png)
2. **Delete CloudFormation Stack**: sdlj-workshop
- Choose **sdlj-workshop** and then click **Delete**
![](../images/7.clean/1.png)
3. **Delete Crawlers**: nyc-taxi-crawler, nyc-yellow-tripdata-parquet-crawler
- Choose the following 2 crawlers:
    - **nyc-taxi-crawler**
    - **nyc-yellow-tripdata-parquet-crawler**
- Click Actions, choose Delete crawlers and type **Delete** to confirm deletion
![](../images/7.clean/3.png)
4. **Delete Glue Studio Transform**: Transform NYC Taxi Trip Data
- Choose **Transform NYC Taxi Trip Data**, then click Actions and choose **Delete job(s)**
![](../images/7.clean/4.png)
5. **Delete Database**: nyctaxi_db
- Choose **nyctaxi_db** and then click **Delete**
![](/images/7.clean/5.png)
6. **Delete Athena – Transformed Yellow Trip Data**: Analysis in Amazon QuickSight
![](../images/7.clean/6.png)