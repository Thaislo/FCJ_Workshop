---
title: "Thêm một nguồn dữ liệu khác"
weight: 5
chapter: false
pre: " <b> 4.5 </b> "
---

#### Thêm bảng tra cứu khu vực đón Taxi
- Quay lại tab **Visual**.
- Nhấn vào tab **Source** và chọn **S3**.
- Trong nút **Data source – S3 bucket**, cấu hình như sau:
  - **Name** – `Pickup Zone Lookup`
  - **Database** – `nyctaxi_db`
  - **Table** – `raw_taxi_zone_lookup`

![](../../../images/4.transforming/17.png)

Nhớ lưu lại tác vụ của bạn.

![](../../../images/4.transforming/18.png)

#### Chỉnh sửa tên cột cho bảng tra cứu khu vực đón Taxi
- Đảm bảo rằng nút **Amazon S3 - Pickup Zone Lookup** đang được chọn.
- Nhấn vào tab **Transform** và chọn **Change Schema**.
- Cấu hình như sau:
  - **Name** – `Change Schema - Pickup Zone Lookup`
  - Chỉnh sửa **target key**:
    - `locationid` thành `pu_location_id`
    - `borough` thành `pu_borough`
    - `zone` thành `pu_zone`
    - `service_zone` thành `pu_service_zone`

![](../../../images/4.transforming/19.png)

- Nhớ lưu lại tác vụ của bạn.

![](../../../images/4.transforming/20.png)
