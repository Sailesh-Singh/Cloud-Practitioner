#   [Getting Started with Databases](https://awseducate.instructure.com/courses/912)

## Overview

The business world is constantly changing and evolving. By accurately recording, updating, and tracking data efficiently and on a regular basis, companies can use the immense potential from the insights that they obtain from their data. Database management systems are the crucial link for managing this data. Like other cloud services, cloud databases offer significant cost advantages over traditional database strategies.

In this module, you learn about database fundamentals and Amazon Relational Database Service (Amazon RDS). Amazon RDS is a managed web service that helps customers create and manage highly scalable and secure relational databases in the AWS Cloud. Customers aren’t responsible for hardware provisioning, database setup, software patching, and backups. AWS manages common database administrative tasks.

Amazon RDS supports most relational database engines, including commercial (such as Oracle and Microsoft SQL Server [MSSQL]), open source (MySQL, PostgreSQL, and MariaDB), and Amazon Aurora. With Amazon RDS, you store and transmit data securely.

In this course, you acquire the knowledge that you need to start using Amazon RDS. You learn about the key elements of Amazon RDS and explore how to configure them. You also learn the basic elements of high availability, backups, and security to set up a database that suits the needs of your workload. 

##  Course Level 

This is a foundational level course that is written for learners beginning with cloud computing and AWS services. When you start this course, you don’t need to have a deep understanding of cloud computing. If you already have a deeper understanding of cloud computing, you might still find this course helpful in refreshing your knowledge and practicing your skills. 

It’s helpful if you already have a basic understanding of cloud computing concepts and the AWS Management Console. AWS Educate supports this background knowledge with the following courses:

+   Introduction to the AWS Management Console
+   Introduction to Cloud 101


##  Objectives
By the end of this course I will be able to do the following:

+   Describe key database concepts.
+   Compare and contrast relational and nonrelational databases.
+   Identify the AWS database services.
+   Discuss the features and concepts of Amazon RDS.
+   Describe the benefits and use cases of Amazon RDS.
+   Describe how to set up an RDS instance using the console.
+   Identify how to connect to the database instance.
+   Discuss how to use SQL commands to read and write to the database.


Click <a href="https://awseducate.instructure.com/courses/912">Getting Started with Databases</a>

---

####    Why databases?
A computer need to store the information, before that the information can be reference or changed . A computer also need to find the right information at the right time A database is logically organized collection of information designed in such a way the information with them can be accessed for later used by a computer program.
<img src="assets/database.PNG" alt="database" style="height:100%; width:100%">    

####    Data models and structure   
Data model is the logical structure of the database and determine the rules for how information can be organized an used. The data model you choose is influenced by the structure of your data. Data structure in three different ways:
1.      Structured data:
    It is stored as a series of data values in related tables. This data is highly structured. This means it is formatted so that it owner can be made accessible for most effective processing and analysis. The data is also able to be used for highly complex queries.

2.      Unstructured database  
    +   Stored as files
    +   Lacks predefined structured
    +   Special tools to catalog and query

3.      Semi structured data
    +   Highly flexible
    +   Changed as needed
    +   Analyzed    

<img src="assets/data model and structure.PNG" alt="data model" style="height:100%; width:100%">   

####    Database terms and concepts
1.      Schema
    A database schema is the blueprint of the database. The schema outlines the relationships within the database and the constraints of the database.
    There are two main types of schemas: schema-less and semi-structured or fixed schema.
    +   A schema-less database maanges information without the need for a blueprint.
    +   Semi-structured data doesnot follow the format of a tabular data model or relational databases because it does not have fixed schema.

2.      Read/Write
    Reading and writing to a database is just what it sounds like.
    +   When you complete actions that read from the database you are accessing the data for a particular purpose.
    +   When complete actions that write to the database you are putting new data into the database or changing data that is already existing.
    knowing if you workload will have more read operations or write operations will help you to design a database that is optimized for speed and efficiency.  

3.      Input/output operations per second
    IOPS is the measure of performance of reads and writes to a storage location like a database.
    Databases are IOPS intensive because they are continuously reading from the database and modifyinf the pages. Given this aspect of database, it is important to consider the impact of your performance when selecting IOPS.
    To improve latency and rea/write throughput, provision more IOPS when configuring the databse. Limiting the IOPS may cause the database to hit the threshold and reduce performance. Over provisioning of IOPS will result in higher costs for the instance.

4.      ACID and BASE compliance
<img src="assets/acid and base.PNG" alt="ACID" style="height:100%; width:100%"> 

<img src="assets/acid.PNG" alt="ACID" style="height:100%; width:100%"> 

<img src="assets/base.PNG" alt="BASE" style="height:100%; width:100%"> 

5.      OLTP/OLAP
<img src="assets/oltp and olap.PNG" alt="oltp" style="height:100%; width:100%">     

6.      Indexes
<img src="assets/indexes.PNG" alt="indexes" style="height:100%; width:100%">     

7.      SQL query language
<img src="assets/SQL.PNG" alt="indexes" style="height:100%; width:100%">     

####    Types of database
1.  Relational database
+   Structured data

2.  Nonrelational database
+   Unstructured and semi structured data

<img src="assets/types of database.PNG" alt="database" style="height:100%; width:100%">  

####    Relational database tables
<img src="assets/database example.PNG" alt="database" style="height:100%; width:100%">  

####    Relational databases benefits
+   Ease of use for structure data
+   Data integrity controls and accuracy
+   Common shared query language
+   Reducing redundancy and overall data storage.

<img src="assets/database benefits.PNG" alt="database" style="height:100%; width:100%"> 
