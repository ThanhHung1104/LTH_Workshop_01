---
title : "Tạo Resolvers (Bộ Phân Giải)"
date : 2025-06-15
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

### **4.5. Tạo Resolvers (Bộ Phân Giải)**

Resolvers (Bộ phân giải) là các hàm mã nguồn (trong trường hợp này là JavaScript) giúp ánh xạ các thao tác GraphQL (Query, Mutation, Subscription) đến các nguồn dữ liệu backend (như DynamoDB). Chúng cho phép API AppSync biết cách thực hiện các thao tác trên dữ liệu của bạn.

1.  Ở thanh điều hướng bên trái của **AppSync Console**, chọn **Schema**.
2.  Cuộn xuống phần **Resolvers** (Bộ phân giải). Bạn sẽ thấy danh sách các hoạt động Query, Mutation và Subscription được tự động tạo từ Schema của mình.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_1.png)

#### **Bước 4.5.1: Tạo Resolver cho `Query.listMessages`**

Resolver này sẽ cho phép bạn lấy danh sách tất cả các tin nhắn từ bảng DynamoDB.

1.  Tìm dòng **`listMessages`** dưới mục **Query**.
2.  Nhấn nút **Attach** (Gắn) bên cạnh nó.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_2.png)
3.  **Cấu hình Resolver:**
    * **Data source name (Tên nguồn dữ liệu):** Chọn **`RealTimeChatDataSource`**.
    * **Resolver runtime (Môi trường Runtime Resolver):** Đảm bảo chọn **AppSync JavaScript (APPSYNC_JS)**.
    * Cuộn xuống cuối trang và nhấn nút **Create** (Tạo).
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_3.png)
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_4.png)
4.  Bạn sẽ được chuyển đến trang chỉnh sửa mã Resolver.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_5.png)
5.  **Dán mã JavaScript sau** vào trình soạn thảo code của Resolver, thay thế nội dung hiện có:
    ```javascript
    /**
     * Sends a request to the attached data source
     * @param {import('@aws-appsync/utils').Context} ctx the context
     * @returns {*} the request
     */
    export function request(ctx) {
      return {
        operation: 'Scan' // Thao tác quét toàn bộ bảng DynamoDB
      };
    }

    /**
     * Returns the resolver result
     * @param {import('@aws-appsync/utils').Context} ctx the context
     * @returns {*} the result
     */
    export function response(ctx) {
      if (ctx.error) {
        util.error(ctx.error.message, ctx.error.type);
      }
      return ctx.result.items; // Trả về danh sách các item từ kết quả Scan
    }
    ```
6.  Nhấn nút **Save** (Lưu) ở góc trên bên phải để lưu Resolver.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_6.png)

#### **Bước 4.5.2: Tạo Resolver cho `Mutation.createMessage`**

Resolver này sẽ cho phép bạn tạo một tin nhắn mới và lưu nó vào bảng DynamoDB.

1.  Tìm dòng **`createMessage`** dưới mục **Mutation**.
2.  Nhấn nút **Attach** (Gắn) bên cạnh nó.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_7.png)
3.  **Cấu hình Resolver:**
    * **Data source name (Tên nguồn dữ liệu):** Chọn **`RealTimeChatDataSource`**.
    * **Resolver runtime (Môi trường Runtime Resolver):** Đảm bảo chọn **AppSync JavaScript (APPSYNC_JS)**.
    * Nhấn nút **Create** (Tạo).
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_8.png)
4.  Bạn sẽ được chuyển đến trang chỉnh sửa mã Resolver.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.5_9.png)
5.  **Dán mã JavaScript sau** vào trình soạn thảo code của Resolver, thay thế nội dung hiện có:
    ```javascript
    /**
     * Sends a request to the attached data source
     * @param {import('@aws-appsync/utils').Context} ctx the context
     * @returns {*} the request
     */
    export function request(ctx) {
      const { sender, content } = ctx.args.input; // Lấy các đối số từ mutation (đã sửa thành ctx.args.input)
      return {
        operation: 'PutItem', // Thao tác thêm item vào DynamoDB
        key: util.dynamodb.toMapValues({ id: util.autoId() }), // Tự động tạo ID duy nhất
        attributeValues: util.dynamodb.toMapValues({ sender, content, timestamp: util.time.nowISO8601() }) // Lưu các thuộc tính
      };
    }

    /**
     * Returns the resolver result
     * @param {import('@aws-appsync/utils').Context} ctx the context
     * @returns {*} the result
     */
    export function response(ctx) {
      if (ctx.error) {
        util.error(ctx.error.message, ctx.error.type);
      }
      return ctx.result; // Trả về kết quả của thao tác PutItem
    }
    ```
6.  Nhấn nút **Save** (Lưu) ở góc trên bên phải để lưu Resolver.

#### **Bước 4.5.3: Cấu hình Subscription `onCreateMessage`**

* Tìm dòng **`onCreateMessage`** dưới mục **Subscription**.
* Bạn **không cần tạo Resolver cho Subscription này**. AppSync sẽ tự động xử lý logic WebSockets khi bạn sử dụng directive `@aws_subscribe` trong schema và nó được liên kết với một Mutation (trong trường hợp này là `createMessage`).

**Bạn đã thành công tạo và cấu hình các Resolvers cơ bản cho ứng dụng chat của mình.**