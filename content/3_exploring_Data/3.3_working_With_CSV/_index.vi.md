---
title: "Làm việc với dữ liệu CSV có dấu ngoặc kép"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

Các tệp CSV đôi khi có dấu ngoặc kép bao quanh các giá trị dữ liệu trong mỗi cột, nhưng những dấu ngoặc này không phải là một phần của dữ liệu cần phân tích. Để đọc đúng tệp CSV, chúng ta có thể cập nhật thuộc tính bảng trong [AWS Glue](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started) để sử dụng OpenCSVSerDe.

- Truy cập [Glue console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- Trong thanh điều hướng bên trái, nhấn **Tables** dưới mục **Data Catalog**.
- Trên màn hình **Tables**, nhấn vào bảng `raw_taxi_zone_lookup`.
- Nhấn **Actions**, sau đó chọn **Edit table**.

![](../../images/3.exploring/9.png)

- Cập nhật trường **Serialization lib** thành `org.apache.hadoop.hive.serde2.OpenCSVSerde`.

![](../../images/3.exploring/10.png)

- Xóa các tham số **Serde** hiện có, sau đó thêm các tham số sau:
  - `escapeChar`: nhập dấu gạch chéo ngược `\`
  - `quoteChar`: nhập dấu ngoặc kép `"`
  - `separatorChar`: nhập dấu phẩy `,`

![](../../images/3.exploring/11.png)

- Nhấn **Save**.

![](../../images/3.exploring/12.png)

- Quay lại **Athena console**.
- Trên trang **Query editor**, nhấn vào biểu tượng menu ⋮ bên cạnh bảng `raw_taxi_zone_lookup`, rồi chọn **Preview table**.

![](../../images/3.exploring/13.png)

{{% notice note%}}
Tất cả giá trị kiểu chuỗi hiện không còn được bao quanh bởi dấu ngoặc kép.
{{% /notice %}}
