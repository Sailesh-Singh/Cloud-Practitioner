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

    Computing is the brain behind IT applications. Organizations all around the world run diverse workloads on different compute platforms. Depending on our workload, we might need a different architectural method for how we set up our computing resources. 

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
		Our Computer's memory, or RAM, stores data that the computer needs to carry out processing tasks. For example, when we run an application, the required data to run the application is temporarily stored on the RAM.
		
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
	
	Cloud Computing is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing. It alleviates the need to buy, own, and maintain physical data centers and servers. Instead, we can access  technology services, such as computing power, storage, and database, on as-needed basis from a cloud provider like AWS.
    
    [<img src="assets/Cloud_Computing.png" alt="Cloud_Computing" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Cloud Computing</i></b></small>
    </p>

    +	####	Benefits of Cloud computing
		Cloud computing has several benefits compared to on-premises computing.
		<!-- +	#####	Save on costs
		+	#####	Scalable
		+	#####	Reliable -->
		
        [<img src="assets/Benefits_of_Cloud-Computing.png" alt="Benefits_of_Cloud-Computing.png" align="left" width="100%" height="100%">]()
        <p align="center">
        <small><b><i>Benefits of Cloud computing</i></b></small>
        </p>

+	####	Computing Methods
    When deciding which computing method would work best for our architecture, we might consider instances, containers, serverless, or a hybrid of cloud and on-premises computing.

	[<img src="assets/Computing_Methods.png" alt="Computing_Methods" align="left" width="100%" height="100%">]()
    <p align="center">
	<small><b><i>Computing Methods</i></b></small>
	</p>

    +	#####	Instances

		An **instance**, or virtual machine, is a computing resource in the cloud. It works like a traditional on-premises server. it can support workloads such as web hosting, applications, databases, authentication services, and anything else a server can do. We choose the operating system (OS), CPU, memory, storage, and other components, and in a few minutes, our instance is ready to use. As soon as we're done, we can stop or terminate the instances. We're not locked in or stuck with servers that we don't need or want. We can treat instances as temporary and disposable computing resources, free from the inflexibility and constraints of a fixed and finite IT infrastructure.
		
		**Instance use cases** include the following:
		+	Hosting environment
		+	Development and testing environments
		+	Backup and disaster recovery

	+	#####	Containers

		**Containers** are a method of operating system virtualization that we can use to run an application and its dependencies in resource-isolated processes. By using containers, we can package an application's code, configurations, and dependencies into simple building blocks that deliver environmental consistency, operational efficiency, developer productivity, and version control.
		Containers are smaller than virtual machines and do not contain an entire operating system. Instead, containers share a virtualized operating system and run as resource-isolated processes, which ensure quick, reliable, and consistent deployments. Containers hold everything that the software needs to run, such as libraries, system tools, code, and the runtime.
		
		**Containers use case** include the following:
		+	Building microservices architecture
		+	Video rendering services
		+	Quick development and deployment

	+	#####	Serverless
		**Serverless computing** gives us the ability to run code without provisioning or managing servers. Serverless computing features automatic scaling, built-in high availability, and a pay-for-use billing model to increase agility and optimize costs. Serverless computing also eliminates infrastructure management tasks like capacity provisioning and patching, so we can focus on writing code that serves our customers.
		
		**Serverless use cases** include the following:
		+	File processing 
		+	Web applications 
		+	Mobile backends
		+	Cron jobs (scheduled computing tasks)

	+	#####	Hybrid

		In a **hybrid** deployment, cloud-based resources are connected to on-premises infrastructure. We might want to use this approach in a number of situations. For example, we have legacy applications that are better maintained on premises, or government regulations require our business to keep certain records on premises.
		
		For example, suppose that a company wants to use cloud services that can automate batch data processing and analytics. However, the company has several legacy applications that are more suitable on premises and will not be migrated to the cloud. With a hybrid deployment, the company could keep the legacy applications on premises while benefiting from the data and analytics services that run in the cloud.

		**Hybrid use cases** include the following:
		+	Legacy applications
		+	Company regulatory requirements
		+	Government regulatory requirements

+	####	AWS Computing Services
	+	#####	Amazon EC2
		Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure and resizable compute capacity in the cloud. We can use it to provision virtual servers that are called Amazon EC2 instances, which can handle almost any computing need.
		With Amazon EC2 we can do the following:
		+	Provision and launch one or more EC2 instances in minutes.
		+	Stop or shut down EC2 instances when we finish running a workload. 
		+	Pay for only the compute time that we use when running an instance.

	+	#####	AWS Lambda

		AWS Lambda is a serverless compute service that helps us run code without provisioning or managing servers. We pay for only the compute time we consume, and we incur no charges when our code is not running.
		With Lambda, we can run code for virtually any type of application or backend service, all with zero administration. We need only to upload our code, and Lambda manages everything required to run and scale our code with high availability. We can set up our code to automatically launch from other AWS services or call it directly from any web or mobile app.

	+	#####	Amazon ECS

		Amazon Elastic Container Service (Amazon ECS) is a highly scalable and high-performance container management system. It helps customers spin up new containers and manage them across EC2 instances. Amazon ECS supports Docker containers. Docker is a software platform that packages software (such as applications) into containers.
		To manage our containers, we must install an open-source Amazon ECS container agent on our EC2 instances. This agent is referred to as a container instance. We can run this agent on both Linux and Windows Amazon Machine Images (AMIs). Amazon ECS uses API calls to control Docker-enabled applications.

	+	#####	Amazon EKS

		Amazon Elastic Kubernetes Service (Amazon EKS) provides the flexibility to start, run, and scale Kubernetes applications in the AWS Cloud or on premises. Kubernetes is an open-source platform for managing containerized applications. It is portable and extensible.
		With Amazon EKS, we will be able to provide highly available and secure clusters. It automates patching, node provisioning, and updates.

	+	#####	AWS Fargate

		AWS Fargate is a serverless compute engine for containers. It supports both Amazon ECS and Amazon EKS architectures. Fargate allocates the right amount of compute, which reduces the need to manage EC2 instances, cluster capacity, and scaling.

	+	#####	AWS Elastic Beanstalk

        AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications. We can upload our code, and Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring. At the same time, we retain full control over the AWS resources powering our application and can access the underlying resources at any time.

        There is no additional charge for Elastic Beanstalk; we pay for only the AWS resources needed to store and run our applications.

###	Introduction to Amazon EC2
In this section, we will be introduced to Amazon EC2, a cloud computing service. Amazon EC2 is a web service that provides resizable compute capacity in the cloud at affordable costs all around the world.

+	####	What is Amazon  EC2?

	Amazon EC2, is a compute service that _provides resizable compute capacity in the cloud_. It's designed to make web-scale computing easier for developers. It eliminates the need to invest in hardware up front, so we can focus on developing and deploying applications faster. We can use Amazon EC2 to launch as many _virtual server_, also known as **compute instances**, as we need.

	+	#####	EC2 instance types

		Amazon EC2 offers a wide selection of instance types optimized to fit different use cases. Instance types are composed of
		
		+	CPU
		+	Memory
		+	Storage
		+	Networking Capacity
		
		Amazon EC2 instances are **_reliable, scalable, highly available, and cost effective_**. 
	
	+	#####	Amazon EC2 purchasing options

		+	On-Demand Instances
		+	Savings Plans
		+	Dedicated Hosts
		+	Spot instances

+	####	What problems does Amazon EC2 solve?

	Running servers on-premises is a big challenge for building our IT architecture.
	Data centers are expensive to build, staff, and maintain. We need to think ahead for computing capacity needs.
	For example, it can be difficult to predict traffic spikes and peak workloads. And this issue must be balanced with making sure that we don't have unused and idle servers running. Unused resources can be wasteful and cost us a lot of money.
	
	With Amazon EC2, we do not need to guess our computing capacity. As traffic spikes or workloads increase, we can launch more instances to meet the computing needs. When workloads die down, we can stop the instance or terminate it so that we don't have idle instances that are costing us money. With Amazon EC2, we pay for only what we use, which helps us save on costs.

+	####	Amazon EC2 Overview

	Amazon EC2 provides virtual machines in the cloud and gives us full administrative control over the operating system that runs on the instance. Amazon EC2 supports most server operating systems, including Windows and Linux.
	With Amazon EC2, we can launch any number of instances of any size into any Availability Zone anywhere in the world in a matter of minutes. We can also control traffic to and from instances by using security groups and Elastic Load Balancing (ELB). Amazon EC2 can host the same kinds of applications that we might run on a traditional on-premises server.

	[<img src="assets/Amazon_EC2_Overview.png" alt="Amazon_EC2_Overview" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Amazon EC2 Overview</i></b></small>
    </p>


+	####	Amazon EC2 benefits

	[<img src="assets/Amazon_EC2_benefits.png" alt="Amazon_EC2_benefits" align="left" width="100%" height="100%">]()
    <p align="center">
    <small><b><i>Amazon EC2 benefits</i></b></small>
    </p>

<details open>
<summary><b>Click to learn more about Amazon EC2 benefits</b></summary>	

<table>
<tr>
<th>
	<img src="assets/Elastic_computing﻿.png" alt="Elastic computing" align="center" width="100px" height="100px"><br>
	Elastic computing
</th>
<td>
We can use Amazon EC2 to increase or decrease capacity within minutes, not hours or days. We can commission one, hundreds, or even thousands of server instances simultaneously. We can also use Amazon EC2 Auto Scaling to maintain availability of our Amazon EC2 fleet and automatically scale our fleet up and down depending on our needs to maximize performance and minimize cost. To scale multiple services, we can use AWS Auto Scaling.
</td>
<tr>

<tr>
<th>
	<img src="assets/Complete_control.png" alt="Complete control" align="center" width="100px" height="100px"><br>
	Complete control
</th>
<td>
We have complete control of our instances, including root access, and the ability to interact with them as we would any machine. We can stop any instance while retaining the data on the boot partition and then subsequently restart the same instance by using web service APIs. Instances can be rebooted remotely by using web service APIs, and we also have access to their console output.
</td>
<tr>

<tr>
<th>
	<img src="assets/Flexible_hosting_services.png" alt="Flexible hosting services" align="center" width="100px" height="100px"><br>
	Flexible hosting services
</th>
<td>
We have the choice of multiple instance types, operating systems, and software packages. With Amazon EC2, we can select a configuration of memory, CPU, instance storage, and boot partition size that's optimal for our choice of operating system and application. For example, choice of operating systems includes numerous Linux distributions and Microsoft Windows Server.
</td>
<tr>

<tr>
<th>
	<img src="assets/Integrated.png" alt="Integrated" align="center" width="100px" height="100px"><br>
	Integrated
</th>
<td>
Amazon EC2 is integrated with most AWS services. For example, these services could include Amazon Simple Storage Service (Amazon S3), Amazon Relational Database Service (Amazon RDS), and Amazon Virtual Private Cloud (Amazon VPC). This integration provides a complete, secure solution for computing, query processing, and cloud storage across a wide range of applications.
</td>
<tr>

<tr>
<th>
	<img src="assets/Reliable.png" alt="Reliable" align="center" width="100px" height="100px"><br>
	Reliable
</th>
<td>
Amazon EC2 offers a highly reliable environment where replacement instances can be rapidly and predictably commissioned. The service runs within the proven network infrastructure and data centers of Amazon.
</td>
<tr>

<tr>
<th>
	<img src="assets/Secure.png" alt="Secure" align="center" width="100px" height="100px"><br>
	Secure
</th>
<td>
Security is our highest priority. As an AWS customer, we will benefit from a data center and network architecture that's built to meet the requirements of the most security-sensitive organizations. Amazon EC2 works in conjunction with Amazon VPC to provide security and robust networking functionality for our compute resources.
</td>
<tr>

<tr>
<th>
	<img src="assets/Inexpensive.png" alt="Inexpensive" align="center" width="100px" height="100px"><br>
	Inexpensive
</th>
<td>
Using Amazon EC2, we can take advantage of Amazon's scale-you can pay a very low rate for the compute capacity that we actually consume.
For more information about Amazon EC2 pricing, see the <a href="https://aws.amazon.com/ec2/pricing/?trk=36c6da98-7b20-48fa-8225-4784bced9843&sc_channel=ps&sc_campaign=acquisition&sc_medium=ACQ-P|PS-GO|Brand|Desktop|SU|Compute|EC2|US|EN|Text&s_kwcid=AL!4422!3!488982705483!p!!g!!amazon%20ec2&ef_id=CjwKCAjw7vuUBhBUEiwAEdu2pFivmVo-FtkL4LGDqt2DTC4ADQ5jtqayYy9VLodSssQxZvZ-ptsVXBoCJ9YQAvD_BwE:G:s&s_kwcid=AL!4422!3!488982705483!p!!g!!amazon%20ec2"> Amazon EC2 Pricing </a>page.
</td>
<tr>

<tr>
<th>
	<img src="assets/Get_started_quickly.png" alt="Get started quickly" align="center" width="100px" height="100px"><br>
	Get started quickly
</th>
<td>
We can get started quickly with Amazon EC2. Whether we launch an instance programmatically or through the AWS Management Console, our instances will be ready to use in minutes. When we no longer need the instances, we can stop or terminate them as quickly as we started them.
</td>
<tr>

</table>

</details>

+	####	Amazon EC2 architecture

	We'll be deciding which Region, Virtual Private Cloud (VPC) on AWS, subnet, and security group to place it in. First, we must choose the the Region. AWS has Regions all over the globe.

    <p align="center">
	<img src="assets/Amazon_EC2_Environment.png" alt="Amazon_EC2_Environment" width="900px" height="100%">
	</p>
    <p align="center">
    <small><b><i>Amazon EC2 Environment</i></b></small>
    </p>
	
	The Region is the outer portion of our architecture. Next, we choose the VPC on AWS that we want to place our EC2 instance in. Within each VPC, we can then specify the subnet to place the EC2 instance in. Each EC2 instance will be placed behind a security group, with the security configurations that we have set up, when we launch the instance. For high availability, it is a best practice to place our instances in multiple subnets in different Availability Zones. Then, have an Elastic Load Balancer attached to route traffic based on our application needs.
   
    <p align="center">
	<img src="assets/Amazon_EC2_architecture.png" alt="Amazon_EC2_architecture" width="80%" height="80%">
	</p>
    <p align="center">
    <small><b><i>Amazon EC2 Architecture</i></b></small>
    </p>

+	####	Amazon EC2 architectural components

	+	#####	Regions
		[<img src="assets/Amazon_EC2_architectural_components-Regions.png" alt="Amazon_EC2_architectural_components-Regions" align="left" width="100%" height="100%">]()
		<p align="center">
		<small><b><i>Regions</i></b></small>
		</p>
		When we launch an EC2 instance, we must choose the Region that we want to provision the instance in. A Region is a physical location around the world where AWS clusters data centers.
		Each Region is designed to be isolated from the other Regions. This separation achieves the greatest possible fault tolerance and stability. Ideally, when we launch an instance, we want to choose the Region that is closest to our users to help cut down on latency.

	+	#####	VPC

		EC2 instances are launched in the VPC that we choose. Amazon VPC is a service that lets us launch AWS resources in a logically isolated virtual network that we define. When we set up an AWS account, we are given a default VPC. However, we can create multiple VPCs in a single Region or place them in different Regions.
		Each VPC can have a dedicated purpose to support different environments, such as production, development, and testing. If we do not specify the VPC to launch our instance in, then it will be launched in our default VPC.

		<p align="center">
		<img src="assets/Amazon_EC2_architectural_components-VPC.png" alt="Amazon_EC2_architectural_components-VPC"  width="400px" height="300px">
		</p>
		<p align="center">
		<small><b><i>VPC</i></b></small>
		</p>

	+	#####	Subnets

		Within each VPC, we can specify the subnet to place the EC2 instance in. A subnet is a range of IP addresses in our VPC. Use a public subnet for resources that must be connected to the internet and a private subnet for resources that won't be connected to the internet.
		Subnets are associated with only one Availability Zone. We will learn more about the architecture of a VPC and subnets in the Getting Started with Networking course. This high-level overview is to help we understand the architectural environment that our EC2 instance will be launched in.

		<p align="center">
		<img src="assets/Amazon_EC2_architectural_components-Subnets.png" alt="Amazon_EC2_architectural_components-Subnets"  width="400px" height="300px">
		</p>
		<p align="center">
		<small><b><i>Subnets</i></b></small>
		</p>

	+	#####	Security groups

		When we launch our EC2 instance, it will be protected by a security group that we select while configuring the instance. A security group acts as a virtual firewall for our EC2 instances to control incoming and outgoing traffic. We want to build our application to be highly available and fault tolerant. To do so, a best practice is to launch instances in multiple Availability Zones and attach an Elastic Load Balancer. An Elastic Load Balancer automatically distributes incoming application traffic across multiple targets and virtual instances in one or more Availability Zones.

		<p align="center">
		<img src="assets/Amazon_EC2_architectural_components-SecurityGroups.png" alt="Amazon_EC2_architectural_components-SecurityGroups" width="400px" height="300px">
		</p>
		<p align="center">
		<small><b><i>Security groups</i></b></small>
		</p>

+	####	Amazon EC2 use cases

	Amazon EC2 has many use cases to help customers manage their applications.

	+	**_Run cloud-native and enterprise applications_**
		Amazon EC2 delivers secure, reliable, high-performance, and cost-effective compute infrastructure to meet demanding business needs.

	+	**_Scale for high performance computing (HPC) applications_**
		Access the on-demand infrastructure and capacity that you need to run HPC applications faster and more cost effectively.

	+	**_Develop for Apple platforms_**
		Build, test, and sign on-demand macOS workloads. Access environments in minutes, dynamically scale capacity as needed, and benefit from AWS pay-as-you-go pricing.

	+	**_Train and deploy machine learning (ML) applications_**
		Amazon EC2 delivers the broadcast choice of compute, networking (up to 400 Gbps), and storage services, purpose-built to optimize price performance for ML projects.

+	####	Instance costs

	Five main aspects of our instance will determine the cost. They are the Instance purchasing options, the tenancy, the Amazon Machine Image (AMI), the EC2 instance type, and the storage type and size that you choose. For now, we are going to focus on the purchasing options and tenancy. We will learn more about the AMI, instance types, and storage in the next section.

	[<img src="assets/Instance_costs.png" alt="Amazon_EC2_architectural_components-SecurityGroups" width="100%" height="100%">]()
	</p>
	<p align="center">
	<small><b><i>Instance Costs</i></b></small>
	</p>

+	####	Instance purchasing options

	Amazon EC2 provides purchasing options so that we can optimize our costs based on our needs. When we choose an instance purchasing option, we should consider the following:
	+	The instance use case
	+	The purchasing option's costs structure

	[<img src="assets/Instance_purchasing_options.png" alt="Instance purchasing options" align="center" width="100%" height="100%">]()
	
	Based on our needs Amazon EC2 provides four main purchasing options:
	<b>1.	On-Demand Instances</b>
	<b>2.	Reserved Instances</b>
	<b>3.	Savings Plans Instances</b>, and 
	<b>4.	Spot Instances</b>

+	####	On-Demand  Instances

	[<img src="assets/On-Demand_Instances.png" alt="On-Demand  Instances" align="left" width="100px" height="100px">]()

	+	Pay for compute capacity per second (Amazon Linux and Ubuntu) or by the hour (all other operating systems)
	+	No long-term commitments
	+	No upfront payments
	+	Increase or decrease our compute capacity depending on the demands of our application

	<table>
	<thead>
	<tr>
	<th style="background:#fb9b04">Use case</th>
	<th style="background:#fb9b04">Problem solved</th>
	</tr>
	</thead>
	<tbody style="background:#fff5e6">
	<tr>
	<td>Short-term, spiky, or unpredictable workloads</td>
	<td rowspan="2">Application development or testing</td>
	</tr>
	<tr>
	<td>Solve the need for immediate compute capacity</td>
	</tr>
	</tbody>
	</table>

+	####	Reserved Instances (RI)

	Reserved Instances can provide a significant discount for your architectures.
	<p align="center">
	<img src="assets/Reserved_Instances.png" alt="Reserved Instances" align="" width="100px" height="100px">
	</p>

	+	Up to 72 percent discount compared to On-Demand Instances
	+	Prepay for capacity (1-year or 3-year buying options)
	+	The upfront payment methods:
		+	Standard RIs
		+	Convertible RIs
		+	Scheduled RIs

	<table>
	<thead>
	<tr style="background:#bbb3db">
	<th>Use case</th>
	<th>Problem solved</th>
	</tr>
	</thead>
	<tbody style="background:#f1f0f8">
	<tr>
	<td>Predictable usage workloads that do not require flexibility in compute power</td>
	<td rowspan="3">Provides the ability to reserve capacity ahead of time reducing cost</td>
	</tr>
	<tr>
	<td>Workloads that  last longer than 1 year</td>
	</tr>
	<tr>
	<td>Users are able to make upfront payments to reduce total  computing costs even further</td>
	</tr>
	</tbody>
	</table>

+	####	Savings Plans Instances

	AWS offers two types of savings plans:

	[<img src="assets/Savings_Plans_Instances.png" alt="Savings Plans Instances" align="left" width="100px" height="100px">]()

	+	**Compute Savings Plans** provide the most flexibility and help to reduce our costs by up to 66 percent.

		+	These plans automatically apply to EC2 instance usage regardless of instance family, size, Availability Zone, Region, Operating System, or tenancy. They also apply to AWS Fargate and AWS Lambda usage.
		
	+	**EC2 Instance Savings Plans** apply to a specific instance family within a specific Region and provide the largest discount (up to 72 percent, like Standard RIs)

	<table>
	<thead>
	<tr style="background:#abe324">
	<th>Use case</th>
	<th>Problem solved</th>
	</tr>
	</thead>
	<tbody style="background:#f7fce9">
	<tr>
	<td>Long time workloads</td>
	<td rowspan="2">Don't have to coordinate our RI purchases</td>
	</tr>
	<tr>
	<td>Computing needs that might need flexibility over location or by instance power</td>
	</tr>
	</tbody>
	</table>

+	####	Spot Instances


	[<img src="assets/Spot_Instances.png" alt="Spot Instances" align="left" width="100px" height="100px">]()

	+	Purchase unused Amazon EC2 capacity
	+	Up to 90 percent off compared to on-demanding pricing
	+	Prices controlled by AWS based on supply and demand
	+	Termination notice provided 2 minutes prior to termination
	+	Spot blocks: Launch Spot Instances with a duration lasting 1-6 hours

	<table>
	<thead>
	<tr style="background:#63d3fb">
		<th>Use case</th>
		<th>Problem solved</th>
	</tr>
	</thead>
	<tbody style="background:#effbff">
	<tr>
		<td>Applications with flexible start and end time</td>
		<td rowspan="3">Low budgeted workloads can be completed with low cost instances, provided that interruptions can be tolerated.</td>
	</tr>
	<tr>
		<td>Applications only feasible at very low compute prices</td>
	</tr>
	<tr>
		<td>Users with  urgent computing needs for large amounts of additional capacity</td>
	</tr>
	</tbody>
	</table>


+	####	Amazon EC2 purchasing options thinking activity (instructions)

	**<p align="center">What is your solution?</p>**

	_**Instructions:** Read the scenario that describes the business problem. Then think about which Amazon EC2 purchasing option you would recommend. The key to selecting the right answer is based on use case and keeping the costs as low as possible. Don't guess; reason it out and see whether you can explain your choice. Then choose the question mark icon to see whether you were correct._

	> **<p align="center">Solution</p>**
	> See if your answer corresponds with the solution. If it doesn't, go back and review the differences between the Amazon EC2 purchasing options in this section.

+	####	Amazon EC2 purchasing options scenario 1

	**<p align="center">What is your solution?</p>**

	_Your manager has told you that you must set up some computing resources by using Amazon EC2. You are told that the project lasts at least 1 year, maybe longer. The resources should be located in Ireland, but they might need to move to the United States within 6 months. Also, some people have discussed the possibility of moving the application to Lambda later in the year. Which Amazon EC2 purchasing option would you recommend?_

	> **<p align="center">Solution</p>**
	> The best instance purchasing option would be the Compute Savings Plans. It provides the flexibility needed and helps to reduce your costs by up to 66 percent. With these instance types, you can make changes to instances regardless of instance family, size, Availability Zone, Region, operating system, or tenancy. Therefore, if the project is relocated from the Ireland Region to the United States Region, your Savings Plans instances let you make that change. Also, if the workload is moved from Amazon EC2 to Lambda, with Saving Plans instances, you can switch to Lambda at the Savings Plans costs.

+	####	Amazon EC2 purchasing options scenario 2

	**<p align="center">What is your solution?</p>**
	
	_You need an inexpensive computing resource to handle a batch processing task. No immediate timeline currently exists for when the work should be done, and it can be interrupted and resumed later if needed. Which EC2 instance purchasing option would you choose?_

	> **<p align="center">Solution</p>**
	> The best solution for this scenario would be Spot Instances. Spot Instances offer discounts up to 90 percent off of what On-Demand Instances offer. Spot Instances are ideal for workloads that have a small budget and when the work can be interrupted and finished later.

+	####	Amazon EC2 purchasing options scenario 3

	**<p align="center">What is your solution?</p>**

	_You need a computing solution for a project that will go on for over a year. The computing resources will be steady throughout the year. However, workloads might spike for a month or two, and you will temporarily need additional computing resources._

	> **<p align="center">Solution</p>**
	> In this scenario, you would use two purchasing options. To handle the steady workload, you can use either Reserved Instances or EC2 Compute Savings Plans. Both offer a savings of up to 72 percent; however, EC2 Compute Savings Plans offer more flexibility for the same price. So, choosing EC2 Compute Savings Plans instead of Reserved Instances would make a better choice.
	> To handle the spike in workload, On-Demand Instances should be used. On-Demand Instances are purpose-built to handle an increase in workloads and then terminate the instances when the spike in the workload decreases.

+	####	Tenancy	

	Tenancy defines how EC2 instances are distributed across the physical host hardware.
	Amazon EC2 offers three tenancy options for hosting our instances. They are shared tenancy, dedicated instances,and dedicated hosts. The tenancy that we choose will affect pricing.

	<p align="center">
	<img src="assets/Tenancy_offers.png" alt="Tenancy Offers"  width="100%" height="100%">
	</p>

+	####	Comparing tenancies

	**<p align="center">Tenancy use cases</p>**
	
	<table>
	<thead>
	<tr>
	<th>Dedicated Host</th>
	<th>Dedicated Instance</th>
	<th>Shared Tenancy</th>
	</tr>
	</thead>
	<tbody>
	<tr>
	<td>Regulatory compliance that requires <i><b>hosts cannot be shared</b></i> between AWS accounts.</td>
	<td>Regulatory compliance that requires <i><b>hosts cannot be shared</b></i> between AWS accounts.</td>
	<td>Regulatory compliance <i><b>is not</b></i> required</td>
	</tr>
	
	<tr>
	<td>Managing the host hardware <i><b>is</b><i> required.</td>
	<td>Managing the host hardware <i><b>is not</b></i> required.</td>
	<td>Development and testing accounts.</td>
	</tr>
	
	<tr>
	<td>When you <i><b>will need enough</b></i> or close to enough dedicated instances to fill a host.</td>
	<td>When you <i><b>do  not need</b></i>enough dedicated instances to fill a host.</td>
	<td></td>
	</tr>
	
	
	<tr>
	<td>Using <i><b>existing</b></i> per-socket, per-core, or per-VM software licenses that are <i><b>bound</b></i> to VMs, sockets, or physical cores, subject to our license terms.</td>
	<td></td>
	<td></td>
	</tr>
	
	</tbody>
	</table>
	
	> _**Note:** A host contains approximately 22 instances._

+	####	Introduction to Amazon EC2 Summary

	<p align="center">
	<img src="assets/Introduction_to_Amazon_EC2_Summary.png" alt="Introduction to Amazon EC2 Summary"  width="100%" height="100%">
	</p>

	<p align="center">
	<b><i>Introduction to Amazon EC2 Summary
	</i></b></p>

###	Using Amazon EC2

+	####	Using Amazon EC2

In this section, we will learn about the seven steps to launch an EC2 instance. We will also learn about configuration for each step. Finally, we will learn that understanding how the instance will be used help to guide us in making good  configuration choices.

<p align="center">
<img src="assets/Using_Amazon_EC2.png" alt="Using_Amazon_EC2"  width="100%" height="100%">
</p>

<p align="center">
<b><i>Using Amazon EC2</i></b>
</p>


+	####	Steps to launching an instance

	This section walks through **seven key decisions** to make when you use the AWS Management Console **Launch Instance Wizard** to create an EC2 instance.
	+	Along the way, we will explore essential Amazon EC2 concepts. In this section of the module, we will  be introduced to the configuration choices that we can make when we launch an instance. These choice include making decisions on _instance names and tags, AMIs, Instance types, key pairs, network settings, storage configurations, and advanced details_.

	[<img src="assets/Steps_to_launching_an_EC2_instance_2.png" alt="Steps_to_launching_an_EC2_instance_2" align="left" width="50%" height="100%">]()[<img src="assets/Steps_to_launching_an_EC2_instance.png" alt="Steps_to_launching_an_EC2_instance" align="left" width="50%" height="100%">]()
	
	<p align="center">
	<b>Steps to launching an instance & Demo</b>
	</p>

+	####	Step 1. Using tags

	The first step in creating an instance is assigning it a name and tags. This steps is optional but recommended. The name of an instance is default tag for the instance name and works like every other tag. Tag work as metadata  to identify and define the AWS resources that they are attached to. Each tag is a label that consists of a customer-defined key and an optional value that can simplify managing, searching for, and filtering resources. Although there are no inherent types of tags, customer can use them to categorize resources by purpose, owner, environment, or other criteria.

	<p align="center">
	<img src="assets/Step1_Using_tags.png" alt="Step1_Using_tags" width="80%" height="100%">
	</p>

+	####	Tag features

	After we have created our instances, we can manage our tags and use them to filter and search for resources by tag.

	<table>
	<tr>
	<th>Manage</th>
	<th>Search and filter</th>
	</tr>

	<tr>
	<td>
	<p align="center"><br>
	<img src="assets/Manage.png" alt="Manage" width="200px" height="100%">
	</p>
	</td>
	<td>
	<p align="center"><br>
	<img src="assets/Search_and_filter.png" alt="Search and filter" width="200px" height="100%">
	</p>
	</td>
	</tr>

	<tr>
	<td>Add, remove or edit tags.</td>
	<td>Search for resources by key or by value.</td>
	</tr>

	<tr>
	<td>The tag limit per Amazon EC2 resources is 50 tags.</td>
	<td rowspan="2">Filter and search for resources by a combination of tag keys and values.</td>
	</tr>
	<tr>
	<td>Naming and tagging resources is optional</td>
	</tr>
	
	</table>

+	####	Benefits of using tags

	+	#####	Resource organization

		Tags are a good way to organize AWS resources in the AWS Management Console. You can configure tags to be displayed with resources, and we can search and filter by tag. With the AWS Resource Groups service, we can create groups of AWS resources based on one or more tags or portions of tags. Using Resource Groups and Tag Editor, we can consolidate and view data for applications that consist of multiple services, resources, and Regions in one place.

	+	#####	Cost Management

		We can use AWS Cost Explorer and detailed billing reports to break down AWS costs by tag. Typically, we use business tags such as cost center, business unit, customer, or project to associate AWS costs with traditional cost-allocation dimensions. But a cost allocation report can include any tag. The following table is an example of a partial cost allocation report.

	+	#####	Automation
	
		Resource-specific or service-specific tags are often used to filter resources during automation activities. Automation tags are used to opt in or opt out of automated tasks or to identify specific versions of resources to archive, update, or delete.
		For example, we can run automated start or stop scripts that turn off development environments during non business hours to reduce costs. In this scenario, EC2 instance tags are a simple way to identify instances to opt out of this action. For scripts that find and delete stale, out-of-date, or rolling Amazon EBS snapshots, snapshot tags can add an extra dimension of search criteria.

	+	#####	Access control

		AWS Identity and Access Management (IAM) provides fine-grained access control across all of AWS. With IAM, we can specify who can access which services and resources, and under which conditions. Using IAM, we can use tagged resources to implement attribute-based control (ABAC). We can create IAM policies that allow operations based on tag information to control access. ABAC helps provide better control over which resources a user can modify, use, or delete.
		For example, we can create an IAM policy that allows users to terminate an instance but denies the action if the instance has the tag environment-production.

+	####	Step 2. Choosing an Amazon Machine Image

	An AMI is required when launching an EC2 instance. The AMI has three main components. They are as follows:
	
	+	**Templates for the root volumes** of the instance contain:
		+	Operating System (OS)
		+	Application servers
		+	Application
		
	+	**Launch permissions** control which AWS accounts can use the AMI.
	
	+	**Block device mapping** specifies the volumes to attach to the instance (if any) when it is launched.

+	####	Using AMIs

	+	Choose an AMI that fits the use case of your instance.
	+	Use the same AMI to launch multiple instances that should have the same configuration.
	+	If instances have different use cases, use AMIs that are specific to the use cases of each instance.
	
	Therefore, before choosing the AMI that we will create our instance from, it is important to fully understand the use case of the instance.

+	####	Where do you get an AMI?

	We can use Amazon's pre-built AMIs,purchase them from the Amazon Market place, Create your own, or get them from  the Community AMI pool.

	+	**Pre-built:** Amazon offers a number of pre-built AMIs to launch our instances. These AMIs include Linux and Windows options, with various  sub-options to tailor our setup.
	
	+	**AWS Marketplace:** The AWS Marketplace offers a digital catalog with thousands of software solutions listed. These AMIs can offer specific  use cases to help us get started quickly.
	
	+	**Create your own:** An AMI is an anonymized, block-level copy of the root volume of a _donor machine or golden instance_. It is a virtual machine (VM) that you've configured with the specific OS and application content that you want placed on the AMI. When you create an AMI, Amazon EC2 stops the instance, snapshots its root volume, and finally registers the snapshot as an AMI.
	
	+	**Community AMIs:** People all over the globe create community AMIs. These AMIs are not vetted by AWS and are used at your own risk. These AMIs can offer many different solutions to various problems, but use them with great care. They should be thoroughly reviewed for security concerns when using them in any production or corporate environment.

+	####	AMI benefits


	AMIs are a required element to creating our EC2 instance, and like most AWS service features, they  come with many benefits.
	
	+	#####	Repeatability

		Instances that are launched from the same AMI are exact replicas of one another. As a result, it greatly facilitates building clusters of similar instances or recreating compute environments.
		
	+	#####	Reusability
	
		AMIs package the full configuration  and content of an EC2 instance such that it can be used over and over again, with efficiency and precision.
		
	+	#####	Recoverability
	
		An AMI is perfect for replacing failed machines with new instances that are created from the same AMI.
		
	+	#####	Marketplace Solutions
	
		Suppose that you are looking for a software solution from a specific vendor. An AMI probably exists on the marketplace that you can launch to implement that solution on an EC2 instance. Additionally, authorized software vendors can create AMIs and also sell them there.
		
	+	#####	Backups
	
		AMIs provide a great way to back up a complete EC2 instance configuration, which we can use to launch a replacement instance in the event of a failure.

+	####	Step 3. Instance types

	The instance type specifies the hardware of the host computer that's used for our instance, such as CPU, memory, storage, and networking capacity.
	Amazon EC2 provides a selection of instance types that these components optimize to fit different use cases. We select the appropriate instance type based on the requirements of the application or software that we plan to run on our instance.

	[<img src="assets/Step3_Instance_types.png" alt="Step3_Instance_types" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>Instance Types</b>
	</p>

+	####	Instance families

	Each instance type belongs to an family. An instance family is a group of instances, with varying configurations, that are based on similar compute, memory, and storage capabilities. Within each family, instance types have specific names. For example, the T family has specific instance types such as t2.micro and t3.large.

	[<img src="assets/Instances_families.png" alt="Instance families" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>Instance Families</b>
	</p>

+	####	Instance types names
	When you look at a specific instance type, we will see that its name has several parts.

	[<img src="assets/Instance_types_names.png" alt="Instance types names" align="left" width="100%" height="100%">]()

+	####	Instance Categories

	Depending on the use case of our EC2 instance, we have a variety of instance categories to choose from.

	[<img src="assets/Instance_categories.png" alt="Instance_categories" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>Instance Categories</b>
	</p>

	+	#####	General Purpose
		[<img src="assets/General_purpose.png" alt="General_purpose" align="" width="100%" height="100%">]()

	+	#####	Compute Optimize
		[<img src="assets/Compute_optimized.png" alt="Compute_optimized" align="" width="100%" height="100%">]()

	+	#####	Memory optimized
		[<img src="assets/Memory_optimized.png" alt="Memory_optimized" align="" width="100%" height="100%">]()

	+	#####	Accelerated computing
		[<img src="assets/Accelerated_computing.png" alt="Accelerated_computing" align="" width="100%" height="100%">]()

	+	#####	Storage optimized
		[<img src="assets/Storage_optimized.png" alt="Storage_optimized" align="" width="100%" height="100%">]()

+	####	Scaling instances vertically

	Unlike the instance's AMI, the instance type can be changed after the instance is launched. Thus, we have the option to scale our instances by changing our instance type to give it more compute power. This kind of expansion is called vertical scaling.
	Vertical scaling _(scaling for more compute power per instance)_ gives us the ability to do the following:
	+	Scale up or down for CPU.
	+	Switch to any instance type in any instance family.

+	####	Step 4. Key pairs

	At instance launch, you can specify an existing key pair, create a new key pair, or choose not to use a key pair for this instance. A key pair cannot be added to the instance after it is launched.

	A key pair consists of the following:
	+	A **public key** that AWS stores
	+	A **private key** file that you store

	[<img src="assets/Step4_Key_pairs.png" alt="Step 4. Key pairs" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>Key Pairs</b>
	</p>

+	####	Connecting to your instance with your key pair

	We can use a key pair to securely connect to the instance.
	
	**Windows AMIs** use the private key to obtain the administrator password that we need to log in to our instance through Remote Desktop Protocol (RDP).
	
	**Linux AMIs** use the private key to use Secure Shell (SSH) to securely connect to our instance.

+	####	Step 5. Network settings

	[<img src="assets/Step5_Network_setting.png" alt="Step 5. Network settings" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>Network Settings</b>
	</p>

+	####	Regions

	Choosing the region to launch our **_EC2 instance_** in is not a network configuration setting in the Amazon EC2 launch wizard. The Region is assumed based on the Region that we are working on our AWS Management Console.

	[<img src="assets/Regions.png" alt="Regions" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>Regions</b>
	</p>

+	####	VPCs and Subnets

	When we start using  **_Amazon VPC_**, we have a default VPC in each AWS Region. A default VPC comes with a public subnet in each Availability Zone of the Region. Therefore we can immediately start launching Amazon EC2 instances into a default VPC. 

	[<img src="assets/VPCs_and_subnets.png" alt="VPCs_and_subnets" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>VPCs and subnets</b>
	</p>
	
	**_In this example_**, we have three Regions: the Northern Virginia Region, the London Region, and the Tokyo Region. Now, take a closer look at the Northern Virginia Region. The Northern Virginia Region has six public subnets, one for each of its six Availability Zones. We can create more public subnets in our defaults VPC, and we can even create and customize additional VPCs in any Region.

	[<img src="assets/VPCs_and_subnets_custom.png" alt="VPCs_and_subnets_custom.png" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>VPCs and subnets custom</b>
	</p>

+	####	Public IP address

	[<img src="assets/Public_IP_address.png" alt="Public_IP_address.png" align="left" width="100%" height="100%">]()
	<p align="center">
	<b>Public IP address</b>
	</p>

+	####	Public IP

	Depending on the situation, a public address might or might not be auto-assigned to our EC2 instance.

	+	#####	Default VPC - default subnet

		By default, the **Auto-assign public IP** setting is set to enabled when we launce an instance in default subnet in the default VPC. However, when launching our instance, we can choose to disable the auto-assignment of the public IP address if we want to.

		<p align="center">
		<img src="assets/Default_VPC-default_subnet.png" alt="Default_VPC-default_subnet.png" width="250px" height="180px">
		</p>
		<p align="center">
		<b>Default VPC-default subnet</b>
		</p>
	
	+	#####	Default VPC - custom subnet

		We have the option to create additional subnets in our default VPC. If we launch our EC2 into a non-default subnet of the default VPC, then the **Auto-assign public IP** setting will be disabled by default. However, we can choose to change it from disabled to enabled.

		<p align="center">
		<img src="assets/Default_VPC-custom_subnet.png" alt="Default_VPC-default_subnet.png" width="250px" height="180px">
		</p>
		<p align="center">
		<b>Default VPC-custom subnet</b>
		</p>

	+	#####	Custom VPC - custom subnet

	    We can also create additional VPCs. If we launch our EC2 into a non-default VPC, then the **Auto-assign public IP** setting will be disabled by default. However, we can choose to change it from disabled to enabled.

		<p align="center">
		<img src="assets/Custom_VPC-custom_subnet.png" alt="Custom_VPC-custom_subnet.png" width="250px" height="180px">
		</p>
		<p align="center">
		<b>Custom VPC-custom subnet</b>
		</p>

+	####	Security groups

	<p align="center">
	<img src="assets/Security_groups.png" alt="Security_groups.png" width="100%" height="100%">
	</p>
	<p align="center">
	<b>Security groups</b>
	</p>

+	####	Rule components

	Internet protocols are different ways that computers and other services on the internet can send information to each other. When we configure a security group's rules, there are four main components: _**type, protocol, port range, and source**_.

	<p align="center">
	<img src="assets/Rule_components.png" alt="Rule_components.png" width="100%" height="100%">
	</p>
	<p align="center">
	<b>Rule components</b>
	</p>

	+	#####	Type

		The type is where we choose the specific type of protocol to open to network traffic. We can choose a common protocol, such as SSH (for a Linux instance), RDP (for a Windows instance), and HTTP and HTTPS to allow internet traffic to reach our instance.

	+	#####	Protocol

		Internet protocols are different ways that computers and other services on the internet can send information to each other. The protocol section shows the protocol to allow for the protocol type. The most common protocols are 6 (TCP), 17 (User Datagram Protocol or UDP), and 1 (Internet Control Message Protocol, or ICMP).

	+	#####	Port Range

		The port range verifies the ports that are allowed to pass traffic for each protocol type. We can specify a single port number (for example, 22), or range of port numbers (for example, 7000-8000).

	+	#####	Source

		The source is where we choose the source (inbound rules) or destination (outbound rules) for the traffic to reach. This option determines the traffic that can reach your instance. We can specify a single IP address, or a range of IP addresses. If the instance is hosting a web page, we can leave it open to all traffic on HTTP.

+	####	Inbound and Outbound rules

	Security group rules are divided into two categories:

	+	#####	Inbound rules
		
		[<img src="assets/Inbound_rules.png" alt="Inbound_rules.png" align="left" width="200px" height="120px">]()
	
		When we create a security group, it has **no inbound rules**. Therefore, no inbound traffic that originates from another host to our instance is allowed until we add inbound rules to the security group.

		In this example, the instance has a security group that is allowing SSH access to the instance, from a source IP 203.0.113.5/32. However, it is not allowing SSH access from any other IP, and it is not allowing any HTTP access.

		<p align="center">
		<img src="assets/Inbound_rules1.png" alt="Inbound_rules1.png"  width="500px" height="150px">
		</p>
		<p align="center">
		<b>Inbound rules</b>
		</p>

	+	#####	Outbound rules

		[<img src="assets/Outbound_rules.png" alt="Outbound_rules.png" align="left" width="200px" height="120px">]()

		By default, a security group includes an outbound rule that **allows all outbound traffic**. We can remove the rule and add outbound rules that allow specific outbound traffic only.
		If your security group has no outbound rules, no outbound traffic that **originates** from our instance is allowed.
		In this example, the security group is configured to allow outbound rules for SSH to a specific IP address but doesn't allow outbound access for HTTP.
		
		<p align="center">
		<img src="assets/Outbound_rules1.png" alt="Outbound_rules1.png"  width="500px" height="180px">
		</p>
		<p align="center">
		<b>Outbound rules</b>
		</p>

+	####	Security groups' stateful attributes

	<p align="center">
	<img src="assets/Security_groups_stateful_attributes.png" alt="Security_groups_stateful_attributes"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Security groups' stateful attributes</b>
	</p>

+	####	Managing security groups

	<p align="center">
	<img src="assets/Managing_security_groups.png" alt="Managing_security_groups"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Managing security groups</b>
	</p>

	+	Security groups act at the instance level, not the subnet level.
	+	Instances in the same subnet can be assigned to a different security group.
	+	We can attach more than one security group to an instance. 
		+	Instance-specific security groups are recommended.
	+	All the rules from all the security groups that are attached to an instance are evaluated before traffic is allowed to pass through.

+	####	Step 6. Configure storage

	[<img src="assets/Step6_Configure_storage.png" alt="Step6_Configure_storage" align="right"  width="200px" height="100%">]()

	The main solution for EC2 instance storage is Amazon Elastic Block Store, or Amazon EBS.
	
	**Amazon Elastic Block Store (Amazon EBS)** is a durable, detachable, high-performance block-storage service designed for Amazon EC2.
	+	Works like an external hard drive
	+	Can provide low latency
	+	Able to handle almost any computing requirements

+	####	EBS volume types

	Amazon EBS provides multiple volume types that we can use optimize storage performance and cost for a broad range of applications.
	
	>These volumes types are divided into two major categories:
	>><b>a.)	Solid State Drives (SSDs)</b>
	>><b>b.)	Hard Disk Drives (HDDs)</b>
	
	**SSDs** are for transactional workloads, such as databases, virtual desktops, and boot volumes, and **HDDs** are for throughput-intensive workloads, such as MapReduce and log processing.

	<p align="center">
	<img src="assets/EBS_volume_types.png" alt="EBS_volume_types.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>EBS volume types</b>
	</p>

	+	#####	Solid State Drives (SSDs)
		+	######	General purpose

			General purpose is an SSD volume that balances price and performance for a wide variety of workloads.
			Its use cases include the following:
			+	Recommended for most workloads
			+	Virtual desktops
			+	Medium-sized single instance databases such as Microsoft SQL Server and Oracle
			+	Latency-sensitive interactive applications
			+	Boot volumes
			+	Development and test environments
			
		+	######	Provisioned IOPS

			<b>Input/Output Operations per Second (IOPS)</b> measures the number of maximum reads and writes that a computing storage device can perform in a second. Provisioned IOPS are the highest-performance SSD volumes for mission-critical low-latency or high-throughput workloads. With these volumes, customers can meet the IOPS and throughput requirements of their most intensive business-critical applications.
			
			Its use cases include the following:
			+	Critical business applications that require sustained IOPS performance
			+	Large database workloads

	+	#####	Hard Disk Drives (HDDs)
		+	######	Throughput Optimized

			Throughput Optimized is a low-cost HDD volume designed for frequently accessed, throughput-intensive workloads.
			Its use cases include the following:
			+	Streaming workloads
			+	Big data
			+	Data warehouses
			+	Log processing
			+	Cannot be a boot volume

		+	######	Cold

			Cold HDD is the lowest cost HDD volume and is designed for less frequently accessed workloads.
			Its use cases include the following:
			+	Throughput-oriented storage for large volumes of data that is infrequently accessed
			+	Scenarios where the lowest storage cost is important
			+	Cannot be a boot volume

+	####	Amazon EBS storage configuration options
	When configuring EBS storage configuration options, we have several options.

	<p align="center">
	<img src="assets/Amazon_EBS_storage_configuration_options.png" alt="Amazon_EBS_storage_configuration_options.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Amazon EBS storage configuration options</b>
	</p>

	+	#####	Volume types

		When choosing a volume type, you cannot use Throughput Optimized or Cold HDD volumes for root volumes. The root volume must be a general purpose or a Provisioned IOPs volume. You can add additional volumes (non-root volumes) to your instance and mix and match any types with other volume types as needed.

	+	#####	Volume size

		The size of the volume is chosen in GiB. If you are creating the volume from a snapshot, then the size of the volume cannot be smaller than the size of the snapshot.
		
		Supported volume sizes are as follows: 
		<i>
		+	General purpose volumes: <b>1 GiB to 16,384 GiB</b>
		+	Provisioned IOPS: <b>4 GiB to 16,384 GiB</b>
		+	Throughput Optimized or Cold HHD: <b>125 GiB to 16,384 GiB</b>
		</i>

	+	#####	Delete on termination

		Delete on termination indicates whether the volume should be automatically deleted when the instance is terminated. If we disable this delete on termination, then the volume will persist independently from the running life of an EC2 instance. As a result, the volume will remain provisioned in our account until we delete it manually.
		We can also change the delete on termination behavior after the instance has been launched.

	+	#####	Encryption

		Amazon EBS encryption is an encryption solution for our EBS volumes. We have the option to encrypt our root volume and any additional volumes that you attach to your EC2 instance. Amazon EBS encryption uses AWS Key Management Service (AWS KMS) keys to encrypt volumes. AWS KMS is a security service that lets we create and manage cryptographic keys and control their use across a wide range of AWS services.

+	####	Adding a file system

	Amazon Elastic File System (Amazon EFS) is a system that we can use to share files among multiple EC2 instances. It automatically grows and shrinks as we add and remove files with no need for management or provisioning.
	We can attach instances to the file system as you launch our instance or afterwards.
	We can remove instances from the file system without losing any files stored on Amazon EFS.
	Amazon EFS cannot act as a root volume. Each instance that is attached to Amazon EFS must have its own root volume.

	<p align="center">
	<img src="assets/Adding_a_file_system.png" alt="Adding_a_file_system.png"  width="200px" height="100%">
	</p>
	<p align="center">
	<b>Adding a file system</b>
	</p>

+	####	Amazon EC2 instance store

	An instance store provides temporary block-level storage for your instance. This storage is located on disks that are physically attached to the host computer. An instance store is ideal for temporary storage of information that changes frequently, such as buffers, caches, scratch data, and other temporary content.

	<p align="center">
	<img src="assets/Amazon_EC2_instance_store.png" alt="Amazon_EC2_instance_store.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Amazon EC2 instance store</b>
	</p>

	+	#####	Persistent volumes

		Instance store volumes are not persistent storage. If our instance is (on purpose or system failure) stopped, hibernated, or terminated, we will loose all of our date on the volume.

	+	#####	Limited availability

		Instance store volumes have limited availability because the are only optional for a certain combination of AMIs and instance types. When selecting an AMIs that offer instance store volumes.

	+	#####	Add volumes

		We can specify instance store volumes for an instance only when we launch. After the instance is launched, we can add EBS volumes to the instance but not instance store volumes.

	+	#####	Detach volumes

		An instance store volume's disks are physically attached to the instance. Therefore, we cannot detach an instance store volume from one instance and attach it to a different instance. AWS does not offer you the option to detach the volume.

	+	#####	Configure volumes

		Instance store volumes are not configurable. The instance type that we choose predetermines the volume type (SSD or HDD) and size. These configurations are not optional. We also cannot encrypt these volumes.

+	####	Amazon EC2 instance store compared to Amazon EBS
	

	https://github.com/Sailesh-Singh/Cloud-Practitioner/assets/58818777/b019f3d2-5053-4f45-88c5-bcfa118f7a70


+	####	Step 7. Advance details
	An IAM role is an IAM identity that we can create in our account that has specific permissions. Roles can be granted temporary credentials that have a more restricted set of permissions than your standard IAm user.

	<p align="center">
	<img src="assets/Step7_advanced_details.png" alt="Step7_advanced_details.png"  width="350px" height="100%">
	</p>
	<p align="center">
	<b>Advance details</b>
	</p>

	+	#####	IAM Identities

		An IAM identity represents a user, and can be authenticated and then authorized to perform actions in AWS.

	+	#####	Assumable access
		To assume a role, the user must meet the requirements outline in the IAM policy. Role access can be granted to IAM users or federated users.

	+	#####	Permission policies
		Policies determine which actions an identity can perform, on which AWS resources, and under which conditions.

	+	#####	Temporary credentials
		Temporary credentials have a more restricted set of permissions than the standard IAM user, and they expire automatically after a set period of time.


+	####	Using IAM roles with AWS services

	EC2 instances often run applications that must make secure API calls to other AWS services. Roles can be used to give instances permissions to access other AWS services to overcome security risks.

	<p align="center">
	<img src="assets/Using_IAM_roles_with_AWS_services.png" alt="Using_IAM_roles_with_AWS_services.png"  width="350px" height="100%">
	</p>
	<p align="center">
	<b>Using IAM roles with AWS services</b>
	</p>

	+	#####	Security risk
		Placing AWS credentials on an EC2 instance to give it permission to make secure API calls to other AWS services is highly insecure.

	+	#####	Security solution
		Attach an IAM role to the EC2 instance that grants permission to make API requests to other services.

+	####	Managing roles
	An instance profile is a container for an IAM role. From the instance profile, we can select a role to associate with the instance.

	<p align="center">
	<img src="assets/Managing_roles.png" alt="Managing_roles.png"  width="350px" height="100%">
	</p>
	<p align="center">
	<b>Managing roles</b>
	</p>

+	####	User data
	When we create our EC2 instances, we have the option of passing user data to the instance.
	
    **User data**

	+	Optionally, specify a user data script at instance launch.
	+	Use user data scripts to customize the runtime environment of your instance.
	
		+	A script runs the first time the instance starts by default.

		+	A script can be configured to run every time the instance starts.
		
	+	These scripts can do the following:
	
		+	Patch and update the instance AMI.
		+	Fetch and install software license keys.
		+	Install additional software.
		+	and more...

	Example of a user data script
	
	+	`#!/bin/bash`<br>
		This command is called a _shebang_ line. This line selects the  interpreter of the script executions, which is required on the first line for our script to work.
		<br>
	
	+	`yum update -y`<br>
		This command updates all the packages on our instance.
		<br>
	
	+	`yum install httpd -y`<br>
		This command installs the most recent Apache HTTP server program on our instance.
		<br>
	
	+	`service httpd start`<br>
		This command starts our Apache server program. Now it is not only  installed on our instance. It is also running on our instance.
		<br>
	
	+	`chkconfig httpd on`<br>
		This command configures our instance to automatically start the Apache server program for each reboot of the instance.

+	####	Additional advance settings options

	+	#####	Request Spot instances
		We can request Spot Instances at the Spot price, which are capped off at the On-Demand price. Remember that Spot Instances are for workloads that can be interrupted. Requesting Spot Instances can affect pricing because they are cheaper than On-Demand Instances.

	+	#####	Shutdown behavior
		The shutdown behavior setting affects how the instance behaves when an OS-level shutdown is performed. Instances can be either terminated or stopped. If no value is specified, the value of the AMI will still be used.
	+	#####	Termination protection
		If **termination protection** is enabled, the instance cannot be terminated by using the console, API, or CLI until termination protection is disabled. If no value is specified, the value of the source AMI will still be used.

	+	#####	Detailed monitoring
		Amazon CloudWatch is a monitoring service that provides you with data and actionable insights to monitor our applications. It is continually monitoring, collecting, and analyzing metrics about our instances. It updates our metrics dashboard every 5 minutes, without any additional charges. If detailed monitoring is enabled, CloudWatch updates metrics to our monitoring dashboards every minute. Additional charges will apply if it is enabled. If no value is specified, the value of the source AMI will still be used.

	+	#####	Tenancy
		We'll recall that in the previous section of the course, we learned about dedicated tenancy. At this point, we can make that choice to have it enabled or disabled. Dedicated tenancy instances run on single-tenant, dedicated hardware. Host tenancy instances run on a dedicated host. If we select dedicated tenancy or dedicated host, our costs will be increased for our instance. We'll have no additional charge for running our instance on shared hardware. If no value is specified, the value of the source AMI will still be used.

+	####	Configuration considerations

	<p align="center">
	<img src="assets/Configuration_considerations.png" alt="Configuration_considerations.png"  width="350px" height="100%">
	</p>
	<p align="center">
	<b>Configuration considerations</b>
	</p>

	Keep in mind the following considerations to help you make good decisions when launching our instance

+	#####	Have no default setting
	+	Key Pair
	
+	#####	Affect costs
	+	Amazon Machine Image
	+	Instance type
	+	Configuration storage
	+	Advanced details
	+	Regions
	
+	#####	Cannot be modified after instance launch
	+	Amazon Machine
	+	Image
	+	Key Pair
	+	Network settings
		+	VPC
		+	Subnet
	+	Region
		
+	#####	Can be modified after instance launch
	+	Name and tags
	+	Instance type
	+	Networking settings
		+	IP address
		+	Security groups
	+	Storage
	+	Advance details
		+	Adding a role
		+	User data scripts

+	####	Putting it all together

	<p align="center">
	<img src="assets/Putting_it_all_together.png" alt="Putting_it_all_together.png"  width="350px" height="100%">
	</p>
	<p align="center">
	<b>Putting it all together</b>
	</p>

+	####	Activity: Configuring an instance based on the use case

	+	#####	Scenario

		Your manager has asked you to create an EC2 instance that will host a dynamic website. After asking your manager more specific questions, you learn the following:
		
		+	The website should be available to everyone on the web, but the primary customer target is on the east coast of the United States.
		
		+	The instance that is hosting the website should have a Windows operating system.
		
		+	The application should be launched with the most recent patches and updates.
		
		+	The instance will need to have an administrator update patches from time to time.
		
		+	The instance must be protected from accidentally being terminated.
		
		+	The application will need to access Amazon S3.
		
		+	The instance's resources should be reportable for costs
		
		+	The costs to run the instance should be kept as low as possible.

	+	#####	Name and tags

		+	######	Requirements to consider:
			+	The instance's resources should be reportable for costs.
			+	The costs to run the instance should be kept as low as possible.

		To help track the costs of the instance, tags should be used. You can run reports based on tags to gain insight into the monthly costs of this particular instance.

		<p align="center">
		<img src="assets/Activity_Name_and_tags.png" alt="Activity_Name_and_tags.png"  width="350px" height="100%">
		</p>
		<p align="center">
		<b>Name and tags</b>
		</p>
		
	+	#####	AMI

		+	######	Requirements to consider:
			
			+	The instance that is hosting the website should have a Windows operating system.
			
			+	The costs to run the instance should be kept as low as possible.

		An **AMI** should be chosen that is packaged with **Windows** as the operating system. Also, you should give careful consideration for any other software that might be needed when choosing your AMI. Your manager said to keep costs as low as possible. However, you don't want the performance of your website to suffer in order to keep costs low. Remember that AMIs cannot be switched out. If you later find that you need a more advanced AMI, you will need to create a new instance.

		+	######	Amazon Machine Image components:

			+	A template for the root volume 
			+	Launch permissions
			+	A block device mapping

	+	#####	Instance type

		+	######	Requirements to consider:
			+	The website should be available to everyone on the web, but the primary customer target is on the east coast of the United States.

			+	The costs to run the instance should be kept as low as possible.

		The instance is going to be used to host a website, and cost is a factor. Therefore, the most cost-effective instance type for a web server is one of the families in the **general purpose** category. Remember that instance types can be changed. You can scale up or scale down as needed. For example, you might start with an instance in the T3 family, and scale up if you need more CPU.

		<table>
			<tr>
				<th>Instance</th>
				<td>A1, M4, M5, T2, T3</td>
			</tr>
			<tr>
				<th>UseCase</th>
				<td>These instances are ideal for applications that use these resources in equal proportions such as web servers and code repositories.</td>
			</tr>
		</table>

	+	#####	Key pair

		+	######	Requirements to consider:
			+	The instance will need to have an administrator update patches from time to time.

		Because the instance will need to have an administrator update patches from time to time, the instance should be created with a key pair. You can either create a new key pair or use an existing key pair. The administrator who is making the updates should have access to this key pair.

		A key consists of the following:
		+	A **public key** that AWS stores
		+	A **private key** file that we store

	+	#####	Network setting

		<p align="">
		<img src="assets/Activity_Network_settings.png" alt="Activity_Network_settings.png"  align="right" width="150px" height="220px">
		</p>

		+	######	Requirements to consider:
			+	The instance that is hosting the website should have a Windows operating system.

			+	The website should be available to everyone on the web, but the primary customer target is on the east coast of the United States.

		The website will be primarily targeting customers on the east coast of the United States. Therefore, the best Region to launch our instance in is the **N. Virginia Region**. We should be sure that the **VPC** and **subnet** that we place our instance in are configured for internet access. Also, a **public IP address** should be assigned to the instance.

		The **security group** should have inbound rules that allow for the following:

		+	Internet (HTTP/HTTPS) traffic for the public website to be accessible to the internet.

		+	Remote desktop protocol (RDP) traffic for an administrator to log in for patching and updating the instance. If the instance had a Linux OS, then you would use SSH instead.

	+	#####	Storage configurations

		+	######	Requirements to consider:
			+	The website should be available to everyone on the web, but the primary customer target is on the east coast of the United States.

			+	The costs to run the instance should be kept as low as possible.

		A **general purpose EBS volume** would make the best choice for this workload. A provisioned IOPS volume is over-resourcing and will cost us more than we need to spend. If the website was hosting a critical business website with a large database, then a provisioned IOPS volume could be the right solution. We can always scale to meet the needs of our storage.

		+	######	Amazon EBS capabilities
			+	Run databases
			+	Host applications
			+	Handle most storage computing needs

	+	#####	Advanced details

		+	######	Requirements to consider:
			+	The instance must have an administrator update patches from time to time.

			+	The application must be protected from accidentally being terminated.

			+	The application will need to access Amazon S3

		Because the application must access Amazon S3, we should attach an **IAM role** to the instance that has sufficient permissions to perform the required tasks.

		To protect the instance from accidental termination, enable **termination protection**.

		To update and patch the instance when it is launched, add the appropriate script to the **user data** field.

+	####	Using Amazon EC2 summary

	<p align="center">
	<img src="assets/Using_Amazon_EC2_summary.png" alt="Using_Amazon_EC2_summary.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Using Amazon EC2 summary</b>
	</p>


### Managing EC2

+	####	Managing Amazon EC2

	<p align="center">
	<img src="assets/Managing_Amazon_EC2.png" alt="Managing_Amazon_EC2.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Managing Amazon EC2</b>
	</p>

+	####	Options for launching EC2 instances

	AWS offers four main methods for launching an EC2 instance. We can use the AWS Management Console, the AWS Command Line Interface (AWS CLI), or AWS SDKs, or we can launch instances through other AWS services.

	<p align="center">
	<img src="assets/Option_for_launching_EC2_instances.png" alt="Option_for_launching_EC2_instances.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Options for launching EC2 instances</b>
	</p>

	+	#####	AWS Management Console
		The AWS management Console is a graphical user interface that we can use to launch, configure, and manage AWS services.
		
	+	#####	AWS Command Line Interface (AWS CLI)
		The AWS CLI is a unified tool to manage our AWS services. With only one tool to download and configure, we can provision and control multiple AWS services from the command line and automate them through scripts.
		
	+	#####	AWS Software Development Kit (SDK)
		SDKs take the complexity out of coding by providing language-specific APIs AWS services. With AWS SDKs, we can launch AWS services, like EC2 instances, by using a variety of codes such as JavaScript, Python, Java, .NET, C++, and more.
		
	+	#####	Through other AWS services
		AWS has some services such as AWS CloudFormation, AWS OpsWorks, and AWS Elastic Beanstalk that can be used to launch multiple resources at the same time. Typically, we would consider using these services to launch EC2 instances when they are part of bigger infrastructure or application.

+	####	Amazon EC2 lifecycle states

| **Instance State**  | Description                                                                                                                                                                            | Instance Usage Billing                                           |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| **Pending**         | The instance is preparing to enter the running state. An instance enters the pending state when it launches for the first time or when it is started after being in the stopped state. | Not billed                                                       |
| **Running**         | The instance is running and ready for use.                                                                                                                                             | Billed                                                           |
| **Rebooting**       | The instance reboots its operating system.                                                                                                                                             | Billed                                                           |
| **Shutting-down**   | The instance is preparing to be terminated.                                                                                                                                            | Not billed                                                       |
| **Terminated**      | The instance has been permanently deleted and cannot be started.                                                                                                                       | Not billed                                                       |
| **Stopping**        | The instance is preparing to be stopped or stop-hibernated.                                                                                                                            | Not billed if preparing to stop Billed if preparing to hibernate |
| **Stopped**         | The instance is shut down and cannot be used. The instance can be started at any time.                                                                                                 | Not billed                                                       |
| **Stop-hibernated** | The instance is shut down and cannot be used. The instance can be started at any time.                                                                                                 | Not billed                                                       |


+	####	EC2 instance lifecycle state flows

	<p align="center">
	<img src="assets/EC2_instance_lifecycle_state_flows.png" alt="EC2_instance_lifecycle_state_flows.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>EC2 instance lifecycle state flows</b>
	</p>

	An instance enters the pending state when it launches for the first time. In this state, the instance is preparing to enter the running state and cannot yet be used. When the instance is fully booted and ready, it exits the pending state and enters the running state. At this state, the  instance is running and ready for use. If we reboot our instance, it will be unavailable for use until it re-enter the running  state again. 
	If we decide to terminate the instance, it will briefly enter an intermediary state of shutting down before it is terminated. After the instance is terminated, it will remain visible in the Amazon EC2 console for a while before the virtual machine is deleted.
	However, we cannot connect to or recover the terminated instance. These states are the only states available for instances that are backed by an instance store volume. However, if our instance is backed by an EBS volume, then you have additional options available in the lifecycle of an instance. Instances that are backed by Amazon EBS can be stopped. They enter the stopping state before they attain the fully stopped state. A stopped instance will not incur the same cost as a running instance. Starting a stopped instance puts it back into the pending state before it enters the running state and is ready for use again. From the stopped state, we can also terminate an instance if we want to.

+	####	Vertical Scaling

	[<img src="assets/Vertical_scaling.png" alt="Vertical_scaling.png"  align="right" width="250px" height="300px">]()

	Amazon EC2 gives you the option to scale your instances by changing your instance type. Thus, you can scale up or down, as needed, for computing power, memory, disk space and more. This process is called vertical scaling.
	To vertically scale an Amazon EC2 instance, you must complete three steps:
	1. Stop the instance.
	2. Make the desired change to the instance size or type. 
	3. Start the instance.
	
	<b>Disadvantages of vertical scaling include the following:</b> 
	+	Manual process (but can be automated with AWS Lambda)
	+	Challenging when you have multiple instances to manage 
	+	Limited on the instance scalability
	+	Requires the instance to be unavailable while making changes

+	####	Horizontal Scaling

	[<img src="assets/Horizontal_scaling.png" alt="Horizontal_scaling.png"  align="right" width="300px" height="220px">]()

	Horizontal scaling is the process of adding or removing Amazon EC2 instances depending on the traffic demands. This process can be automated by using the Amazon EC2 Auto Scaling service. With horizontal scaling, you can add as many instances as you need for the computing job and terminate them when they are no longer needed.

	+	#####	Benefits:
		+	Improves fault tolerance
		+	Increases application availability 
		+	Lowers costs
		+	Requires no downtime to implement

+	####	Auto Scaling

	**Amazon EC2 Auto Scaling** helps you maintain application availability and lets us automatically or remove EC2 instances according to conditions that we define.
	+	Launches or terminates instances based on specified conditions
	+	Automatically registers new instances with load balancers when specified
	+	Can launch instances across Availability Zones
	+	Replaces unhealthy or unreachable instances with new instances
	+	Helps to save money by automating the number of instances based on condition needs

+	####	Amazon EC2 Auto Scaling options
	Amazon EC2 Auto Scaling offers three main ways to automate horizontal scaling.

	<p align="center">
	<img src="assets/Amazon EC2 Auto Scaling options.png" alt="Amazon EC2 Auto Scaling options.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Amazon EC2 Auto Scaling options</b>
	</p>

	+	#####	Scheduled scaling

		<b>Scheduled scaling</b> is based on a schedule so that we scale our application ahead of known load changes. For example, every week the traffic to our web application starts to increase on Wednesday, remains high on Thursday, and starts to decrease on Friday. We can plan our scaling activities based on the known traffic patterns of your web application.
			
	+	#####	Dynamic scaling

		<b>Dynamic scaling</b> lets us follow the demand curve for our applications closely, which reduces the need to manually provision Amazon EC2 capacity in advance. Thus, we can use target tracking scaling policies to select a metric for your application, such as CPU utilization. For example, when CPU utilization reaches a threshold that we specify, Amazon EC2 Auto Scaling will then automatically add more instances. And when the CPU utilization drops below the threshold that we specify, Amazon EC2 Auto Scaling will terminate the extra instances.

	+	#####	Predictive scaling

		<b>Predictive scaling</b> uses machine learning to schedule the right number of EC2 instances in anticipation of approaching traffic changes. Predictive scaling uses machine learning algorithms to predict future traffic, including regularly occurring spikes, and provisions the right number of EC2 instances in advance. As a result, it removes the need for manual adjustment to Amazon EC2 Auto Scaling parameters. It also delivers faster, simpler, and more accurate capacity provisioning, which results in lower cost and more responsive applications.

+	####	Vertical scaling use case

	A good example of when we might implement vertical scaling is when the instance size is not big enough to handle common processing tasks.
	In this example, the instance size is not big enough to handle the basic processing needs of the workload. So, we can scale up from an m5.large to a m5.xlarge. If we still need more CPU, then we can scale up to m5.2xlarge.
	Scaling horizontally would not work in this scenario, because adding more instances would not address the issue of instances that cannot handle basic processing needs.

	<p align="center">
	<img src="assets/Vertical_scaling_use_case.png" alt="Vertical_scaling_use_case.png"  width="700px" height="100%">
	</p>
	<p align="center">
	<b>Vertical scaling use case</b>
	</p>

+	####	Horizontal scaling use case
	A good use case to implement horizontal scaling, using Amazon EC2 Auto Scaling, is when we have more processing requests coming in tha our instance can handle.

	<p align="center">
	<img src="assets/Horizontal_scaling_use_case1.png" alt="Horizontal_scaling_use_case1.png"  width="700px" height="100%">
	</p>
	<p align="center">
	<img src="assets/Horizontal_scaling_use_case2.png" alt="Horizontal_scaling_use_case2.png"  width="700px" height="100%">
	</p>

	In this example, we have an instance with an m5.large instance type. The instance is able to handle basic processing tasks. However, it is being overloaded by the number of processing tasks that are coming in at the  moment. Amazon EC2 Auto Scaling can detect that the instance has over 50 percent of its CPU utilized, so it spins up more instances to spread out the workload. As soon as the instance's CPU utilization drops below a certain threshold, Amazon EC2 Auto Scaling will begin terminating the extra instances.
	In this scenario, vertical scaling would not be the best option because our application would need to be offline while we scaled up and down. Automating horizontal scaling with Amazon EC2 Auto Scaling is the best choice.

	<p align="center">
	<img src="assets/Horizontal_scaling_use_case3.png" alt="Horizontal_scaling_use_case3.png"  width="700px" height="100%">
	</p>
	<p align="center">
	<b>Horizontal scaling use case</b>
	</p>

+	####	Elastic Load Balancing (ELB)
	Another part of managing our EC2 instances is making sure that they are available. Thus, we need to consider managing traffic to our application on our instance.
	For example, if we deployed our application on one EC2 instance, over time, the instance response time might decrease, or the instance might stop responding. To resolve the issue, we would have to review our logs, identify the issue, and launch another EC2 instance. During this response action, our customers would not be able to access our web application.
	To help avoid this situation, AWS offers Elastic Load Balancing (ELB). Elastic Load Balancers are a highly available and scalable AWS service that automatically distributes incoming application traffic across multiple targets, such  as EC2 instances. The target can be in a single Availability Zone or multiple zones. With Elastic Load Balancers, we would have two or more EC2 instances. If one instances stops responding, the Elastic Load Balancer will distribute the traffic to other instances without affecting our customers.

	<p align="center">
	<img src="assets/ELB.png" alt="ELB.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Elastic Load Balancing (ELB)</b>
	</p>

+	####	ELB options
	AWS offers three main ways to manage traffic to our EC2 instances.

	<p align="center">
	<img src="assets/ELB_options.png" alt="ELB_options.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>ELB options</b>
	</p>

	+	#####	Application Load Balancer
		An Application Load Balancer is ideal for load balancing HTTP and HTTPS traffic. It operates at the request level (layer 7) and routes traffic to targets (EC2 instances, containers, IP addresses, and Lambda functions) based on the request content. Choose an Application Load Balancer when you need a flexible feature set for our applications with HTTP and HTTPS traffic.
		
	+	#####	Network Load Balancer
		A Network Load Balancer is ideal for load balancing TCP and UDP traffic. Choose a Network Load Balancer when we need ultra-high performance and static IP addresses for our applications. Operating at the connection level (layer 4), Network Load Balancers are capable of handling millions of requests per second securely while maintaining ultra-low latencies.
		
	+	#####	Gateway Load Balancer
		A Gateway Load Balancer helps us to deploy, scale, and manage our third-party virtual appliances. It operates at the network level (level 3) and provides a gateway for distributing traffic across multiple virtual appliances while scaling them up and down based on demand.
		We choose a Gateway Load Balancer when we need to deploy and manage a fleet of third-party virtual appliances that support GENEVE protocols. You can use these appliances to improve security, compliance, and policy controls. Gateway Load Balancers operate at the third layer.

+	####	Additional options for connecting to our instance
	+	#####	EC2 Instance Connect
		<p align="center">
		<img src="assets/EC2_Instance_Connect.png" alt="EC2_Instance_Connect.png"  width="100px" height="100%">
		</p>

		**Amazon EC2 Instance Connect** provides a simple and secure way to connect to our instances by using Secure Shell (SSH).
		We can connect by using Amazon EC2 Instance Connect with a valid user name and without a key pair.

	+	#####	Session Manager
		<p align="center">
		<img src="assets/Session_Manager.png" alt="Session_Manager.png"  width="100px" height="100%">
		</p>

		**Session Manager** is a fully managed AWS Systems Manager capability. We can use it to manage our EC2 instances, on-premises instances, and virtual machines through an interactive one-click, browser-based shell or through the AWS CLI.
		Fleet Manager, an AWS Systems Manager capability, is a unified UI experience that helps us remotely manage our nodes that run on AWS or on premises. With Fleet Manager, we can view the health and performance status of our entire server fleet from one console.
		To connect to an instance by using Session Manager, we must be granted the necessary permissions.

	+	#####	SSH client
		After launching our instance, we can connect to it and use it the way that you'd use a computer that's sitting in front of you. If the instance is created without a key pair, we cannot connect to the instance through SSH.

	+	#####	EC2 serial console
		<p align="center">
		<img src="assets/EC2_serial_console.png" alt="EC2_serial_console.png"  width="100px" height="100%">
		</p>

		The **Amazon EC2 serial console** provides access to your EC2 instance's serial port. We can use the serial console to troubleshoot boot, network configuration, and other issues. The serial console does not require our instance to have any networking capabilities. On the serial console, we can enter commands to an instance as if our keyboard and monitor are directly attached to the instance's serial port.
		To connect to an instance by using the Amazon EC2 serial console, the account must be authorized in the Amazon EC2 account settings.
	
+	####	Optimizing instance costs
	<p align="center">
	<img src="assets/Optimizing_Instance_cost1.png" alt="Optimizing_Instance_cost1.png"  width="200px" height="100%">
	</p>
	Finally, as we manage our instances, we must optimize them for costs to keep our computing budget as low as possible.

	<p align="center">
	<img src="assets/Optimizing_Instance_cost2.png" alt="Optimizing_Instance_cost2.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Optimize instance cost pillars</b>
	</p>

	Optimizing instance costs has four pillars. These pillars are:

	+	#####	Using the right  size instance
		Right-sizing your instances means that you choose the right balance of instance types. This process includes monitoring when servers can be either sized down or turned off and still meet your performance requirements.

	+	#####	Increasing  elasticity
		Increase elasticity is the practice of designing your deployments to reduce the amount of server capacity that is idle by implementing deployments that are elastic. For example, you can have deployments that use automatic scaling to handle peak loads.

	+	#####	Choosing  optimal pricing models
		Optimal pricing model is about recognizing the available pricing options. Analyze your usage patterns so that you can run EC2 instances with the right mix of pricing options.

	+	#####	Optimizing storage choices
		Optimizing storage choices requires you to analyze the storage requirements of your deployments. The goal is to reduce unused storage overhead when possible and choose less expensive storage options if they still meet your requirements for storage performance.


+	####	Other AWS Storage Services summary
	<p align="center">
	<img src="assets/Other_AWS_Storage_Services_summary.png" alt="Other_AWS_Storage_Services_summary.png"  width="100%" height="100%">
	</p>
	<p align="center">
	<b>Other AWS Storage Summary</b>
	</p>

+	###	Summary

	Key takeaways from the course:

	<p align="center">
	<img src="assets/Summary.png" alt="Summary.png"  width="100%" height="100%">
	</p>

+	###	Continue your learning journey

	<p align="center">
	<img src="assets/Continue_your_learning_journey.png" alt="Continue_your_learning_journey.png"  width="100%" height="100%">
	</p>

+	###	Thank you for choosing AWS Educate

	<p align="center">
	<img src="assets/Thank_you_for_choosing_AWS_Educate.png" alt="Thank_you_for_choosing_AWS_Educate.png"  width="100%" height="100%">
	</p>

### Getting Started with Amazon EC2 Lab Guide

This lab guide teaches you the basic overview of launching, resizing, managing,and monitoring  an Amazon Elastic Compute Cloud (Amazon EC2) instance. _Click to [Learn more ...](https://awseducate.instructure.com/courses/907/modules/items/15905)_


### <a href="./Lab: Getting Started with Amazon EC2/README.md">Getting Started with Amazon EC2 Lab</a>

<a  href="./Lab: Getting Started with Amazon EC2/README.md">Click to learn more ...</a>