---
title : "Discovering and Cataloging Data "
weight : 2
chapter : false
pre : " <b> 2. </b> "
---

### Overview
With multiple data sources and formats in your data lake, it’s essential to have the ability to discover and catalog the data to gain better insights and integrate it with AWS’s tailored analytics services.

In this exercise, we will create AWS Glue Crawlers to automatically discover the schema of the data stored in Amazon S3. The discovered metadata about the data stored in S3 will be registered in the AWS Glue Catalog. This enables AWS Glue to use the cataloged information for ETL processing and allows other AWS services like Amazon Athena to query the data stored in Amazon S3.

![](/images/2.discover/2_01.png)

### Introduction to AWS Glue
**AWS Glue** is a fully managed, serverless ETL (extract, transform, and load) service that simplifies and reduces the cost of classifying, cleaning, enriching, and reliably moving your data between various data stores. AWS Glue consists of the following core components:

- **Data Catalog** – a central repository to store metadata about the structure and operational aspects of your data assets.
- **ETL Engine** – automatically generates Scala or Python code.
- **Jobs System** – provides managed infrastructure to orchestrate your ETL workflows.

### Content
- [Create a Glue Crawler](2.1-creategluecrawler/)
- [Run the Glue Crawler](2.2-rungluecrawler/)
- [Review the metadata in Glue Data Catalog](2.3-review/)