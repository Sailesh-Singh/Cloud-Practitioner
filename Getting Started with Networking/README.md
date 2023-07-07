#   [Getting Started with Networking](https://awseducate.instructure.com/courses/911)

##	Overview
Computer networking refers to interconnected computing devices that can exchange data and share resources with each other. These networked devices use a system of rules, called communications protocols, to transmit information over physical or wireless technologies. Modern-day network solutions deliver more than connectivity. They are critical for the digital transformation and success of businesses today.

Amazon Virtual Private Cloud (Amazon VPC) is a service that we can use to provision a logically isolated section of the AWS Cloud. This section (called a virtual private cloud, or VPC) is where you can launch our Amazon Web Services (AWS) resources. With Amazon VPC, we have control over your virtual networking resources. These resources include the selection of our own IP address range, the creation of subnets, and the configuration of route tables and network gateways.

In this course, we will acquire the knowledge that we need to start using Amazon VPC. We will learn about the key elements of Amazon VPC and explore how to configure them. We will learn how to set up security for VPCs and learn about other AWS networking services.   


##	Objectives
By the end of this course, we will be able to do the following:

+   Describe networking fundamental concepts.
+   Explain Amazon VPC features, benefits, and use cases.
+   Discuss how to configure public and private subnets.
+   Discuss how to configure route tables to direct traffic in your network.
+   Describe how to use an internet gateway and a virtual private gateway to allow traffic into your network.
+   Discuss how to configure security in a VPC by using network access control lists (network ACLs) and security groups.
+   Describe types of IP addressing, including use and benefits.
+   Identify ways to manage your VPC.

---

# Getting started with Networking

###	1.	Beginning Scenes
**A.  Introduction to networking**

+	Network basics
+	OSI model
+	IP Address
+	VPCs

**B.  Introduction to Amazon Virtual Private Cloud(Amazon VPC)**

+	Key concepts
+	Architecture
+	Use cases
+	VPC pricing

**C.  Using Amazon VPC**
+	Subnets
+	Network gateways
+	Route tables
+	Firewalls

**D.  Managing your network**
+	Using additional VPC features 
+	AWS VPN
+	AWS Direct Connect
+	Other AWS networking services

### 2.  Keyboard Shortcuts

**A.    Windows keys**
+   Play/Pause	`Ctrl+Alt+P`
+   Previous slide	`Ctrl+Alt+,(Comma)`
+   Next slide	`Ctrl+Alt+.(period)`
+   All shortcuts	`Shift+?`

**B.    Mac keys**
+   Play/Pause	`Ctrl+Option+P`
+   Previous slide	`Ctrl+Option+,(Comma)`
+   Next slide	`Ctrl+Option+.(period)`
+   All shortcuts	`Shift+?`



### 3.	Introduction to Networking
Computer network is two or more devices connected together to share resources. Devices on network are called **nodes**. Nodes on network are divided into two categories. They are:
+   #####   Host node
    Centralized node that shares files, applications, and resources with other nodes on the network.
    Examples:
    +	File Servers
    +	Email Servers
    +	Web Servers

+   #####    Client node
    Nodes that depend on the host node for files, applications, and resources.
    Examples:
    +	Computers
    +	Printers
    +	Mobile devices