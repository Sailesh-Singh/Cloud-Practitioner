#   [Getting Started with Compute](https://awseducate.instructure.com/courses/817)

##	Overview
When we consider running our workloads on Amazon Web Services (AWS), we will want to consider our compute options. AWS provides the services that we need to build the compute solution that’s right for our workload and our business. We will review the primary compute types and the differences between them. We will also learn how computing balances different amounts of compute, memory, storage, and networking to optimize for our use case.

We will then focus on Amazon Elastic Compute Cloud (Amazon EC2), a secure and resizable compute service that offers reliable, scalable infrastructure on demand. Customers of all sizes and industries can use the broad range of instance choices from Amazon EC2 to match their workloads’ needs. We will learn about the types of instances to meet our use case. These instance types include general purpose, compute optimized, memory optimized, storage optimized, and accelerated computing. 

In this course, we acquire the knowledge that we need to start using Amazon EC2. We will learn about the key concepts and features of Amazon EC2. We will learn how to launch and configure an instance to meet our workload’s needs. We will choose storage for our compute instance and configure security to keep our data secure.  


##	Objectives
By the end of this course, we will be able to do the following:

+   Discuss different types of compute solutions and their features and benefits.
+   Discuss the basic features and concepts of Amazon EC2.
+   Describe EC2 instance types and how to choose an instance type.
+   Describe how to use Amazon EC2 to launch and configure an instance.
+   Describe how to manage EC2 instances.
+   Use Amazon EC2 to launch and manage and instance.

Click <a href="https://awseducate.instructure.com/courses/817">Getting Started with Compute</a>

[<img src="assets/Welcome_to_getting_started_with_compute.png" alt="Welcome_to_getting_started_with_storage.png" align="left" width="100%" height="100%">]()
<small>**_Getting Started with Compute_**</small>

+   In this module we learn about the compute domain and the Amazon Elastic Compute Cloud (Amazon EC2) service. It is broken into four sections.

    ####  [1.  Introduction to Compute]()
    ####  [2.  Amazon Elastic Compute Cloud (Amazon EC2)]()
    ####  [3.  Using Amazon EC2]()
    ####  [4.  Managing Amazon EC2]()

[<img src="assets/Four_Sections.png" alt="Four_Sections" align="left" width="100%" height="100%">]()
<small>**_Four Sections_**</small>

### Introduction to Compute
+   ####    Introduction to Compute

    Computing is the brain behind IT applications. Organizations all around the world run diverse workloads on different compute platforms. Dependin on our workload, we might need a different architectural method for how we set up our computing resources. 

    [<img src="assets/Introduction_to_Compute.png" alt="Introduction_to_Compute" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Introduction to Compute</i></b></small>
    </p>

    [<img src="assets/Introduction_to_Compute_2.png" alt="Introduction_to_Compute" align="left" width="100%" height="100%">]()

    In this section of the module, we will be introduced to the basics of compute, compute architectural methods, and some compute services that AWS offers.


+	####	What is computing?

    Computers have been around for a long time. Through the years, they have changed a lot. We rely on them for many things, including  things that we might not ordinarily associate with computers.

    [<img src="assets/Computer_development.png" alt="Computer_development" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Computer Development</i></b></small>
    </p>

	For example, we rely on computing for communication, travel, medical equipment, scientific research, financial security, sales transactions, everyday business tasks, entertainment, and much more.

    [<img src="assets/Examples_of_computing.png" alt="Examples_of_computing" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Examples of Computing</i></b></small>
    </p>

    At  its most base level, computing is the brain that makes IT applications work. It collects any necessary data, and it can then analyze that data, process that data, and, finally distribute that data.

    The main components of computing are CPU, memory, hard drive and network performance.


    [<img src="assets/Components_of_computing.png" alt="Components_of_computing" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Components of Computing</i></b></small>
    </p>


	+	#####	CPU
		CPU is the central processing unit. It is responsible for running and processing instructions that it is given.
		
	+	#####	RAM
		Our Computer's memory, or RAM, stores data that the computer needs to carry out processing tasks. For example, when you run an application, the required data to run the application is temporarily stored on the RAM.
		
	+	#####	Hard drive
		The hard drive is long-term storage where all of our files are stored and kept.
		
		
	+	#####	Network Performance
		The computer's network performance is the speed at  which a message can be sent or received. It is measured in two ways: bandwidth and latency.
		
		+	######	Bandwidth
			Bandwidth is the amount of data  that can be sent  over  a specified time.
		+	######	Latency 
			Latency is how long it takes the data to travel.

    [<img src="assets/OS_packages.png" alt="OS_packages" align="right" width="100px" height="90px">]()

	Every computer has an operating system. The operating system is the software package that manages the computer's hardware and software.
    
	Some of the most familiar operating systems are Microsoft Windows, Linux, and Apple's MacOS. The operating system, combined with our computer's hardware and additional software, determines the capabilities of our computer.

    [<img src="assets/Examples_of_OS.png" alt="Examples_of_OS" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Examples of OS</i></b></small>
    </p>

	With the expansion of virtualization technologies, computing has moved into what is called the **cloud**.
	
	Cloud Computing is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing. It alleviates the need to buy, own, and maintain physical data centers and servers. Instead, you can access  technology services, such as computing power, storage, and database, on as-needed basis from a cloud provider like AWS.
    
    [<img src="assets/Cloud_Computing.png" alt="Cloud_Computing" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Cloud Computing</i></b></small>
    </p>

    +	####	Benefits of Cloud computing
		Cloud computing has several benefits compared to on-permises computing.
		<!-- +	#####	Save on costs
		+	#####	Scalable
		+	#####	Reliable -->
		
        [<img src="assets/Benefits_of_Cloud-Computing.png" alt="Benefits_of_Cloud-Computing.png" align="left" width="100%" height="100%">]()
        <p align="center">
        <small><b><i>Benefits of Cloud computing</i></b></small>
        </p>

+	####	Computing Methods
    When deciding which computing method would work best for our architecture, we might consider instances, containers, serverless, or a hybrid of cloud and on-premises computing.

    +	#####	Instances

		An **instance**, or virtual machine, is a computing resource in the cloud. It works like a traditional on-premises server. it can support workloads such as web hosting, applications, databases, authentication services, and anything else a serveer can do. We choose the operating system (OS), CPU, memory, storage, and other components, and in a few minutes, our instance is ready to use. As soon as we're done, we can stop or terminate the instances. We're not locked in or stuck with servers that we don't need or want. We can treat instances as temproary and disposable computing resources, free from the inflexibility and constraints of a fixed and finite IT infrastructure.
		
		**Instance use cases** include the following:
		+	Hosting environment
		+	Development and testing environments
		+	Backup and disaster recovery

	+	#####	Containers