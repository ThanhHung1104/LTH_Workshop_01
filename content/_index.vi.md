---
title : "Xây dựng ứng dụng chat thời gian thực đơn giản trên AWS với AppSync và Amplify"
date : 2025-06-15
weight : 1 
chapter : false
---
## Workshop: Xây dựng ứng dụng chat thời gian thực đơn giản trên AWS với AppSync và Amplify

### **Tổng quan**

Trong bài lab thực hành này, bạn sẽ học cách xây dựng một ứng dụng chat thời gian thực đơn giản. Bạn sẽ khám phá cách tích hợp các dịch vụ chính của AWS như **AWS AppSync** (cho GraphQL và thời gian thực), **Amazon DynamoDB** (cơ sở dữ liệu), **Amazon Cognito** (quản lý người dùng), và triển khai frontend React sử dụng **AWS Amplify Hosting**. Mục tiêu là giúp bạn nắm vững các kiến thức cốt lõi để phát triển ứng dụng fullstack trên nền tảng Serverless của AWS.

### **Chi phí ước tính**

* **Chi phí:** Khoảng **0 USD**
    * *Lý do:* Việc sử dụng các dịch vụ trong bài lab này được thiết kế để nằm trong **Tầng Miễn phí (Free Tier)** của AWS. Do đó, bạn sẽ không phát sinh chi phí đáng kể nào trong suốt quá trình thực hành, nếu bạn tuân thủ các giới hạn của Free Tier và nhớ dọn dẹp tài nguyên sau khi hoàn tất.

### **Thời gian thực hiện dự kiến**

* **Thời gian:** Khoảng **2 - 3 giờ**
    * *(Phụ thuộc vào độ quen thuộc với AWS Console, React và Git. Thời gian này bao gồm cả quá trình thiết lập, thực hành và gỡ lỗi tiềm năng).*

### **Nội dung**

1.  [Giới thiệu](1-introduce/)
2.  [Các bước chuẩn bị](2-Prerequiste/)
3.  [Thiết lập AWS Amplify Hosting](3-AmplifyHosting/)
4.  [Thiết Lập Backend với AWS AppSync và DynamoDB](4-backend/)
5.  [Thêm Xác thực người dùng và kết nối backend với frontend](5-Authentication/)
6.  [Dọn dẹp tài nguyên](6-cleanup/)