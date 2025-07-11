---
title : "Cấu hình AWS AppSync API để sử dụng Cognito User Pools"
date : 2025-06-15
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

### **5.2. Cấu hình AWS AppSync API để sử dụng Cognito User Pools**

Bây giờ, chúng ta sẽ cấu hình API AWS AppSync của bạn để sử dụng Amazon Cognito User Pool vừa tạo làm phương thức xác thực chính.

1.  **Truy cập lại dịch vụ AWS AppSync:**
    * Trong **AWS Console**, tìm và chọn dịch vụ **AWS AppSync**.
    * Chọn API của bạn: `RealtimeChatAppAPI_Final`.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.2_1.png)

2.  **Bắt đầu thay đổi phương thức xác thực mặc định:**
    * Ở thanh điều hướng bên trái, chọn **Settings** (Cài đặt).
    * Tại phần **Primary authorization mode** (Chế độ ủy quyền chính), nhấn nút **Edit** (Chỉnh sửa).
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.2_2.png)

3.  **Cấu hình phương thức xác thực chính và Lưu:**
    * Trên giao diện chỉnh sửa hiện ra:
    * Trong trường **Primary authorization mode**, chọn **Amazon Cognito User Pools**.
    * **AWS Region (Vùng AWS):** Chọn vùng AWS của bạn (ví dụ: `US-EAST-1`).
    * **User pool (Nhóm người dùng):** Chọn User Pool bạn đã tạo ở bước trước (ví dụ: `RealTimeChat`).
    * Nhấn nút **Save** (Lưu).
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.2_3.png)

4.  **Xác nhận thay đổi phương thức xác thực (Confirm authorization mode change):**
    * Sau khi nhấn **Save** ở bước trên, một giao diện xác nhận **"Edit primary authorization mode"** sẽ xuất hiện.
    * Tích chọn ô **"Instead of deleting, make API key an additional authorization mode"** (Để chuyển API Key thành phương thức xác thực bổ sung).
    * Để xác nhận thay đổi này, gõ chính xác từ **`confirm`** vào ô văn bản.
    * Nhấn nút **Confirm**.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.2_4.png)

**Chúc mừng! Bạn đã thiết lập thành công AWS AppSync API để sử dụng Amazon Cognito User Pools để xác thực người dùng.**
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/au_5.2_5.png)