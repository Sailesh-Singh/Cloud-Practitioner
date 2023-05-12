#   LAB5: Creating a Virtual Private Cloud

### Lab overview and objectives

Traditional networking is difficult. It involves equipment, cabling, complex configurations, and specialist skills. Amazon Virtual Private Cloud (Amazon VPC) hides the complexity and simplifies the deployment of secure private networks. 

This lab shows you how to build your own virtual private cloud (VPC), deploy resources, and create private peering connections between VPCs.
_Click to [Learn more...](https://awseducate.instructure.com/courses/768/assignments/3157?module_item_id=13573)_

After completing this lab, you will know how to:

+   Deploy a VPC 
+   Create an internet gateway and attach it to the VPC 
+   Create a public subnet 
+   Create a private subnet 
+   Create an application server to test the VPC 

####   Duration
This lab requires approximately  45 minutes  to complete.

####    Task 1: Creating a VPC

A VPC is a virtual network that is dedicated to your Amazon Web Services (AWS) account. It is logically isolated from other virtual networks in the AWS Cloud. You can launch AWS resources, such as Amazon Elastic Compute Cloud (Amazon EC2) instances, into the VPC. You can configure the VPC by modifying its IP address range and can create subnets. You can also configure route tables, network gateways, and security settings. 

+   In the AWS Management Console, on the  Services   menu, choose  VPC . 

    The VPC console provides a wizard that can automatically create several VPC architectures. However, in this lab, you create the VPC components manually. 

+   In the left navigation pane, choose  Your VPCs . 

    A default VPC is provided so that you can launch resources as soon as you start using AWS. There is also a shared VPC that you use later in the lab. However, you now create your own  Lab VPC . 

    The VPC will have a Classless Inter-Domain Routing (CIDR) range of  10.0.0.0/16 , which includes all IP address that start with 10.0.x.x. It contains more than 65,000 addresses. You later divide the addresses into separate subnets. 

+   Choose Create VPC . 

+   Under Resources to create, choose VPC only . 

+   Configure the following settings: 

    +   For Name tag  enter `Lab VPC`
    +   For IPv4 CIDR block, enter  `10.0.0.0/16`
    +   For Tenancy, `select` Default . 
    +   For Tags, ensure that: 
    Key:  `Name`
    Value:  `Lab VPC`

+   Choose  Create VPC . 
+   From the  VPC Details  page, choose the  Tags  tab. 

Tags are useful for identifying resources. For example, you can use a tag to identify cost centers or different environments (such as development, test, or production). 

+   Choose  Actions   and select  Edit VPC settings . 

+   In the  DNS settings  section, select   Enable DNS hostnames . 

This option assigns a friendly Domain Name System (DNS) name to EC2 instances in the VPC, such as the following: 

ec2-52-42-133-255.us-west-2.compute.amazonaws.com 

+   Choose  Save . 

Any EC2 instances that are launched into the VPC now automatically receive a DNS hostname. You can also add a more-meaningful DNS name (such as app.example.com) later by using Amazon Route 53.

####    Task 2: Creating subnets

A subnet is a subrange of IP addresses in the VPC. AWS resources can be launched into a specified subnet. Use a  public subnet  for resources that must be connected to the internet, and use a  private subnet  for resources that must remain isolated from the internet. 

In this task, you create a public subnet and a private subnet:

#####   Create a public subnet

You use the public subnet for internet-facing resources. 

+   In the left navigation pane, choose  Subnets . 

+   Choose  Create subnet  and configure the following settings: 

    +   For  VPC ID , choose  Lab VPC . 
    +   For  Subnet name , enter  Public Subnet
    +   For  Availability zone , select the first Availability Zone in the list. Do not choose  No Preference . 
    +   For  IPv4 CIDR block , enter  10.0.0.0/24
    +   Choose  Create subnet 

 The VPC has a CIDR block of  10.0.0.0/16 , which includes all 10.0.x.x IP addresses. The subnet you just created has a CIDR block of  10.0.0.0/24 , which includes all 10.0.0.x IP addresses. They might look similar, but the subnet is smaller than the VPC because of the  /24  in the CIDR range. 

You now configure the subnet to automatically assign a public IP address for all instances that are launched in it. 

+   Select the check box for Public Subnet . 

+   Choose Actions and select Edit subnet settings. Then configure the following option: 

    +   Under Auto-assign IP settings, select   Enable auto-assign public IPv4 address . 

    +   Choose Save 

 Though this subnet is named  Public Subnet , it is not yet public. A public subnet must have an internet gateway, which you attach in the next task.

 #####  Create a private subnet

 You use the private subnet for resources that must remain isolated from the internet. 

+   Use what you learned in the previous steps to create another subnet with the following settings: 

    +   For VPC ID, choose Lab VPC . 
    +   For Subnet name, enter Private Subnet
    +   For Availability Zone, select the first Availability Zone in the list. Do not choose  No Preference . 
    +   For IPv4 CIDR block, enter 10.0.2.0/23
    +   Choose Create subnet 

The CIDR block of  10.0.2.0/23  includes all IP addresses that start with 10.0.2.x and 10.0.3.x. This is twice as large as the public subnet because most resources should be kept private unless they specifically must be accessible from the internet. 

Your VPC now has two subnets. However, the public subnet is totally isolated and cannot communicate with resources outside the VPC. Next, you configure the public subnet to connect to the internet via an internet gateway.

####    Task 3: Creating an internet gateway 