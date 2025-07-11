---
title : "Cấu Hình Nguồn Dữ liệu (Data Source)"
date : 2025-06-15
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

### **4.4. Cấu Hình Nguồn Dữ liệu (Data Source)**

Chúng ta sẽ kết nối API GraphQL với bảng DynamoDB đã tạo, bằng cách cấu hình một Nguồn dữ liệu (Data Source) trong AppSync.

1.  Ở thanh điều hướng bên trái của **AppSync Console**, chọn **Data Sources** (Nguồn dữ liệu). Sau đó, nhấn nút **Create data source** (Tạo nguồn dữ liệu).
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_1.png)

2.  **Điền thông tin nguồn dữ liệu:**
    * **Data source name (Tên nguồn dữ liệu):** Nhập `RealTimeChatDataSource` (hoặc tên bất kỳ bạn thích).
    * **Data source type (Loại nguồn dữ liệu):** Chọn **Amazon DynamoDB table**.
    * **Region (Vùng):** Chọn vùng AWS tương ứng (phải giống với vùng bạn đã tạo bảng DynamoDB), ở đây là `us-east-1`.
    * **Table name (Tên bảng):** Chọn bảng `RealTimeChat` mà bạn đã tạo trước đó.
    * **Create or use an existing role (Tạo hoặc sử dụng vai trò hiện có):** Chọn **New role** (Vai trò mới).
    * Nhấn nút **Create** (Tạo).
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_2.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_3.png)

**Chúc mừng! Bạn đã thành công tạo nguồn dữ liệu cho API AppSync.**
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.4_4.png)