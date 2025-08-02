---
title: "Kết nối với nguồn dữ liệu"
weight: 2
chapter: false
pre: " <b> 6.2 </b> "
---

#### Tạo tập dữ liệu trong QuickSight
- Trên trang **QuickSight**, nhấp vào **Datasets** ở thanh điều hướng bên trái.
- Ở góc trên bên phải màn hình, nhấn **New dataset**.
![](../../../images/6.visualize/7.png)

- Chọn **Athena**.
![](../../../images/6.visualize/8.png)

- Trong cửa sổ **New Athena data source**, nhập các thông tin sau:
  - **Tên nguồn dữ liệu** – `Athena - SDL Jumpstart`
  - **Athena workgroup** – `primary`
  - Sau đó nhấn **Create Data Source**.
![](../../../images/6.visualize/9.png)

- Trong cửa sổ **Choose your table**, nhập các thông tin sau:
  - **Catalog** – `AwsDataCatalog`
  - **Cơ sở dữ liệu** – `nyctaxi_db`
  - **Bảng** – `v_yellow_tripdata`
  - Sau đó nhấn **Select**.
![](../../../images/6.visualize/10.png)

- Trong cửa sổ **Finish dataset creation**, chọn **Import to SPICE for quicker analytics**. Sau đó nhấn **Edit/Preview data**.
![](../../../images/6.visualize/11.png)

{{% notice info %}}
SPICE là viết tắt của **Super-fast**, **Parallel**, **In-memory Calculation Engine**. Đây là công cụ được thiết kế cho việc tính toán nâng cao và phân tích dữ liệu tốc độ cao. Dung lượng SPICE được chia sẻ giữa tất cả người dùng QuickSight trong cùng một vùng AWS.
{{% /notice %}}
