#   Lab 2: Introduction to Amazon EC2

### Lab overview and objectives

This lab provides you with a basic overview of launching, resizing, managing, and monitoring an Amazon Elastic Compute Cloud (Amazon EC2) instance. 

Amazon EC2 is a web service that provides resizable compute capacity in the cloud. It is designed to make web-scale cloud computing simple and intuitive to use.  _Click to [Learn more...](https://awseducate.instructure.com/courses/768/assignments/3146)_

After completing this lab, you will know how to:

+   Launch a web server with termination protection enabled 
+   Monitor Your EC2 instance 
+   Modify the security group that your web server is using to allow HTTP access 
+   Resize your  EC2 instance to scale 
+   Explore Amazon EC2 limits 
+   Test termination protection 
+   Terminate your EC2 instance 

####   Duration
This lab requires approximately **45** minutes to complete. You will have a total time of **180** minutes to complete this lab.

####    Task 1: Launching your EC2 instance 
<img src="./assets/Lab1_AmazonS3_T1_Start-Lab.png" alt="Lab1_AmazonS3_T1_Start-Lab.png" width="50%" height="80%" ><img src="./assets/Lab2_AmazonEC2_T1_AWS_Management_Console-Services.png" alt="Lab2_AmazonEC2_T1_AWS_Management_Console-Services.png" width="50%" height="80%" >
<small><b>*_Start and Launch AWS Management Console_*</b></small>


+   In the AWS Management Console on the Services menu, choose EC2.
+   In the left navigation pane, choose EC2 Dashboard to ensure that you are on the dashboard page.
+   Choose Launch instance, and then select Launch instance.


#####   Step 1: Name your EC2 instance 

+   In the Name and tags section, for Name, enter Web-Server
+   Choose the Add additional tags link.
+   From the Resource types dropdown list, ensure that both Instances and Volumes are selected.


#####   Step 2: Choose an Amazon Machine Image (AMI)

An Amazon Machine Image (AMI) provides the information required to launch an instance, which is a virtual server in the cloud. An AMI includes the following:

+       A template for the root volume for the instance (for example, an operating system or an application server with applications)
+       Launch permissions that control which AWS accounts can use the AMI to launch instances
+       A block device mapping that specifies the volumes to attach to the instance when it is launched

The <b>Quick Start</b> list contains the most commonly used AMIs. You can also create your own AMI or select an AMI from the AWS Marketplace, an online store where you can sell or buy software that runs on AWS.

+   Locate the <b>Application and OS Images (Amazon Machine Image)</b> section. It is just below the <b>Name and tags</b> section. 
+   In the <b>AMI Machine Image (AMI)</b> box, notice that <b>Amazon Linux 2 AMI</b> is selected by default. Keep this setting.

#####   Step 3: Choose an instance type 

Amazon EC2 provides a wide selection of instance types that are optimized to fit different use cases. Instance types comprise varying combinations of CPU, memory, storage, and networking capacity and give you the flexibility to choose the appropriate mix of resources for your applications. Each instance type includes one or more instance sizes so that you can scale your resources to the requirements of your target workload. 

In this step, you choose a <b>t2.micro</b>  instance. This instance type has 1 virtual CPU and 1 GiB of memory.

+   Keep the default instance type, <b>t2.micro</b>.

#####   Step 4: Configure a key pair

Amazon EC2 uses public key cryptography to encrypt and decrypt login information. To log in to your instance, you must create a key pair, specify the name of the key pair when you launch the instance, and provide the private key when you connect to the instance. 

In this lab, you do not log in to your instance, so you do not require a key pair.

+   In the <b>Key pair (login)</b> section, from the <b>Key pair name - required</b> dropdown list, choose <b>Proceed without a key pair</b>.

#####   Step 5: Configure the network settings

You use this pane to configure networking settings. 

The virtual private cloud (VPC) indicates which VPC you want to launch the instance into. You can have multiple VPCs, including different ones for development, testing, and production.

+   In the <b>Network settings</b> section, choose <b>Edit</b>. 

+   From the <b>VPC - required</b> dropdown list, choose <b>Lab VPC</b>.  

+   In the <b>Network settings</b> section, for  <b>Security group name - required</b>, enter  `Web Server security group`

+   To delete the existing SSH rule, next to  <b>Security group rule 1</b>, choose  <b>Remove</b>. 

#####   Step 6: Add storage

Amazon EC2 stores data on a network-attached virtual disk called Amazon Elastic Block Store (Amazon EBS). 

You launch the EC2 instance using a default 8 GiB disk volume. This is your root volume (also known as a boot volume).

+   In the <b>Configure storage</b> pane, keep the default storage configuration.

#####   Step 7: Configure advanced details

+   Expand the  Advanced details  pane. 

+   From the  Termination protection  dropdown list, choose   Enable . 

+   Copy the following commands, and paste them into theIn the  User data  text box. 

        #!/bin/bash 
        yum -y install httpd 
        systemctl enable httpd 
        systemctl start httpd 
        echo '<html><h1>Hello From Your Web Server!</h1></html>' 
        > /var/www/html/index.html 

    The script does the following:

    +   Install an Apache web server (httpd)
    +   Configure the web server to automatically start on boot 
    +   Activate the Web server 
    +   Create a simple web page

    #####   Step 8: Launch an EC2 instance

+   In the <b>Summary</b> section, choose  <b>Launch instance</b>. 
+   Choose <b>View all instances</b> 

The instance appears in a <b>Pending</b> state, which means that it is being launched. It then changes to <b>Running</b>, which indicates that the instance has started booting. There will be a short time before you can access the instance. 

The instance receives a public Domain Name System (DNS) name that you can use to contact the instance from the Internet. 

Next to your <b>Web-Server</b>, select the   check box. The <b>Details</b> tab displays detailed information about your instance. 

To view more information in the <b>Details</b>  tab, drag the window divider upward. 

Review the information displayed in the  <b>Details, Security</b> and <b>Networking</b> tabs. 

+   Wait for your instance to display the following: 

    <b>Note:</b>  Refresh if needed.

    +   <b>Instance State:</b>   Running 
    +   <b>Status Checks:</b>    2/2 checks passed 