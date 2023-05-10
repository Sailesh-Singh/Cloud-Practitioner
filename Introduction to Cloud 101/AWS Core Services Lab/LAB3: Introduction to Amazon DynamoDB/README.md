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

####    Task 2: Adding Data

Each table contains multiple items. An item is a group of attributes that is uniquely identifiable among all of the other items. Items in DynamoDB are similar in many ways to rows in other database systems. In DynamoDB, there is no limit to the number of items that you can store in a table.
Each item consists of one or more attributes. An attribute is a fundamental data element, something that does not need to be broken down any further. For example, an item in a Music table contains attributes such as song and artist. Attributes in DynamoDB are similar to columns in other database systems, but each item (row) can have different attributes (columns).

When you write an item to a DynamoDB table, only the primary key and sort key (if used) are required.  Other than these fields, the table does not require a schema, which means that you can add attributes to one item that may be different than the attributes on other items.
+   Select Explore items on the left side navigation pane.

+   Click the radio button next to Music to select the table you created.

+   Click Create item.

+   Add in the following values.

    +   Artist: Pink Floyd
    +   Song: Money

These are the only required attributes, but you can now add additional attributes.
+   To create an additional attribute, click the Add new attribute button.

+   In the dropdown list, choose String.

+   A new attribute row is added.

+   For the new attribute, replace NewValue withAlbum and in the Value column enter The Dark Side of the Moon.

+   Add another new attribute by choosing the Add new attribute button.
+   In the dropdown list, choose Number.

+   For the new attribute, replace NewValue with Year and in the Value column replace 0 with 1973.
+   Choose Create item to store the new item with its four attributes.


+   The item appears in the Items returned pane in the console.
+   Next, follow the previous steps and use the following attributes to create a second item:
    <table>
    <tr>
    <th>Attribute name</td>
    <th>Attribute type</td>
    <th>Attribute value</td>
    </tr>

    <tr>
    <td>Artist</td>
    <td>String</td>
    <td>John Lennon</td>
    </tr>

    <tr>
    <td>Song</td>
    <td>String</td>
    <td>Imagine</td>
    </tr>

    <tr>
    <td>Album</td>
    <td>String</td>
    <td>Imagine</td>
    </tr>

    <tr>
    <td>Year</td>
    <td>Number</td>
    <td>1971</td>
    </tr>

    <tr>
    <td>Genre</td>
    <td>String</td>
    <td>Soft rock</td>
    </tr>

    </table>


    Note that this item has an additional attribute called Genre. Adding this attribute is an example of each item being capable of having different attributes without having to pre-define a table schema.

+   Follow the previous steps and use the following attributes to create a third item:
    <table>
    <tr>
    <th>Artist name</td>
    <th>Attribute type</td>
    <th>Attribute value</td>
    </tr>

    <tr>
    <td>Artist</td>
    <td>String</td>
    <td>Lennon</td>
    </tr>

    <tr>
    <td>Song</td>
    <td>String</td>
    <td>Gnagam style</td>
    </tr>

    <tr>
    <td>Album</td>
    <td>String</td>
    <td>Psy 6 (Six Rules), Part 1</td>
    </tr>

    <tr>
    <td>Year</td>
    <td>Number</td>
    <td>2011</td>
    </tr>

    <tr>
    <td>Length</td>
    <td>Seconds</td>
    <td>Number 219</td>
    </tr>

    </table>

    Once again, this item has a new LengthSeconds attribute that identifies the length of the song. The ability to include this attribute demonstrates the flexibility of a NoSQL database.
    There are also faster ways to load data into DynamoDB, such as using AWS Data Pipeline, programmatically loading data, or using one of the free tools available on the internet.