---
title : "Thay đổi Code Frontend và push lại code lên github"
date : 2025-06-15
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

### **5.3. Thay đổi Code Frontend và Push lại Code lên GitHub**

Chúng ta cần cập nhật và đẩy lại mã nguồn frontend để kết nối chính xác với backend và phương thức xác thực đã được cấu hình.

#### **Bước 5.3.1: Cập nhật file `src/aws-exports.js`**

Mở file `src/aws-exports.js` trong thư mục mã nguồn của bạn.
![ConnectPrivate](/images/au_5.3_1.png)

Thay thế các giá trị bằng thông tin thực tế từ AWS Console của bạn:

* **`aws_appsync_region`**: Là Region AWS bạn đang thực hiện bài lab (ví dụ: `us-east-1`).

* **`aws_appsync_graphqlEndpoint`**:
    * Truy cập **AWS AppSync Console**.
    * Chọn **APIs**.
    * Chọn API của bạn (ví dụ: `RealtimeChatAppAPI`).
    * Trong bảng điều khiển bên trái, chọn **Settings** (Tổng quan).
    * Tìm và sao chép **API URL** (nó chính là GraphQL endpoint).
    ![ConnectPrivate](/images/au_5.3_2.png)

* **`aws_user_pools_id`**:
    * Vào **AWS AppSync Console** -> Chọn **APIs**.
    * Chọn API của bạn (ví dụ: `RealtimeChatAppAPI`).
    * Trong bảng điều khiển bên trái, chọn **Settings**.
    * Cuộn xuống phần **Amazon Cognito User Pool** để tìm **User Pool ID**.
    ![ConnectPrivate](/images/au_5.3_3.png)

* **`aws_user_pools_web_client_id`**:
    * Vào **Amazon Cognito Console**.
    * Chọn **User pools** (Nhóm người dùng) và chọn User Pool đã tạo (ví dụ: `RealTimeChat`).
    * Ở menu bên trái, chọn **App integration** (Tích hợp ứng dụng).
    * Cuộn xuống phần **App clients**.
    * Chọn App client đã tạo của bạn (ví dụ: `RealTimeChat`).
    * Tại đây, bạn có thể lấy **Client ID**.
    ![ConnectPrivate](/images/au_5.3_4.png)
    ![ConnectPrivate](/images/au_5.3_5.png)

* **`oauth.domain`**:
    * Vào **Amazon Cognito Console**.
    * Chọn **User pools** (Nhóm người dùng) và chọn User Pool đã tạo (ví dụ: `RealTimeChat`).
    * Ở menu bên trái, chọn **App integration**.
    * Cuộn xuống phần **Hosted UI** (Giao diện người dùng được lưu trữ).
    * Tìm **Domain** của bạn (ví dụ: `yourchatdomain-dev.auth.us-east-1.amazoncognito.com`).
    ![ConnectPrivate](/images/au_5.3_6.png)

Sau khi thay thế các thông tin trên, hãy **lưu file `src/aws-exports.js` lại.**
![ConnectPrivate](/images/au_5.3_7.png)

#### **Bước 5.3.2: Đẩy Code đã thay đổi lên GitHub**

1.  **Mở cửa sổ Command Prompt (CMD)** tại thư mục gốc của dự án mã nguồn của bạn.
2.  **Chạy các lệnh sau theo thứ tự:**
    ```bash
    git add .
    git commit -m "Update Amplify configuration for authentication"
    git push origin main # Hoặc git push origin master (tùy thuộc vào tên nhánh chính của bạn)
    ```

**Lưu ý:** Sau khi bạn đẩy code lên GitHub, AWS Amplify Hosting sẽ tự động phát hiện thay đổi và kích hoạt quá trình build và triển khai mới cho ứng dụng frontend của bạn.

---