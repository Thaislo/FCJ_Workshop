---
title : "Connect to a Data source"
weight : 2
chapter : false
pre : " <b> 6.2 </b> "
---
#### Create a Dataset in QuickSight
- On the **QuickSight** page, click **Datasets** in the left navigation pane.
- In the top-right corner of the screen, click **New dataset**.
![](../../images/6.visualize/7.png)
- Select **Athena**.
![](../../images/6.visualize/8.png)
- In the **New Athena data source** window, provide the following information:
  - **Data source name** – `Athena - SDL Jumpstart`
  - **Athena workgroup** – `primary`
  - Then, click **Create Data Source**.
![](../../images/6.visualize/9.png)
- In the **Choose your table** window, provide the following information:
  - **Catalog** – `AwsDataCatalog`
  - **Database** – `nyctaxi_db`
  - **Tables** – `v_yellow_tripdata`
  - Then, click **Select**.
![](../../images/6.visualize/10.png)
- In the **Finish dataset creation** window, select **Import to SPICE for quicker analytics**. Then, click **Edit/Preview data**.
![](../../images/6.visualize/11.png)
{{% notice info %}}
SPICE stands for **Super-fast**, **Parallel**, **In-memory Calculation Engine**. It is designed for fast, advanced calculations and data serving. SPICE capacity is shared among all QuickSight users within an AWS Region.
{{% /notice %}}