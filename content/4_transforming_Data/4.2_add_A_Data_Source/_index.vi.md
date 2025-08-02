---
title: "Thêm nguồn dữ liệu"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

#### Thêm dữ liệu chuyến đi taxi vàng từ Amazon S3
- Nhấn vào tab **Source** và chọn **S3**.
![](../../images/4.transforming/5.png)

- Trong phần **Data source – S3 bucket**, cấu hình như sau:
  - **Name** – `Yellow Trip Data`
  - **Database** – `nyctaxi_db`
  - **Table** – `raw_yellow_tripdata`
![](../../images/4.transforming/6.png)

- Nhấn **Save**. Hãy nhớ lưu tác vụ khi bạn tiếp tục xây dựng các bước biến đổi dữ liệu.

#### Xem schema dữ liệu và xem trước dữ liệu
- Chuyển sang tab **Output schema** để xem cấu trúc dữ liệu.
![](../../images/4.transforming/7.png)

- Chuyển sang tab **Data preview** để xem mẫu dữ liệu khi đang chỉnh sửa tác vụ.
![](../../images/4.transforming/8.png)
