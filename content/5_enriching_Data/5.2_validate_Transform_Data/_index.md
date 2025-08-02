---
title : "Validate transformed data"
weight : 1
chapter : false
pre : " <b> 5.2 </b> "
---
#### Check Data in the yellow_tripdata Table
- Access the [Athena console](https://ap-southeast-1.console.aws.amazon.com/athena/home?region=ap-southeast-1#/query-editor/history/1b856f66-eec5-4539-86be-ba904bf9922d).
- Select **Preview table** to view data in the `yellow_tripdata table`.
![](/images/5.enriching/9.png)
- On the **Query editor** page, run the following queries to validate the data:
{{< highlight sql >}}
SELECT COUNT(*) "Count"
FROM   yellow_tripdata;
{{< /highlight >}}
![](/images/5.enriching/10.png)
{{< highlight sql >}}
SELECT DATE_TRUNC('month', pickup_datetime) "Period", 
       COUNT(*) "Total Records"
FROM   yellow_tripdata
GROUP BY DATE_TRUNC('month', pickup_datetime)
ORDER BY 1;
{{< /highlight >}}
![](/images/5.enriching/11.png)