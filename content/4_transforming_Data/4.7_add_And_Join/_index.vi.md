---
title: "Thêm và Nối tập dữ liệu khác"
weight: 7
chapter: false
pre: " <b> 4.7 </b> "
---

#### Thêm bảng tra cứu khu vực trả khách
- Nhấn vào biểu tượng **Source** và chọn **S3**.
- Trong nút **Data source – S3 bucket**, cấu hình như sau:
  - **Name** – `Dropoff Zone Lookup`
  - **Database** – `nyctaxi_db`
  - **Table** – `raw_taxi_zone_lookup`
![](../../images/4.transforming/23.png)

- Nhớ lưu lại tác vụ của bạn.
![](../../images/4.transforming/24.png)

#### Chỉnh sửa tên cột cho bảng tra cứu khu vực trả khách
- Đảm bảo rằng nút **Amazon S3 - Dropoff Zone Lookup** đang được chọn.
- Nhấn vào biểu tượng **Transform** và chọn **Change Schema**.
- Cấu hình như sau:
  - **Name** – `Change Schema - Dropoff Zone Lookup`
  - Chỉnh sửa **target key** cho các cột sau:
    - `locationid` thành `do_location_id`
    - `borough` thành `do_borough`
    - `zone` thành `do_zone`
    - `service_zone` thành `do_service_zone`
![](../../images/4.transforming/25.png)

- Nhớ lưu lại tác vụ của bạn.
![](../../images/4.transforming/26.png)

#### Nối dữ liệu chuyến đi taxi vàng với bảng tra cứu khu vực trả khách
- Nhấn vào biểu tượng **Transform** và chọn **Join**.
- Cấu hình như sau:
  - **Name** – `Yellow Trip Data + Pickup Zone Lookup + Drop-off Zone Lookup`
  - **Node Parents**:
    - `Yellow Trip Data + Pickup Zone Lookup`
    - `Change Schema - Dropoff Zone Lookup`
  - Trong phần **Join conditions**, chọn các khóa nối sau:
    - `Change Schema - Dropoff Zone Lookup` – `do_location_id`
    - `Filter - Yellow Trip Data + Pickup Zone Lookup` – `pulocationid`
![](../../images/4.transforming/27.png)
