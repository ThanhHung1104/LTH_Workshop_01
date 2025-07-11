---
title : "Định Nghĩa GraphQL Schema"
date : 2025-06-15
weight : 3 
chapter : false
pre : " <b> 4.3. </b> "
---

### **4.3. Định Nghĩa GraphQL Schema**

Schema GraphQL là trái tim của API AppSync, nó định nghĩa cấu trúc dữ liệu và các thao tác (Query, Mutation, Subscription) mà client có thể thực hiện. Sau khi tạo API, bước tiếp theo là định nghĩa schema cho ứng dụng chat phức tạp của chúng ta.

1. **Sau khi tạo API, bạn sẽ được đưa đến trang tổng quan của AppSync API.**
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.3_1.png)

2.  Ở thanh điều hướng bên trái, chọn **Schema**.
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.3_2.png)

3.  Trong cửa sổ soạn thảo Schema, **xóa bất kỳ nội dung mặc định nào (nếu có)** và **dán toàn bộ schema phức tạp dưới đây** vào:

    ```graphql
    type Message {
        id: ID!
        sender: String!
        content: String!
        timestamp: AWSDateTime!
    }

    type Mutation {
        # Tạo một tin nhắn mới
        createMessage(sender: String!, content: String!): Message
    }

    type Query {
        # Lấy danh sách tất cả tin nhắn
        listMessages: [Message]
    }

    type Subscription {
        # Kích hoạt khi có một tin nhắn mới được tạo bởi mutation 'createMessage'
        onCreateMessage: Message
            @aws_subscribe(mutations: ["createMessage"])
    }

    schema {
        query: Query
        mutation: Mutation
        subscription: Subscription
    }
    ```
4.  Nhấn nút **Save Schema** (Lưu Schema).
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.3_3.png)

**Chúc mừng! Bạn đã thành công định nghĩa và lưu Schema GraphQL phức tạp của ứng dụng chat.**
    ![ConnectPrivate](https://ThanhHung1104.github.io/LTH_Workshop_01/images/be_4.3_4.png)