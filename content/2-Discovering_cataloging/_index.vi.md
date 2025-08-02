---
title: "Khám phá và Lập danh mục Dữ liệu"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

### Tổng quan
Với nhiều nguồn dữ liệu và định dạng khác nhau trong hồ dữ liệu của bạn, việc có khả năng khám phá và lập danh mục dữ liệu là điều cần thiết để hiểu rõ hơn về dữ liệu và tích hợp với các dịch vụ phân tích chuyên biệt của AWS.

Trong bài thực hành này, chúng ta sẽ tạo các Crawler trong AWS Glue để tự động khám phá schema của dữ liệu được lưu trữ trong Amazon S3. Siêu dữ liệu được phát hiện về dữ liệu trong S3 sẽ được đăng ký vào AWS Glue Catalog. Điều này cho phép AWS Glue sử dụng thông tin đã được lập danh mục cho xử lý ETL và cho phép các dịch vụ AWS khác như Amazon Athena truy vấn dữ liệu lưu trữ trong Amazon S3.

![](/images/2.discover/2_01.png)

### Giới thiệu về AWS Glue
**AWS Glue** là một dịch vụ ETL (trích xuất, chuyển đổi và tải) không máy chủ, được quản lý hoàn toàn, giúp đơn giản hóa và giảm chi phí trong việc phân loại, làm sạch, làm giàu và di chuyển dữ liệu giữa các kho dữ liệu khác nhau một cách đáng tin cậy. AWS Glue bao gồm các thành phần cốt lõi sau:

- **Data Catalog** – một kho trung tâm để lưu trữ siêu dữ liệu về cấu trúc và hoạt động của các tài sản dữ liệu.
- **ETL Engine** – tự động sinh mã Scala hoặc Python.
- **Jobs System** – cung cấp hạ tầng được quản lý để điều phối các quy trình ETL của bạn.

### Nội dung
- [Tạo Glue Crawler](2.1-creategluecrawler/)
- [Chạy Glue Crawler](2.2-rungluecrawler/)
- [Xem lại siêu dữ liệu trong Glue Data Catalog](2.3-review/)
