---
title : "Configure Data Sources"
date : 2025-06-15
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

### **4.4. Configure Data Sources**

We will connect the GraphQL API to the created DynamoDB table by configuring a Data Source in AppSync.

1.  In the left navigation pane of **AppSync Console**, select **Data Sources**. Then, click the **Create data source** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_1.png)

2.  **Fill in the data source information:**
    * **Data source name:** Enter a name for your data source, e.g., `RealTimeChatDataSource` (or any name you prefer).
    * **Data source type:** Select **Amazon DynamoDB table**.
    * **Region:** Select the corresponding AWS region (must be the same as where you created the DynamoDB table), which is `us-east-1` here.
    * **Table name:** Select the `ChatMessages` table that you created earlier.
    * **Create or use an existing role:** Select **New role**.
    * Click the **Create** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_2.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_3.png)

**Congratulations! You have successfully created the data source for your AppSync API.**
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_4.png)