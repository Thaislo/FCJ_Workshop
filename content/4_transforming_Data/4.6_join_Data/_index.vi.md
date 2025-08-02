---
title: "Nối dữ liệu"
weight: 6
chapter: false
pre: " <b> 4.6 </b> "
---

#### Nối dữ liệu chuyến đi taxi vàng với bảng tra cứu khu vực đón
- Nhấn vào biểu tượng **Transform** và chọn **Join**.
- Cấu hình như sau:
  - **Name** – `Yellow Trips Data + Pickup Zone Lookup`
  - **Node Parents**:
    - `Change Schema - Pickup Zone Lookup`
    - `Filter - Yellow Trip Data`
  - Trong phần **Join conditions**, chọn các khóa nối sau:
    - `Change Schema - Pickup Zone Lookup` – `pu_location_id`
    - `Filter - Yellow Trip Data` – `pulocationid`

![](../../../images/4.transforming/21.png)

- Nhớ lưu lại tác vụ của bạn.
![](../../../images/4.transforming/22.png)
