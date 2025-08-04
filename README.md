
# AWS Serverless Data Lake

## 📄 Executive Summary

### Problem Statement  
Nhiều tổ chức và doanh nghiệp hiện đang gặp khó khăn trong việc phân tích và khai thác dữ liệu lớn do thiếu hệ thống phân tích dữ liệu hiện đại, linh hoạt và tiết kiệm chi phí. Dữ liệu dạng bán cấu trúc từ nhiều nguồn như CSV, S3 logs, logs IoT... không được xử lý đúng cách, dẫn đến khó tối ưu hóa insight và hiệu suất kinh doanh.

### Solution Overview  
Dự án này xây dựng một nền tảng phân tích dữ liệu đầu-cuối (end-to-end) trên AWS, xử lý tập dữ liệu NYC Taxi Trip từ thô sang phân tích trực quan, gồm các thành phần chính:

- Khám phá dữ liệu bằng Amazon Athena
- Chuyển đổi dữ liệu ETL bằng AWS Glue Studio
- Catalog và phân tích nâng cao bằng Glue + Athena
- Trực quan hóa dữ liệu với Amazon QuickSight

### Business Benefits

- Giảm thời gian phân tích dữ liệu từ vài ngày xuống còn vài giờ
- Tăng chất lượng dữ liệu thông qua quá trình làm sạch và enrich tự động
- Khả năng mở rộng không giới hạn nhờ AWS serverless
- Cung cấp báo cáo và dashboard BI trực quan hỗ trợ quyết định chiến lược

### Investment & Timeline

- Thời gian triển khai: ~3 ngày cho MVP
- AWS Free Tier hoặc <$30/tháng nếu dùng dữ liệu lớn hơn
- Nhân sự yêu cầu: 1-2 Data Engineers

---

## 🎯 Problem Statement

### Current Situation  
Dữ liệu taxi của NYC hiện tồn tại dưới dạng CSV, có các vấn đề như:

- Trường dữ liệu bị bao quanh bởi dấu ngoặc kép
- Thiếu metadata (schema)
- Nhiều dòng có giá trị NULL hoặc lỗi
- Không được tổ chức để phân tích theo thời gian, địa điểm

### Pain Points

- Việc phân tích mất thời gian và không hiệu quả
- Không thể tạo dashboard BI dễ dàng từ dữ liệu thô
- Rủi ro chất lượng dữ liệu làm sai lệch phân tích

### Stakeholders  

- Nhà phân tích dữ liệu: cần truy vấn nhanh, chính xác
- Quản lý: cần dashboard trực quan
- Kỹ sư dữ liệu: cần pipeline tự động hóa

### Business Consequences

- Mất khả năng ra quyết định nhanh
- Chi phí tăng cao khi phải xử lý dữ liệu thủ công

---

## 🏗️ Solution Architecture

### High-Level Diagram

```
S3 (raw) --> AWS Glue Crawler --> Athena
         ↘ Glue Studio ETL Jobs ↘
            S3 (transformed) --> Glue Catalog --> Athena/QuickSight
```

### AWS Services Used

- Amazon S3 – Lưu trữ dữ liệu thô và kết quả ETL
- AWS Glue Studio – ETL pipeline (serverless Spark)
- AWS Glue Catalog – Metadata và schema registry
- Amazon Athena – Phân tích dữ liệu bằng SQL
- Amazon QuickSight – BI dashboard

### Data Flow

1. Raw CSV → Crawled và tạo schema
2. Athena → Preview và khám phá lỗi
3. Glue Studio → ETL + enrich
4. Crawler lại → Catalog transformed data
5. QuickSight → Dashboard

### Security & Compliance

- IAM Roles tách biệt theo chức năng (ETL, Athena, QuickSight)
- Truy cập dữ liệu qua S3 với least privilege
- Glue và Athena hoạt động theo workgroup đã cấu hình

### Scalability

- Glue job scale tự động theo khối lượng dữ liệu
- QuickSight dùng SPICE cho hiệu năng cao
- Athena hỗ trợ phân tích tới petabyte dữ liệu

---

## 🔧 Technical Implementation

### Implementation Phases

1. **Data Discovery**: Dùng Athena để preview và hiểu cấu trúc dữ liệu
2. **ETL with Glue Studio**: Làm sạch, lọc dữ liệu Q4/2020, đổi tên cột, enrich
3. **Catalog Transformed Data**: Dùng Glue crawler để định nghĩa bảng mới
4. **Athena View**: Tạo view enriched dữ liệu có label rõ ràng
5. **Visualization**: Kết nối QuickSight tới Athena, tạo biểu đồ

### Technical Requirements

- S3 bucket (2 buckets: raw + transformed)
- Glue Studio job 1 DPU, dùng Spark 3
- Athena workgroup `primary`
- QuickSight Standard edition

---

## 📅 Timeline & Milestones

| Phase                     | Duration | Deliverable                          |
|--------------------------|----------|--------------------------------------|
| Data Discovery           | 0.5 day  | Xác minh schema & chất lượng dữ liệu |
| Glue ETL Job             | 1 day    | Dataset đã làm sạch và enriched      |
| Glue Crawler + View      | 0.5 day  | Bảng và View cho QuickSight          |
| Dashboard QuickSight     | 1 day    | Dashboard với biểu đồ phân tích      |

- Buffer: 0.5 day cho lỗi job hoặc S3 permission

---

## 💰 Budget Estimation

### AWS Costs (ước tính theo 1 tháng)

| Component           | Cost                     |
|---------------------|--------------------------|
| S3 Storage (5GB)    | ~$0.12                   |
| Glue Job (10 runs)  | ~$2                      |
| Athena Queries      | ~$3                      |
| QuickSight Standard | ~$9/user                 |
| **Tổng cộng**       | **~$15 - $20/tháng**     |

### ROI & Optimization

- Tăng tốc độ phân tích từ >1 ngày xuống vài phút
- Giảm chi phí ETL nhờ Glue serverless
- Tái sử dụng được kiến trúc này cho các dự án sau

---

## ⚠️ Risk Assessment

| Risk                                | Impact     | Likelihood | Mitigation                         |
|-------------------------------------|------------|------------|------------------------------------|
| Glue job failed                     | High       | Medium     | Logs, retry + debug mode           |
| Dữ liệu mới khác schema             | Medium     | High       | Bổ sung Glue Crawler định kỳ       |
| Chi phí Athena tăng đột biến        | Medium     | Low        | Dùng partition + kiểm soát query   |
| Sự cố permission giữa các service   | High       | Medium     | Rà soát IAM role kỹ càng           |
| QuickSight không truy cập được data | Medium     | Low        | Kiểm tra kết nối Athena/S3         |

---

## 🎯 Expected Outcomes

### Success Metrics

- Truy vấn trả về < 2s (Athena)
- Job ETL xử lý ≥ 99% dữ liệu hợp lệ
- Dashboard QuickSight đầy đủ thông tin

### Benefits

- **0-6 tháng**: Tăng hiệu suất phân tích dữ liệu
- **6-18 tháng**: Có nền tảng BI cho các loại dữ liệu khác
- **18+ tháng**: Tích hợp hệ thống báo cáo tự động

### Strategic Capabilities

- Khả năng mở rộng sang nhiều dataset khác
- Có sẵn khung kiến trúc chuẩn hóa trên AWS
- Tăng năng lực phân tích nội bộ doanh nghiệp
