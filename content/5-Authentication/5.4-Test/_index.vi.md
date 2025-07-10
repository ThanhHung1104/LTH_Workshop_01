---
title : "Chạy thử"
date : 2025-06-15
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

### **5.4. Chạy thử**

Sau khi hoàn tất các bước trên, chúng ta sẽ kiểm tra xem ứng dụng web chat đã hoạt động đúng hay chưa.

#### **Bước 5.4.1: Truy cập ứng dụng**

1.  Truy cập vào URL Domain mà bạn đã nhận được từ phần "3. Thiết lập AWS Amplify Hosting".
    * **Ví dụ:** `https://master.d285j22zzz8mbh.amplifyapp.com/`
    ![ConnectPrivate](/images/au_5.4_1.png)

2.  Bạn sẽ thấy giao diện đăng nhập/đăng ký của ứng dụng.
    ![ConnectPrivate](/images/au_5.4_2.png)

#### **Bước 5.4.2: Tạo tài khoản và Đăng nhập**

1.  Nhấn vào tab **"Create Account"** (Tạo tài khoản).
2.  Điền các thông tin cần thiết như **email**, **username**, **password**, và nhấn nút **Create Account** (Tạo tài khoản).
    ![ConnectPrivate](/images/au_5.4_3.png)

3.  Sau khi nhấn **Create Account**, bạn sẽ được chuyển đến trang xác thực tài khoản.
    ![ConnectPrivate](/images/au_5.4_4.png)

4.  Vào hộp thư **email** của bạn để nhận mã xác thực từ Amazon Cognito.
    ![ConnectPrivate](/images/au_5.4_5.png)

5.  Nhập mã xác thực vừa nhận vào ô và nhấn nút **Confirm** (Xác nhận).
    ![ConnectPrivate](/images/au_5.4_6.png)

6.  Sau khi xác thực thành công, bạn sẽ được chuyển đến trang chat chính của ứng dụng.
    ![ConnectPrivate](/images/au_5.4_7.png)

#### **Bước 5.4.3: Kiểm tra chức năng chat thời gian thực**

1.  Thử gửi một tin nhắn bất kỳ.
    ![ConnectPrivate](/images/au_5.4_8.png)
    ![ConnectPrivate](/images/au_5.4_9.png)

2.  Để kiểm tra tính năng thời gian thực, hãy mở ứng dụng trên một trình duyệt khác (hoặc tab ẩn danh) và tạo thêm một tài khoản mới để đăng nhập.
    ![ConnectPrivate](/images/au_5.4_10.png)
    ![ConnectPrivate](/images/au_5.4_11.png)
    ![ConnectPrivate](/images/au_5.4_12.png)

3.  Từ tài khoản mới, hãy gửi một tin nhắn.
4.  Quan sát tab trình duyệt của tài khoản ban đầu. Bạn sẽ thấy tin nhắn từ tài khoản mới xuất hiện ngay lập tức . Điều này xác nhận tính năng chat thời gian thực đã hoạt động.
    ![ConnectPrivate](/images/au_5.4_13.png)

---