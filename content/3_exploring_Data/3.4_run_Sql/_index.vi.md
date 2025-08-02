---
title: "Chạy truy vấn SQL để khám phá dữ liệu"
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

- Kiểm tra số lượng bản ghi chuyến đi của taxi vàng.

{{< highlight SQL >}}
SELECT COUNT(*) "Count" FROM raw_yellow_tripdata;
{{< /highlight >}}
![](../../../images/3.exploring/14.png)

- Khám phá các danh mục dữ liệu.

{{< highlight SQL >}}
SELECT vendorid, COUNT(*) "Count"
FROM  raw_yellow_tripdata
GROUP BY vendorid
ORDER BY 1;
{{< /highlight >}}
![](../../../images/3.exploring/15.png)

{{< highlight SQL >}}
SELECT pulocationid, COUNT(*) "Count"
FROM   raw_yellow_tripdata
GROUP BY pulocationid
ORDER BY 1;
{{< /highlight >}}
![](../../../images/3.exploring/16.png)

{{< highlight SQL >}}
SELECT payment_type, COUNT(*) "Count"
FROM   raw_yellow_tripdata
GROUP BY payment_type
ORDER BY 1;
{{< /highlight >}}
![](../../../images/3.exploring/17.png)

- Truy vấn các bản ghi có **Vendor ID** bị thiếu (NULL).

{{< highlight SQL >}}
SELECT * 
FROM   raw_yellow_tripdata
WHERE  vendorid IS NULL
LIMIT 100;
{{< /highlight >}}
![](../../../images/3.exploring/18.png)

- Phân tích bản ghi theo giai đoạn thời gian.

{{< highlight SQL >}}
SELECT SUBSTR(tpep_pickup_datetime, 1, 7) "Period", COUNT(*) "Total Records"
FROM   raw_yellow_tripdata
GROUP BY SUBSTR(tpep_pickup_datetime, 1, 7) 
ORDER BY 1;
{{< /highlight >}}
![](../../../images/3.exploring/19.png)

- Đếm các bản ghi nằm ngoài năm 2020.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata 
WHERE  SUBSTR(tpep_pickup_datetime, 1, 7) NOT LIKE '2020%';
{{< /highlight >}}
![](../../../images/3.exploring/20.png)

- Đếm các bản ghi bị thiếu Vendor ID trong phạm vi năm 2020.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata
WHERE  vendorid IS NULL
AND    SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020%';
{{< /highlight >}}
![](../../../images/3.exploring/21.png)

- Đếm các bản ghi thuộc quý cuối cùng của năm 2020, loại trừ các bản ghi bị thiếu Vendor ID.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata
WHERE  vendorid IS NOT NULL
AND    SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020-1%';
{{< /highlight >}}
![](../../../images/3.exploring/22.png)

- Thực hiện nối bảng giữa dữ liệu chuyến đi taxi và bảng tra cứu khu vực.

{{< highlight SQL >}}
SELECT td.*, pu.*, do.*
FROM   raw_yellow_tripdata td, 
       raw_taxi_zone_lookup pu, 
       raw_taxi_zone_lookup do 
WHERE  td.pulocationid = pu.locationid AND
       td.pulocationid = do.locationid AND
       vendorid IS NOT NULL AND
       SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020-1%'
LIMIT 100;
{{< /highlight >}}
![](../../../images/3.exploring/23.png)

- Đếm tổng số bản ghi đã được nối trong quý cuối cùng của năm 2020.

{{< highlight SQL >}}
SELECT COUNT(*) "Count"
FROM   raw_yellow_tripdata td, 
       raw_taxi_zone_lookup pu, 
       raw_taxi_zone_lookup do 
WHERE  td.pulocationid = pu.locationid AND
       td.pulocationid = do.locationid AND
       vendorid IS NOT NULL AND
       SUBSTR(tpep_pickup_datetime, 1, 7) LIKE '2020-1%';
{{< /highlight >}}
![](../../../images/3.exploring/24.png)
