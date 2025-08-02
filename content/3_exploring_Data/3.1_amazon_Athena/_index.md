---
title : "Using Amazon Athena for the first time"
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---

**Amazon Athena** automatically stores query results and metadata for each query run at a query result location that you can specify in **Amazon S3**. If needed, you can access the files in this location to work with them. You can also download query result files directly from the Athena console.

- Access the [Athena console](https://ap-southeast-1.console.aws.amazon.com/athena/home?region=ap-southeast-1#/landing-page). Click **Launch query editor**.

![](../../images/3.exploring/1.png)

- In the top menu, click **Workgroup: primary**.

![](../../images/3.exploring/2.png)

- Select **Settings**, click **Browse S3**, and choose `s3://serverlessanalytics-[your-account-id]-athena` as the value for the **Location of query result - optional** field.

![](../../images/3.exploring/3.png)
![](../../images/3.exploring/4.png)

- Scroll to the bottom of the page and click **Save**.

![](../../images/3.exploring/5.png)

- Return to the top menu and click **Editor** to go back to the **Query editor** page.
