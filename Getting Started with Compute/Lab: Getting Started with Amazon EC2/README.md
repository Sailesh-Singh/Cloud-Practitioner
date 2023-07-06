# Lab: Getting Started with Amazon EC2

### Lab overview and objectives

This lab provides you with a basic overview of launching, resizing, managing, and monitoring an Amazon Elastic Compute Cloud (Amazon EC2) instance. _Click to [Learn more ...](https://awseducate.labs.awsevents.com/sa/lab/arn%3Aaws%3Alearningcontent%3Aus-east-1%3A470679935125%3Ablueprintversion%2FCUR-TF-100-EDSTOR-1%2F01-lab-s3%3A1.0.2-cff75cb4/en-US)_


####    Objectives
After completing this lab, you will know how to do the following:

+   Launch an EC2 instance with termination protection turned on.

+   Monitor your EC2 instance.

+   Modify the security group that your web server is using to allow HTTP access.

+   Connect to your EC2 instance using the AWS Systems Manager Fleet Manager.

+   Manage the state of an EC2 instance.

+   Change your  EC2 instance type.

+   Test termination protection.

+   Explore Amazon EC2 limits.

####   Duration
This lab requires approximately **60 minutes** to complete. We will have a total time of **180 minutes** to complete this lab.

#### Prerequisites

This lab requires the following:

+   A notebook computer running Microsoft Windows, macOS, or Linux (Ubuntu, SUSE, or Red Hat)
+   An internet connection
+   For Microsoft Windows users, administrator access to the computer
+   The latest version of an internet browser such as Chrome or Firefox

><b>_Note:</b> This lab is incompatible with Internet Explorer 11. Use a different browser to launch this lab._

---


####    Task 1: Launching your EC2 instance

In the AWS Management Console on the Services menu, enter EC2. From the search results, choose EC2.

In the left navigation pane, choose EC2 Dashboard to ensure that you are on the dashboard page.

In the Launch instance section, choose the Launch instance dropdown list, and then choose Launch instance.

+   #####  Step 1: Name your EC2 instance
 
    +   In the Name and tags pane, in the Name text box, enter Web-Server
    +   Choose the Add additional tags link.
    +   From the Resource types dropdown list, select Instances and Volumes.
     

+   #####  Step 2: Choose an AMI

    +   Locate the Application and OS Images (Amazon Machine Image) section. It is just below the Name and tags section.
    +   In the search box, enter Windows Server 2019 Base and press Enter.
    +   Next to Microsoft Windows Server 2019 Base, choose Select.
    +   Choose Confirm Changes.
 

+   #####  Step 3: Choose an instance type

    +   In the Instance type section, keep the default instance type, t2.micro.
 

+   #####  Step 4: Configure a key pair

    +   In the Key pair (login) section, from the Key pair name - required dropdown list, choose Proceed without a key pair (not recommended).
     

+   #####  Step 5: Configure the network settings

    +   In the Network settings section, choose Edit.
    
    +   From the VPC - required dropdown list, choose Lab VPC.
    
    +   For Security group name - required, enter `Web Server security group`
    
    +   To delete the existing RDP rule,  next to Security group rule 1, choose Remove.
    <img src="vpc_required.PNG" alt="vpc_requiredg" style="height: 100%; width:100%;"/>

+   #####  Step 6: Add storage

    +   In the Configure storage section, keep the default storage configuration.
     

+   #####  Step 7: Configure advanced details
 
    
    +   Expand the Advanced details section.
    
    +   For IAM instance profile, choose the role that has LabInstanceProfile in the name.
    
    
    +   From the Termination protection dropdown list, choose Enable.
    
      
    
    +   Copy the following commands, and paste them into the User data text box.
    
    ```
    <powershell>
    # Installing web server
    Install-WindowsFeature -name Web-Server -IncludeManagementTools
    # Getting website code
    wget https://us-west-2-tcprod.s3.us-west-2.amazonaws.com/courses/CUR-TF-100-EDCOMP/v1.0.2.prod-5a679941/01-lab-ec2/scripts/code.zip -outfile "C:\Users\Administrator\Downloads\code.zip"
    # Unzipping website code
    Add-Type -AssemblyName System.IO.Compression.FileSystem
    function Unzip
    {
        param([string]$zipfile, [string]$outpath)
        [System.IO.Compression.ZipFile]::ExtractToDirectory($zipfile, $outpath)
    }
    Unzip "C:\Users\Administrator\Downloads\code.zip" "C:\inetpub\"
    # Setting Administrator password
    $Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force
    $UserAccount = Get-LocalUser -Name "Administrator"
    $UserAccount | Set-LocalUser -Password $Secure_String_Pwd
    </powershell>

    
    ```
    
    The script does the following:
    
    +   Installs a Microsoft Internet Information
    +    Services (IIS) web server
    +   Creates a simple web site
    +   Sets the password for the Administrator user
     

+   #####  Step 8: Launch an EC2 instance

 

    +   In the Summary section, choose Launch instance.
    
    +   Choose View all instances
    
    +   Next to your Web-Server, select the  check box. The Details tab displays detailed information about your instance
    
    <img src="instance_launch.PNG" alt="instance_launch" style="height: 100%; width:100%;"/>


#### Task 2: Monitor your instance

+   Choose the Status checks tab.


+   At the top of the page, choose the Actions  dropdown menu. Select Monitor and troubleshoot  Get system log.

+   Scroll through the log and review the messages in the output.

+   To return to the Amazon EC2 dashboard, choose Cancel.

+   With your Web-Server selected, choose the Actions  dropdown menu, and select Monitor and troubleshoot  Get instance screenshot.

+   At the bottom of the page, choose Cancel.

 

### Task 3: Updating your security group and accessing the web server


+   Select the check box next to the Amazon EC2 Web-Server that you created, and then choose the Details tab.

+   Copy the Public IPv4 address of your instance to your clipboard.


+   Keep the browser tab open, but return to the EC2 Management Console tab.

+   In the left navigation pane, choose Security Groups.

+   Next to Web Server security group, select the  check box.

+   Choose the Inbound rules tab.

The security group currently has no rules.

+   Choose Edit inbound rules, and then choose Add rule, and configure the following options:

Type: Choose HTTP.
Source: Choose Anywhere-IPv4.

>   <b>Note:</b> Notice the "Rules with source of 0.0.0.0/0 allow all IP addresses to access your instance. We recommend setting security group rules to allow access from known IP addresses only." While this is true and common best practice, this lab allows access from any IP address (Anywhere) to simplify both the security group configuration and testing of the website running on your EC2 instance.

 <img src="3.PNG" alt="Connecting " style="height: 100%; width:100%;"/>
 

+   Choose Save rules

+   Return to the web server browser tab with the public IPv4 address that you previously opened, and choose  to refresh the page.
 

#### Task 4: Connecting to your instance using AWS Systems Manager Fleet Manager


+   In the AWS Management Console on the Services menu, search for and select Systems Manager.

+   In the left navigation pane, select Fleet Manager.

+   Under Managed nodes, select  your Web-Server EC2 instance. 

+   From the Node actions dropdown list, choose Connect with Remote Desktop.

A new tab opens.

+   Enter the following values:
    
    +   Username: `Administrator`
    +   Password: `P@ssW0rD!`
+   Choose Connect.

+   To disconnect from your Web-Server instance, choose End session. 

+   In the pop-up window, choose End session again .
 <img src="4.PNG" alt="Connecting " style="height: 100%; width:100%;"/>
 

#### Task 5: Resizing your instance

#####   Stop your instance

Before you can resize an instance, you must stop it.

When you stop an instance, it is shut down. There is no charge for a stopped EC2 instance, but the storage charge for attached EBS volumes remains.

+   From the AWS Management Console on the Services menu, choose EC2

+   On the EC2 Management Console, in the left navigation pane, choose Instances.

+   Select the check box next to your Web-Server instance. At the top of the page, choose the Instance state  dropdown menu, and choose Stop instance.

+   In the Stop instance? pop-up window, choose Stop.

    Your instance performs a normal shutdown and then stops running.

+   Wait for the Instance state to display Stopped.

 

#####   Change the instance type
+   Select the check box next to your Web-Server. From the Actions  dropdown menu, select Instance settings  Change instance type, and then configure the following option:

Instance type: Select t2.nano.

+   Choose Apply

>   Note: You are restricted from using other instance types in this lab.

#####   Start the resized instance
When the instance is started again, it is a t2.nano instance. You now start the instance again, which has less memory but more disk space.

 +   In left navigation pane, choose Instances. Next to your Web-Server, select the  check box.

+   From the Instance state  dropdown menu, choose Start instance.

+   Once the instance is restarted, the Instance state displays Running.


 <img src="5.PNG" alt="Resizing your instance " style="height: 100%; width:100%;"/>

#### Task 6: Testing termination protection 

+   Select the check box next to your Web-Server instance. From the Instance state  dropdown menu, choose Terminate instance.

+       Notice the message next to the Terminate instance option: Termination protection is enabled for one or more of the selected instances. 


+   From the Actions dropdown menu, choose Instance settings, and then choose Change termination protection.

+   Clear the check box for  Enable.

+   Choose Save.

+   Now, try to terminate the instance again.
    The instance state will now successfully be terminated.

 

#### Task 7: Exploring EC2 limits 

+   In the left navigation pane, choose Limits.


###  END OF LAB 
 