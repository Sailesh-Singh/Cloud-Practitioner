#   LAB6: Introduction to IAM

### Lab overview and objectives
In this lab, you will explore users, groups, and policies in the AWS Identity and Access Management (IAM) service. _Click to [Learn more...](https://awseducate.instructure.com/courses/768/assignments/3158?module_item_id=13574)_

After completing this lab, you will know how to:

+   Exploring pre-created <b>IAM Users and Groups</b> 
+   Inspecting <b>IAM policies</b> as applied to the pre-created groups 
+   Following a <b>real-world scenario</b>, adding users to groups with specific capabilities enabled 
+   Locating and using the <b>IAM sign-in URL</b> 
+   <b>Experimenting</b> with the effects of policies on service access

####   Duration
This lab requires approximately <b>40 minutes</b> to complete.

####    Task 1: Explore the users and groups

In this task, you will explore the users and groups that have already been created for you in IAM. 

+   First, note the Region that you are in; for example, <b>N. Virginia</b>. The Region is displayed in the upper-right corner of the console page.  

+   Choose the <b>Services</b> menu, locate the <b>Security, Identity, & Compliance</b> services, and choose <b>IAM</b>. 

+   In the navigation pane on the left, choose <b>Users</b>. 

    The following IAM users have been created for you: 
    +   user-1 
    +   user-2 
    +   user-3 

+   Choose the name of <b>user-1</b>. 
    +   This brings you to a summary page for user-1. The <b>Permissions</b> tab will be displayed. 
    +   Notice that user-1 does not have any permissions. 

+   Choose the <b>Groups</b> tab. 

    Notice that user-1 also is not a member of any groups. 

+   Choose the <b>Security credentials</b>  tab. 

    Notice that user-1 is assigned a  <b>Console password</b>. This allows the user to access the AWS Management Console. 

+   In the navigation pane on the left, choose <b>User groups</b>. 

    The following groups have already been created for you: 
    +   EC2-Admin 
    +   EC2-Support 
    +   S3-Support 

+   Choose the name of the <b>EC2-Support</b> group. 

    This brings you to the summary page for the <b>EC2-Support</b> group. 

+   Choose the <b>Permissions</b> tab. 

    This group has a managed policy called <b>AmazonEC2ReadOnlyAccess</b> associated with it. Managed policies are prebuilt policies (built either by AWS or by your administrators) that can be attached to IAM users and groups. When the policy is updated, the changes to the policy are immediately applied against all users and groups that are attached to the policy. 

+   Under <b>Policy Name</b>, choose the link for the <b>AmazonEC2ReadOnlyAccess</b> policy. 

+   Choose the <b>{} JSON</b> tab. 

    +   A policy defines what actions are allowed or denied for specific AWS resources. This policy is granting permission to  _List_ and _Describe_  (view) information about Amazon Elastic Compute Cloud (Amazon EC2), Elastic Load Balancing, Amazon CloudWatch, and Amazon EC2 Auto Scaling. This ability to view resources, but not modify them, is ideal for assigning to a support role. 

    +   Statements in an IAM policy have the following basic structure: 
        +   <b>Effect</b> says whether to  _Allow or Deny_ the permissions. 

        +   <b>Action</b> specifies the API calls that can be made against an AWS service (for example,  _cloudwatch:ListMetrics_). 

        +   <b>Resource</b> defines the scope of entities covered by the policy rule (for example, a specific Amazon Simple Storage Service [Amazon S3] bucket or Amazon EC2 instance; an asterisk [ * ] means _any resource_). 

+   In the navigation pane on the left, choose <b>User groups</b>. 

+   Choose the name of the <b>S3-Support</b> group. 

+   Choose the <b>Permissions</b> tab. 

    The S3-Support group has the  <b>AmazonS3ReadOnlyAccess</b> policy attached. 

+   Under <b>Policy Name</b>, choose the link for the <b>AmazonS3ReadOnlyAccess</b>  policy. 

+   Choose the <b>{} JSON</b> tab. 

    This policy has permissions to _Get_  and _List_ for all resources in Amazon S3. 

+   In the navigation pane on the left, choose <b>User groups</b>. 

+   Choose the name of the <b>EC2-Admin</b> group. 

+   Choose the <b>Permissions</b> tab. 

    This group is different from the other two. Instead of a managed policy, the group has an _inline policy_, which is a policy assigned to just one user or group. Inline policies are typically used to apply permissions for specific situations. 

+   Under _Policy Name_, choose the name of the _EC2-Admin-Policy_ policy. 

+   Choose the <b>JSON</b> tab. 

    This policy grants permission to  Describe  information about Amazon EC2 instances, and also the ability to  _Start_ and _Stop_ instances. 

+   At the bottom of the screen, choose  <b>Cancel</b> to close the policy.

####    Business scenario

For the remainder of this lab, you will work with these users and groups to enable permissions that support the following business scenario. 

Your company is growing its use of AWS services, and is using many Amazon EC2 instances and Amazon S3 buckets. You want to give access to new staff depending upon their job function, as indicated in the following table: 

<table>

<th>User</th>
<th>In Group</th>
<th>Permissions</th>

<tr>
    <td>user-1</td>
    <td>S3-Support </td>
    <td>Read-only access to Amazon S3</td>
</tr>

<tr>
    <td>user-2</td>
    <td>EC2-Support</td>
    <td>Read-only access to Amazon EC2</td>
</tr>

<tr>
    <td>user-3</td>
    <td>EC2-Admin</td>
    <td>View, Start, and Stop Amazon EC2 instances</td>
</tr>

</table>

####    Task 2: Add users to groups

You have recently hired _user-1_ into a role where they will provide support for Amazon S3. You will add them to the  _S3-Support_ group so that they inherit the necessary permissions via the attached _AmazonS3ReadOnlyAccess_ policy. 

Ignore any "not authorized" errors that appear during this task. They are caused by your lab account having limited permissions and will not impact your ability to complete the lab.

#####   Add user-1 to the S3-Support group

+   In the left navigation pane, choose  <b>User groups</b>. 
+   Choose the name of the <b>S3-Support</b> group. 
+   On the <b>Users</b> tab, choose <b>Add users</b>. 
+   Select <b>user-1</b>, and choose <b>Add users</b>. 
    On the <b>Users</b> tab, notice that  _user-1_ has been added to the group. 

#####   Add user-2 to the EC2-Support group

You have hired _user-2_ into a role where they will provide support for Amazon EC2. You will add them to the _EC2-Support_  group so that they inherit the necessary permissions via the attached  _AmazonEC2ReadOnlyAccess_ policy. 

+   Use what you learned from the previous steps to add _user-2_ to the _EC2-Support_ group. 

    _user-2_ should now be part of the  _EC2-Support_ group. 

#####   Add user-3 to the EC2-Admin group

You have hired  user-3  as your Amazon EC2 administrator to manage your EC2 instances. You will add them to the  _EC2-Admin_ group so that they inherit the necessary permissions via the attached  _EC2-Admin-Policy_. 

+   Use what you learned from the previous steps to add _user-3_ to the _EC2-Admin_  group. 

    _user-3_ should now be part of the  _EC2-Admin_ group. 

+   In the navigation pane on the left, choose <b>User groups</b>. 

    Each group should have a <b>1</b> in the <b>Users</b> column. This indicates the number of users in each group. 

    If you do not have a <b>1</b> for the  <b>Users</b> column for a group, revisit the previous steps to ensure that each user is assigned to a group, as shown in the table in the <b>Business scenario</b> section. 

####    Task 3: Sign in and test users 

In this task, you will test the permissions of each IAM user in the console. 
#####   Get the console sign-in URL

+   In the navigation pane on the left, choose <b>Dashboard</b>. 

    >Notice the <b>Sign-in URL for IAM users in this account</b> section at the top of the page. The sign-in URL looks similar to the following: <b>https://123456789012.signin.aws.amazon.com/console</b>
    This link can be used to sign in to the AWS account that you are currently using. 

+   Copy the sign-in link to a text editor. 

#####   Test user-1 permissions

+   Open a private or incognito window in your browser. 

+   Paste the sign-in link into the private browser, and press ENTER. 

    You will now sign-in as _user-1_, who has been hired as your Amazon S3 storage support staff. 

+   Sign in with the following credentials: 
    +   <b>IAM user name</b>:   `user-1`
    +   <b>Password:</b>  `Lab-Password1`

+   Choose the <b>Services</b> menu, and choose <b>S3</b>. 

+   Choose the name of one of your buckets, and browse the contents. 

    Because this user is part of the  _S3-Support_ group in IAM, they have permissions to view a list of Amazon S3 buckets and their contents. 

    Now, test whether the user has access to Amazon EC2. 

+   Choose the _Services_ menu, and choose _EC2_. 

+   In the left navigation pane, choose  <b>Instances</b>. 

    You cannot see any instances. Instead, an error message says _you are not authorized to perform this operation_. This user has not been assigned any permissions to use Amazon EC2. 

    You will now sign in as _user-2_, who has been hired as your Amazon EC2 support person. 

+   First, sign out _user-1_ from the console: 
    +   In the upper-right corner of the page, choose <b>user-1</b>. 
    +   Choose <b>Sign Out</b>. 

#####   Test user-2 permissions

+   Paste the sign-in link into the private browser again, and press ENTER. 

+   Sign in with the following credentials: 
    +   <b>IAM user name:</b>  `user-2`
    +   <b>Password:</b>  `Lab-Password2`

+   Choose the <b>Services</b> menu, and choose <b>EC2</b>. 

+   In the navigation pane on the left, choose <b>Instances</b>. 
    +   You are now able to see an EC2 instance. However, you cannot make any changes to Amazon EC2 resources because you have read-only permissions. 
    +   If you cannot see an EC2 instance, then your Region might be incorrect. In the upper-right corner of the page, choose the Region name, and then choose the Region that you were in at the beginning of the lab (for example, <b>N. Virginia</b>). 

+   Select the EC2 instance. 

+   Choose the <b>Instance state</b> menu, and then choose <b>Stop instance</b>. 

+   To confirm that you want to stop the instance, choose <b>Stop</b>. 

    An error message appears and says that _You are not authorized to perform this operation_. This demonstrates that the policy only allows you to view information without making changes. 

    Next, check if _user-2_ can access Amazon S3. 

+   Choose the <b>Services</b> menu, and choose <b>S3</b>. 

    An error message says _You don't have permissions to list buckets_ because  _user-2_ does not have permissions to use Amazon S3. 

    You will now sign-in as _user-3_, who has been hired as your Amazon EC2 administrator. 

+   First, sign out _user-2_ from the console: 
    +   In the upper-right corner of the page, choose <b>user-2</b>. 
    +   Choose <b>Sign Out</b>. 

#####   Test user-3 permissions

+   Paste the sign-in link into the private browser again, and press ENTER. 

+   Sign in with the following credentials: 
    +   <b>IAM user name:</b>  `user-3`
    +   <b>Password:</b>  `Lab-Password3`

+   Choose the <b>Services</b> menu, and choose <b>EC2</b>. 

+   In the navigation pane on the left, choose <b>Instances</b>. 
    +   An EC2 instance is listed. As an Amazon EC2 Administrator, this user should have permissions to  Stop  the EC2 instance. 
    +   If you cannot see an EC2 instance, then your Region might be incorrect. In the upper-right corner of the page, choose the Region name, and then choose the Region that you were in at the beginning of the lab (for example,  <b>N. Virginia</b>). 

+   Select the EC2 instance. 

+   Choose the <b>Instance state</b> menu, and then choose <b>Stop instance</b>. 

+   To confirm that you want to stop the instance, choose <b>Stop</b>. 

    This time, the action is successful because _user-3_ has permissions to stop EC2 instances. The <b>Instance state</b> changes to _Stopping_ and starts to shut down. 

+   Close your private browser window. 

####    Submitting your work

+   At the top of these instructions, choose <b>Submit</b> to record your progress and when prompted, choose <b>Yes</b>. 
     
+   If the results don't display after a couple of minutes, return to the top of these instructions and choose <b>Grades</b> 

+   To find detailed feedback on your work, choose <b>Details</b> and then choose <b>View Submission Report</b>.

####    Lab complete