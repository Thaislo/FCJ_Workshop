---
title : "Create a Glue Crawler"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

**Glue Crawler** is a feature that automatically infers the schema of your database and tables from your source data, then stores related metadata in the AWS Glue Data Catalog.

- Go to the [AWS Glue Console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- In the left navigation menu, click **Crawlers**.
- On the Crawlers page, click **Create crawler**.
![](/images/2.discover/2.1-01.png)
- Set the name of the **crawler** to `nyc-taxi-crawler`, then click **Next**.
![](/images/2.discover/2.1-02.png)
- On the **Choose data sources and classifiers** page, specify the following details, then click **Next**:
  - Click **Add a data source**
  - Select **Data source** – S3
  - Choose **Location of S3 data** - *In this account*
  - Include S3 path – `s3://serverlessanalytics[your-account-id]-raw/nyc-taxi/`
  - For **Subsequent crawler runs**, select *Crawl all sub-folders*
  - Then click **Add an S3 data source.**
![](/images/2.discover/03.png)
![](/images/2.discover/04.png)
- On the **Configure security settings** screen, choose **ServerlessAnalyticsRole** from **Existing IAM role**, then click **Next**.
![](/images/2.discover/05.png)
- On the **Set output and scheduling** screen, click **Add database**.
  - Set the unique database name to `nyctaxi_db`, then click Create database.
![](/images/2.discover/06.png)
![](/images/2.discover/07.png)
- Return to the previous tab (**Set output and scheduling**), refresh the **Target database** selection, and choose the newly created database `nyctaxi_db`.
  - Enter `raw_` in the **Table name prefix - optional** field.
  - For **Crawler schedule**, set the frequency to *On demand*, then click **Next**.
![](/images/2.discover/08.png)
- Review the **crawler** details, then click **Create crawler**.
- Successfully created.
![](/images/2.discover/09.png)

