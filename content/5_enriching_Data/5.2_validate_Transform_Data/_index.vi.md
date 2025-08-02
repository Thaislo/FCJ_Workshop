---
title: "Xác thực dữ liệu đã biến đổi"
weight: 1
chapter: false
pre: " <b> 5.2 </b> "
---

#### Kiểm tra dữ liệu trong bảng yellow_tripdata
- Truy cập [Athena console](https://ap-southeast-1.console.aws.amazon.com/athena/home?region=ap-southeast-1#/query-editor/history/1b856f66-eec5-4539-86be-ba904bf9922d).
- Chọn **Preview table** để xem dữ liệu trong bảng `yellow_tripdata`.
![](/images/5.enriching/9.png)

- Trên trang **Query editor**, chạy các truy vấn sau để xác thực dữ liệu:

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
