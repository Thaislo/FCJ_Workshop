---
title : "Create a job using Glue Studio"
weight : 1
chapter : false
pre : " <b> 4.1 </b> "
---

- Go to the [Glue console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- In the left navigation pane, click on **ETL jobs**.
- On the **AWS Glue Studio** page, click on **Visual ETL**.

![](/images/4.transforming/1.png)

- In the Glue Studio editor page, go to the **Job details** tab and configure the following:
  - **Name** – `Transform NYC Taxi Trip Data`
  - **IAM Role** – `ServerlessAnalyticsRole`
  - **Job bookmark** – `Disable`
  - **Number of retries** – `0`

![](/images/4.transforming/2.png)
![](/images/4.transforming/3.png)

{{% notice info %}}
**Job bookmark** is a feature of AWS Glue that helps maintain state information and prevents reprocessing of old data. It allows the job to process only new data when it is rerun according to a predefined schedule.
{{% /notice %}}

- Click **Save**. Return to the **Visual** tab.
![](/images/4.transforming/4.png)