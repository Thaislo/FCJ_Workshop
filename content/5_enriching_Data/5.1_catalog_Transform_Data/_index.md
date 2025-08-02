---
title : "Catalog transformed data"
weight : 1
chapter : false
pre : " <b> 5.1 </b> "
---
#### Create a Glue Crawler
- Access the [AWS Glue console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- In the left navigation menu, click on **Crawlers**.
- On the **Crawlers** page, click on **Create Crawler**.
![](../../images/5.enriching/1.png)
- Name the crawler `nyc-yellow-tripdata-parquet-crawler`, then click **Next**.
![](../../images/5.enriching/2.png)
- On the **Choose data sources and classifiers** screen, specify the following and click **Next**:
  - Click **Add a data source**.
  - Select **Data source** – `S3`.
  - Choose **Location of S3 data** – `In this account`.
  - Include the S3 path – `s3://serverlessanalytics-[your-account-id]-transformed/nyc-taxi/yellow-tripdata`.
  - For **Subsequent crawler runs**, choose **Crawl all sub-folders**.
  - Then click **Add an S3 data source**.
![](../../images/5.enriching/3.png)
![](../../images/5.enriching/4.png)
- On the **Configure security settings** screen, select `ServerlessAnalyticsRole` from **Existing IAM role**, then click **Next**.
![](../../images/5.enriching/5.png)
- On the **Set output and scheduling** screen, select `nyctaxi_db` as the database.
- For the **Crawler schedule**, set the frequency to **On demand**, then click **Next**.
![](../../images/5.enriching/6.png)
- Review the crawler details, then click **Create crawler**.
![](../../images/5.enriching/7.png)
- On the **Crawlers** page, select `nyc-yellow-tripdata-parquet-crawler`, then click **Run**.
![](../../images/5.enriching/8.png)