---
title: "Làm giàu dữ liệu đã biến đổi"
weight: 3
chapter: false
pre: " <b> 5.3 </b> "
---

- Chạy truy vấn sau để tạo một view làm giàu bảng dữ liệu với thông tin bổ sung.

{{< highlight sql >}}
CREATE OR REPLACE VIEW v_yellow_tripdata
AS
SELECT CASE vendor_id
            WHEN 1 THEN 'Creative Mobile'
            WHEN 2 THEN 'VeriFone'
            ELSE 'No Data'
       END "vendor_name",
       pickup_datetime,
       dropoff_datetime,
       passenger_count,
       trip_distance,
       CASE ratecodeid
            WHEN 1 THEN 'Standard Rate'
            WHEN 2 THEN 'JFK'
            WHEN 3 THEN 'Newark'
            WHEN 4 THEN 'Nassau/Westchester'
            WHEN 5 THEN 'Negotiated Fare'
            WHEN 6 THEN 'Group Ride'
            WHEN 99 THEN 'Special Rate'
            ELSE 'No Data'
       END "rate_type",
       store_and_fwd_flag,
       pu_borough,
       pu_zone,
       pu_service_zone,
       do_borough,
       do_zone,
       do_service_zone,
       CASE payment_type
            WHEN 1 THEN 'Credit Card'
            WHEN 2 THEN 'Cash'
            WHEN 3 THEN 'No Charge'
            WHEN 4 THEN 'Dispute'
            WHEN 5 THEN 'Unknown'
            WHEN 6 THEN 'Voided Trip'
            ELSE 'No Data'
       END "payment_type",
       fare_amount,
       extra,
       mta_tax,
       tip_amount,
       tolls_amount,
       improvement_surcharge,
       congestion_surcharge,
       total_amount
FROM   yellow_tripdata;
{{< /highlight >}}

- Chọn **Preview table** để kiểm tra dữ liệu đã được làm giàu trong **view v_yellow_tripdata** trên Athena.
![](../../../images/5.enriching/12.png)

- Chạy truy vấn sau để truy xuất thông tin chi tiết:

{{< highlight sql >}}
SELECT vendor_name "Vendor",
       rate_type "Rate Type", 
       payment_type "Payment Type",
       ROUND(AVG(fare_amount), 2) "Fare",
       ROUND(AVG(extra), 2) "Extra",
       ROUND(AVG(mta_tax), 2) "MTA",
       ROUND(AVG(tip_amount), 2) "Tip",
       ROUND(AVG(tolls_amount), 2) "Toll",
       ROUND(AVG(improvement_surcharge), 2) "Improvement",
       ROUND(AVG(congestion_surcharge), 2) "Congestion",
       ROUND(AVG(total_amount), 2) "Total"
FROM   v_yellow_tripdata
GROUP BY vendor_name,
         rate_type,
         payment_type
ORDER BY 1, 2, 3;
{{< /highlight >}}
![](../../../images/5.enriching/13.png)
