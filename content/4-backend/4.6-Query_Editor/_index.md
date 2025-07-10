---
title : "Test API with Query Editor (Important)"
date : 2025-06-15
weight : 6
chapter : false
pre : " <b> 4.6. </b> "
---

### **4.6. Test API with Query Editor (Important)**

This is a crucial step to confirm that your chat application's backend is working correctly before proceeding with the frontend. You will use the built-in Query Editor in the AppSync Console to test your GraphQL operations.

1.  In the left navigation pane of **AppSync Console**, select **Queries**.
    ![ConnectPrivate](/images/be_4.6_1.png)

2.  You will see an integrated GraphQL editor. This is where you will input and run your Queries, Mutations, and Subscriptions.

#### **Step 4.6.1: Test Mutation (`createMessage`)**

You will send a new message to test the data writing functionality.

1.  Delete any existing content in the editor.
2.  **Paste the following Mutation code** into the editor and click the **"Run"** button (Play icon) to execute it:

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
3.  You will see the result returned in the right window, including the message `id`, sender name, content, and timestamp. This confirms the Mutation was successful.
    ![ConnectPrivate](/images/be_4.6_2.png)

#### **Step 4.6.2: Test Subscription (`onCreateMessage`)**

You will subscribe to listen for new messages in real-time.

1.  **Open a new browser tab** and revisit your **AppSync Console** (or keep the current tab and open another). Navigate to the **Queries** section for your API.
2.  In this new tab, **paste the following Subscription code** into the editor and click the **"Run"** button:

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
3.  When you run this Subscription, it will display **"Listening..."** indicating that it is waiting for new messages.
    ![ConnectPrivate](/images/be_4.6_3.png)
4.  **Go back to the original browser tab** (or open a third tab).
5.  **Run the `createMessage` Mutation again** with different content (e.g., `content: "This is a real-time message!"`).
    ![ConnectPrivate](/images/be_4.6_4.png)
6.  **Observe the tab with the Subscription.** You will see the new message appear instantly without needing to refresh the page! This confirms that the WebSocket connection and real-time functionality are working.
    ![ConnectPrivate](/images/be_4.6_5.png)

#### **Step 4.6.3: Test Query (`listMessages`)**

You will retrieve all sent messages.

1.  In another tab (or after completing the steps above), **paste the following Query code** into the editor and click the **"Run"** button:

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
2.  You will see a list of all messages you have created in the result window.
    ![ConnectPrivate](/images/be_4.6_6.png)

**Congratulations! Your chat application's backend is working as expected. You are now ready to proceed to the Frontend section.**