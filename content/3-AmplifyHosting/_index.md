---
title : "Set up AWS Amplify Hosting"
date : 2025-06-15
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---

## **Set up AWS Amplify Hosting**

You have prepared the frontend source code on GitHub. Now, we will connect it to AWS Amplify Hosting to deploy the application.

### **1. Access AWS Amplify and connect Repository**

1.  **Log in to the AWS Management Console.**
2.  Find and select the **AWS Amplify** service.
3.  On the main Amplify Console page, click the **"Deploy an app"** button.
![ConnectPrivate](/images/ah_1.png) 

#### **Step 1: Choose Source code provider and branch**

1.  In the **Connect repository** section, select your source code provider (e.g., **GitHub**).
2.  Click the **Next** button.
    * *Note:* Amplify will request access to your GitHub account. Please grant access and authorize according to GitHub's instructions.
![ConnectPrivate](/images/ah_2.png) 

#### **Step 2: Choose Repository and Branch**

1.  After granting access, you will see a list of your repositories.
2.  Select your repository (e.g., **`ThanhHung1104/realtime-chat-frontend`**).
3.  In the **Branch** section, select the branch you want to deploy (e.g., **`main`** or **`master`**).
4.  Click the **Next** button.
    ![ConnectPrivate](/images/ah_3.png) 
    ![ConnectPrivate](/images/ah_4.png) 

#### **Step 3: Configure App settings**

1.  In the **App name** section, the application name will be automatically filled (e.g., **`realtime-chat-app-frontend`**). You can change it if you wish.
2.  **Build settings** will be automatically detected by Amplify (e.g., `Frontend build command: npm run build`, `Build output directory: build`). Please verify them to ensure accuracy.
3.  Click the **Next** button.
    ![ConnectPrivate](/images/ah_5.png) 

#### **Step 4: Review and Deploy**

1.  Review all your configured settings in the **Review** section.
2.  Click the **Save and deploy** button.
    ![ConnectPrivate](/images/ah_6.png) 

### **2. Successful Deployment and Accessing the Application**

After clicking **Save and deploy**, you will be redirected to the application's deployment status page.

* The system will start the **Provisioning**, **Building**, and **Deploying** processes. Please wait until all stages change to **"Deployed"** status (green). This process may take a few minutes.
* Once the deployment is complete, you will receive an automatically assigned **URL Domain** from AWS Amplify.
    ![ConnectPrivate](/images/ah_7.png) 

* **Access the assigned Domain:** `https://master.d285j22zzz8mbh.amplifyapp.com/`
    ![ConnectPrivate](/images/ah_8.png) 

**Conclusion:**

You have **successfully deployed the frontend** of your real-time chat application and are running it using **AWS Amplify Hosting**. From now on, you can **update your code** on your GitHub repository, and AWS Amplify Hosting will automatically trigger a new build and deployment process, keeping your application always up-to-date.

---