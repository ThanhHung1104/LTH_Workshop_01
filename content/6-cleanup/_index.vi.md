+++
title = "Dọn dẹp tài nguyên"
date = 2021
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

### **6. Dọn dẹp tài nguyên**

Để tránh phát sinh chi phí không mong muốn sau khi hoàn thành bài thực hành này, chúng ta sẽ tiến hành xóa tất cả các tài nguyên AWS đã được tạo. Vui lòng làm theo các bước theo đúng trình tự được khuyến nghị để đảm bảo các phụ thuộc được xử lý đúng cách.

#### **6.1. Xóa ứng dụng AWS Amplify Hosting**

* **Tài nguyên bị xóa:** Ứng dụng frontend của bạn đã triển khai, các bản build, và các tài nguyên liên quan như CloudFront distribution hay S3 bucket mà Amplify đã tạo ra.

1.  **Đăng nhập vào AWS Management Console.**
2.  Tìm và chọn dịch vụ **Amplify**.
3.  Chọn ứng dụng của bạn (ví dụ: `realtime-chat-app-frontend`).
4.  Ở thanh điều hướng bên trái, nhấn vào **App settings**.
5.  Nhấn vào **General settings**.
6.  Nhấn nút **Delete app** (Xóa).
    ![ConnectPrivate](/images/de_1.png)
7.  Nhập `Delete` và nhấn **Delete App**.
    ![ConnectPrivate](/images/de_2.png)

#### **6.2. Xóa API AWS AppSync**

* **Tài nguyên bị xóa:** API GraphQL của bạn, các resolvers, các nguồn dữ liệu (Data Sources) mà AppSync đã tự động tạo cho các bảng DynamoDB, và có thể cả một số log liên quan trong CloudWatch.

1.  Trong **AWS Management Console**, tìm và chọn dịch vụ **AWS AppSync**.
2.  Ở thanh điều hướng bên trái, chọn **APIs**.
3.  Tích chọn API của bạn (ví dụ: **`RealtimeChatAppAPI`**).
4.  Ở góc trên bên phải, nhấn nút **Delete** (Xóa).
    ![ConnectPrivate](/images/de_3.png)
5.  Nhập chính xác tên API (`RealtimeChatAppAPI`) vào ô xác nhận, sau đó nhấn **Delete** lần nữa.
    ![ConnectPrivate](/images/de_4.png)

#### **6.3. Xóa các Bảng Amazon DynamoDB**

* **Tài nguyên bị xóa:** Tất cả các bảng DynamoDB chứa dữ liệu chat của bạn.

1.  Trong **AWS Management Console**, tìm và chọn dịch vụ **DynamoDB**.
2.  Ở thanh điều hướng bên trái, chọn **Tables** (Bảng).
3.  Tìm và chọn bảng của bạn đã được tạo bởi AppSync (ví dụ: **`RealTimeChat`**).
4.  Đối với mỗi bảng, nhấn nút **Delete** (Xóa).
    ![ConnectPrivate](/images/de_5.png)
5.  Xác nhận xóa bảng (thường là gõ `confirm` vào ô xác nhận hoặc tích chọn nếu có), sau đó nhấn **Delete**.
    ![ConnectPrivate](/images/de_6.png)

#### **6.4. Xóa Amazon Cognito User Pool**

* **Tài nguyên bị xóa:** Tất cả tài khoản người dùng đã đăng ký (username, password, email, v.v.) và các App Client bạn đã tạo trong User Pool đó.

1.  Trong **AWS Management Console**, tìm và chọn dịch vụ **Cognito**.
2.  Ở thanh điều hướng bên trái, chọn **User Pools** (Nhóm người dùng).
3.  Chọn User Pool của bạn (tên bạn đã đặt, ví dụ: **`RealTimeChat`** hoặc `ChatAppUsersPool`).
4.  Ở góc trên bên phải, nhấn nút **Delete** (Xóa nhóm người dùng).
    ![ConnectPrivate](/images/de_7.png)
5.  Xác nhận và nhấn **Delete**.
    ![ConnectPrivate](/images/de_8.png)

#### **6.5. Xóa các IAM Role không còn sử dụng**

* **Tài nguyên bị xóa:** Các Role IAM mà AppSync hoặc Cognito đã sử dụng để tương tác với các dịch vụ khác (ví dụ: Role để AppSync truy cập DynamoDB, Role để AppSync ghi log). Đôi khi chúng sẽ tự động xóa khi bạn xóa các dịch vụ chính, nhưng đôi khi không.

1.  Trong **AWS Management Console**, tìm và chọn dịch vụ **IAM (Identity and Access Management)**.
2.  Ở thanh điều hướng bên trái, chọn **Roles**.
3.  Trong thanh tìm kiếm, tìm kiếm các Role có tên liên quan đến API của bạn hoặc các dịch vụ đã sử dụng. Ví dụ:
    * Role cho AppSync Service Access: Bắt đầu bằng `AppSyncServiceRole-` hoặc chứa tên API của bạn (ví dụ: `RealtimeChatAppAPI_Final-service-role-...` hoặc `AppSyncFullDynamoDBAccessRole` nếu bạn tự tạo).
    * Role cho AppSync Logging: Bắt đầu bằng `AppSyncLoggingRole-` hoặc chứa ID API của bạn.
4.  Chọn (các) Role không còn cần thiết.
5.  Nhấn nút **Delete** (Xóa).
    ![ConnectPrivate](/images/de_9.png)
6.  Xác nhận và nhấn **Delete**.
    ![ConnectPrivate](/images/de_10.png)

**Sau khi hoàn thành tất cả các bước trên, bạn đã xóa sạch sẽ mọi tài nguyên AWS đã tạo trong bài thực hành này và sẽ không phát sinh thêm chi phí.**

---