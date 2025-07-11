---
title : "Create DynamoDB Table"
date : 2025-06-15
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

### **4.1. Create DynamoDB Table**

We will use Amazon DynamoDB, a high-performance NoSQL database, to store chat messages in our application.

1.  In the **AWS Console** search bar, type "DynamoDB" and select the **DynamoDB** service.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.1_1.png)

2.  In the left navigation pane, select **Tables**.

3.  Click the **Create table** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.1_2.png)

4.  **Fill in the table information:**
    * **Table name:** Enter a name for your table, e.g., `RealTimeChat` (or any name you prefer).
    * **Partition key:** Type `id`, select **String** type. This will be the unique primary key for each item (record) in your table.
    * Leave other settings as default.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.1_3.png)

5.  Scroll down to the bottom of the page and click the **Create table** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.1_4.png)

6.  Wait for the table's status to change to **Active**. Once the table is Active, it's ready for use.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.1_5.png)

**Congratulations! You have successfully created the DynamoDB database for your chat application.**