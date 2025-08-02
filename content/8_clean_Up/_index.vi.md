---
title: "Dọn dẹp"
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

1. **Xóa dữ liệu khỏi S3**  
   - Chọn từng bucket để **Làm trống (Empty)**, nhập `permanently delete` để xác nhận xóa, sau đó chọn từng bucket để **Xóa (Delete)**  
   ![](../../images/7.clean/2.png)

2. **Xóa CloudFormation Stack**: `sdlj-workshop`  
   - Chọn **sdlj-workshop** rồi bấm **Delete**  
   ![](../../images/7.clean/1.png)

3. **Xóa các Crawler**: `nyc-taxi-crawler`, `nyc-yellow-tripdata-parquet-crawler`  
   - Chọn 2 crawler sau:  
     - **nyc-taxi-crawler**  
     - **nyc-yellow-tripdata-parquet-crawler**  
   - Bấm **Actions**, chọn **Delete crawlers**, rồi nhập **Delete** để xác nhận  
   ![](../../images/7.clean/3.png)

4. **Xóa tác vụ Glue Studio Transform**: `Transform NYC Taxi Trip Data`  
   - Chọn **Transform NYC Taxi Trip Data**, sau đó bấm **Actions** và chọn **Delete job(s)**  
   ![](../../images/7.clean/4.png)

5. **Xóa Cơ sở dữ liệu (Database)**: `nyctaxi_db`  
   - Chọn **nyctaxi_db** rồi bấm **Delete**  
   ![](../../images/7.clean/5.png)

6. **Xóa bảng phân tích Athena – Transformed Yellow Trip Data**: trong Amazon QuickSight  
   ![](../../images/7.clean/6.png)
