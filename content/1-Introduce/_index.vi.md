---
title : "Giới thiệu"
date : 2025-06-15
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

## Workshop: Xây Dựng Ứng Dụng Chat Thời Gian Thực trên AWS

### **1. Giới thiệu các dịch vụ chính**

Để xây dựng các ứng dụng web thời gian thực mạnh mẽ, có khả năng mở rộng và bảo mật, chúng ta sẽ tận dụng sức mạnh của các dịch vụ cốt lõi trên nền tảng điện toán đám mây của Amazon Web Services (AWS). Sau đây là các dịch vụ chính mà chúng ta sẽ sử dụng trong workshop này:

#### **1.1. AWS AppSync**
![AWS AppSync Diagram](https://ThanhHung1104.github.io/LTH_Workshop_01/images/AWSAppSync.png)
Là một dịch vụ GraphQL được quản lý hoàn toàn (fully managed), cho phép bạn xây dựng các API linh hoạt để truy vấn, thay đổi và đồng bộ hóa dữ liệu. AppSync tích hợp sẵn khả năng thời gian thực (real-time) thông qua GraphQL Subscriptions và WebSockets, cũng như quản lý bảo mật và mở rộng.

#### **1.2. Amazon DynamoDB**
![AWS DynamoDB](https://ThanhHung1104.github.io/LTH_Workshop_01/images/DynamoDB.png) 
Là một cơ sở dữ liệu NoSQL hiệu suất cao, phi máy chủ (serverless) và được quản lý hoàn toàn. DynamoDB cung cấp khả năng mở rộng gần như không giới hạn, độ trễ thấp và tính sẵn sàng cao, lý tưởng cho các ứng dụng yêu cầu hiệu suất cao.

#### **1.3. Amazon Cognito**
![Amazon Cognito](https://ThanhHung1104.github.io/LTH_Workshop_01/images/Cognito.png) 
Là một dịch vụ quản lý danh tính người dùng (User Identity Management) mạnh mẽ và có khả năng mở rộng. Cognito giúp bạn dễ dàng tích hợp các tính năng đăng ký, đăng nhập và quản lý tài khoản người dùng một cách bảo mật vào ứng dụng web và di động mà không cần tự xây dựng hệ thống xác thực.

#### **1.4. AWS Amplify Hosting**
![AWS Amplify Hosting](https://ThanhHung1104.github.io/LTH_Workshop_01/images/Amplify.png) 
Là một dịch vụ hosting và CI/CD (Continuous Integration/Continuous Delivery) được quản lý hoàn toàn, được thiết kế đặc biệt cho các ứng dụng web tĩnh (static websites) và Single-Page Applications (SPAs) như React. Amplify Hosting tự động hóa quá trình build và triển khai, đồng thời cung cấp CDN toàn cầu.

### **2. Giới thiệu bài Workshop: Ứng dụng Chat Thời gian thực**

Trong bài lab này, bạn sẽ học cách xây dựng một ứng dụng chat thời gian thực hoàn chỉnh, minh họa sự phối hợp chặt chẽ giữa các dịch vụ AWS đã giới thiệu ở trên. Mục tiêu cuối cùng là có được một ứng dụng chat hoạt động đầy đủ tính năng, có khả năng mở rộng và bảo mật.

![tgt](https://ThanhHung1104.github.io/LTH_Workshop_01/images/tgt.png) 

* **AWS AppSync** sẽ là **cổng API trung tâm** cho ứng dụng chat. Mọi yêu cầu từ frontend (gửi tin nhắn, lấy lịch sử chat, nhận tin nhắn mới) đều đi qua AppSync. Nó sẽ xử lý các GraphQL Query, Mutation và đặc biệt là các **Subscription** để đẩy tin nhắn mới theo thời gian thực đến tất cả các thành viên trong cuộc trò chuyện.
* **Amazon DynamoDB** sẽ là **nơi lưu trữ tất cả dữ liệu chat** của bạn, bao gồm thông tin người dùng (`User`), cuộc trò chuyện (`Conversation`), bản ghi thành viên (`UserConversation`) và các tin nhắn cụ thể (`Message`).
* **Amazon Cognito** sẽ được sử dụng để **xác thực người dùng** cho ứng dụng chat, quản lý các tài khoản người dùng và cung cấp quy trình đăng ký/đăng nhập bảo mật.
* **AWS Amplify Hosting** sẽ là **nơi triển khai ứng dụng React frontend** của bạn, tự động build code từ GitHub và triển khai lên một mạng lưới phân phối nội dung (CDN) toàn cầu.

### **3. Cách thực hiện bài Workshop**

Workshop này được cấu trúc theo một lộ trình rõ ràng để bạn dễ dàng theo dõi và thực hiện:

* [2. Các bước chuẩn bị](./2-Prerequiste/)
* [3. Thiết lập AWS Amplify Hosting](./3-AmplifyHosting/)
* [4. Thiết Lập Backend với AWS AppSync và DynamoDB](./4-backend/)
* [5. Thêm Xác thực người dùng và kết nối backend với frontend](./5-Authentication/)
* [6. Dọn dẹp tài nguyên](./6-cleanup/)

---