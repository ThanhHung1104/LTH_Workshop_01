---
title : "Kiểm Tra API với Query Editor (Quan trọng)"
date : 2025-06-15
weight : 6
chapter : false
pre : " <b> 4.6. </b> "
---

### **4.6. Kiểm Tra API với Query Editor (Quan trọng)**

Đây là bước cực kỳ quan trọng để bạn xác nhận rằng backend của ứng dụng chat đã hoạt động đúng cách trước khi chuyển sang phần frontend. Bạn sẽ sử dụng Query Editor tích hợp sẵn trong AppSync Console để kiểm thử các hoạt động GraphQL.

1.  Ở thanh điều hướng bên trái của **AppSync Console**, chọn **Queries** (Truy vấn).
    ![ConnectPrivate](/images/be_4.6_1.png)

2.  Bạn sẽ thấy một trình soạn thảo GraphQL tích hợp. Đây là nơi bạn sẽ nhập và chạy các Query, Mutation và Subscription.

#### **Bước 4.6.1: Thử nghiệm Mutation (`createMessage`)**

Bạn sẽ gửi một tin nhắn mới để kiểm tra chức năng ghi dữ liệu.

1.  Xóa nội dung hiện có trong trình soạn thảo.
2.  **Dán đoạn mã Mutation sau** vào trình soạn thảo và nhấn nút **"Run"** (biểu tượng Play) để thực thi:

    ```graphql
    mutation CreateNewMessage {
      createMessage(sender: "Alice", content: "Hello from AppSync!") {
        id
        sender
        content
        timestamp
      }
    }
    ```
3.  Bạn sẽ thấy kết quả trả về trong cửa sổ bên phải, bao gồm `id` của tin nhắn, tên người gửi, nội dung và thời gian gửi. Điều này xác nhận Mutation đã thành công.
    ![ConnectPrivate](/images/be_4.6_2.png)

#### **Bước 4.6.2: Thử nghiệm Subscription (`onCreateMessage`)**

Bạn sẽ đăng ký lắng nghe tin nhắn mới theo thời gian thực.

1.  **Mở một tab trình duyệt mới** và truy cập lại **AppSync Console** của bạn (hoặc giữ tab hiện tại và mở một tab khác). Điều hướng đến phần **Queries** cho API của bạn.
2.  Trong tab mới này, **dán đoạn mã Subscription sau** vào trình soạn thảo và nhấn nút **"Run"**:

    ```graphql
    subscription OnNewMessage {
      onCreateMessage {
        id
        sender
        content
        timestamp
      }
    }
    ```
3.  Khi bạn chạy Subscription này, nó sẽ hiển thị **"Listening..."** cho thấy nó đang chờ tin nhắn mới.
    ![ConnectPrivate](/images/be_4.6_3.png)
4.  **Quay lại tab trình duyệt ban đầu** (hoặc mở một tab thứ ba khác).
5.  **Chạy lại Mutation `createMessage`** với nội dung khác (ví dụ: `content: "This is a real-time message!"`).
    ![ConnectPrivate](/images/be_4.6_4.png)
6.  **Quan sát tab có Subscription.** Bạn sẽ thấy tin nhắn mới xuất hiện ngay lập tức mà không cần làm mới trang! Điều này xác nhận kết nối WebSocket và chức năng thời gian thực đang hoạt động.
    ![ConnectPrivate](/images/be_4.6_5.png)

#### **Bước 4.6.3: Thử nghiệm Query (`listMessages`)**

Bạn sẽ lấy tất cả các tin nhắn đã gửi.

1.  Trong một tab khác (hoặc sau khi hoàn thành các bước trên), **dán đoạn mã Query sau** vào trình soạn thảo và nhấn nút **"Run"**:

    ```graphql
    query GetAllMessages {
      listMessages {
        id
        sender
        content
        timestamp
      }
    }
    ```
2.  Bạn sẽ thấy danh sách tất cả các tin nhắn bạn đã tạo trong cửa sổ kết quả.
    ![ConnectPrivate](/images/be_4.6_6.png)

**Chúc mừng! Backend của ứng dụng chat đã hoạt động đúng như mong đợi. Bạn đã sẵn sàng để chuyển sang phần Frontend.**