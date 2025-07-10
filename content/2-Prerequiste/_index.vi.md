---
title : "Chuẩn bị mã nguồn"
date : 2025-06-15
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}
Bạn cần có tài khoản AWS và tài khoản Github (hoặc các nhà cung cấp Git khác) đã sẵn sàng để thực hiện bài thực hành này.
{{% /notice %}}

### **Chuẩn bị Code Frontend**

Bạn sẽ tải mã nguồn frontend mẫu từ GitHub và chuẩn bị nó cho việc triển khai.

#### **Bước 1: Tải Mã nguồn mẫu (Clone từ GitHub)**

1.  **Mở cửa sổ Command Prompt (CMD)** tại folder bạn muốn lưu mã nguồn.
2.  **Chạy lệnh sau:**
    ```bash
    git clone https://github.com/ThanhHung1104/realtime-chat-frontend.git
    ```
    Lệnh này sẽ tải toàn bộ mã nguồn của dự án chat mẫu về máy tính của bạn, vào một thư mục có tên `realtime-chat-frontend`.
    ![ConnectPrivate](/images/cb_1.png) 
3.  **Di chuyển vào thư mục dự án:**
    ```bash
    cd realtime-chat-frontend
    ```

#### **Bước 2: Đẩy Mã nguồn lên GitHub của bạn**

Sau khi tải mã nguồn mẫu, bạn cần tạo một kho lưu trữ (repository) trên tài khoản GitHub cá nhân của mình và đẩy mã nguồn đã tải lên đó. AWS Amplify Hosting sẽ kết nối với kho lưu trữ này.

1.  **Tạo Project mới trên GitHub:**
    * **Truy cập và đăng nhập vào tài khoản GitHub của bạn.**
    * Trên trang chính của GitHub, nhấn vào nút **New** (hoặc biểu tượng dấu `+` ở góc trên bên phải) để tạo một kho lưu trữ mới.
      ![ConnectPrivate](/images/cb_2.png) 
    * Trong phần **Repository name**, nhập tên cho kho lưu trữ của bạn: `realtime-chat-app-frontend` (hoặc tên tương tự, ví dụ: `my-chat-app`).
    * Để nguyên các lựa chọn mặc định khác (chọn `Public` hoặc `Private` tùy ý, nhưng **đảm bảo KHÔNG tích chọn "Initialize this repository with a README", "Add .gitignore", "Choose a license"**).
    * Nhấn nút **Create repository**.
      ![ConnectPrivate](/images/cb_3.png) 
2.  **Đưa Mã nguồn lên Git:**
    * Đảm bảo bạn đang ở trong thư mục gốc của dự án (`realtime-chat-app-frontend`) trong CMD.
    * **Chạy các lệnh sau theo thứ tự:**
        ```bash
        git add .
        git commit -m "Initial commit: Set up real-time chat frontend"
        # LƯU Ý QUAN TRỌNG: Thay thế 'YOUR_GITHUB_USERNAME' và 'YOUR_REPO_NAME' bằng thông tin của bạn
        git remote set-url origin https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPO_NAME.git
        git push -u origin main # Hoặc git push -u origin master (tùy thuộc vào tên nhánh chính của bạn)
        ```
        * **Lưu ý:** Bạn cần thay thế `https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPO_NAME.git` trong lệnh `git remote add origin` bằng **URL kho lưu trữ GitHub mới của CHÍNH BẠN** mà bạn vừa tạo ở bước trên. 
        ![ConnectPrivate](/images/cb_4.png) 
        * ví dụ 
        ```bash
        git remote set-url origin https://github.com/ThanhHung1104/realtime-chat-app-frontend.git 
        ```
    ![ConnectPrivate](/images/cb_5.png) 
    * kiểm tra bên github
    ![ConnectPrivate](/images/cb_6.png) 

Bạn đã sẵn sàng để bắt đầu hành trình xây dựng ứng dụng chat thời gian thực trên AWS!