---
title : "Create Resolvers"
date : 2025-06-15
weight : 5
chapter : false
pre : " <b> 4.5. </b> "
---

### **4.5. Create Resolvers**

Resolvers are source code functions (in this case, JavaScript) that map GraphQL operations (Query, Mutation, Subscription) to operations on backend data sources (like DynamoDB). They allow your AppSync API to know how to perform operations on your data.

1.  In the left navigation pane of **AppSync Console**, select **Schema**.
    ![ConnectPrivate](/images/be_4.5_1.png)

2.  Scroll down to the **Resolvers** section. You will see a list of Query, Mutation, and Subscription operations automatically generated from your Schema.

#### **Step 4.5.1: Create Resolver for `Query.listMessages`**

This resolver will allow you to retrieve a list of all messages from the DynamoDB table.

1.  Find the line **`listMessages`** under the **Query** section.
2.  Click the **Attach** button next to it.
    ![ConnectPrivate](/images/be_4.5_2.png)
3.  **Configure Resolver:**
    * **Data source name:** Select **`RealTimeChatDataSource`**.
    * **Resolver runtime:** Make sure **AppSync JavaScript (APPSYNC_JS)** is selected.
    * Scroll down to the bottom of the page and click the **Create** button.
    ![ConnectPrivate](/images/be_4.5_3.png)
    ![ConnectPrivate](/images/be_4.5_4.png)
4.  You will be redirected to the Resolver code editor page.
    ![ConnectPrivate](/images/be_4.5_5.png)
5.  **Paste the following JavaScript code** into the Resolver code editor, replacing the existing content:
    ```javascript
    /**
     * Sends a request to the attached data source
     * @param {import('@aws-appsync/utils').Context} ctx the context
     * @returns {*} the request
     */
    export function request(ctx) {
      return {
        operation: 'Scan' // Operation to scan the entire DynamoDB table
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
      return ctx.result.items; // Returns the list of items from the Scan result
    }
    ```
6.  Click the **Save** button in the top right corner to save the Resolver.
    ![ConnectPrivate](/images/be_4.5_6.png)

#### **Step 4.5.2: Create Resolver for `Mutation.createMessage`**

This resolver will allow you to create a new message and save it to the DynamoDB table.

1.  Find the line **`createMessage`** under the **Mutation** section.
2.  Click the **Attach** button next to it.
    ![ConnectPrivate](/images/be_4.5_7.png)
3.  **Configure Resolver:**
    * **Data source name:** Select **`RealTimeChatDataSource`**.
    * **Resolver runtime:** Make sure **AppSync JavaScript (APPSYNC_JS)** is selected.
    * Click the **Create** button.
    ![ConnectPrivate](/images/be_4.5_8.png)
4.  You will be redirected to the Resolver code editor page.
    ![ConnectPrivate](/images/be_4.5_9.png)
5.  **Paste the following JavaScript code** into the Resolver code editor, replacing the existing content:
    ```javascript
    /**
     * Sends a request to the attached data source
     * @param {import('@aws-appsync/utils').Context} ctx the context
     * @returns {*} the request
     */
    export function request(ctx) {
      const { sender, content } = ctx.args.input; // Get arguments from the mutation (corrected to ctx.args.input)
      return {
        operation: 'PutItem', // Operation to add an item to the DynamoDB table
        key: util.dynamodb.toMapValues({ id: util.autoId() }), // Auto-generate a unique ID
        attributeValues: util.dynamodb.toMapValues({ sender, content, timestamp: util.time.nowISO8601() }) // Save attributes
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
      return ctx.result; // Return the result of the PutItem operation
    }
    ```
6.  Click the **Save** button in the top right corner to save the Resolver.

#### **Step 4.5.3: Configure Subscription `onCreateMessage`**

* Find the line **`onCreateMessage`** under the **Subscription** section.
* You **do not need to create a Resolver for this Subscription**. AppSync automatically handles the WebSocket logic when you use the `@aws_subscribe` directive in your schema and it is linked to a Mutation (in this case, `createMessage`).

**You have successfully created and configured the basic Resolvers for your chat application.**