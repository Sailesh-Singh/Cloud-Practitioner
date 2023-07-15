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
    +   A schema-less database manages information without the need for a blueprint.
    +   Semi-structured data does not follow the format of a tabular data model or relational databases because it does not have fixed schema.

2.      Read/Write
    Reading and writing to a database is just what it sounds like.
    +   When you complete actions that read from the database you are accessing the data for a particular purpose.
    +   When complete actions that write to the database you are putting new data into the database or changing data that is already existing.
    knowing if you workload will have more read operations or write operations will help you to design a database that is optimized for speed and efficiency.  

3.      Input/output operations per second
    IOPS is the measure of performance of reads and writes to a storage location like a database.
    Databases are IOPS intensive because they are continuously reading from the database and modifying the pages. Given this aspect of database, it is important to consider the impact of your performance when selecting IOPS.
    To improve latency and rea/write throughput, provision more IOPS when configuring the database. Limiting the IOPS may cause the database to hit the threshold and reduce performance. Over provisioning of IOPS will result in higher costs for the instance.

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

####    Use case of Relational database
<img src="assets/use case of database.PNG" alt="database" style="height:100%; width:100%"> 

####    Nonrelational database
<img src="assets/non relational database.PNG" alt="database" style="height:100%; width:100%"> 


####    Non relational database benefits
+   flexibility
+   Scalability
+   High performance
+   Highly functional APIs

####    Non relational database use case
<img src="assets/use case of non relational database.PNG" alt="database" style="height:100%; width:100%"> 

####    Why AWS database
+       purpose built
    AWS database service are purpose-built to support what your application is designed to do. Choose database service that best matches your workload.

+       performance at scale
    AWS offers databases hat are three to five times faster than popular alternatives, or non-relational databases that give you microsecond to sub-millisecond latency.

+       fully managed
    AWS manages database tasks such as server provisioning, patching, configuration, and backups so you can focus on developing your application.

+       secure and highly available
    AWS database are built for business-critical, enterprise workloads. They offer high availability, reliability, and security with multi-region and end-to-end encryption support.

####    Database deployments and management
+   On-premises database
<img src="assets/on-premises.PNG" alt="database" style="height:100%; width:100%"> 

+   Hosted on Amazon EC2
<img src="assets/hosted on amazon ec2.PNG" alt="database" style="height:100%; width:100%"> 

+   AWS managed    
<img src="assets/aws managed.PNG" alt="database" style="height:100%; width:100%"> 

####    AWS databases
<img src="assets/aws database.PNG" alt="database" style="height:100%; width:100%"> 

+   Relational
<img src="assets/relational.PNG" alt="database" style="height:100%; width:100%"> 

+   key-value
<img src="assets/key value.PNG" alt="database" style="height:100%; width:100%"> 

+   Document
<img src="assets/document.PNG" alt="database" style="height:100%; width:100%"> 

+   Timestream
<img src="assets/timestream.PNG" alt="database" style="height:100%; width:100%">

+   In-memory
<img src="assets/in-memory.PNG" alt="database" style="height:100%; width:100%">

+   Graph
<img src="assets/graph.PNG" alt="database" style="height:100%; width:100%">

+   Ledger
<img src="assets/graph.PNG" alt="database" style="height:100%; width:100%">


+   Key spaces
<img src="assets/keyspaces.PNG" alt="database" style="height:100%; width:100%">

####    Introduction to Amazon Relational Database Service(Amazon RDS)
+   Cost-efficient
+   Automating administration tasks
+   Resizable capacity

####    Amazon RDS engines
<img src="assets/RDS engine.PNG" alt="RDS" style="height:100%; width:100%">

####    Amazon RDS
    It is fully managed relational database service that supports the major relational database engines.

<b>Why move to a fully managed services?</b>

1.  Pass on the burden of repetitive tasks.
such as:

+   Backups and restores
+   Software installations and patching
+   Managing hardware

2.  Pass on the responsibility and engineering efforts.
+   scaling servers
+   highly available environments
+   maintenance free migration

####    Amazon RDS benefits
+   Easy to administer
+   Available and durable
+   Highly scalable
+   Fast
+   Secure
+   Inexpensive

####    High availability: Multi-AZ deployments
<img src="assets/multi-az.PNG" alt="az" style="height:100%; width:100%">

####    High availability: Multi-AZ deployments benefits
+       Enhanced durability
    +   Multi-AZ deployments for the MySQL, MariaDB, Oracle, and PostgreSQL engines utilize synchronous physical replication to keep data on the standby up to date with the primary.
    +   Multi-AZ deployments for the SQL Server engine use synchronous logical replication o achieve the same result, employing SQL Server-native mirroring technology.
    +   If the storage volume on the primary instance falls, Amazon RDS automatically initiates a failover to the standby.

+       Increased availability
    +   If there is an Availability Zone or primary database failure, your availability impact is limited to the time automatic failover takes to complete-typically under two minutes.
    +   This availability benefit extends to planned maintenance and backups as well.
    +   Upgrades and patches are installed on the standby instance first.
    +   Once completed, a failover is initiated, and the updates or patches are installed on the remaining instance.

+       No administrative intervention
    +   DB instance failover is fully automatic and requires no administrative intervention.
    +   Amazon RDS monitors the health of your primary and standbys and initiates a failover automatically in response to a variety of failover conditions.

####    Amazon RDS read replicas
+   Amazon RDS allows you to create a special type of database instance called a read replica from a source database instance.
+   Elastically scale out beyond the capacity constraints of a single database instance for read-heavy database workloads.
+   Create one or more replicas of a given source database instance to increase aggregate read throughput. 

<img src="assets/read replicas.PNG" alt="read replicas" style="height:100%; width:100%">

####    Amazon RDS read replicas benefits
+       Enhanced performance
    Amazon RDS uses the MariaDB, Microsoft SQL Server, MySQL, Oracle, and PostgreSQL DB engines built-in replication functionality to create a special type of DB instance called a read replica from as source DB instance. The source DB instance becomes the primary DB instance. Updates made to the primary DB instance are asynchronously copied to the read replica. You can reduce the load on your primary DB instance by routing read queries from your applications to the read replica. Using read replicas, you can elastically scale out beyond the capacity constraints of a single DB instance for read-heavy database workloads.

+       Increased availability
    Enhanced availability by deploying a standby instance in a second AZ, and achieve fault tolerance in the event of an AZ or database instance failure.

+       Designed for security 
    When you create a read replica for Amazon RDS for MySQL, MariaDB, or Postgres SQL, Amazon RDS sets up a secure communications channel using public key encryption between the source DB instance and the read replica, even when replicating across Regions. Amazon RDS establishes any possible security configurations, such as adding security group entries, needed to enable the secure channel. You can also create read replicas within a Region or between Regions for you Amazon RDS for MYSQL, MariaDB, PostgreSQL, or Oracle database instances encrypts at rest with AWS KMS.

There is a limit of five read replicas per primary    

####    High availability example
<img src="assets/high availability example.PNG" alt="high avilability" style="height:100%; width:100%">    

####    Amazon RDS High availability failover
<img src="assets/high availability failover.PNG" alt="failover" style="height:100%; width:100%"> 

####    Amazon RDS High availability failover sequence4
<img src="assets/sequence4.PNG" alt="sequence" style="height:100%; width:100%"> 

####    Multi-AZ vs read replicas
<img src="assets/az vs replicas.PNG" alt="az" style="height:100%; width:100%">

####    Database backups
<img src="assets/database backups.PNG" alt="database" style="height:100%; width:100%">

####    Database retention and backup storage
<img src="assets/database backups.PNG" alt="database" style="height:100%; width:100%">

<img src="assets/database backups.PNG" alt="database" style="height:100%; width:100%">

####    AWS backup
+   Use AWS backup to manage backups of Amazon RDS DB instances
+   AWS backup service provides a centralized backup console
+   Backups managed by AWS backup are counted as manual backups.

####    Amazon RDS backup solution
<img src="assets/Amazon RDS backup solution.PNG" alt="Amazon RDS backup solution" style="height:100%; width:100%">

####    Restoring Amazon RDS databases
<img src="assets/Restoring Amazon RDS databases.PNG" alt="Restoring Amazon RDS databases" style="height:100%; width:100%">

####    Use case for Amazon RDS
<img src="assets/use case for amazon RDS.PNG" alt="use case" style="height:100%; width:100%">

####    RDS costs
<img src="assets/RDS costs.PNG" alt="cost" style="height:100%; width:100%">

####    Setting up Amazon RDS
<img src="assets/setting up RDS.PNG" alt="RDS" style="height:100%; width:100%">

####    Amazon RDS workflow
<img src="assets/Amazon RDS workflow.PNG" alt="RDS workflow" style="height:100%; width:100%">

####    Amazon RDS decision points
+   creating a virtual private cloud(VPC)
+   Amazon Elastic Compute Cloud (Amazon EC2) instance and the Amazon RDS database
+   Understand your workload, what is it that you want to accomplish

<b>    Database engine</b>
+   Database engine you want to run
+   Each database engine has its own unique characteristics and features.

<b> Instance storage</b>

+   DB instance class you select determines the computation and memory capacity of the Amazon RDS DB instance.
+   Three DB instance class types that are supported by Amazon RDS are standard, memory optimized, and burstable performance.

<b>Security groups</b>

+   control access to a database instance.
+   Amazon RDS can use three types of security groups: database, VPC and EC2
+   Amazon RDS uses AWS Identity and Access Management or IAM.
+   IAM policies assign permissions that determine who can manage Amazon RDS resources.

####    Options for creating a database in the console
<img src="assets/creating db console.PNG" alt="DB" style="height:100%; width:100%">

####    Amazon RDS creation
<img src="assets/RDS creation.PNG" alt="RDS" style="height:100%; width:100%">

<img src="assets/creation1.PNG" alt="RDS" style="height:100%; width:100%">

<img src="assets/creation2.PNG" alt="RDS" style="height:100%; width:100%">

####   Amazon RDS creation Engine type
<img src="assets/engine type.PNG" alt="engine" style="height:100%; width:100%">

####   Amazon RDS creation templates
<img src="assets/templates.PNG" alt="templates" style="height:100%; width:100%">

####   Amazon RDS creation -deployment options
<img src="assets/deployment options.PNG" alt="RDS" style="height:100%; width:100%">

####   Amazon RDS creation - DB cluster identifier
<img src="assets/db cluster.PNG" alt="RDS" style="height:100%; width:100%">

####    Amazon RDS settings - DB instance class
<img src="assets/instance1.PNG" alt="instance" style="height:100%; width:100%">

<img src="assets/instance2.PNG" alt="instance" style="height:100%; width:100%">

<img src="assets/instance3.PNG" alt="instance" style="height:100%; width:100%">

####    Amazon RDS settings storage type
<img src="assets/storage type.PNG" alt="storage type" style="height:100%; width:100%">

####    Connectivity - compute resource
<img src="assets/connectivity.PNG" alt="connectivity" style="height:100%; width:100%">


####    Connectivity - VPC
<img src="assets/connectivity vpc.PNG" alt="connectivity" style="height:100%; width:100%">

####    Connectivity - security groups
<img src="assets/security groups.PNG" alt="connectivity" style="height:100%; width:100%">

####    Connectivity - security groups example
<img src="assets/security example.PNG" alt="connectivity" style="height:100%; width:100%">


####   Connectivity - additional configuration

<img src="assets/additional configuration.PNG" alt="connectivity" style="height:100%; width:100%">

####    Modify settings
<img src="assets/connectivity modify.PNG" alt="modify" style="height:100%; width:100%">

####    Modify setting- easy use
<img src="assets/easy modify.PNG" alt="modify" style="height:100%; width:100%">

####  Using Amazon RDS
+   Connect to the database engine
+   Working with the data in the database

####    Connecting to the database
+   A database connection allows you to work  with database tables directly.
+   Use any standard SQL client application to connect to a database on the DB instance.

####    Steps to connecting to database
<img src="assets/connecting db step.PNG" alt="database" style="height:100%; width:100%">

####    MySQL command-line
<img src="assets/command line.PNG" alt="command line" style="height:100%; width:100%">

####    Troubleshooting
1.      Inbound rules
<img src="assets/inbound rules.PNG" alt="inbound rules" style="height:100%; width:100%">  

2.      Public accessibility
<img src="assets/public accesibility.PNG" alt="public accessibility rules" style="height:100%; width:100%">

3.      Port
<img src="assets/port.PNG" alt="port" style="height:100%; width:100%">

4.      Availability
    For a newly created DB instance, the DB instance has a status of creating until the DB instance is ready to use. When the state changes to available, you can connect to the DB instance. Depending on the size of your DB instance, it can take up to 20 minutes before an instance is available.

5.      Internet gateway
    For DB instance to be publicly accessible, the subnets in
    its DB subnet group must have an internet gateway. 

6.      DNS port
    The wrong DNS name or endpoint is used to connect to the DB instance.

7.      User authentication
    User authentication is incorrect because of one of the following reasons:
    +   You are using an incorrect user name or password at the database level to access the instance from the DB client.
    +   You don't have the required database permissions to access the instance.
    +   The client is running on a version that's incompatible with the database version.

 ####    Role based access
<img src="assets/role based access.PNG" alt="role based access" style="height:100%; width:100%">    

####    Identifying roles
1.      Service user
<img src="assets/service user.PNG" alt="Identifying roles" style="height:100%; width:100%"> 

2.      Service administrator
<img src="assets/service administrator.PNG" alt="Identifying roles" style="height:100%; width:100%"> 

3.      IAM administrator
    If you are an IAM administrator, you might want to learn details about how you can write policies to manage access to Amazon RDS.

####    Basic SQL commands - CRUD
+   Structured Query Language = SQL
+   SQL is a programming language that communicated with databases.
+   Uses sets of keywords to retrieve data from databases, these keywords are called statements.
+   Create, read, update, delete are the four basic operations for creating and managing persistent data elements.
+   CRUD refers to the major operations which are implemented by databases. Each letter in the acronym can be mapped to a standard SQL statement.

####    Adding data in the database
<img src="assets/data in database.PNG" alt="data in database" style="height:100%; width:100%"> 

####    Quering data
<img src="assets/quering data.PNG" alt="quering data" style="height:100%; width:100%"> 

####    Removing data
<img src="assets/removing data.PNG" alt="removing data" style="height:100%; width:100%"> 

####    Monitoring Amazon RDS
<img src="assets/monitoring.PNG" alt="monitor
" style="height:100%; width:100%">

####    Monitoring Amazon in console
<img src="assets/monitoring console.PNG" alt="monitor
" style="height:100%; width:100%">

####    Monitoring tab metrics
<img src="assets/monitoring tab metrics.PNG" alt="monitor
" style="height:100%; width:100%">

####    Types of metrics
1.      High CPU or RAM
    A baseline helps you to interpret the results of this metric. There is no clear value at which you need to worry. It all depends on the database design.    
2.      Disk space
    You should be connected if this metric returns values at or above 85 percent of the total disk space. Consider deleting data or archiving data to a different system to free up space.

3.      Network traffic
    A baseline helps you to interpret the results of his metric. Work with your network architect to understand what expected throughput is. Investigate network traffic if throughput is consistently lower than expected.

4.      Database connections
    The optimal number of user connections for your database instance will vary based on your instance class and the complexity of the operations being performed. You can determine the number of database connections by associating your database instance with a parameter group where the User Connections parameter is set to a value other than 0 (unlimited). You can either use an existing parameter group or create a new one.

5.      IOPS metrics
    A baseline helps you to interpret the results of their metric. You should be concerned if values are consistently different than your baseline. For best IOPS performance, make sure your typical working set fits into memory to minimize read and write operations.

6.      Amazon CloudWatch alarms
    You can watch a single metric over a specific period of time and perform one or more actions based on the value of the metric relative to a threshold you set.

7.      Amazon CloudWatch logs
    Most database engines enable you to monitor, store, and access your database log files in CloudWatch logs.


##     LAB
####   Task 1: Creating an Amazon RDS database
In this task, you create a MySQL database in your virtual private cloud (VPC). MySQL is a popular open-source relational database management system (RDBMS), so there are no software licensing fees.

+   On the Services  menu, choose RDS.

+   Choose  Create database

+   For this lab, you will keep the Choose a database creation method as Standard create to understand the full set of features available. 

+   Under Engine options, select  MySQL.

+   For Version, keep MySQL 8.0.28. 

+   In the options, you might notice Amazon Aurora. Aurora is a global-scale relational database service built for the cloud with full MySQL and PostgreSQL compatibility. If your company uses large-scale MySQL or PostgreSQL databases, Aurora can provide enhanced performance.

+   In the Templates section, select  Dev/Test.

You can now select a database configuration, including software version, instance class, storage, and login settings. The Multi-AZ deployment option automatically creates a replica of the database in a second Availability Zone for high availability.

+   In the Availability and durability section, choose Single DB instance

+   In the Settings section next, configure the following options :

    +   DB instance identifier: inventory-db
    +   Master username: admin

    +   Master password: lab-password
    +   Confirm password: lab-password

Note: Please use these values verbatim, do not make any changes.

+   In the Instance configuration section, configure the following options for DB instance class:

    +   Choose  Burstable classes (includes t classes).
    +   Choose db.t3.micro.
+   In the Storage section next,

    +   For Storage type choose General Purpose SSD (gp2) from the Dropdown menu.
    +   For Allocated storage keep 20.
    +   Clear or Deselect Enable storage autoscaling.
 

+   In the Connectivity section, configure the following options: 

    +   For Compute resource

        +   keep default  Don’t connect to an EC2 compute resource, as you will establish this manually at a later stage.
    +   For Virtual private cloud (VPC) Choose Lab VPC from the Dropdown menu.

    +   For DB Subnet group, keep default value rds-lab-db-subnet-group

    +   For Public access Keep default value (No)   

    +   For VPC security group (firewall) 

        +   Choose the X on default to remove this security group. 
        +   Choose DB-SG from the dropdown list to add it.
        +   For Availability Zone, Keep default No preference  
    +   For Database authentication keep default value    Password authentication

+   In the Monitoring section

    +   Clear/DeSelect the  Enable Enhanced monitoring option.
+   Expand the following Additional configuration section by choosing 

    +   Under Database options, for Initial database name, enter inventory
This is the logical name of the database that the application will use.

 You can review the few other options displayed on the page, but leave them set to their default values. Options include automatic backups, Log exports , Encryption and automatic version upgrades. The ability to activate these features with check boxes demonstrates the power of using a fully managed database solution instead of installing, backing up, and maintaining the database yourself.

+   At the bottom of the page, choose Create database

You should receive this message: Creating database inventory-db.

 If you receive an error message that mentions rds-monitoring-role, confirm that you have cleared the Enable Enhanced monitoring option in the previous step, and then try again.

Before you continue to the next task, the database instance status must be Available. This process could take several minutes.


####   Task 2: Configuring web application communication with the database instance
This lab automatically deployed an Amazon Elastic Compute Cloud (Amazon EC2) instance with a running web application. You must use the IP address of the instance to connect to the application. I this task, you will use application to configure connection settings which will be stored in AWS Secrets Manager for further use.

+   On the Services  menu, choose EC2.

+   In the left navigation pane, choose Instances.

In the center pane, there should be a running instance that is named App Server.

+   Select the check box for the App Server instance.

+   In the Details tab, copy the Public IPv4 address to your clipboard.

Tip: You can choose copy   to copy the displayed value the displayed value.

+   Open a new web browser tab, paste the IP address into the address bar, and then press Enter.

The web application should appear. It does not display much information because the application is not yet connected to the database.

+   Choose  Settings.

You can now configure the application to use the Amazon RDS database instance that you created earlier. You first retrieve the database endpoint so that the application knows how to connect to a database.

+   Return to the AWS Management Console, but do not close the application tab. (You will return to it soon).

+   On the Services  menu, choose RDS.

+   In the left navigation pane, choose Databases.

+   Under DB identifier, Choose 'inventory-db'.

+   From the Connectivity & security section, copy the Endpoint to your clipboard.

It should look similar to this example: inventory-db.crwxbgqad61a.rds.amazonaws.com

+   Return to the browser tab with the inventory application, and enter the following values:

    +   For Endpoint, paste the endpoint you copied earlier.
    +   For Database, enter inventory
    +   For Username, enter admin
    +   For Password, enter lab-password
    +   Choose Save.
The application will now Save this information into AWS Secrets Manager  and connect to the database, load some initial data, and display information.

+   You can use the web application to   Add inventory,  edit, and  delete inventory information.

The inventory information is stored in the Amazon RDS MySQL database that you created earlier in the lab. This means that any failure in the application server will not lead to loss of any data. It also means that multiple application servers can access the same data.

+   Insert new records into the table. Ensure that the table has 5 or more inventory records.

 You have now successfully launched the application and connected it to the database.

Optional: To access the saved parameters, go to the AWS Management console. On the Services  menu, choose Secrets Manager , choose Secrets. 


####   Task 3: Monitoring the Database Instance
Monitoring is an important part of maintaining the reliability, availability, and performance of any database. Amazon RDS service provides many useful metrics to monitor the health of your database instance. In this task you will explore few useful metrics for the database instance you created.

+   Return to the AWS Management Console.

+   On the Services  menu , choose RDS.

+   Choose Databases.

+   Choose 'inventory-db'.

+   In the pane below, choose Monitoring tab.

+   Observe the CloudWatch metrics indicating respective database Instance parameters as shown in example below.


+   Perform various operations on the web application like add, update or remove records from inventory database and observe the changes in the values mentioned above.

+   Scroll down further to observe other  available metrics.

####   Task 4: Performing operations on Database.
In this task, you learn about a few administrative tasks that can be performed on the database in Amazon RDS.

+   Return to the RDS Management Console (if you have navigated out)

+   Choose Databases.

+   Choose 'inventory-db'.

+   Under Actions menu, there are various operations to perform e.g. Stop temporarily, Reboot, etc.

+   Choose Stop temporarily, to stop the instance temporarily. (Database automatically restarts after 7 days)

    +   Select checkbox under 'Acknowledgement'
    +   Choose  Stop temporarily
	Note: Stopping the instance also stops the billing charges associated with the running instance. Database(s) continues to occupy storage space and incur billing charges.

+   Refresh the browser after few minutes to verify that the instance is stopped. (Status = Stopped) 

Optional - You can Start the instance, re-connect it to the  web application and continue to use.

In this lab you launched MYSQL RDS database instance, configured an existing web application to interact with the database instance. Then you performed basic tasks such as querying, updating records and monitored the various metrics to gain insights  into the health of the database and finally performed basic database administrative operations.