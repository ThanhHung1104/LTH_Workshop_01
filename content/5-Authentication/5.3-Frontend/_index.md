---
title : "Modify Frontend Code and Push Code to GitHub"
date : 2025-06-15
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

### **5.3. Modify Frontend Code and Push Code to GitHub**

We need to update and push the frontend source code to correctly connect the backend and the configured authentication method.

#### **Step 5.3.1: Update `src/aws-exports.js` file**

Open the `src/aws-exports.js` file in your source code directory.
![ConnectPrivate](/images/au_5.3_1.png)

Replace the values with actual information from your AWS Console:

* **`aws_appsync_region`**: This is your AWS Region where you are performing the lab (e.g., `us-east-1`).

* **`aws_appsync_graphqlEndpoint`**:
    * Access **AWS AppSync Console**.
    * Select **APIs**.
    * Select your API (e.g., `RealtimeChatAppAPI`).
    * In the left control panel, select **Overview**.
    * Find and copy the **API URL** (which is the GraphQL endpoint).
    ![ConnectPrivate](/images/au_5.3_2.png)

* **`aws_user_pools_id`**:
    * Go to **AWS AppSync Console** -> Select **APIs**.
    * Select your API (e.g., `RealtimeChatAppAPI`).
    * In the left control panel, select **Settings**.
    * Scroll down to the **Amazon Cognito User Pool** section to find your **User Pool ID**.
    ![ConnectPrivate](/images/au_5.3_3.png)

* **`aws_user_pools_web_client_id`**:
    * Go to **Amazon Cognito Console**.
    * Select **User pools** and choose your created User Pool (e.g., `RealTimeChat`).
    * In the left menu, select **App integration**.
    * Scroll down to the **App clients** section.
    * Select your created App client (e.g., `RealTimeChat`).
    * Here, you can find the **Client ID**.
    ![ConnectPrivate](/images/au_5.3_4.png)
    ![ConnectPrivate](/images/au_5.3_5.png)

* **`oauth.domain`**:
    * Go to **Amazon Cognito Console**.
    * Select **User pools** and choose your created User Pool (e.g., `RealTimeChat`).
    * In the left menu, select **App integration**.
    * Scroll down to the **Hosted UI** section.
    * Find your **Domain** (e.g., `yourchatdomain-dev.auth.us-east-1.amazoncognito.com`).
    ![ConnectPrivate](/images/au_5.3_6.png)

After replacing the above information, **save the `src/aws-exports.js` file.**
![ConnectPrivate](/images/au_5.3_7.png)

#### **Step 5.3.2: Push the Modified Code to GitHub**

1.  **Open a Command Prompt (CMD) window** in the root directory of your source code project.
2.  **Run the following commands in order:**
    ```bash
    git add .
    git commit -m "Update Amplify configuration for authentication"
    git push origin main # Or git push origin master (depending on your main branch name)
    ```

**Note:** After you push your code to GitHub, AWS Amplify Hosting will automatically detect the changes and trigger a new build and deployment process for your frontend application.

---