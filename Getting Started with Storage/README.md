#   Getting Started with Storage

## Overview

When you consider running your workloads on Amazon Web Services (AWS), you might first consider your storage options. AWS storage provides the services that you need to build the storage solution that’s right for your business. You will review the primary storage types and the differences between them. You will also learn how to identify the right solution in the cloud based on your requirements. 

You will then focus on Amazon Simple Storage Service (Amazon S3), an object storage service that offers industry-leading scalability, data availability, security, and performance.  Customers of all sizes and industries can use Amazon S3 to store and protect any amount of data for a range of use cases. These use cases include websites, mobile applications, backup and restore, archive, enterprise applications, Internet of Things (IoT) devices, and big data analytics. 

In this course, you acquire the knowledge that you need to start using Amazon S3. You learn about the key elements of Amazon S3 and explore how to configure them. You learn how to upload data to Amazon S3 and what additional AWS services you can use to transfer data to Amazon S3 at scale. You also learn the basic elements of security within Amazon S3.

##  Objectives
By the end of this course I will be able to do the following:


+   Discuss different types of storage solutions and their features and benefits.
+   Discuss the features and concepts of Amazon S3.
+   Describe Amazon S3 storage classes and associated use cases.
+   Discuss how to use Amazon S3 to create a bucket, upload objects, and work with objects.
+   Describe Amazon S3 configurations for cost savings and security.
+   Identify other AWS storage solutions and their use cases.
+   Use Amazon S3 to create a static website.

Click <a href="./Getting Started with Storage/README.md">Getting Started with Storage</a>

[<img src="assets/Welcome_to_getting_started_with_storage.png" alt="Welcome_to_getting_started_with_storage.png" align="left" width="100%" height="100%">]()
<small>**_Getting Started with Storage_**</small>

+   In this module we learn about basic storage domain and AWS course storage services. It is broken into following four sections:
    ####  [1.  Introduction to Storage](#introduction-to-storage)
    ####  [2.  Introduction to Amazon S3](#introduction-to-amazon-s3)
    ####  [3.  Using Amazon S3](#)
    ####  [4.  Additional AWS Storage Services](#)

[<img src="assets/Four_Sections.png" alt="Four_Sections" align="left" width="100%" height="100%">]()
<small>**_Four Sections_**</small>

### Introduction to Storage
+   #### Introduction to Storage

    Computers use data to complete tasks, and this data must be stored to be accessed. Some data can be stored internal to the computer itself, such as files that help the computer start up and run. More data can be stored on servers to be accessed by our computer. When data is on server in the cloud, people  all around the world can access it. 

    [<img src="assets/Introduction-to-storage.png" alt="Introduction-to-storage" align="left" width="100%" height="100%">]()
    <small>**_Introduction to Storage_**</small>

    There are different types of storage for different applications. Before learning about the types of cloud storage, it is important to understand the difference between **_On-premises storage and Cloud storage_**

    <table>
    <tr>
        <th>On-Premises</th>
        <th>Cloud Storage</th>
    </tr>

    <tr>
    <td>
    <p align="center">
        <img src="assets/On-premises-storage.png" alt="On-premises-storage" align="" width="50%" height="50%">
    </p>
    </td>

    <td>
    <p align="center">
        <img src="assets/Cloud_Storage.png" alt="Introduction-to-storage" align="" width="50%" height="50%">
    </p>
    </td>
    </tr>

    <tr>
    <td>
    <p align="center">
        <img src="assets/On-premises-storage-detail.png" alt="On-premises-storage-detail" align="" width="50%" height="50%">
    </p>
    </td>

    <td>
    <p align="center">
        <img src="assets/Cloud_Storage-detail.png" alt="Cloud_Storage-detail" align="" width="50%" height="50%">
    </p>
    </td>
    </tr>

    <tr>
    <td>
    <b>On-premises storage</b> means that our server is hosted within our organization's infrastructure and might be physically onsite. Company controls, administers, and maintains the server. Data and other information are shared between computers through our local network.
    </td>

    <td>

    With <b>Cloud Storage</b>, an outside service provider like AWS hosts our data. The cloud providers procures, installs, and maintains all hardware, software, and other supporting infrastructure in its data centers. We access these services and manage our account through the internet.
    </td>
    </tr>

    </table>

+   ####    Benefits of Cloud Storage

    [<img src="assets/Benefits_of_Cloud-Storage.png" alt="Benefits of Cloud Storage" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Benefits of Cloud Storage</i></strong></small>
    </p>


    <b>1.  Cost Efficient</b> so we pay for only what we use.

    <b>2.  Secure</b> because data is saved across multiple servers.

    <b>3.  Accessible</b> to multiple users in an account.

    <b>4.  Scalable</b> so it can grow and shrink as our workloads change.

    <b>5.  Managed</b> so we don't have to worry about servers, and we can focus on our data and applications.

    <b>6.  Backed up</b> so copies of data are stored in different physical locations in case of failure.

+   ####    Types of Cloud Storage

    [<img src="assets/Types_of_cloud-storage.png" alt="    Types_of_cloud-storage" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Types of Cloud Storage</i></strong></small>
    </p>

    Storage comes in three basic types: <b>block storage, file storage, and object storage</b>.

    #####   1.   Block Storage

    [<img src="assets/Block_storage.png" alt="Types_of_cloud-storage" align="left" width="90px" height="90px">]()

    Block storage breaks up data into blocks and then stores those blocks as separate pieces, each with a unique identifier. They are stored wherever it is most efficient. Thus, it can store those blocks across different systems and each block can be configured to work with different operating systems.
    
    <br>

    #####   2.   Cloud Storage

    [<img src="assets/File_storage.png" alt="File_storage" align="right" width="500px" height="150px">]()
    File storage is a methodology that helps users, applications, and services access data in a shared file system. Data is stored in a hierarchical structure. This structure is similar to a centralized shared network drive in a company where employees store and access file.

    <br>

    #####   3.   Object Storage

    [<img src="assets/Object_storage.png" alt="File_storage" align="right" width="100%" height="110px">]()

    In Object storage, files are stored as objects based on attributes and metadata. Each object consists of data, metadata, and an object key. The metadata has information about the data (object size, object purpose, and more), and the object key is the unique identifier of the object. When you update files in object storage, the entire file object is updated, instead of a piece of a file, as in block storage.

+   ####    Choosing the right storage type

    [<img src="assets/Choosing_the_right_storage_type.png" alt="Choosing the right storage type" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Choosing the right storage type</i></strong></small>
    </p>

+   ####    Storage use cases

    [<img src="assets/Storage_use_cases.png" alt="Storage_use_cases" align="left" width="40px" height="50px">]()

    Storage use cases gives ideas for how to solve storage problems that we might face. We will discuss about two use cases:  

    #####   1.   Block storage use cases

     [<img src="assets/Block_and_its_types.png" alt="Block_and_its_types" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Block storage and its types</i></strong></small>
    </p>

    ######  Hosting database instances
    Block storage scales with your performance needs, whether you are supporting millions of gaming customers or billions of e-commerce transactions. Databases such as SAP HANA, Oracle, Microsoft SQL Server, MySQL, and PostgreSQL are widely deployed on block storage.
    Block storage volumes provide consistent and low-latency performance for running NoSQL databases such as Cassandra, MongoDB, and CouchDB.

    ######  Big data analytics
    Block storage offers data persistence, dynamic-performance adjustments, and the ability to detach and reattach volumes. Therefore, you can resize clusters for big data analytics engines such as Apache Hadoop and Apache Spark.
    Block storage provides persistent, fast storage to address key components of your solution, including data warehouses, search and indexing, NoSQL databases, and streaming data.

    ######  Enterprise applications
    Block storage provides high availability and high durability storage to reliably run mission-critical applications on AWS.
    The design of block storage provides versatile storage services with:
    +   Low latency and consistently high input/output operations per second (IOPS) and throughput performance
    +   Capacity and performance scalability without workload disruption
    +   High availability

    #####   2.   Object storage use cases

    [<img src="assets/Object_and_its_types.png" alt="Object_and_its_types" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Object storage and its types</i></strong></small>
    </p>

    ######  Disaster recovery
    Protect critical data, applications, and IT systems that run in the AWS Cloud or your on-premises environment without incurring the expense of a second physical site. With object storage and other cloud services, you can create disaster recovery architectures to recover from outages caused by natural disasters, system failures, and human errors.

    ######  Data lakes
    Accelerate innovation by building a data lake with object storage. You can then extract valuable insights using query- in-place, analytics, and machine learning tools.
    You can also store large amounts of data that you only need to access periodically. For instance, suppose that your business does a lot of production work, in any medium. You probably need a lot of space to store your finished projects after their useful life is complete. However, you probably also need access to the files in case you or a client needs them again in the future.

    ######  Cloud-native applications
    Build fast, cost-effective cloud-native applications by using object storage to store development and production data. The microservices that make up cloud-native applications share this data. With object storage, you can upload any amount of data and access it anywhere to deploy applications faster and reach more users.

+   ####	AWS core storage services
    +   #####   Amazon Elastic Block Store (Amazon EBS)

        [<img src="assets/Amazon(EBS).png" alt="Amazon(EBS)" align="right" width="90px" height="90px">]()

        Amazon EBS is a scalable, high-performance block-storage service designed for Amazon Elastic Compute Cloud (Amazon EC2). You can use Amazon EBS to create storage volumes and attach them to Amazon EC2 instances. All EBS volume types offer durable snapshot capabilities and are designed for 99.999 percent availability. Amazon EBS provides a range of options that you can choose from to optimize storage performance and cost for your workload.

        [<img src="assets/Amazon(EBS)_Working.png" alt="Amazon(EBS)_Working" align="center" width="100%" height="100%">]()
        <p align="center">
        <small><strong><i>Amazon(EBS) Working</i></strong></small>
        </p>  

    +   #####   Amazon Elastic File System (Amazon EFS)

        [<img src="assets/Amazon(EFS).png" alt="Amazon(EFS)" align="left" width="90px" height="90px">]()

        Amazon Elastic File System (Amazon EFS) is a simple elastic file system that lets you share file data without provisioning or managing storage. It can be used with AWS services and on-premises resources.
        Amazon EFS is well suited to support a broad spectrum of use cases. These use cases include storage for serverless applications, web serving and content management, application development and testing, and database backups.

        [<img src="assets/Amazon(EFS)__Working.png" alt="Amazon(EFS)__Working" align="center" width="100%" height="100%">]()
        <p align="center">
        <small><strong><i>Amazon(EFS) Working</i></strong></small>
        </p> 

    +   #####   Amazon Simple Storage Services

        [<img src="assets/Amazon(S3).png" alt="Amazon(EFS)" align="right" width="90px" height="90px">]()

        Amazon Simple Storage Service (Amazon S3) is an object storage service that stores data as objects within buckets. An object is a file and any metadata that describes the file. A bucket is a container for objects.
        Amazon S3 can be used for many applications. It can be used for data lakes, websites, mobile applications, backup and restore, archive, enterprise applications, loT devices, and big data analytics.

        [<img src="assets/Amazon(S3)_Working.png" alt="Amazon(S3)_Working" align="center" width="100%" height="100%">]()
        <p align="center">
        <small><strong><i>Amazon(S3) Working</i></strong></small>
        </p>

+   ####	Introduction to Storage summary

    [<img src="assets/Storage_Summary.png" alt="Storage_Summary" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Storage Summary</i></strong></small>
    </p>

### Introduction to Amazon S3
+   ####    Introduction to Amazon S3
    Amazon S3, an object-level storage service. Amazon S3 stores objects inside buckets within the Region of our choice. Objects are then used in our applications or business operations.

    [<img src="assets/Amazon_S3_Object-Storage.png" alt="Amazon_S3_Object-Storage" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Amazon S3 Object Storage</i></strong></small>
    </p>

+   ####    Meet Amazon S3

    Amazon S3 is an object storage service that you can use to collect, store, and analyze data in any amount from anywhere in the world. Amazon S3 is available to businesses of all sizes and in any industry for a range of use cases.

    Common use cases include:
    +	<b>Data lakes</b>, for storing large amounts of data
    +	<b>File storage</b>, for static website hosting
    +	<b>Backups</b> of data, for use in disaster recovery
    +	<b>Archive</b>, for data that isn't being actively used but saved for the future.
    
    Amazon S3 offers high levels of <b>scalability, data durability and availability, perfomance, and security</b>.

+   ####    Basic S3 workflow

    First, we move our data into  Amazon S3. It accepts data of all file types. Although there is no limit to the amount of data that can be stored, individual objects must be less than 5 terabytes (TB).

    The data is stored as objects in an S3 bucket. Each object has a unique identifier.

    Using the unique identifier, we can use the objects in applications or to analyze data.

    [<img src="assets/Basic_S3-workflow.png" alt="Basic_S3-workflow" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Basic S3 Workflow</i></strong></small>
    </p>

+   ####    Object-level storage

    [<img src="assets/Object-level_storage.png" alt="Object-level_storage" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Object-level storage</i></strong></small>
    </p>

    The files, or objects, that we upload to Amazon S3 consist of data and metadata. The metadata consists of information about the data, such as content type, last modified date, and more. In addition to the data and metadata, an object's key serves as a unique identifier.
    S3 buckets are created inside regions. Objects are stored in a bucket, which is similar to a directory or folder in your computer. When you store  an object in a bucket, the combination of a bucket name, key, and version ID uniquely identifies the object  so that you can interact with that object.

+   ####    Active and archive storage

    [<img src="assets/Active_and_archive_storage.png" alt="Active_and_archive_storage" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Active and archive storage</i></strong></small>
    </p>

    Object storage can be classified by how often we must access our data. The two broad categories are active storage and archive storage. 

    Active storage is for the data we use all the time. It also includes data that we access less frequently, but it is important that data can be accessed quickly. Examples are files for a static website or backups.

    Archive storage is for data that we rarely access but must be maintained. Examples could include data for compliance or business continuity operations.

+   ####    Amazon S3 storage classes

    [<img src="assets/Amazon_S3_Storage_classes.png" alt="Amazon_S3_Storage_classes" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Amazon S3 Storage classes</i></strong></small>
    </p>

    Amazon S3 storage classes support virtually every storage use case from backup and recovery, to archive and digital preservation, to data lakes, business critical applications, and analytics. Storage class are based on the data access, resiliency, and cost requirements of our workloads.

    +   ##### Amazon S3 Standard 
    +   ##### Amazon S3 Standard-infrequent Access(IA)
    +   ##### Amazon S3 One Zone-infrequent Access(IA)
    +   ##### Amazon S3 Glacier Flexible Retrieval
    +   ##### Amazon S3 Glacier Deep Archive
    +   ##### Amazon S3 Intelligent-Tiering

+   ####    Amazon S3 storage classes use cases
    +   #####   Amazon S3 Standard
        +   Websites that only include static content
        +   Storage for log files that are frequently accessed, reviewed, or have analytics run against them
        +   Storage for application installers, configuration files, and provisioning and deployment tools

    +   #####   Amazon S3 Standard-infrequent Access(IA)
        +   Backups of your systems
        +   Files that are rarely accessed but must be quickly accessed if needed.

    +   #####   Amazon S3 One Zone-infrequent Access(IA)
        +   Storage for cross-Region replication backups from other 53 buckets
        +   Off-site storage of copies of on-premises backups, which gives us extra protection for your backups 
        +   Easily replaceable files

    +   #####   Amazon S3 Glacier Flexible Retrieval

        +   Storage of long term backups or archives for compliance purposes, or for backups that need to be retained for a long period of time
        +   Replacement for magnetic tapes stored on-premises or off site
        +   Digital media asset archive for large media files

    +   #####   Amazon S3 Glacier Deep Archive

        +   Archives or datasets that must be retained for compliance purposes
        +   Long-term data libraries

    +   #####   Amazon S3 Intelligent-Tiering

        +   Unpredictable workloads 
        +   Unknown workloads
        +   Rapidly changing workloads

+   ####    Choosing a Storage class - case 1

    >A user uploads a video to your application and your application generates a thumbnail preview of the video. Your user agreement permits a user to access the video thumbnail for one year. However, your usage data indicates that most thumbnail previews are not often accessed after 60 days but must be accessed quickly.
    <b>Which storage class might you recommend?</b>
    
    _<b>Amazon S3 - Infrequent Access</b> is the best choice for this situation. Using Amazon S3 - IA gives users quick access to the thumbnail but saves costs. You could consider using a lifecycle policy to move the thumbnail into archive storage after 60 days._

+   ####    Choosing a Storage class - case 2

    >A business wants to implement stronger business continuity practices and keep backups of their data for a long period of time. They do not anticipate needing to access the data often. But they want to be able to have the data within a few hours in the event of disaster recovery.
    <b>Which storage class might you recommend?</b>

    _<b>Amazon S3 Glacier Flexible Retrieval</b> is a low-cost option for long-term storage. Data can be retrieved in a number of hours with standard retrieval or 1-5 minutes with expedited retrieval._

+   ####    Choosing a Storage class - case 3

    >A company builds a cloud-native application with Amazon S3 storage for school exams. The application gets some use during the school term but then is used very heavily during the exam season near the end of the term. The application has unpredictable use patterns, and the company is trying to control costs.
    <b>Which storage class might you recommend?</b>
    
    _<b>Amazon S3 Intelligent-Tiering</b> should be used when workloads are unpredictable. Amazon S3 Intelligent-Tiering will optimize storage costs by automatically moving data to the most cost-effective access tier when access patterns change._

+   ####    Amazon S3 costs

    <table>

    <tr>
    <th>What costs money ?</th>
    <th>What doesn't cost money ?</th>
    </tr>

    <tr>
    <td>

    Pricing depends on the storage class you choose and the features that you require:
    
    **•** GB per month
    **•** Transfers OUT to other Regions or the internet
    **•** PUT, COPY, POST, LIST, and GET requests
    
    </td>

    <td>

    **•** Transfer IN to Amazon S3.
    **•** Transfer between S3 buckets in the same Region. 
    **•** Transfer OUT to Amazon EC2 in the same Region. 
    **•** Transfer OUT to Amazon CloudFront in the same Region.
    **•** DELETE and CANCEL requests.
    </td>
    </tr>

    <tr>
    <th>AWS Free Tier</th>
    <th>Estimate your own costs</th>
    </tr>

    <tr>
    <td>

    New AWS customers receive 5 GB of Amazon S3 for the first 12 months. Each month of the first 12 months includes:

    **•** 20,000 GET requests
    **•** 2,000 PUT, COPY, POST, or LIST requests
    **•** 100 GB of data transfer out
    </td>

    <td>

    The AWS pricing calculator will help you understand the costs of your own workload.

    For more information, see [AWS Pricing Calculator](https://calculator.aws/#/)
    </td>
    </tr>
    </table>

+   ####    Introduction to Amazon S3 summary

    In this section you have learned the basics of Amazon S3. Amazon S3 is an object storage service.

    The key takeaways from this section are:
    +   Amazon S3 is an object storage service.
    +   Buckets can store unlimited data but no object larger than 5 TB. 
    +   Amazon S3 has storage classes to suit every use case.
    +   Pricing is based on the type of object, how long it's stored, and how it is accessed. As with all AWS services, pricing is transparent.

### Using Amazon S3

+   ####    Using Amazon S3
    Now that we are familiar with the basics of Amazon S3, we will learn how to use the service. In this section, we will walk through the basic steps to create and configure a bucket, upload objects, and manage the service. Then, we will learn how to configure andwork with our buckets and objects.

    [<img src="assets/Using_Amazon_S3.png" alt="Using_Amazon_S3" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Using Amazon S3</i></strong></small>
    </p>

+   ####    Create a bucket

    The first step to create a bucket is to give the bucket a name. The name that we assign to our bucket must be globally unique even though  the bucket is created inside a Region.
    Bucket names can be 3-63 characters and must include only lowercase letters, numbers, dots (.), and hyphens (-). Bucket names begin and end with a letter or number.

    [<img src="assets/Using_Amazon_S3-create_a_bucket.png" alt="Using_Amazon_S3-create_a_bucket.png" align="center" width="100%" height="100%">]()
    <p align="center">
    <small><strong><i>Create a bucket</i></strong></small>
    </p>

    When we store an object in a bucket, the combination of a bucket name, key, and version ID uniquely identifies the object.

    For example, if we store an object called `myphotos.zip` in a bucket called `photobucket`, the URL would be as follows:
    `https://photobucket.s3.amazonaws.com/2021-04-13/myphotos.zip`
    The key  is `2021-04-13/myphotos.zip`. We use this unique URL to reference objects within the bucket.