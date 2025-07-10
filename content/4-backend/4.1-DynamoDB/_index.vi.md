---
title : "Tạo Bảng DynamoDB"
date : 2025-06-15
weight : 1 # Đã chỉnh weight để khớp với 4.1. (ví dụ)
chapter : false
pre : " <b> 4.1. </b> "
---

### **4.1. Tạo Bảng DynamoDB**

Chúng ta sẽ sử dụng Amazon DynamoDB, một cơ sở dữ liệu NoSQL hiệu suất cao, để lưu trữ các tin nhắn trong ứng dụng chat của mình.

1.  Trong ô tìm kiếm của **AWS Console**, gõ "DynamoDB" và chọn dịch vụ **DynamoDB**.
    ![ConnectPrivate](/images/be_4.1_1.png)

2.  Ở thanh điều hướng bên trái, chọn **Tables** (Bảng).

3.  Nhấn nút **Create table** (Tạo bảng).
    ![ConnectPrivate](/images/be_4.1_2.png)

4.  **Điền thông tin bảng:**
    * **Table name (Tên bảng):** Nhập tên cho bảng của bạn, ví dụ: `RealTimeChat` (hoặc tên bất kỳ bạn thích).
    * **Partition key (Khóa phân vùng):** Gõ `id`, chọn kiểu **String**. Đây sẽ là khóa chính duy nhất cho mỗi bản ghi (item) trong bảng của bạn.
    * Để mặc định các cài đặt khác.
    ![ConnectPrivate](/images/be_4.1_3.png)

5.  Cuộn xuống cuối trang và nhấn nút **Create table** (Tạo bảng).
    ![ConnectPrivate](/images/be_4.1_4.png)

6.  Chờ cho trạng thái của bảng chuyển sang **Active** (Hoạt động). Khi bảng ở trạng thái Active, nó đã sẵn sàng để sử dụng.
    ![ConnectPrivate](/images/be_4.1_5.png)

**Chúc mừng! Bạn đã thành công tạo cơ sở dữ liệu DynamoDB cho ứng dụng chat của mình.**