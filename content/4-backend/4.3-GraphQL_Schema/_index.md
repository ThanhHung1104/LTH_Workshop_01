---
title : "Define GraphQL Schema"
date : 2025-06-15
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---

### **4.3. Define GraphQL Schema**

The GraphQL Schema is the heart of your AppSync API; it defines the data structure and the operations (Query, Mutation, Subscription) that clients can perform. After creating the API, the next step is to define the schema for our complex chat application.

1.  After creating the API, you will be directed to the AppSync API overview page.
    ![ConnectPrivate](/images/be_4.3_1.png)

2.  In the left navigation pane, select **Schema**.
    ![ConnectPrivate](/images/be_4.3_2.png)

3.  In the Schema editor window, **delete any default content (if present)** and **paste the entire complex schema below**:

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
4.  Click the **Save Schema** button.
    ![ConnectPrivate](/images/be_4.3_3.png)

**Congratulations! You have successfully defined and saved the complex GraphQL Schema for your chat application.**
    ![ConnectPrivate](/images/be_4.3_4.png)