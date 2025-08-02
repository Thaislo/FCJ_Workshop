---
title: "Loại bỏ các bản ghi có giá trị NULL"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

- Nhấn vào tab **Transform** và chọn **Custom transform**.
![](../../../images/4.transforming/9.png)

- Trong phần **Transform – Custom code**, cấu hình như sau:
  - **Name** – `Remove Records with NULL`
  - Thêm đoạn mã sau vào **Code block**:
  
{{< highlight python >}}
def MyTransform(glueContext, dfc) -> DynamicFrameCollection:
    df = dfc.select(list(dfc.keys())[0]).toDF().na.drop()
    results = DynamicFrame.fromDF(df, glueContext, "results")
    return DynamicFrameCollection({"results": results}, glueContext)
{{< /highlight >}}

![](../../../images/4.transforming/10.png)

- Nhấn vào tab **Transform** và chọn **SelectFromCollection**.
- Trong phần **Transform – SelectFromCollection**, cấu hình như sau:
  - **Name** – `SelectFromCollection`
  - **Frame index** – `0`
![](../../../images/4.transforming/11.png)

Hãy nhớ lưu lại tác vụ của bạn.
![](../../../images/4.transforming/12.png)
