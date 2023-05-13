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
This lab requires approximately <b>45 minutes</b> to complete.

####    Task 1: Creating a VPC

A VPC is a virtual network that is dedicated to your Amazon Web Services (AWS) account. It is logically isolated from other virtual networks in the AWS Cloud. You can launch AWS resources, such as Amazon Elastic Compute Cloud (Amazon EC2) instances, into the VPC. You can configure the VPC by modifying its IP address range and can create subnets. You can also configure route tables, network gateways, and security settings. 

+   In the AWS Management Console, on the  <b>Services</b> menu, choose <b>VPC</b>. 

    The VPC console provides a wizard that can automatically create several VPC architectures. However, in this lab, you create the VPC components manually. 

+   In the left navigation pane, choose  <b>Your VPCs</b>. 

    A default VPC is provided so that you can launch resources as soon as you start using AWS. There is also a shared VPC that you use later in the lab. However, you now create your own  <b>Lab VPC</b>. 

    The VPC will have a Classless Inter-Domain Routing (CIDR) range of  <b>10.0.0.0/16</b>, which includes all IP address that start with 10.0.x.x. It contains more than 65,000 addresses. You later divide the addresses into separate subnets. 

+   Choose <b>Create VPC</b>. 

+   Under <b>Resources to create</b>, choose <b>VPC only</b>. 

+   Configure the following settings: 

    +   For <b>Name tag</b>  enter `Lab VPC`
    +   For <b>IPv4 CIDR block</b>, enter  `10.0.0.0/16`
    +   For <b>Tenancy</b>, `select` <b>Default</b>. 
    +   For Tags, ensure that: 
    <b>Key:</b>  `Name`
    <b>Value:</b>  `Lab VPC`

+   Choose  <b>Create VPC</b>. 
+   From the <b>VPC Details</b> page, choose the <b>Tags</b> tab. 

Tags are useful for identifying resources. For example, you can use a tag to identify cost centers or different environments (such as development, test, or production). 

+   Choose <b>Actions</b> and select <b>Edit VPC settings</b>. 

+   In the <b>DNS settings</b> section, select <b>Enable DNS hostnames</b>. 

This option assigns a friendly Domain Name System (DNS) name to EC2 instances in the VPC, such as the following: 

<b>ec2-52-42-133-255.us-west-2.compute.amazonaws.com</b>

+   Choose <b>Save</b>. 

Any EC2 instances that are launched into the VPC now automatically receive a DNS hostname. You can also add a more-meaningful DNS name (such as <b>app.example.com</b>) later by using Amazon Route 53.

####    Task 2: Creating subnets

A subnet is a subrange of IP addresses in the VPC. AWS resources can be launched into a specified subnet. Use a  public subnet  for resources that must be connected to the internet, and use a  private subnet  for resources that must remain isolated from the internet. 

In this task, you create a public subnet and a private subnet:

#####   Create a public subnet

You use the public subnet for internet-facing resources. 

+   In the left navigation pane, choose  <b>Subnets</b>. 

+   Choose <b>Create subnet</b> and configure the following settings: 

    +   For <b>VPC ID</b>, choose <b>Lab VPC</b>. 
    +   For <b>Subnet name</b>, enter  `Public Subnet`
    +   For <b>Availability zone</b>, select the first Availability Zone in the list. Do not choose <b>No Preference</b>. 
    +   For <b>IPv4 CIDR block</b>, enter  `10.0.0.0/24`
    +   Choose <b>Create subnet</b> 

 The VPC has a CIDR block of <b>10.0.0.0/16</b>, which includes all 10.0.x.x IP addresses. The subnet you just created has a CIDR block of <b>10.0.0.0/24</b>, which includes all 10.0.0.x IP addresses. They might look similar, but the subnet is smaller than the VPC because of the  <b>/24</b> in the CIDR range. 

You now configure the subnet to automatically assign a public IP address for all instances that are launched in it. 

+   Select the check box for <b>Public Subnet</b>. 

+   Choose <b>Actions</b> and select <b>Edit subnet settings</b>. Then configure the following option: 

    +   Under <b>Auto-assign IP settings</b>, select <b>Enable auto-assign public IPv4 address</b>. 

    +   Choose <b>Save</b> 

 Though this subnet is named <b>Public Subnet</b>, it is not yet public. A public subnet must have an internet gateway, which you attach in the next task.

 #####  Create a private subnet

 You use the private subnet for resources that must remain isolated from the internet. 

+   Use what you learned in the previous steps to create another subnet with the following settings: 

    +   For <b>VPC ID</b>, choose <b>Lab VPC</b>. 
    +   For <b>Subnet name</b>, enter `Private Subnet`
    +   For <b>Availability Zone</b>, select the first Availability Zone in the list. Do not choose <b>No Preference</b>. 
    +   For <b>IPv4 CIDR block</b>, enter `10.0.2.0/23`
    +   Choose <b>Create subnet</b> 

The CIDR block of  10.0.2.0/23  includes all IP addresses that start with 10.0.2.x and 10.0.3.x. This is twice as large as the public subnet because most resources should be kept private unless they specifically must be accessible from the internet. 

Your VPC now has two subnets. However, the public subnet is totally isolated and cannot communicate with resources outside the VPC. Next, you configure the public subnet to connect to the internet via an internet gateway.

####    Task 3: Creating an internet gateway

An internet gateway is a horizontally scaled, redundant, and highly available VPC component. It allows communication between the instances in a VPC and the internet. It imposes no availability risks or bandwidth constraints on network traffic. 

An internet gateway serves two purposes: 
+       To provide a target in route tables that connects to the internet 

+       To perform network address translation (NAT) for instances that were assigned public IPv4 addresses 

In this task, you create an internet gateway so that internet traffic can access the public subnet. 

+   In the left navigation pane, choose <b>Internet Gateways</b>. 

+   Choose <b>Create internet gateway</b>  and configure the following settings: 

    +   For <b>Name tag</b>, enter  <b>Lab IGW</b>
    +   Choose <b>Create internet gateway</b> 

You can now attach the internet gateway to your <b>Lab VPC</b>. 

+   Choose <b>Actions</b> and then <b>Attach to VPC</b>, and configure the following settings: 

    +   For <b>Available VPCs</b>, select <b>Lab VPC</b>. 
    +   Choose <b>Attach internet gateway</b> 

This action attaches the internet gateway to your <b>Lab VPC</b>. Although you created an internet gateway and attached it to your VPC, you must also configure the public subnet route table so that it uses the internet gateway.

####    Task 4: Configuring route tables

A route table contains a set of rules, called routes, that are used to determine where network traffic is directed. Each subnet in a VPC must be associated with a route table because the table controls the routing for the subnet. A subnet can be associated with only one route table at a time, but you can associate multiple subnets with the same route table. 

To use an internet gateway, a subnet's route table must contain a route that directs internet-bound traffic to the internet gateway. If a subnet is associated with a route table that has a route to an internet gateway, it is known as a public subnet. 

In this task, you: 

+       Create a public route table for internet-bound traffic 
+       Add a route to the route table to direct internet-bound traffic to the internet gateway 
+       Associate the public subnet with the new route table 

+   In the left navigation pane, choose <b>Route Tables</b>. 

    Several route tables are displayed, but there is only one route table associated with <b>Lab VPC</b>. This route table routes traffic locally, so it is a private route table. 

+   In the <b>VPC</b> column, find the route table that shows <b>Lab VPC</b>, and select the check box for this route table. (You can expand the column to see the names.) 

+   In the <b>Name</b> column, choose and then enter the name `Private Route Table` and choose <b>Save</b> 

+   In the lower half of the page, choose the <b>Routes</b> tab. 

There is only one route. It shows that all traffic that is destined for 10.0.0.0/16 (which is the range of the <b>Lab VPC</b>) will be routed locally. This route allows all subnets in a VPC to communicate with each other. 

You now create a new public route table to send public traffic to the internet gateway. 

+   Choose <b>Create route table</b> and configure the following settings: 

    +   For <b>Name</b>, enter `Public Route Table`
    +   For <b>VPC</b>, choose <b>Lab VPC</b>. 
    +   Choose <b>Create route table</b> 

+   In the <b>Routes</b> tab, choose <b>Edit routes</b> 
    You now add a route to direct internet-bound traffic (0.0.0.0/0) to the internet gateway. 

+   Choose <b>Add route</b> and then configure the following settings: 

    +   For <b>Destination</b>, enter `0.0.0.0/0`
    +   For <b>Target</b>, select <b>Internet Gateway</b>, and then from the dropdown list select <b>Lab IGW</b>. 
    +   Choose <b>Save changes</b> 

The last step associates this new route table with the public subnet. 

+   Choose the <b>Subnet associations</b> tab. 
+   In the <b>Subnets without explicit associations</b>  section, choose <b>Edit subnet associations</b> 
+   Select the row with <b>Public Subnet</b>. 
+   Choose <b>Save associations</b> 

    The public subnet is now public because it has a route table entry that sends traffic to the internet via the internet gateway. 

    To summarize, you can create a public subnet by following these steps: 

    +   Create an internet gateway. 
    +   Create a route table. 
    +   Add a route to the route table that directs 0.0.0.0/0 traffic to the internet gateway. 
    +   Associate the route table with a subnet, which then becomes a public subnet.

####    Task 5: Creating a security group for the application server

A _security_ group acts as a virtual firewall for instances to control inbound and outbound traffic. Security groups operate at the level of the elastic network interface for the instance. Security groups do not operate at the subnet level. Thus, each instance can have its own firewall that controls traffic. If you do not specify a particular security group at launch time, the instance is automatically assigned to the default security group for the VPC. 

In this task, you create a security group that allows users to access your application server via HTTP. 

+   In the left navigation pane, choose <b>Security Groups</b>. 

+   Choose <b>Create security group</b> and configure the following settings: 

    +   For <b>Security group name</b>, enter `App-SG`
    +   For <b>Description</b>, enter `Allow HTTP traffic`
    +   For <b>VPC</b>, choose <b>Lab VPC</b>. 
    +   Choose <b>Create security group</b> 

+   Choose the <b>Inbound Rules</b> tab. 

    The settings for <b>Inbound Rules</b> determine what traffic is permitted to reach the instance. You configure it to permit HTTP (port 80) traffic that comes from anywhere on the internet (0.0.0.0/0). 

+   Choose <b>Edit inbound rules</b> 

+   Choose <b>Add rule</b> and then configure the following settings: 

    +   For <b>Type</b>, choose <b>HTTP</b>. 
    +   From the <b>Source type</b> dropdown list, choose <b>Anywhere IPv4</b>. 
    +   For <b>Description</b>, enter `Allow web access`
    +   Choose <b>Save rules</b> 

You use this <b>App-SG</b> in the next task.

####    Task 6: Launching an application server in the public subnet

+   On the <b>Services</b> menu, choose <b>EC2</b>. 

+   Choose  <b>Launch instance</b> and then select  <b>Launch instance</b> from the dropdown list. Configure the following options: 

    +   In the <b>Name and tags</b> pane, in the <b>Name</b> text box, enter `App Server`

    +   In the <b>Application and OS Images (Amazon Machine Image)</b> section, keep default selection, <b>Amazon Linux 2</b>. 

    +   In the <b>Instance type</b> section, keep the default instance type, <b>t2.micro</b>.  

    +   In the <b>Key pair (login)</b> section, from the <b>Key pair name -</b> *_required_* dropdown list, choose <b>Proceed without a key pair (not recommended)</b>. 

    +   In the <b>Network settings</b> section, choose  <b>Edit</b> 

        +   From the <b>VPC -</b> *_required_* dropdown list, choose <b>Lab VPC</b>. 

        +   From the <b>Subnet</b> dropdown list, choose <b>Public Subnet</b>. 

        +   Ensure that <b>Auto-assign public IP</b> is  <b>Enable</b>. 

    +   In the <b>Firewall (security groups)</b> section, choose <b>Select existing security group</b> 

        +   From the <b>Common security groups</b>  dropdown list, choose `App-SG`. 

    +   In the <b>Configure storage</b> section, keep the default storage configuration. 

    +   Expand the <b>Advanced details</b> section. 

        +   For <b>IAM instance profile</b>, choose the role <b>Inventory-App-Role</b>. 

        +   Scroll down to <b>User data</b> section, copy and paste the below code in the block.

            ```
            #!/bin/bash 
            # Install Apache Web Server and PHP 
            yum install  -y  httpd mysql 
            amazon-linux-extras install  -y  php7.2 
            # Download Lab files 
            wget  https://aws-tc-largeobjects.s3-us-west-2.amazonaws.com/ILT-TF-200-ACACAD-20-EN/mod6-guided/scripts/inventory-app.zip 
            unzip inventory-app.zip  -d  /var/www/html/ 
            # Download and install the AWS SDK for PHP 
            wget  https://github.com/aws/aws-sdk-php/releases/download/3.62.3/aws.zip 
            unzip aws  -d  /var/www/html 
            # Turn on web server 
            chkconfig httpd on 
            service  httpd  start
            ``` 

    +   From the  <b>Summary</b> section, choose <b>Launch instance</b> 

+   Choose <b>View all instances</b> 

+   Wait for the application server to fully launch. It should display the following status: 

    +   <b>Instance State:</b> Running 

+   Select <b>App Server</b>. 
+   From the <b>Details</b> tab, copy the <b>Public IPv4 address</b> address. 
+   Open a new browser tab, paste the IP address you just copied, and press Enter. 

If you configured the VPC correctly, the Inventory application and this message should appear: <b>Please configure Settings to connect to database</b>. You have not configured any database settings yet, but the appearance of the Inventory application demonstrates that the public subnet was correctly configured.

####    Submitting your work

+   At the top of these instructions, choose <b>Submit</b> to record your progress and when prompted, choose <b>Yes</b>. 
     
+   If the results don't display after a couple of minutes, return to the top of these instructions and choose <b>Grades</b> 

+   To find detailed feedback on your work, choose <b>Details</b> and then choose <b>View Submission Report</b>.

####    Lab complete