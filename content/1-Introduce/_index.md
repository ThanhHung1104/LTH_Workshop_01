---
title : "Introduction"
date : 2025-06-15
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

## Workshop: Building a Real-time Chat Application on AWS

### **1. Introduction to Key Services**

To build powerful, scalable, and secure real-time web applications, we will leverage the capabilities of core services on the Amazon Web Services (AWS) cloud platform. The following are the key services we will use in this workshop:

#### **1.1. AWS AppSync**
![AWS AppSync Diagram](https://ThanhHung1104.github.io/LTH_Workshop_01/images/AWSAppSync.png)
It is a fully managed GraphQL service that allows you to build flexible APIs to query, mutate, and synchronize data. AppSync includes built-in real-time capabilities through GraphQL Subscriptions and WebSockets, as well as security and scalability management.

#### **1.2. Amazon DynamoDB**
![AWS DynamoDB](/images/DynamoDB.png) 
It is a high-performance, serverless, and fully managed NoSQL database. DynamoDB offers virtually unlimited scalability, low latency, and high availability, making it ideal for high-performance applications.

#### **1.3. Amazon Cognito**
![Amazon Cognito](/images/Cognito.png) 
It is a powerful and scalable User Identity Management service. Cognito helps you easily integrate secure user registration, login, and account management features into your web and mobile applications without having to build your own authentication system.

#### **1.4. AWS Amplify Hosting**
![AWS Amplify Hosting](/images/Amplify.png) 
It is a fully managed hosting and CI/CD (Continuous Integration/Continuous Delivery) service, specifically designed for static websites and Single-Page Applications (SPAs) like React. Amplify Hosting automates the build and deployment process and provides a global CDN.

### **2. Workshop Overview: Real-time Chat Application**

In this lab, you will learn how to build a complete real-time chat application, illustrating the close coordination among the AWS services introduced above. The ultimate goal is to achieve a fully functional, scalable, and secure chat application.

![tgt](/images/tgt.png) 

* **AWS AppSync** will be the **central API gateway** for the chat application. All requests from the frontend (sending messages, fetching chat history, receiving new messages) will go through AppSync. It will handle GraphQL Queries, Mutations, and especially **Subscriptions** to push new messages in real-time to all members of the conversation.
* **Amazon DynamoDB** will be the **storage location for all your chat data**, including user information (`User`), conversations (`Conversation`), membership records (`UserConversation`), and specific messages (`Message`).
* **Amazon Cognito** will be used for **user authentication** in the chat application, managing user accounts and providing a secure registration/login process.
* **AWS Amplify Hosting** will be the **deployment destination for your React frontend application**, automatically building your code from GitHub and deploying it to a global content delivery network (CDN).

### **3. How to Conduct the Workshop**

This workshop is structured with a clear roadmap for you to easily follow and execute:

* [2. Preparation Steps](./2-Prerequiste/)
* [3. Set up AWS Amplify Hosting](./3-AmplifyHosting/)
* [4. Backend Setup with AWS AppSync and DynamoDB](./4-backend/)
* [5. Add User Authentication and Connect Backend to Frontend](./5-Authentication/)
* [6. Resource Cleanup](./6-cleanup/)

---