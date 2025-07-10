---
title : "Tạo Amazon Cognito User Pool"
date : 2025-06-15
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

### **5.1. Tạo Amazon Cognito User Pool**

Chúng ta sẽ tạo một User Pool trong Amazon Cognito để quản lý người dùng (đăng ký, đăng nhập) cho ứng dụng chat của mình.

1.  Trong ô tìm kiếm của **AWS Console**, gõ "Cognito" và chọn dịch vụ **Amazon Cognito**.
    * Ở thanh điều hướng bên trái, chọn **User pools**.
    * Nhấn nút **Create user pool** (Tạo nhóm người dùng).
    ![ConnectPrivate](/images/au_5.1_1.png)

#### **Bước 5.1.1: Cấu hình trải nghiệm đăng nhập (Configure sign-in experience)**

* **Define your application (Xác định ứng dụng của bạn):** Chọn **Single-page application (SPA)**.
* **Name your application (Tên ứng dụng của bạn):** Nhập tên cho ứng dụng, ví dụ: `RealTimeChat` (hoặc tên tùy chọn).
* **Cognito user pool sign-in options (Tùy chọn đăng nhập nhóm người dùng Cognito):** Chọn **Username**. (Đây là cách đơn giản nhất cho workshop này).
* **Required attributes for sign-up (Thuộc tính bắt buộc khi đăng ký):** Chọn **Email** (để yêu cầu người dùng cung cấp địa chỉ email khi đăng ký).
* **Add a return URL (Thêm URL chuyển hướng):** Nhập `http://localhost:3000/` (Đây là URL mặc định của ứng dụng React của bạn khi chạy local).
    * *Lưu ý:* Nếu bạn đã triển khai ứng dụng lên AWS Amplify Hosting, bạn cũng cần thêm URL của ứng dụng đã triển khai vào đây, ví dụ: `https://master.d285j22zzz8mbh.amplifyapp.com/`.
* Cuộn xuống cuối trang và nhấn nút **Create user directory** (Tạo thư mục người dùng).
    ![ConnectPrivate](/images/au_5.1_2.png)
    ![ConnectPrivate](/images/au_5.1_3.png)

**Chúc mừng! Bạn đã thành công tạo Amazon Cognito User Pool.** User Pool này sẽ được sử dụng để xác thực người dùng cho ứng dụng của bạn.
    ![ConnectPrivate](/images/au_5.1_4.png)
    ![ConnectPrivate](/images/au_5.1_5.png)