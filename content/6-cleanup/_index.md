+++
title = "Resource Cleanup"
date = 2021
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

### **6. Resource Cleanup**

To avoid incurring unwanted costs after completing this lab, we will proceed with deleting all AWS resources that were created. Please follow the steps in the recommended order to ensure dependencies are handled correctly.

#### **6.1. Delete AWS Amplify Hosting Application**

* **Resources deleted:** Your deployed frontend application, its builds, and associated resources like the CloudFront distribution or S3 bucket created by Amplify.

1.  **Log in to the AWS Management Console.**
2.  Find and select the **Amplify** service.
3.  Select your application (e.g., `realtime-chat-app-frontend`).
4.  In the left menu, click **App settings**.
5.  Click **General settings**.
6.  Click the **Delete app** button.
    ![ConnectPrivate](/images/de_1.png)
7.  Type `Delete` and click **Delete App**.
    ![ConnectPrivate](/images/de_2.png)

#### **6.2. Delete AWS AppSync API**

* **Resources deleted:** Your GraphQL API, its resolvers, the Data Sources that AppSync automatically created for DynamoDB tables, and potentially some related logs in CloudWatch.

1.  In the **AWS Management Console**, find and select the **AWS AppSync** service.
2.  In the left navigation pane, select **APIs**.
3.  Check your API (e.g., **`RealtimeChatAppAPI`**).
4.  In the top right corner, click the **Delete** button.
    ![ConnectPrivate](/images/de_3.png)
5.  Type the exact API name (`RealtimeChatAppAPI`) into the confirmation field, then click **Delete** again.
    ![ConnectPrivate](/images/de_4.png)

#### **6.3. Delete Amazon DynamoDB Tables**

* **Resources deleted:** All DynamoDB tables containing your chat data.

1.  In the **AWS Management Console**, find and select the **DynamoDB** service.
2.  In the left navigation pane, select **Tables**.
3.  Find and select your table(s) created by AppSync (e.g., **`RealTimeChat`**).
4.  For each table, click the **Delete** button.
    ![ConnectPrivate](/images/de_5.png)
5.  Confirm table deletion (usually by typing `confirm` into the confirmation field or checking a box if available), then click **Delete**.
    ![ConnectPrivate](/images/de_6.png)

#### **6.4. Delete Amazon Cognito User Pool**

* **Resources deleted:** All registered user accounts (username, password, email, etc.) and the App Clients you created in that User Pool.

1.  In the **AWS Management Console**, find and select the **Cognito** service.
2.  In the left navigation pane, select **User Pools**.
3.  Select your User Pool (the name you gave it, e.g., **`RealTimeChat`** or `ChatAppUsersPool`).
4.  In the top right corner, click the **Delete** button.
    ![ConnectPrivate](/images/de_7.png)
5.  Confirm and click **Delete**.
    ![ConnectPrivate](/images/de_8.png)

#### **6.5. Delete Unused IAM Roles**

* **Resources deleted:** IAM Roles that AppSync or Cognito used to interact with other services (e.g., Role for AppSync to access DynamoDB, Role for AppSync logging). Sometimes they are automatically deleted when you delete the main services, but sometimes they are not.

1.  In the **AWS Management Console**, find and select the **IAM (Identity and Access Management)** service.
2.  In the left navigation pane, select **Roles**.
3.  In the search bar, look for Roles with names related to your API or the services used. For example:
    * Role for AppSync Service Access: Starts with `AppSyncServiceRole-` or contains your API name (e.g., `RealtimeChatAppAPI_Final-service-role-...` or `AppSyncFullDynamoDBAccessRole` if you created it manually).
    * Role for AppSync Logging: Starts with `AppSyncLoggingRole-` or contains your API ID.
4.  Select the Role(s) that are no longer needed.
5.  Click the **Delete** button.
    ![ConnectPrivate](/images/de_9.png)
6.  Confirm and click **Delete**.
    ![ConnectPrivate](/images/de_10.png)

**After completing all the steps above, you will have cleanly deleted all AWS resources created in this lab and will not incur any further costs.**