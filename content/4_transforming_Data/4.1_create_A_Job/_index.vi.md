---
title: "Tạo một tác vụ bằng Glue Studio"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

- Truy cập [Glue console](https://ap-southeast-1.console.aws.amazon.com/glue/home?region=ap-southeast-1#/v2/getting-started).
- Trong thanh điều hướng bên trái, nhấn vào **ETL jobs**.
- Trên trang **AWS Glue Studio**, nhấn vào **Visual ETL**.

![](../../images/4.transforming/1.png)

- Tại trang trình chỉnh sửa của Glue Studio, chuyển sang tab **Job details** và cấu hình các thông tin sau:
  - **Name** – `Transform NYC Taxi Trip Data`
  - **IAM Role** – `ServerlessAnalyticsRole`
  - **Job bookmark** – `Disable`
  - **Number of retries** – `0`

![](../../images/4.transforming/2.png)  
![](../../images/4.transforming/3.png)

{{% notice info %}}
**Job bookmark** là một tính năng của AWS Glue giúp lưu trạng thái của dữ liệu đã xử lý, nhằm tránh xử lý lại dữ liệu cũ. Khi kích hoạt, tính năng này cho phép tác vụ chỉ xử lý dữ liệu mới mỗi khi chạy lại theo lịch trình định sẵn.
{{% /notice %}}

- Nhấn **Save**. Quay lại tab **Visual**.
![](../../images/4.transforming/4.png)
