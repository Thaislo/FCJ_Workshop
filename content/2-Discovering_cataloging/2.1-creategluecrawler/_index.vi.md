---
title: "Tạo Glue Crawler"
weight: 1
chapter: false
pre: " <b> 2.1 </b> "
---

**Glue Crawler** là một tính năng giúp tự động suy luận schema của cơ sở dữ liệu và bảng từ dữ liệu nguồn, sau đó lưu trữ siêu dữ liệu liên quan vào AWS Glue Data Catalog.

- Truy cập [AWS Glue Console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- Trong thanh điều hướng bên trái, nhấn vào **Crawlers**.
- Trên trang Crawlers, nhấn **Create crawler**.
![](../../../images/2.discover/2.1-01.png)

- Đặt tên cho **crawler** là `nyc-taxi-crawler`, sau đó nhấn **Next**.
![](../../../images/2.discover/2.1-02.png)

- Trên trang **Choose data sources and classifiers**, cấu hình các thông tin sau rồi nhấn **Next**:
  - Nhấn **Add a data source**
  - Chọn **Data source** – S3  
  - Chọn **Location of S3 data** – *In this account*  
  - Nhập đường dẫn S3 – `s3://serverlessanalytics[your-account-id]-raw/nyc-taxi/`  
  - Với **Subsequent crawler runs**, chọn *Crawl all sub-folders*
  - Sau đó nhấn **Add an S3 data source.**
![](../../../images/2.discover/03.png)  
![](../../../images/2.discover/04.png)

- Trên màn hình **Configure security settings**, chọn **ServerlessAnalyticsRole** từ **Existing IAM role**, rồi nhấn **Next**.
![](../../../images/2.discover/05.png)

- Trên màn hình **Set output and scheduling**, nhấn **Add database**.
  - Đặt tên cơ sở dữ liệu là `nyctaxi_db`, rồi nhấn **Create database**.
![](../../../images/2.discover/06.png)  
![](../../../images/2.discover/07.png)

- Quay lại tab trước (**Set output and scheduling**), làm mới mục **Target database**, và chọn cơ sở dữ liệu vừa tạo `nyctaxi_db`.
  - Nhập `raw_` vào ô **Table name prefix - optional**.  
  - Với **Crawler schedule**, đặt tần suất là *On demand*, sau đó nhấn **Next**.
![](../../../images/2.discover/08.png)

- Xem lại thông tin **crawler**, sau đó nhấn **Create crawler**.  
- Đã tạo thành công.
![](../../../images/2.discover/09.png)
