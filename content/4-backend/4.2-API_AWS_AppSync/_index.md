---
title : "Create AWS AppSync API"
date : 2025-06-15
weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---

### **4.2. Create AWS AppSync API**

Now, we will create the main GraphQL API service for your real-time chat application. This API will be the connection point between your frontend and backend.

1.  In the **AWS Console** search bar, type "AppSync" and select the **AWS AppSync** service.

2.  Click the **Create API** button and choose **GraphQL API**.
    ![ConnectPrivate](/images/be_4.2_1.png)

#### **Step 4.2.1: Choose API type**

* **API type:** Keep the default selection as **GraphQL APIs**. (This is the type of GraphQL API that manages a single schema, suitable for our needs).
* **GraphQL API Data Source:** Select the **Design from scratch** option.
* Scroll down to the bottom of the page and click the **Next** button.
    ![ConnectPrivate](/images/be_4.2_2.png)

#### **Step 4.2.2: Specify API details**

* **API name:** Enter a name for your API, e.g., `RealTimeChatAppAPI_Final`.
* **Private API configuration:** Make sure **NOT to select** **Use private API features**.
* Click the **Next** button.
    ![ConnectPrivate](/images/be_4.2_3.png)

#### **Step 4.2.3: Specify GraphQL resources**

* **Create a GraphQL type backed by a DynamoDB table:** Select **Create GraphQL resources later**.
* Click the **Next** button.
    ![ConnectPrivate](/images/4.2_4.png)

#### **Step 4.2.4: Review and create API**

1.  Review your API configuration settings in the **Review** section.
2.  Click the **Create API** button.
    ![ConnectPrivate](/images/4.2_5.png)

**Congratulations! You have successfully created your AWS AppSync API.**
    ![ConnectPrivate](/images/4.2_6.png)