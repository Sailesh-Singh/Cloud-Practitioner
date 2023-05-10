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

####    Task 2: Monitoring your instance

Monitoring is an important part of maintaining the reliability, availability, and performance of your EC2 instances and your AWS solutions.

+   Choose the <b>Status checks</b> tab.
+   Choose the <b>Monitoring</b> tab.
+   At the top of the page, choose the <b>Actions</b>▼ dropdown menu. Select <b>Monitor and troubleshoot ►Get system log</b>.
+   Scroll through the output, and note that the HTTP package was installed from the user data that you added when you created the instance. The entries in the system log should be similar to the following example: 

    ```
    [   26.760639] cloud-init[3280]: Installed: 

    [   26.770051] cloud-init[3280]: httpd.x86_64 0:2.4.52-1.amzn2 

    [   26.777748] cloud-init[3280]: Dependency Installed: 

    [   26.781750] cloud-init[3280]: apr.x86_64 0:1.7.0-9.amzn2 

    [   26.793739] cloud-init[3280]: apr-util.x86_64 0:1.6.1-5.amzn2.0.2 

    [   26.796595] cloud-init[3280]: apr-util-bdb.x86_64 0:1.6.1-5.amzn2.0.2 

    [ 26.805964] cloud-init[3280]: generic-logos-httpd.noarch 0:18.0.0-4.amzn2 

    [ 26.817765] cloud-init[3280]: httpd-filesystem.noarch 0:2.4.52-1.amzn2 

    [   26.829760] cloud-init[3280]: httpd-tools.x86_64 0:2.4.52-1.amzn2 

    [ 26.833753] cloud-init[3280]: mailcap.noarch 0:2.1.41-2.amzn2 

    [   26.845761] cloud-init[3280]: mod_http2.x86_64 0:1.15.19-1.amzn2.0.1 

    [   26.849762] cloud-init[3280]: Complete! 
    ```

+   To return to the Amazon EC2 dashboard, choose <b>Cancel</b>.

+   With your <b>Web-Server</b> selected, choose the <b>Actions</b>▼dropdown menu, and select  <b>Monitor and troubleshoot</b>►<b>Get instance screenshot</b>.

    This option shows you what your EC2 instance console would look like if a screen were attached to it. It is essentially a command line interface.

+   At the bottom of the page, choose <b>Cancel</b>. 


####    Task 3: Updating your security group and accessing the web server

When you launched the EC2 instance, you provided a script that installed a web server and created a simple web page. In this task, you access content from the web server. 

+   Select the check box next to the Amazon EC2 <b>Web-Server</b> that you created, and then choose the <b>Details</b> tab. 

+   Copy the <b>Public IPv4 address</b> of your instance to your clipboard. 

+   In your web browser, open a new tab, paste the IP address that you just copied, and then press Enter. 

    <b>Question:</b> Are you able to access your web server? Why not? 

    You are not currently able to access your web server because the security group is not permitting inbound traffic on port 80, which is used for HTTP web requests. This is a demonstration of how to use a security group as a firewall to restrict the network traffic that is allowed in and out of an instance. 

    To correct this issue, you now update the security group to permit web traffic on port 80. 

+   Keep the browser tab open, but return to the <b>EC2 Management Console</b> tab. 

+   In the left navigation pane, choose  <b>Security Groups</b>. 

+   Next to <b>Web Server security group</b>, select the check box. 

+   Choose the <b>Inbound rules</b> tab. 

    The security group currently has no rules. 

+   Choose <b>Edit inbound rules</b>, and then choose <b>Add rule</b> and configure the following options:

    +   <b>Type:</b> Choose <b>HTTP</b>. 
    +   <b>Source:</b> Choose  <b>Anywhere-IPv4</b>. 

>    <b>Note:</b>  Notice the  _"Rules with source of 0.0.0.0/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only."_  While this is true and common best practice, this lab allows access from any IP address (Anywhere) to simplify both the security group configuration and testing of the website running on your EC2 instance. 

     

+   Choose <b>Save rules</b> 

+   Return to the web server browser tab with the public IPv4 address that you previously opened, and choose to refresh the page. 

    You should see the message <b>Hello From Your Web Server!</b>

####    Task 4: Resizing your instance - instance type and EBS volume 