---
title: "Sử dụng Amazon Athena lần đầu"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

**Amazon Athena** tự động lưu kết quả truy vấn và siêu dữ liệu của mỗi lần chạy tại một vị trí kết quả truy vấn mà bạn có thể chỉ định trong **Amazon S3**. Nếu cần, bạn có thể truy cập các tập tin trong vị trí đó để xử lý tiếp. Bạn cũng có thể tải trực tiếp các tập tin kết quả truy vấn từ giao diện Athena Console.

- Truy cập [Athena Console](https://ap-southeast-1.console.aws.amazon.com/athena/home?region=ap-southeast-1#/landing-page). Nhấn **Launch query editor**.

![](../../images/3.exploring/1.png)

- Ở menu trên cùng, nhấn vào **Workgroup: primary**.

![](../../images/3.exploring/2.png)

- Chọn **Settings**, nhấn **Browse S3**, và chọn `s3://serverlessanalytics-[your-account-id]-athena` làm giá trị cho trường **Location of query result - optional**.

![](../../images/3.exploring/3.png)  
![](../../images/3.exploring/4.png)

- Cuộn xuống cuối trang và nhấn **Save**.

![](../../images/3.exploring/5.png)

- Quay lại menu trên cùng và nhấn **Editor** để quay lại trang **Query editor**.
