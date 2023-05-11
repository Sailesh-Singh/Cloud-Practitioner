#   LAB4: Creating an Amazon RDS Database

### Lab overview and objectives
Traditionally, creating a database can be a complex process that requires either a database administrator or a systems administrator. In the cloud, you can simplify this process by using Amazon Relational Database Service (Amazon RDS). _Click to [Learn more...](https://awseducate.instructure.com/courses/768/assignments/3156)_

After completing this lab, you will know how to:

+   Launch a database using Amazon RDS 
+   Configure a web application to connect to the database instance

####   Duration
This lab requires approximately  30 minutes  to complete. 

####    Task 1: Creating an Amazon RDS database

+   In the AWS Management Console, choose Services, and then choose RDS.
+   Choose Create database 
+   Under Engine options, select MySQL.
    The options include several use cases, ranging from enterprise-class databases to Dev/Test systems. In the options, you might notice Amazon Aurora. Aurora is a MySQL-compatible system that was re-architected for the cloud. If your company uses large-scale MySQL or PostgreSQL databases, Aurora can provide enhanced performance. 

+   In the  Templates  section, select   Dev/Test . 

    You can now select a database configuration, including software version, instance class, storage, and login settings. The Multi-AZ deployment option automatically creates a replica of the database in a second Availability Zone for high availability.  

+   In  Availability and durability  section, choose   Single DB instance . 

+   In the  Settings  section, configure the following options: 
    +   DB instance identifier: `inventory-db`
    +   Master username: `admin`
    +   Master password: `lab-password`
    +   Confirm password: `lab-password`

+   In the  DB instance class  section, configure the following options: 
    +   Select   Burstable classes (includes t classes) . 
    +   Select  db.t3.micro . 

+   In the  Storage  section, configure the following options: 
    +   Storage type:  Select  General Purpose SSD (gp2) . 
    +   Allocated storage:  Enter  20 GiB . 

+   In the  Connectivity  section, configure the following option:  
    +   Virtual private cloud (VPC):  Lab VPC 

+   In the  Connectivity  section, for  Existing VPC security groups , choose the  X  on  default  to remove this security group. Then choose the dropdown list, and select  DB-SG  to add it. 

+   Scroll to the  Monitoring  section, and clear (deselect) the  Enable Enhanced monitoring  option. 

+   Scroll to the  Additional configuration  section, and choose   to expand it.  

+   For  Initial database name , enter  inventory

	This is the logical name of the database that the application will use. 

	>You can review the many other options displayed on the page, but leave them set to their default values. Options include automatic backups, the ability to export log files, and automatic version upgrades.  
    The ability to activate these features with check boxes demonstrates the power of using a fully managed database solution instead of installing, backing up, and maintaining the database yourself. 

+   At the bottom of the page, choose Create database 

	You should receive this message:  Creating database inventory-db.

    If you receive an error message that mentions  rds-monitoring-role ,  	confirm that you   have cleared the  Enable Enhanced monitoring  option in the previous step, and then try again. 

	Before you continue to the next task, the database instance status must be  Available . This process could take several minutes.  