---
title: "Chuẩn bị"
weight: 1 
chapter: false
pre: " <b> 1. </b> "
---

Chúng ta sẽ bắt đầu bằng cách thiết lập các tài nguyên cần thiết cho workshop này. Chúng ta sẽ tạo các bucket S3 để lưu trữ tập tin và các vai trò IAM phù hợp cho các dịch vụ sẽ sử dụng. Các tài nguyên này đã được định nghĩa sẵn trong một mẫu CloudFormation.

- Truy cập [CloudFormation trong AWS Console](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks?filteringText=&filteringStatus=active&viewNested=true).
- Trong menu điều hướng bên phải, nhấn **Create stack** và chọn **With new resources (standard)**.
- Tải xuống tập tin này: [Mẫu CFN](https://drive.google.com/uc?export=download&id=1SRDkQrSHtpAknpcRDSyAc2TIMxHqU63h).
- Chọn **Upload a template file**, sau đó tải lên tập tin bạn vừa tải về.
- Nhấn **Next**.
- Đặt tên cho stack là `sdlj-workshop`
- Nhấn **Next** cho đến khi bạn đến trang Review.
- Tích vào ô **I Acknowledge that AWS CloudFormation might create IAM resources with custom names**.
- Nhấn **Submit**.
- Chờ quá trình khởi tạo tài nguyên hoàn tất.

![](/images/1.prepare/001-prepare.png)  
![](/images/1.prepare/002-prepare.png)
