---
title: "Biến đổi dữ liệu và lưu vào đích"
weight: 8
chapter: false
pre: " <b> 4.8 </b> "
---

#### Chỉnh sửa tên cột và kiểu dữ liệu của tập dữ liệu đã được nối

- Nhấn vào biểu tượng **Transform** và chọn **Change Schema**.
- Cấu hình như sau:
  - **Name** – `Change Schema - Joined Data`
  - Chỉnh sửa **Target key** và **Data type** cho các trường sau:
    - `vendorid` thành `vendor_id`
    - `tpep_pickup_datetime` thành `pickup_datetime`, từ `string` thành `timestamp`
    - `tpep_dropoff_datetime` thành `dropoff_datetime`, từ `string` thành `timestamp`
  - Xoá các **Source keys** sau:
    - `pulocationid`
    - `dolocationid`
![](../../../images/4.transforming/29.png)

- Nhớ lưu lại tác vụ của bạn.
![](../../../images/4.transforming/30.png)

#### Lưu dữ liệu đã biến đổi vào Amazon S3
- Nhấn vào tab **Target** và chọn **Amazon S3**.
- Cấu hình như sau:
  - **Name** – `Transformed Yellow Trip Data`
  - Trong tab **Data target properties – S3**, chỉ định:
    - **Format** – `Parquet`
    - **Compression Type** – `Snappy`
    - **S3 Target Location** – `s3://serverlessanalytics-[your-account-id]-transformed/nyc-taxi/yellow-tripdata/`
![](../../../images/4.transforming/31.png)

- Nhớ lưu lại tác vụ của bạn.
![](../../../images/4.transforming/32.png)
