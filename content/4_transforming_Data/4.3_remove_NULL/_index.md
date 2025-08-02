---
title : "Remove records with NULL values"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

- Click on the **Transform** tab and select **Custom transform**.
![](../../images/4.transforming/9.png)
- In **Transform – Custom code**, specify the following:
  - **Name** – `Remove Records with NULL`
  - Add the following code to the **Code block**:
{{< highlight python >}}
def MyTransform(glueContext, dfc) -> DynamicFrameCollection:
    df = dfc.select(list(dfc.keys())[0]).toDF().na.drop()
    results = DynamicFrame.fromDF(df, glueContext, "results")
    return DynamicFrameCollection({"results": results}, glueContext)
{{< /highlight >}}
![](../../images/4.transforming/10.png)
- Click on the **Transform** tab and select **SelectFromCollection**.
- In **Transform – SelectFromCollection**, specify the following:
  - **Name** – `SelectFromCollection`
  - **Frame index** – `0`
![](../../images/4.transforming/11.png)
Remember to save your job.
![](../../images/4.transforming/12.png)