---
title : "Test Run"
date : 2025-06-15
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

### **5.4. Test Run**

After completing the steps above, we will check if the web chat application is working correctly.

#### **Step 5.4.1: Access the Application**

1.  Access the URL Domain you received from the "3. Set up AWS Amplify Hosting" section.
    * **Example:** `https://master.d285j22zzz8mbh.amplifyapp.com/`
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_1.png)

2.  You will see the application's login/signup interface.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_2.png)

#### **Step 5.4.2: Create Account and Log in**

1.  Click the **"Create Account"** tab.
2.  Fill in the required information such as **email**, **username**, **password**, and click the **Create Account** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_3.png)

3.  After clicking **Create Account**, you will be redirected to the account verification page.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_4.png)

4.  Go to your **email** inbox to receive the verification code from Amazon Cognito.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_5.png)

5.  Enter the received verification code into the field and click the **Confirm** button.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_6.png)

6.  After successful verification, you will be directed to the main chat page of the application.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_7.png)

#### **Step 5.4.3: Test Real-time Chat Functionality**

1.  Try sending any message.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_8.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_9.png)

2.  To test the real-time feature, open the application in another browser (or incognito tab) and create an additional account to log in.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_10.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_11.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_12.png)

3.  From the new account, send a message.
4.  Observe the browser tab of the original account. You will see the message from the new account appear immediately. This confirms that the real-time chat feature is working.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.4_13.png)

---