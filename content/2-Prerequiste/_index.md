---
title : "Prepare the source code"
date : 2025-06-15
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}
You need to have an AWS account and a GitHub account (or other Git providers) ready to perform this lab.
{{% /notice %}}

### **Prepare Frontend Code**

You will download the sample frontend source code from GitHub and prepare it for deployment.

#### **Step 1: Download Sample Source Code (Clone from GitHub)**

1.  **Open a Command Prompt (CMD) window** in the folder where you want to save the source code.
2.  **Run the following command:**
    ```bash
    git clone [https://github.com/ThanhHung1104/realtime-chat-frontend.git](https://github.com/ThanhHung1104/realtime-chat-frontend.git)
    ```
    This command will download the entire source code of the sample chat project to your computer, into a folder named `realtime-chat-frontend`.
    ![ConnectPrivate](/images/cb_1.png) 
3.  **Navigate into the project directory:**
    ```bash
    cd realtime-chat-frontend
    ```

#### **Step 2: Push Source Code to Your GitHub**

After downloading the sample source code, you need to create a repository on your personal GitHub account and push the downloaded source code there. AWS Amplify Hosting will connect to this repository.

1.  **Create a New Project on GitHub:**
    * **Access and log in to your GitHub account.**
    * On the GitHub homepage, click the **New** button (or the `+` icon in the top right corner) to create a new repository.
    * In the **Repository name** field, enter a name for your repository: `realtime-chat-app-frontend` (or a similar name, e.g., `my-chat-app`).
    * Leave other default options as they are (choose `Public` or `Private` as desired, but **make sure NOT to check "Initialize this repository with a README", "Add .gitignore", "Choose a license"**).
    * Click the **Create repository** button.
    * ![ConnectPrivate](/images/cb_2.png) 
    * ![ConnectPrivate](/images/cb_3.png) 
2.  **Push Source Code to Git:**
    * Ensure you are in the root directory of your project (`realtime-chat-app-frontend`) in CMD.
    * **Run the following commands in order:**
        ```bash
        git add .
        git commit -m "Initial commit: Set up real-time chat frontend"
        # IMPORTANT NOTE: Replace 'YOUR_GITHUB_USERNAME' and 'YOUR_REPO_NAME' with your information
        git remote set-url origin [https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPO_NAME.git](https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPO_NAME.git)
        git push -u origin main # Or git push -u origin master (depending on your main branch name)
        ```
        * **Note:** You need to replace `https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPO_NAME.git` in the `git remote set-url origin` command with **YOUR OWN new GitHub repository URL** that you created in Step 2.1.
        * ![ConnectPrivate](/images/cb_4.png) 
        * *Example:*
            ```bash
            git remote set-url origin [https://github.com/ThanhHung1104/realtime-chat-app-frontend.git](https://github.com/ThanhHung1104/realtime-chat-app-frontend.git) 
            ```
        * ![ConnectPrivate](/images/cb_5.png) 
    * *Check on GitHub:*
    * ![ConnectPrivate](/images/cb_6.png) 

You are now ready to start your journey of building a real-time chat application on AWS!