#   LAB4: Creating an Amazon RDS Database

### Lab overview and objectives
Traditionally, creating a database can be a complex process that requires either a database administrator or a systems administrator. In the cloud, you can simplify this process by using Amazon Relational Database Service (Amazon RDS). _Click to [Learn more...](https://awseducate.instructure.com/courses/768/assignments/3156)_

After completing this lab, you will know how to:

+   Launch a database using Amazon RDS 
+   Configure a web application to connect to the database instance

####   Duration
This lab requires approximately <b>30 minutes</b> to complete. 

####    Task 1: Creating an Amazon RDS database

+   In the <b>AWS Management Console</b>, choose <b>Services</b>, and then choose <b>RDS</b>.
+   Choose <b>Create database</b> 
+   Under <b>Engine options</b>, select <b>MySQL</b>.
    The options include several use cases, ranging from enterprise-class databases to Dev/Test systems. In the options, you might notice Amazon Aurora. Aurora is a MySQL-compatible system that was re-architected for the cloud. If your company uses large-scale MySQL or PostgreSQL databases, Aurora can provide enhanced performance. 

+   In the <b>Templates section</b>, select <b>Dev/Test</b>. 

    You can now select a database configuration, including software version, instance class, storage, and login settings. The Multi-AZ deployment option automatically creates a replica of the database in a second Availability Zone for high availability.  

+   In <b>Availability and durability</b> section, choose <b>Single DB instance</b>. 

+   In the <b>Settings</b> section, configure the following options: 
    +   <b>DB instance identifier:</b> `inventory-db`
    +   <b>Master username:</b> `admin`
    +   <b>Master password:</b> `lab-password`
    +   <b>Confirm password:</b> `lab-password`

+   In the <b>DB instance class</b> section, configure the following options: 
    +   Select <b>Burstable classes (includes t classes)</b>. 
    +   Select <b>db.t3.micro</b>. 

+   In the <b>Storage</b> section, configure the following options: 
    +   <b>Storage type:</b> Select <b>General Purpose SSD (gp2)</b>. 
    +   <b>Allocated storage:</b> Enter `20` <b>GiB</b>. 

+   In the <b>Connectivity</b> section, configure the following option:  
    +   <b>Virtual private cloud (VPC):  Lab VPC</b> 

+   In the  <b>Connectivity</b> section, for <b>Existing VPC security</b> groups, choose the <b>X</b> on <b>default</b>  to remove this security group. Then choose the dropdown list, and select <b>DB-SG</b> to add it. 

+   Scroll to the <b>Monitoring</b> section, and clear (deselect) the <b>Enable Enhanced monitoring</b> option. 

+   Scroll to the <b>Additional configuration</b> section, and choose to expand it.  

+   For <b>Initial database name</b>, enter `inventory`

	This is the logical name of the database that the application will use. 

	>You can review the many other options displayed on the page, but leave them set to their default values. Options include automatic backups, the ability to export log files, and automatic version upgrades.  
    The ability to activate these features with check boxes demonstrates the power of using a fully managed database solution instead of installing, backing up, and maintaining the database yourself. 

+   At the bottom of the page, choose <b>Create database</b> 

	You should receive this message:  <b>Creating database inventory-db</b>.

    If you receive an error message that mentions  <b>rds-monitoring-role</b>, confirm that you have cleared the <b>Enable Enhanced monitoring</b> option in the previous step, and then try again. 

	Before you continue to the next task, the database instance status must be <b>Available</b>. This process could take several minutes.

####    Task 2: Configuring web application communication with a database instance

This lab automatically deployed an Amazon Elastic Compute Cloud (Amazon EC2) instance with a running web application. You must use the IP address of the instance to connect to the application. 

+   On the <b>Services</b> menu, choose <b>EC2</b>. 
+   In the left navigation pane, choose  Instances . 

In the center pane, there should be a running instance that is named <b>App Server</b>. 

+   Select the check box for the <b>App Server</b> instance. 
+   In the <b>Details</b> tab, copy the <b>Public IPv4 address</b> to your clipboard. 

Tip:  If you hover over the IP address, a copy icon appears. To copy the displayed value, choose the icon. 

+   Open a new web browser tab, paste the IP address into the address bar, and then press Enter. 

The web application should appear. It does not display much information because the application is not yet connected to the database. 

+   Choose   <b>Settings</b>. 

You can now configure the application to use the Amazon RDS database instance that you created earlier. You first retrieve the database endpoint so that the application knows how to connect to a database. 

+   Return to the AWS Management Console, but do not close the application tab. (You will return to it soon.) 
+   On the <b>Services</b> menu, choose <b>RDS</b>. 
+   In the left navigation pane, choose <b>Databases</b>. 
+   Choose <b>inventory-db</b>. 
+   Scroll to the <b>Connectivity & security</b> section, and copy the <b>Endpoint</b> to your clipboard. 

It should look similar to this example: <b>inventory-db.crwxbgqad61a.rds.amazonaws.com</b> 

+   Return to the browser tab with the inventory application, and enter the following values: 
    +   For  <b>Endpoint</b>, paste the endpoint you copied earlier. 
    +   For  <b>Database</b>, enter `inventory`
    +   For  <b>Username</b>, enter `admin`
    +   For  <b>Password</b>, enter `lab-password`
    +   Choose <b>Save</b>. 

		The application will now connect to the database, load some initial data, and display information. 

+   You can use the web application to Add inventory,   edit, and delete inventory information. 

 >The inventory information is stored in the Amazon RDS MySQL database that you created earlier in the lab. This means that in the event of any failure in the application server, you will not lose any data. It also means that multiple application servers can access the  same data. 

+   Insert new records into the table. Ensure that the table has <b>5</b> or more inventory records before submitting your work. 

 You have now successfully launched the application and connected it to the database. 

><b>Optional:</b> To access the saved parameters, go to the AWS Management console. On the <b>Services</b> menu, choose <b>Systems Manager</b>. In the left navigation menu, choose <b>Parameter Store</b>.  

####    Submitting your work

+   At the top of these instructions, choose <b>Submit</b> to record your progress and when prompted, choose <b>Yes</b>. 
     
+   If the results don't display after a couple of minutes, return to the top of these instructions and choose <b>Grades</b> 

+   To find detailed feedback on your work, choose <b>Details</b> and then choose <b>View Submission Report</b>.

####    Lab complete 