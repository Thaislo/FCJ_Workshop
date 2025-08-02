---
title: "Tạo catalog cho dữ liệu đã biến đổi"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

#### Tạo Glue Crawler
- Truy cập [AWS Glue console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- Trong menu điều hướng bên trái, nhấn vào **Crawlers**.
- Ở trang **Crawlers**, nhấn **Create Crawler**.
![](../../../images/5.enriching/1.png)

- Đặt tên crawler là `nyc-yellow-tripdata-parquet-crawler`, sau đó nhấn **Next**.
![](../../../images/5.enriching/2.png)

- Ở màn hình **Choose data sources and classifiers**, điền thông tin sau rồi nhấn **Next**:
  - Nhấn **Add a data source**.
  - Chọn **Data source** – `S3`.
  - Chọn **Location of S3 data** – `In this account`.
  - Nhập đường dẫn S3 – `s3://serverlessanalytics-[your-account-id]-transformed/nyc-taxi/yellow-tripdata`.
  - Với **Subsequent crawler runs**, chọn **Crawl all sub-folders**.
  - Nhấn **Add an S3 data source**.
![](../../../images/5.enriching/3.png)
![](../../../images/5.enriching/4.png)

- Ở màn hình **Configure security settings**, chọn `ServerlessAnalyticsRole` từ danh sách **Existing IAM role**, rồi nhấn **Next**.
![](../../../images/5.enriching/5.png)

- Ở màn hình **Set output and scheduling**, chọn `nyctaxi_db` làm database.
- Với **Crawler schedule**, chọn tần suất là **On demand**, rồi nhấn **Next**.
![](../../../images/5.enriching/6.png)

- Xem lại thông tin crawler, sau đó nhấn **Create crawler**.
![](../../../images/5.enriching/7.png)

- Tại trang **Crawlers**, chọn `nyc-yellow-tripdata-parquet-crawler`, rồi nhấn **Run**.
![](../../../images/5.enriching/8.png)
