---
title: "Lọc bản ghi"
weight: 4
chapter: false
pre: " <b> 4.4 </b> "
---

{{%notice note%}}
Lọc các bản ghi để loại bỏ các mục có giá trị **Pickup DateTime** không hợp lệ. Để tiết kiệm thời gian, chúng ta sẽ lọc các bản ghi từ tháng 10 đến tháng 12 năm 2020 nhằm giảm thời gian xử lý của tác vụ trong quá trình thực hành.
{{%/notice%}}

- Nhấn vào tab **Transform** và chọn **Filter**.
![](../../images/4.transforming/13.png)

- Cấu hình các thông tin sau:
  - **Name** – `Filter - Yellow Trip Data`
  - **Filter condition** – `tpep_pickup_datetime` / `matches` / `^2020-1`
![](../../images/4.transforming/14.png)

- Nhớ lưu lại tác vụ của bạn.
![](../../images/4.transforming/15.png)

#### Xem lại đoạn mã được tạo tự động
- Chuyển sang tab **Script**.
- Quan sát đoạn mã được **Glue Studio** tạo tự động.
![](../../images/4.transforming/16.png)
