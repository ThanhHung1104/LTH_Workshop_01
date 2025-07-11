---
title : "Create Amazon Cognito User Pool"
date : 2025-06-15
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

### **5.1. Create Amazon Cognito User Pool**

We will create a User Pool in Amazon Cognito to manage users (sign-up, sign-in) for our chat application.

1.  In the **AWS Console** search bar, type "Cognito" and select the **Amazon Cognito** service.
    * In the left navigation pane, select **User pools**.
    * Click the **Create user pool** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.1_1.png)

#### **Step 5.1.1: Configure sign-in experience**

* **Define your application:** Select **Single-page application (SPA)**.
* **Name your application:** Enter a name for your application, e.g., `RealTimeChat` (or any preferred name).
* **Cognito user pool sign-in options:** Select **Username**. (This is the simplest method for this workshop). You can choose other options like Email, Phone number if desired.
* **Required attributes for sign-up:** Select **Email** (to require users to provide an email address upon sign-up).
* **Add a return URL:** Enter `http://localhost:3000/` (This is the default URL for your React application when running locally).
    * *Note:* If you have deployed the application to AWS Amplify Hosting, you also need to add the URL of your deployed application here, e.g., `https://master.d285j22zzz8mbh.amplifyapp.com/`.
* Scroll down to the bottom of the page and click the **Create user directory** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.1_2.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.1_3.png)

**Congratulations! You have successfully created your Amazon Cognito User Pool.** This User Pool will be used to authenticate users for your application.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.1_4.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.1_5.png)