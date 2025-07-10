---
title : "Tạo API AWS AppSync"
date : 2025-06-15
weight : 2 # Đã chỉnh weight để khớp với 4.2. (ví dụ)
chapter : false
pre : " <b> 4.2. </b> "
---

### **4.2. Tạo API AWS AppSync**

Bây giờ, chúng ta sẽ tạo dịch vụ GraphQL API chính của ứng dụng chat thời gian thực. API này sẽ là điểm kết nối giữa frontend và backend của bạn.

1.  Trong ô tìm kiếm của **AWS Console**, gõ "AppSync" và chọn dịch vụ **AWS AppSync**.

2.  Nhấn nút **Create API** (Tạo API) và chọn **GraphQL API**.
    ![ConnectPrivate](/images/be_4.2_1.png)

#### **Bước 4.2.1: Chọn loại API**

* **API type (Loại API):** Giữ nguyên lựa chọn mặc định là **GraphQL APIs**. (Đây là loại API GraphQL quản lý một schema duy nhất, phù hợp với nhu cầu của chúng ta).
* **GraphQL API Data Source (Nguồn dữ liệu API GraphQL):** Chọn tùy chọn **Design from scratch** (Thiết kế từ đầu).
* Cuộn xuống cuối trang và nhấn nút **Next**.
    ![ConnectPrivate](/images/be_4.2_2.png)

#### **Bước 4.2.2: Chỉ định chi tiết API**

* **API name (Tên API):** Nhập tên cho API của bạn, ví dụ: `RealTimeChatAppAPI_Final`.
* **Private API configuration (Cấu hình API riêng tư):** Đảm bảo **KHÔNG chọn** **Use private API features** (Sử dụng tính năng API riêng tư).
* Nhấn nút **Next**.
    ![ConnectPrivate](/images/be_4.2_3.png)

#### **Bước 4.2.3: Chỉ định tài nguyên GraphQL**

* **Create a GraphQL type backed by a DynamoDB table (Tạo một loại GraphQL được hỗ trợ bởi bảng DynamoDB):** Chọn **Create GraphQL resources later** (Tạo tài nguyên GraphQL sau).
* Nhấn nút **Next**.
    ![ConnectPrivate](/images/be_4.2_4.png)

#### **Bước 4.2.4: Xem lại và tạo API**

1.  Xem lại thông tin cấu hình của API trong phần **Review** (Xem lại).
2.  Nhấn nút **Create API** (Tạo API).
    ![ConnectPrivate](/images/be_4.2_5.png)

**Chúc mừng! Bạn đã thành công tạo API AWS AppSync của mình.**
    ![ConnectPrivate](/images/be_4.2_6.png)