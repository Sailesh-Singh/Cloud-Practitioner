# Lab: Getting Started with Networking Lab
### Lab overview and objectives
Traditional networking is difficult. It involves equipment, cabling, complex configurations, and specialist skills. Amazon Virtual Private Cloud (Amazon VPC) hides the complexity and simplifies the deployment of secure private networks.

This lab shows you how to build your own virtual private cloud (VPC), and deploy resources into it. _Click to [Learn more ...](https://awseducate.labs.awsevents.com/sa/lab/arn%3Aaws%3Alearningcontent%3Aus-east-1%3A470679935125%3Ablueprintversion%2FCUR-TF-100-EDNETW-1%2F1-lab-getting-started-vpc%3A1.0.2-9e7485ec/en-US)_

####    Objectives
After completing this lab, you will know how to do the following:

+   Explain the basic components of a VPC
+   Deploy a basic VPC with public subnets
+   Deploy an EC2 instance into a VPC


####    LAB
Lab: Creating a Virtual Private Cloud

###   Part 1: Exploring the default VPC
 

+   ####  Task 1: Explore the default VPC configuration
    In this lab, you begin by exploring the default VPC that is automatically included with each AWS account.

    A VPC is a virtual network that is dedicated to your AWS account. It is logically isolated from other virtual networks in the AWS Cloud. You can launch AWS resources, such as Amazon Elastic Compute Cloud (Amazon EC2) instances, into the VPC. 

    AWS region with a VPC
    In the preceding diagram, an VPC is deployed into an AWS region.

    +   In the AWS Management Console on the Services menu, enter VPC. From the search results, choose VPC.

    +   In the left navigation pane, choose Your VPCs.

        There is a default VPC that is provided so that you can launch resources as soon as you start using AWS. 

    +   Notice that the default VPC is configured with the CIDR range of  172.31.0.0/16.

        This CIDR range includes all addresses from 172.31.0.0 through 172.31.255.255, which is a total of 65,536 addresses.

 

+   ####  Task2: Explore a default Subnet
    In this task, you explore a public subnet.

    A subnet is a sub-range of IP addresses in the VPC. AWS resources can be launched into a specified subnet. Use a public subnet for resources that must be connected to the internet, and use a private subnet for resources that must remain isolated from the internet.

    +   In the left navigation pane, choose Subnets.

        Notice that all of the default subnets are associated with the same VPC, the default VPC. Also notice that each subnet has an IPv4 CIDR range. Each subnet CIDR range is a distinct subset of the addresses available in the VPC. When designing your subnets, you must ensure that the CIDR ranges do not overlap with address ranges used in other subnets.

    +   From the list of subnets, choose the subnet with the IPv4 CIDR range 172.31.0.0/20. 

    +   Notice that the value for Auto-assign public IPv4 address is Yes, which means that it is turned on.

    This means that the subnet automatically assigns a public IP address for all instances that are launched into it.

+   ####  Task 3: Explore the internet gateway
    +   In the left navigation pane, choose Internet Gateways.

    +   The internet gateway should already be selected. If it isn't, select it.

    Notice that the State of the internet gateway is Attached. The internet gateway is attached to the VPC shown under VPC ID. This is the VPC ID of the default VPC.

+   ####  Task 4: Explore the route table
    +   In the left navigation pane, choose Route Tables.

        One route table is displayed, and it is associated with the default VPC. 

    +   In the lower half of the page, choose the Routes tab.

        There are two routes: **a local route** and **a public route**.

        All traffic that is destined for 172.31.0.0/16 (which is the range of the default VPC) is routed locally. This route allows all subnets in a VPC to communicate with each other.

        All public traffic (0.0.0.0/0) is routed to the internet gateway.

    +   Choose the Subnet associations tab.

        In the Subnets without explicit associations section, notice that the subnet with the IPv4 CIDR 172.31.0.0/20 is included in the list. This is the same subnet that you reviewed earlier.

        All of the subnets in this list are public subnets because they have a route table entry that sends traffic to the internet through the internet gateway.

+   #### Task 5: Explore the default security group
    +   In the left navigation pane, choose Security Groups.

    The default security group should already be selected.

    +   In the lower half of the page, choose the Outbound rules tab.

    You should find one rule. This rule allows All protocols and All port ranges to send traffic to any IP address (0.0.0.0/0).

    +   Choose the Inbound rules tab.

    You should find one rule for incoming traffic. This rule allows incoming traffic to All protocols and All port ranges from resources that use the default security group.

    In a later step, you deploy an EC2 instance with a website into the default VPC. For incoming traffic from sources outside your VPC to access this website, you must add a new security group rule. Because you should not make changes to the default security group, you create a new one. Then, you add a rule to your new security group that permits HTTP (port 80) traffic that comes from anywhere on the internet (0.0.0.0/0).
    +   Choose Create security group.

    +   For Security group name, enter Web-Server-SG.

    +   For Description, enter Allows HTTP access.

    +   Keep the VPC selection.

    +   In the Inbound rules section, choose Add rule, and then configure the following settings:

        +   For Type, choose HTTP.
        +   From the Source type dropdown list, choose Anywhere IPv4.
        +   For Description, enter Allow web access.
    +   Choose Create security group.    

+   ####  Task 6: Deploy an EC2 instance
    +   On the Services  menu, choose EC2.

    +   Choose Launch instance, and then choose Launch instance from the dropdown list. Configure the following options:

        +   In the Name and tags pane, in the Name text box, enter Web-Server.

        +   Choose an Amazon Machine Image (AMI).

            +   In the Application and OS Images (Amazon Machine Image) section, choose Amazon Linux.
        +   Choose an instance type:

            +   Select t2.micro.
        +   In the Key pair (login) section, from the Key pair name - required dropdown list, choose Proceed without a key pair (Not recommended).

        +   In the Network settings section, choose Edit.

        +   For Firewall (security groups), choose Select an existing security group.

        +   In the Common security groups dropdown list, choose the security group named Web-Server-SG.

        +   In the  Advanced Details section, for IAM instance profile, choose Work-Role.
        +   In the  Advanced Details section, copy the following commands, and paste them into the User data text box:


            ```#!/bin/bash
            # Install Apache Web Server and PHP
            yum install -y httpd mysql
            amazon-linux-extras install -y php7.2
            # Download Lab files
            wget https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-100-EDNETW-1-60961/1-lab-getting-started-vpc/s3/inventory-app.zip
            unzip inventory-app.zip -d /var/www/html/
            # Download and install the AWS SDK for PHP
            wget https://github.com/aws/aws-sdk-php/releases/download/3.62.3/aws.zip
            unzip aws -d /var/www/html
            # Turn on web server chkconfig httpd on
            service httpd start
            ```

        +   In the Summary section, choose Launch instance.
        A message indicates that you successfully initiated the launch of your instance.

    +   Choose View all instances.

    +   Wait for the application server to fully launch. It should display the following status:

        Instance State: Running
        You can choose refresh  occasionally to update the display.

    +   Select  Web-Server.
    +   From the Details tab, copy the Public IPv4 address address.
    +   Open a new browser tab, paste the IP address that you just copied, and then press Enter.
   
###   Part 2: Creating a VPC
Being able to use the default VPC when you are first learning about and working with AWS cloud is very convenient. However, in the real world, you often need to create custom VPCs to meet a customer's requirements. For example, a customer might have already used the CIDR range of the default VPC in their on-premises network configuration. A customer might also want to vary how many addresses are included in each subnet. Because it is not possible to change the CIDR ranges assigned to the VPC or its subnets, you need to create a new VPC for your customer. 

In this scenario, you create a new VPC. Your customer provided the following network requirements for the VPC's CIDR ranges:

Top-level VPC

+   VPC IPv4 CIDR - 10.0.0.0/16

Availability Zones:

+   They need to deploy their resources to two Availability Zones.

Two public subnets:

+   Public Subnet 1 - 10.0.0.0/24
+   Public Subnet 2 - 10.0.1.0/24

Two private subnets:

+   Private Subnet 1 - 10.0.2.0/24
+   Private Subnet 2 - 10.0.3.0/24

The default VPC that you explored earlier did not have any private subnets. Remember that the difference between a public subnet and a private subnet is whether they can be reached directly from the internet. The route table associated with a public subnet includes a route to an internet gateway, and the route table for a private subnet does not.

 

+   ####  Task 7: Create a custom VPC
    You can configure the VPC by defining its IP address range and creating subnets. You can also configure route tables, network gateways, and security settings.

    The VPC console provides a wizard that can automatically create several VPC architectures. You use this wizard to create a new VPC.

    If the configuration of a setting is not mentioned in these steps, leave the default value.

    +   Return to the browser tab with the AWS console.

    +   In the AWS Management Console on the Services menu, enter VPC. From the search results, choose VPC.

    +   In the left navigation pane, choose Your VPCs.

        
    +   Choose Create VPC and configure the following settings:

        +   For Resources to create, choose VPC and more
        +   For Name tag auto-generation, enter Lab.
        +   For IPv4 CIDR block, ensure that the value is 10.0.0.0/16.
        +   For Availability Zones (AZs), choose 2.
        +   For Number of public subnets, choose 2.
        +   For Number of private subnets, choose 2.
        +   Expand Customize subnets CIDR blocks.
        +   Update the subnet CIDR block values using the ranges provided by your customer.
    +   Take a moment to review the Preview diagram provided in the wizard.  

    +   Choose Create VPC.

        The wizard immediately starts creating your VPC. After it finishes, you have a VPC that has all of the components that you explored earlier: subnets, route tables, an internet gateway, and a default security group. The VPC wizard also automatically configures the routes in the route tables for both the public subnets and the private subnets.

        Like the default security group you explored earlier, the default security group created by the wizard blocks incoming traffic from the internet. To reach a web server in the new VPC, you need to add a rule to this default security group.

    +   Choose View VPC.

        Recall that a VPC's default security group does not allow traffic from outside the VPC. Because you should not change the default security group, you add a new security group to your custom VPC.

    +   In the left navigation pane, choose Security Groups.

    +   Choose Create security group.

    +   For Security group name, enter Web-Server2-SG.

    +   For Description, enter Allows HTTP access.

    +   For VPC, clear the selection and then choose Lab-vpc.

    +   In the Inbound rules section, choose Add rule, and then configure the following settings:

        +   For Type, choose HTTP.
        +   From the Source type dropdown list, choose Anywhere IPv4.
        +   For Description, enter Allow web access.
    +   Choose Create security group.

+   ####  Task 8: Deploy an EC2 instance into your custom VPC
    +   On the Services  menu, choose EC2.

    +   Choose Launch instance, and then choose Launch instance from the dropdown list. Configure the following options:

        +   In the Name and tags pane, in the Name text box, enter Web-Server2.

        +   Choose an Amazon Machine Image (AMI).

            +   In the Application and OS Images (Amazon Machine Image) section, choose Amazon Linux.
        +   Choose an Instance Type:

            +   Select t2.micro.

        +   In the Key pair (login) section, from the Key pair name - required dropdown list, choose Proceed without a key pair (not recommended).

        +   In the Network settings section, choose Edit.

        +   For VPC - required, choose Lab-vpc.

        +   For Subnet, choose the subnet with public1 in the name.

        +   For Auto-assign public IP, choose Enable.

        +   For Firewall (security groups), choose Select an existing security group.

        +   From the Common security groups dropdown list, choose the Web-Server2-SG security group.

        +   In the  Advanced Details section, for IAM instance profile, choose Work-Role.

        +   In the  Advanced Details section, copy the following commands, and paste them into the User data text box:

            ```#!/bin/bash
            # Install Apache Web Server and PHP
            yum install -y httpd mysql
            amazon-linux-extras install -y php7.2
            # Download Lab files
            wget https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-100-EDNETW-1-60961/1-lab-getting-started-vpc/s3/inventory-app.zip
            unzip inventory-app.zip -d /var/www/html/
            # Download and install the AWS SDK for PHP
            wget https://github.com/aws/aws-sdk-php/releases/download/3.62.3/aws.zip
            unzip aws -d /var/www/html
            # Turn on web server
            chkconfig httpd on
            service httpd start```
    

        +   In the Summary section, choose Launch instance.

        A message indicates that you successfully initiated the launch of your instance.

    

    +   Choose View all instances.

    +   Wait for the application server to fully launch. It should display the following status:

        +   Instance State: Running
        You can choose refresh  occasionally to update the display.

    +   Select  Web-Server2.
    +   From the Details tab, copy the Public IPv4 address address.
    +   Open a new browser tab, paste the IP address that you just copied, and then press Enter.
    If you configured the VPC correctly, the Inventory application and this message should appear: Please configure Settings to connect to database. You have not configured any database settings yet, but the appearance of the Inventory application demonstrates that the public subnet was correctly configured.

    If the Inventory application does not appear, wait for 60 seconds and refresh  the page to try again. It can take a couple of minutes for the EC2 instance to boot and run the script that installs the software.

 
### END OF LAB
