---
title: "Tóm tắt"
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

#### Quy trình Xử lý Dữ liệu

- **Nạp dữ liệu (Data Ingestion)**: Bạn đã nạp dữ liệu từ nhiều nguồn khác nhau vào Amazon S3, kho lưu trữ trung tâm của hệ thống dữ liệu. Bước này bao gồm việc thu thập và lưu trữ dữ liệu thô ở định dạng gốc để xử lý sau.

- **Chuyển đổi dữ liệu (Data Transformation)**: Sử dụng AWS Glue, bạn đã định nghĩa và thực thi các tác vụ ETL (Trích xuất, Biến đổi, Tải) để xử lý dữ liệu thô được lưu trong S3. Các tác vụ này đã chuyển đổi dữ liệu thành định dạng có cấu trúc, phù hợp cho việc phân tích và báo cáo.

- **Danh mục dữ liệu (Data Catalog)**: AWS Glue Data Catalog đóng vai trò then chốt trong việc tổ chức và quản lý siêu dữ liệu cho kho dữ liệu của bạn. Nó cung cấp một kho lưu trữ tập trung để lưu trữ định nghĩa lược đồ, phả hệ dữ liệu và các siêu dữ liệu khác liên quan đến tập dữ liệu của bạn.

- **Phân tích dữ liệu (Data Analysis)**: Với Amazon Athena, bạn đã thực hiện truy vấn và phân tích dữ liệu đã chuyển đổi được lưu trữ trên S3 bằng cú pháp SQL tiêu chuẩn. Kiến trúc serverless của Athena cho phép bạn thực hiện các truy vấn linh hoạt mà không cần triển khai hoặc quản lý hạ tầng.

- **Trực quan hóa dữ liệu (Data Visualization)**: Cuối cùng, bạn đã kết nối Amazon QuickSight với các nguồn dữ liệu, cho phép bạn tạo các biểu đồ và bảng điều khiển tương tác. QuickSight cung cấp một giao diện thân thiện để khám phá và trình bày các thông tin chuyên sâu từ dữ liệu của bạn.
