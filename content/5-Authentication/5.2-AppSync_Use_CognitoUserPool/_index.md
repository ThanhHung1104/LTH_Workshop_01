---
title : "Configure AWS AppSync API to Use Cognito User Pools"
date : 2025-06-15
weight : 2 
chapter : false
pre : " <b> 5.2. </b> "
---

### **5.2. Configure AWS AppSync API to Use Cognito User Pools**

Now, we will configure your AWS AppSync API to use the newly created Amazon Cognito User Pool as the primary authorization method.

1.  **Access the AWS AppSync service again:**
    * In the **AWS Console**, find and select the **AWS AppSync** service.
    * Select your API: `RealtimeChatAppAPI_Final`.
    ![ConnectPrivate](/images/au_5.2_1.png)

2.  **Initiate changing the default authorization method:**
    * In the left navigation pane, select **Settings**.
    * In the **Primary authorization mode** section, click the **Edit** button.
    ![ConnectPrivate](/images/au_5.2_2.png)

3.  **Configure the primary authorization method and Save:**
    * On the edit interface that appears:
    * In the **Primary authorization mode** field, select **Amazon Cognito User Pools**.
    * **AWS Region:** Select your AWS region (e.g., `US-EAST-1`).
    * **User pool:** Select the User Pool you created in the previous step (e.g., `RealTimeChat`).
    * Click the **Save** button.
    ![ConnectPrivate](/images/au_5.2_3.png)

4.  **Confirm authorization method change:**
    * After clicking **Save** in the step above, an **"Edit primary authorization mode"** confirmation dialog will appear.
    * Check the box **"Instead of deleting, make API key an additional authorization mode"**.
    * To confirm this change, type exactly **`confirm`** into the text field.
    * Click the **Confirm** button.
    ![ConnectPrivate](/images/au_5.2_4.png)

**Congratulations! You have successfully configured your AWS AppSync API to use Amazon Cognito User Pools for user authentication.**
    ![ConnectPrivate](/images/au_5.2_5.png)