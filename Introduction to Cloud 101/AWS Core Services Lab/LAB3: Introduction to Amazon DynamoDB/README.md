#   Lab 3: Introduction to Amazon DynamoDB

### Lab overview and objectives

Amazon DynamoDB is a fast and flexible NoSQL database service for all applications that need consistent, single-digit millisecond latency at any scale. It is a fully managed database that supports both document and key-value data models. Its flexible data model and reliable performance make it a great fit for mobile, web, gaming, advertising technology, Internet of Things (IoT), and many other applications. _Click to [Learn more...](https://awseducate.instructure.com/courses/768/assignments/3147?module_item_id=13565)_

After completing this lab, you will know how to:

+   Create a DynamoDB table
+   Enter data into a DynamoDB table
+   Query a DynamoDB table
+   Delete a DynamoDB table

####   Duration
This lab requires approximately 30 minutes to complete.

####    Task 1: Creating a New Table

+   In the AWS Management Console, choose Services, and then choose DynamoDB.

+   Choose Create table
+   For Table name, enter `Music`
+   For Partition key, enter `Artist` and leave String selected.
+   For Sort key - optional, enter `Song` and leave String selected.
+   Under Settings select Customize settings then configure the following:

    #####   Read capacity
    +   <b>Provisioned capacity units:</b> `10`

    #####   Write capacity
    +   <b>Provisioned capacity units:</b> `2`

    Amazon DynamoDB has two read/write capacity modes for processing reads and writes on your tables:

    +   On-demand
    +   Provisioned (default, free-tier eligible)

    The read/write capacity mode controls how you are charged for read and write throughput and how you manage capacity. You can set the read/write capacity mode when creating a table or you can change it later.

    Your table will use default settings for indexes.

+   Choose Create table.
            
    The table is created in less than 1 minute.