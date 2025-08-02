---
title : "Working with CSV data enclosed in quotes"
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

CSV files sometimes have quotes surrounding the data values intended for each column, but these quotes are not part of the data to be analyzed. To properly read a CSV file, we can update the table property in [AWS Glue](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started) to use OpenCSVSerDe.

- Go to the [Glue console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- In the left navigation menu, click **Tables** under **Data Catalog**.
- On the **Tables** screen, click the `raw_taxi_zone_lookup` table.
- Click **Actions**, then select **Edit table**.

![](/images/3.exploring/9.png)

- Update the **Serialization lib** with `org.apache.hadoop.hive.serde2.OpenCSVSerde`.

![](/images/3.exploring/10.png)

- Remove the existing **Serde** parameters, and then add the following parameters:
  - `escapeChar`, enter a backslash `\`
  - `quoteChar`, enter a double quote `"`
  - `separatorChar`, enter a comma `,`

![](/images/3.exploring/11.png)

- Click **Save**.

![](/images/3.exploring/12.png)

- Return to the **Athena console**.
- In the **Query editor** page, click the action menu icon ⋮ next to the `raw_taxi_zone_lookup` table, and click **Preview table**.

![](/images/3.exploring/13.png)


{{% notice note%}}
All string values are no longer enclosed in quotes.
{{% /notice %}}
