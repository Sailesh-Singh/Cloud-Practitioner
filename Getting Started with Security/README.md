#   [Getting Started with Security](https://awseducate.instructure.com/courses/890)

##	Overview
AWS Identity and Access Management (IAM) is a web service that helps you securely control access to Amazon Web Services (AWS) resources. IAM enables you to securely manage access to AWS offerings and resources. Using IAM, you can create and manage AWS users and groups and use permissions to allow and deny their access to AWS resources. IAM is a feature of your AWS account that’s offered at no additional charge. You will be charged only for use of other AWS services by your users.

In this course, you acquire the knowledge that we need to start using AWS Identity and Access Management (IAM). We learn about the key concepts and features of IAM. We learn how to write security policies, set up users, groups, and roles, apply permissions, and review credentials. You also learn about additional AWS security services. 


##	Objectives
By the end of this course, we will be able to do the following:

+   Describe security fundamental concepts.
+   Explain AWS IAM features, benefits, and use cases.
+   Discuss how to create and configure IAM user, groups, and roles.
+   Discuss IAM policies.
+   Discuss how to setup ms.
+   Discuss how to setup multi-factor authentication (MFA).
+   Describe how to set up password policies.
+   Identify other AWS security services.

---

# Getting started with Security

####    In this module
+   Introduction to security
+   Introduction to AWS IAM
+   Using IAM
+   Additional AWS Security Services

####    IT security

<img src="assets/IT security1.PNG" alt="security" style="height:100%; width:100%;">

<img src="assets/IT security2.PNG" alt="security" style="height:100%; width:100%;">

####    Principle of least privilege

<img src="assets/privilege1.PNG" alt="privilege" style="height:100%; width:100%;">

<img src="assets/privilege2.PNG" alt="privilege" style="height:100%; width:100%;">

<img src="assets/privilege3.PNG" alt="privilege" style="height:100%; width:100%;">
 
####    Identity and access management
   working sessions can have thousands of users that will need different level of permissions, therefore this need to be carefully managed.

   To do this organization should use IAM.
   <img src="assets/IAM.PNG" alt="IAM" style="height:100%; width:100%;">

####    Authentication and authorization
1.      Authentication
    It is a basic computer security concept: a user or system must first prove their identity. Consider how you authenticate yourself when you go to the airport and you want to get through airport security so that you can catch your flight. In this situation, you must present some form of identification to the security official to prove who you are before you can enter a restricted area. A similar concept applies for gaining access to IT resources.

2.      Authorization
    It is the process of determining what permissions a user should be granted. After a user has been authenticated, they must be authorized to access the IT resource or data that they are requesting.    

<b> Authentication and authorization together</b>

    First, user enter username and password. The username and password are verified by database. If the entered password or username does not match then user return to login again. If entered information matches authentication is completed. After this the authorization process determine permission the user has to the applications.

<img src="assets/aa.PNG" alt="security" style="height:100%; width:100%;">

### Layers of security
IT security starts with protecting physical data center then actual data files. The forming layer of IT security are:
+   Perimeter layer
    +   Building:  
    Aws data centers are housed in nondescript, undisclosed facilities. They are protected by a number of security features such as security guards, fencing, security feeds, and other security measures.

    +   Surveillance:
    Professional security staff use video surveillance, intrusion detection, access log monitoring systems and other electronic means. Entrances are secured with devices that sound alarms if a door is forced or held open.

    +   Employee scrutinization:
    Only AWS employees who routinely need access are given permissions to relevant areas of the facility based on job function. If an employee doesn't have an ongoing business need to be at a data center, they have to go through the visitor process and have an escort assigned throughout the duration of their visit.

    +   Principle of least privilege:
    AWS limits access to  pre-approved areas and only provides data center access to employees and contractors who have a legitimate business need for such privileges.


+       Environment layer
    +   Mitigate environmental risks:
    AWS carefully chooses their data center locations to mitigate environmental risks like flooding, extreme weather, and seismic activity.

    +   High availability and performance:
    Customers requiring high availability and performance can deploy their applications across multiple Availability Zones in the same region. This provides lower latency, reduced costs and data compliance, while opening up the potential to engineer for fault tolerance.

    +   AWS business continuity testing
    To mitigate and prepare for the unexpected, AWS tests their business Continuity Plan regularly with drills that simulate different scenarios.

    +   Energy saving:
    Companies generally use 77% fewer servers, 84% less power, and tap into a 28% cleaner mix of solar and wind power in the AWS Cloud versus their own traditional data centers.

+       Infrastructure layer
    +   Fire detection:
    Automatic fire detection and suppression equipment reduces the risk of fire-related accidents. Smoke detection sensors are in all data center environments, mechanical and electrical spaces, chiller rooms and generator equipment rooms.

    +   Monitoring:
    AWS monitors electrical, mechanical and life support systems. Preventive maintenance is regularly performed.

    +   Climate control:
    It is ued to maintain a constant operating temperature for servers and other hardware. This prevents overheating and reduces the possibility of service outages.

    +   Power:
    Electrical systems are fully redundant and maintainable without impact power for critical and essential loads and generators provide backup power for the entire facility.

+   Data layer
<img src="assets/data layer.PNG" alt="security" style="height:100%; width:100%;">
    
####    AWS Shared Responsibility
<img src="assets/shared responsibility1.PNG" alt="security" style="height:100%; width:100%;">
<img src="assets/shared responsibility2.PNG" alt="security" style="height:100%; width:100%;">
<img src="assets/shared responsibility3.PNG" alt="security" style="height:100%; width:100%;">
Examples
<img src="assets/shared responsibility4.PNG" alt="security" style="height:100%; width:100%;">


####    Introduction to Amazon S3

#####   Getting started with AWS Identity and Access Management(IAM)

#####       IAM credentials types
User is given access to <b>AWS Management Console</b> and <b>Programmatic access</b>
For AWS Management Console user is given username and password and for programmatic access user is given access key.

1.      AWS Management Console:
<img src="assets/aws management console.PNG" alt="security" style="height:100%; width:100%;">

2.      Programmatic access:
<img src="assets/programmatic access.PNG" alt="security" style="height:100%; width:100%;">

####    Multi-factor authentication(MFA)
<img src="assets/mfa.PNG" alt="security" style="height:100%; width:100%;">

<img src="assets/mfa2.PNG" alt="security" style="height:100%; width:100%;">

To create, modify or delete an easy to instance we need IAM users credential that has necessary information to perform those functions.
<img src="assets/EC2.PNG" alt="security" style="height:100%; width:100%;">

IAM Identity Center:
+   Securely create or connect your workforce identities
+   Manage their access centrally across AWS accounts and applications.

#####   IAM use cases
1.      Apply detailed permissions
    AWS IAM lets you create and apply permissions based on user attributes-such as department, job role, and team name-by using attribute-based access control.
    +   Application developer
    +   Application tester

2.      Manage per-account and application access
    With AWS IAM, you can manage per-account identities. This means that you can provide multi-account access and application assignments across AWS.

3.      Establish organization-wide guardrails on AWS
    AWS IAM provides you with the ability to establish organization-wide and preventative guardrails on AWS. You can do this by using services control policies to establish permissions guardrails for IAM users and roles, and implement a data perimeter around your accounts in AWS Organizations.

4.      Set, verify and right-size permissions.
    AWS IAM is built to help you set, verify, and right-size user permissions in accordance with the least privilege principle policy. You can streamline permissions management and use cross-account findings as you set, verify and refine policies on the journey toward least privilege.

#####   IAM costs
<img src="assets/IAM costs.PNG" alt="security" style="height:100%; width:100%;">

#####   Option for using IAM
1.      AWS Management Console:
    The AWS Management Console is a graphical user interface that you can use to launch, configure, and manage AWS services from.

2.      AWS Command Line Interface(CLI):
    The AWS Command Line Interface(CLI) is a unified tool to manage your AWS services. With just one tool to download and configure, you can provision and control multiple AWS services from the command line and automate them through scripts.

3.      AWS Software Development kit(SDK):
    SDKs take the complexity out of coding by providing languages-specific APIs for AWS services. With AWS SDKs, you can launch AWS services, like EC2 instances, using a variety of codes, such as JavaScript, Python, Java, .NET, C++ and more.

#####   Root user
Root user have key access to the following:
<img src="assets/root user.PNG" alt="root" style="height:100%; width:100%;">

<b>To ensure the safety of root user follow these practices:</b>

+   Choose a strong password.
+   Enable multi-factor authentication.
+   Never share your root user password or access keys.
+   Disable or delete root user access keys.
+   Create a power IAM user (with full access to your AWS account, except for building) for administrative tasks.

#####       IAM policies
Policies can be attached to any IAM entity such as user groups or role.
#####   IAM policies :
    Affects when a user requests access to resources
    what actions allowed
    which resources to allow the actions on

<img src="assets/IAM policy.PNG" alt="root" style="height:100%; width:100%;"> 

<b>Single statement</b>
<img src="assets/policy1.PNG" alt="root" style="height:100%; width:100%;">

<img src="assets/policy2.PNG" alt="root" style="height:100%; width:100%;">

<img src="assets/policy3.PNG" alt="root" style="height:100%; width:100%;">

<img src="assets/policy4.PNG" alt="root" style="height:100%; width:100%;">

<b>Multiple statement</b>
<img src="assets/multiple policy1.PNG" alt="root" style="height:100%; width:100%;">

<img src="assets/multiple policy2.PNG" alt="root" style="height:100%; width:100%;">

#####   Identity based policies
1.      AWS-managed policies
    AWS managed policies are managed policies that are created and managed by AWs. If you are new to using policies, we recommend that you start by using AWS managed policies. IAM has a library of over 1,000 AWS managed policies.

2.      Customer-managed policies
    It is managed policies that you create and manage in your AWS account. Customer managed policies provide more precise control over your policies than AWS managed policies. You can create and edit an IAM policy in the visual editor or by creating the JSON policy document directly.

3.      Inline policies
    It is policies that you create and manage and that are embedded directly into a single user, group or role. Using inline policies to grant permissions to users is high maintenance and not recommended.    

#####   Resource based policies
<img src="assets/resource based policies.PNG" alt="root" style="height:100%; width:100%;">

#####   Resource and Identity compared
<img src="assets/resource based policies.PNG" alt="root" style="height:100%; width:100%;">  

#####   Conflicting policies
<img src="assets/conflicting policies.PNG" alt="root" style="height:100%; width:100%;">

######  IAM groups
<img src="assets/IAM groups.PNG" alt="root" style="height:100%; width:100%;">
<img src="assets/IAM groups2.PNG" alt="root" style="height:100%; width:100%;">

#####   IAM roles
<img src="assets/IAM roles.PNG" alt="root" style="height:100%; width:100%;">

#####   IAM roles trust policy
<img src="assets/IAM trust policy.PNG" alt="root" style="height:100%; width:100%;">

#####   Use case for roles
1.      Roles for IAM user
    With roles, you don't have to share long-term security credentials for each user that requires access to a resource. This eliminates the need to create multiple accounts for individual users. Therefore, roles can make managing permissions easier and more secure.

2.      Roles for AWS services
    Some AWS services can also assume an IAM role to perform actions in your AWS account on your behalf. When you are configuring such services, you need to define the role for the services to assume. The role needs to include to all the permissions required so that the service assuming the role has the proper permissions. These roles are referred to as services linked roles. You will commonly see them associate with Amazon EC2 and AWS Lambda.

3.      Roles for external users
    If you already manage user identities outside of AWS, you can use IAM roles to grant users access to AWS. Imagine that you have a business with 5,000 employees that must access an AWS account. You already have an identity provider in place that allows your employed to log in to their work laptops. Instead of creating 5,000 IAM accounts, you can use IAM roles to grant access to AWS through existing identities from your enterprise user directory, known as federated users.

#####   IAM Access Analyzer
<img src="assets/IAM access.PNG" alt="root" style="height:100%; width:100%;">        

1.      Set detailed permissions
    Policy generation with IAM Access Analyzer generates a detailed policy based on the access activity  that is captured in your logs. This means that after you build and run an application, you can generate policies that grant only the required permissions to operate the application.
    Policy validation with IAM Access Analyzer guides you to author and validate secure and functional policies with more than 100 policy checks. You can use these checks while creating new policies or to validate existing policies.

2.      Verify Intended permission
<img src="assets/verify.PNG" alt="root" style="height:100%; width:100%;">     

3.      Refine permissions by removing unused access
<img src="assets/refine.PNG" alt="root" style="height:100%; width:100%;"> 

#####   IAM credential reports
    Lists all users in your account

    Details the status of their various credentials:
+   Passwords
+   Access keys
+   MFA devices
+   And more   

You can use to credentials reports to assist you in auditing and compliance efforts.
You can use report already effects of credential lifecycle requirement.
provide report to the external auditor.

#####   IAM Scenario
1.      Scenario:
    You opened a new AWS account. The account consists of five teams of 10 developers. Your firs tasks are the following:
    +   You need to create 50 users. 40 of them are developers, five are managers, and five are administrators. The 40 developers will have the same permissions, the fice managers will have the same permissions, the five administrators will have the same permissions.
    +   If possible, the developers should have access to Amazon EC2 without security credentials tied to their IAM user.
    +   Amazon EC2 instances will need access to Amazon S3.
    +   You need a way to audit so that credential lifecycle requirements are compliant.
    +   You need a way to manage IAM user permissions.
    +   You need to apply strong security measures to protect the AWS account.

2.          IAM setup:
    <b>Requirements:</b>
    +   You need to apply strong security measure to protect the AWS account.

    <b>Solution</b>
    Secure your root user credentials and don't use them for everyday tasks. Configure the root user to require MFA to log in. Only use the root user to complete the tasks hat only the root user can perform. Create a new user that can conduct everyday admin tasks and assign it the appropriate permissions.
    Create a strong password policy that will be enforced for all IAM users in this account. The policy should require users to create their own password when they first login.

3.      IAM users
    <b>Requirements:</b>    
    +   You need to create 50 users. 40 of them are developers, five are managers and five are administrators. The 40 developers will have the same permissions, the five managers will have the same permissions, the five administrators will have the same permissions.
    +   You need to apply strong security measures to protect the AWS account.    

4.      IAM groups
    <b>Requirements:</b>
    +   You need to create 50 users. 40 of them are developers, five are managers and five area administrators. The 40 developers will have the same permissions, the five managers will have the same permissions, the five administrators will have the same permissions.
    <b>Solution:</b>
    Create a group for the developers, a group for the managers, and a group for the administrators. Place the appropriate users in the group that aligns with their job function.    
    <b>IAM group: Administrators</b>
    <b>IAM group: Managers</b>
    <b>IAM group: Developers</b>

5.     IAM policies
    <b>Requirements:</b>
    +   You need to create 50 users. 40 of them are developers, five are managers and five are administrators. The 40 developers will have the same permissions, the five managers will have the same permissions, the five administrators will have same permissions.
    <b>Solution:</b>
    Create a policy for each of the groups(developers, managers, and administrators). The policy should follow the principle of least privilege. Attach the policy to the group. This will provide each user in the groups with the appropriate permissions. If any user in a group need special permissions, that the other users in the group don't need, then create an additional IAM policy with the permissions needed and attach it to the specific user and not the group.

6.      Roles
    <b>Requirements:</b>
    +   If possible, the developers should have access to Amazon EC2 without security credentials tied to their IAM user.
    +   Amazon EC2 instances will need access to Amazon S3.    
    <b>Solution:</b>
    Create a role with permission that lets a user access Amazon EC2. Make the principle of the trust policy to be the users in the developer group.
    Create another role for the EC2 instances, so that they can access Amazon S3. In the trust policy, make sure that Amazon EC2 is the trusted principle.

7.      AWS Access Analyzer:
    <b>Requirements:</b>
    +   You need a way to manage IAM user permissions.
    +   You need to apply strong measure to protect the AWS account.
    <b>Solution:</b>
    Turn on IAM Access Analyzer. It continuously monitors for new or updated resource permissions to help you identify permissions that grant public and cross- account access. Update permission to groups and users as needed. Refining your users permissions, based on evolving need is a security best practice.  

    Set, or grant your detailed permissions.
    Verify who can access what.
    Refine by removing overly broad access.  

8.      IAM Credential Report
    <b>Requirements:</b>
    +   You need a way to audit so that credential lifecycle requirements are compliant.
    +   You need to apply strong security measure to protect the AWS account.

    <b>Solution</b>
    Run IAM credential reports as often as needed to verify that credential lifecycle requirements are compliant. Auditing your user credentials is a good way to help protect your AWS Account.    
    Lists all users in your account.
    Details the status of their various credentials.

#####   Additional AWS Security Services
        Amazon Cognito provides Authentication and Authorization for web and mobile apps
<img src="assets/Amazon cognito.PNG" alt="cognito" style="height:100%; width:100%;">

#####   Amazon Cognito Components
+   User pools

<img src="assets/user pools.PNG" alt="user pools" style="height:100%; width:100%;">

+   Identity pools
<img src="assets/identity pools.PNG" alt="identity pools" style="height:100%; width:100%;">

#####   Amazon Cognito workflow
<img src="assets/cognito workflow.PNG" alt="cognito workflow" style="height:100%; width:100%;">

#####   AWS Key Management Service(KMS)
<img src="assets/kms.PNG" alt="kms" style="height:100%; width:100%;">

#####   AWS KMS key types
+       AWS-owned keys
    They are a collection of KMS keys that an AWS service owns and manages for use with multiple AWS accounts. Although AWS-owned keys aren't in your account, an AWS service can use an AWS-owned key to protect the resources in your account. In general, unless you are required to audit or control the encryption key that protects your resources, an AWS-owned key is a good choice.
+       AWS-managed keys
    They are KMS keys in your account that are created, managed, and used on your behalf by an AWS Service integrated with AWS KMS. In general, unless you are required to control the encryption key that protects your resources, an AWS-managed key is a good choice. You don't have to maintain or create the key or its key policy, and there's never a monthly fee for an AWS-managed key.
+       Customer-managed keys
<img src="assets/customer managed key.PNG" alt="kms" style="height:100%; width:100%;">

#####   Customer managed key types
1.      Symmetric key:
    A single key used for encrypting and decrypting data.

2.      Asymmetric key:
    A public and private key pair used for encrypting and decrypting data.    

#####   Defining AWS KMS permissions
    Customer managed key also require to define permissions. First you need to configure the main components which are:
+       Key administrator:
    A   key administrator is one or more IAM users that manage the key.

+       Key policy:
    A key policy is a JSON document that contains the permissions for what the key can be used to do.

+       Key user:
    Users that can use the key to perform the actions that are listed in the key policy.        

<img src="assets/KMS permission.PNG" alt="kms" style="height:100%; width:100%;">    

#####   AWS Secret Manager
    designed to centrally manage secrets used to access resources on:
+   AWS
+   Third-party
+   On-premises

<b>Secrets can be:</b>

+   Database credentials
+   Passwords
+   Third-party API keys
+   Arbitrary text

#####   AWS Secrets Manager benefits
+   Retrieve the secret programmatically.
+   Rotate secrets automatically.
+   Control access to your secrets.
+   Audit and monitor your secrets usage.

#####   AWS Shield 
+   Always on detection
+   Automatic inline mitigation
+   Minimize application latency.

#####   AWS Shield Advanced
<img src="assets/aws shield.PNG" alt="shield" style="height:100%; width:100%;"> 

#####   Amazon Inspector
<img src="assets/amazon inspector.PNG" alt="shield" style="height:100%; width:100%;">

#####   Amazon Inspector benefits
+       Quick discovery:
    With Amazon Inspector, you can quickly discover vulnerabilities in compute workloads. Amazon Inspector can automatically discover and quickly route vulnerability findings in near real time to the appropriate teams, so that they can take immediate action.

+       Prioritize remediation
    Amazon Inspector can help you prioritize patch remediation issues. It uses up-to-date common vulnerabilities and exposures information, combined with factors such as network accessibility to create context-based risk scores. This helps you prioritize and address vulnerable resources.

+       Meet compliance regulations    
    Amazon Inspector can help you meet compliance requirements. Amazon Inspector support compliance requirements and best practices for NIST CSF,PCI DSS, and other regulations with Amazon Inspector scans.

#####   Amazon GuardDuty
+   Machine learning
+   Anomaly detection
+   Integrated threat intelligence

#####   Amazon GuardDuty benefits
+       Security visibility
    Amazon GuardDuty helps improve security operations visibility. With Guard Duty, you can gain insight of compromised credentials, unusual data access in Amazon S3, suspicious logins in Amazon Aurora(Preview), and API calls from known malicious IP addresses.

+       Find malware
    GuardDuty can help identify files containing malware. It scans Amazon Elastic Block Store(EBS) for files that might have malware creating suspicious behavior on instance and container workloads running on Amazon EC2.

+       Route security findings
    GuardDuty can be used to route insightful information on security findings. With Amazon GuardDuty, can route findings to your preferred operational tools using integrations with AWS Security Hub and Amazon Event Bridge.

####    LAB
######  Task 1: Explore the users and groups

In this task, you will explore the users and groups that have already been created for you in IAM.

+   First, note the Region that you are in; for example, N. Virginia. The Region is displayed in the upper-right corner of the console page.

You might need this information later in the lab.

+   Choose the Services menu, locate the Security, Identity, & Compliance services, and choose IAM.

+   In the navigation pane on the left, choose Users.

The following IAM users have been created for you:

user-1
user-2
user-3

+   Choose the name of user-1.

    +   This brings you to a summary page for user-1. The Permissions tab will be displayed.
    +   Notice that user-1 does not have any permissions.
+   Choose the Groups tab.

Notice that user-1 also is not a member of any groups.

+   Choose the Security credentials tab.

Notice that user-1 is assigned a Console password. This allows the user to access the AWS Management Console.

+   In the navigation pane on the left, choose User groups.

The following groups have already been created for you:

EC2-Admin
EC2-Support
S3-Support
+   Choose the name of the EC2-Support group.

This brings you to the summary page for the EC2-Support group.

+   Choose the Permissions tab.

This group has a managed policy called AmazonEC2ReadOnlyAccess associated with it. Managed policies are prebuilt policies (built either by AWS or by your administrators) that can be attached to IAM users and groups. When the policy is updated, the changes to the policy are immediately applied against all users and groups that are attached to the policy.

+   Under Policy Name, choose the link for the AmazonEC2ReadOnlyAccess policy.

+   Choose the {} JSON tab.

    +   A policy defines what actions are allowed or denied for specific AWS resources. This policy is granting permission to List and Describe (view) information about Amazon Elastic Compute Cloud (Amazon EC2), Elastic Load Balancing, Amazon CloudWatch, and Amazon EC2 Auto Scaling. This ability to view resources, but not modify them, is ideal for assigning to a support role.

    +   Statements in an IAM policy have the following basic structure:

        +   Effect says whether to Allow or Deny the permissions.
        +   Action specifies the API calls that can be made against an AWS service (for example, cloudwatch:ListMetrics).
        +   Resource defines the scope of entities covered by the policy rule (for example, a specific Amazon Simple Storage Service [Amazon S3] bucket or Amazon EC2 instance; an asterisk [ * ] means any resource).
+   In the navigation pane on the left, choose User groups.

+   Choose the name of the S3-Support group.

+   Choose the Permissions tab.

The S3-Support group has the AmazonS3ReadOnlyAccess policy attached.

+   Under Policy Name, choose the link for the AmazonS3ReadOnlyAccess policy.

+   Choose the {} JSON tab.

This policy has permissions to Get and List for all resources in Amazon S3.

+   In the navigation pane on the left, choose User groups.

+   Choose the name of the EC2-Admin group.

+   Choose the Permissions tab.

This group is different from the other two. Instead of a managed policy, the group has an inline policy, which is a policy assigned to just one user or group. Inline policies are typically used to apply permissions for specific situations.

+   Under Policy Name, choose the name of the EC2-Admin-Policy policy.

+   Choose the JSON tab.

This policy grants permission to Describe information about Amazon EC2 instances, and also the ability to Start and Stop instances.

At the bottom of the screen, choose Cancel to close the policy.


######  Task 2: Add users to groups
You have recently hired user-1 into a role where they will provide support for Amazon S3. You will add them to the S3-Support group so that they inherit the necessary permissions via the attached AmazonS3ReadOnlyAccess policy.

Ignore any "not authorized" errors that appear during this task. They are caused by your lab account having limited permissions and will not impact your ability to complete the lab.

<b>Add user-1 to the S3-Support group</b>

+   In the left navigation pane, choose User groups.

+   Choose the name of the S3-Support group.

+   On the Users tab, choose Add users.

+   Select  user-1, and choose Add users.

On the Users tab, notice that user-1 has been added to the group.

<b>Add user-2 to the EC2-Support group</b>
You have hired user-2 into a role where they will provide support for Amazon EC2. You will add them to the EC2-Support group so that they inherit the necessary permissions via the attached AmazonEC2ReadOnlyAccess policy.

+   Use what you learned from the previous steps to add user-2 to the EC2-Support group.

user-2 should now be part of the EC2-Support group.

<b>Add user-3 to the EC2-Admin group</b>
You have hired user-3 as your Amazon EC2 administrator to manage your EC2 instances. You will add them to the EC2-Admin group so that they inherit the necessary permissions via the attached EC2-Admin-Policy.

+   Use what you learned from the previous steps to add user-3 to the EC2-Admin group.

user-3 should now be part of the EC2-Admin group.

+   In the navigation pane on the left, choose User groups.

Each group should have a 1 in the Users column. This indicates the number of users in each group.

If you do not have a 1 for the Users column for a group, revisit the previous steps to ensure that each user is assigned to a group, as shown in the table in the Business scenario section.

 

<b>Task 3: Sign in and test users</b>
In this task, you will test the permissions of each IAM user in the console.

Get the console sign-in URL
+   In the navigation pane on the left, choose Dashboard.

Notice the Sign-in URL for IAM users in this account section at the top of the page. The sign-in URL looks similar to the following: https://123456789012.signin.aws.amazon.com/console

This link can be used to sign in to the AWS account that you are currently using.

+   Copy the sign-in link to a text editor.

<b>Test user-1 permissions</b>
+   Open a private or incognito window in your browser.

+   Paste the sign-in link into the private browser, and press ENTER.

You will now sign-in as user-1, who has been hired as your Amazon S3 storage support staff.

+   Sign in with the following credentials:

    +   IAM user name: user-1
    +   Password: Lab-Password1
+   Choose the Services menu, and choose S3.

+   Choose the name of one of your buckets, and browse the contents.

Because this user is part of the S3-Support group in IAM, they have permissions to view a list of Amazon S3 buckets and their contents.

Now, test whether the user has access to Amazon EC2.

+   Choose the Services menu, and choose EC2.

+   In the left navigation pane, choose Instances.

You cannot see any instances. Instead, an error message says you are not authorized to perform this operation. This user has not been assigned any permissions to use Amazon EC2.

You will now sign in as user-2, who has been hired as your Amazon EC2 support person.

+   First, sign out user-1 from the console:

    +   In the upper-right corner of the page, choose user-1.
    +   Choose Sign Out.
    
<b>Test user-2 permissions</b>

+   Paste the sign-in link into the private browser again, and press ENTER.

+   Sign in with the following credentials:

IAM user name: user-2
Password: Lab-Password2

+   Choose the Services menu, and choose EC2.

+   In the navigation pane on the left, choose Instances.

    +   You are now able to see an EC2 instance. However, you cannot make any changes to Amazon EC2 resources because you have read-only permissions.
    +   If you cannot see an EC2 instance, then your Region might be incorrect. In the upper-right corner of the page, choose the Region name, and then choose the Region that you were in at the beginning of the lab (for example, N. Virginia).
Select the EC2 instance.

+   Choose the Instance state menu, and then choose Stop instance.

+   To confirm that you want to stop the instance, choose Stop.

An error message appears and says that You are not authorized to perform this operation. This demonstrates that the policy only allows you to view information without making changes.

Next, check if user-2 can access Amazon S3.

+   Choose the Services menu, and choose S3.

An message says No buckets because user-2 does not have permissions to use Amazon S3.

You will now sign-in as user-3, who has been hired as your Amazon EC2 administrator.

+   First, sign out user-2 from the console:

In the upper-right corner of the page, choose user-2.
Choose Sign Out.
Test user-3 permissions
Paste the sign-in link into the private browser again, and press ENTER.

+   Sign in with the following credentials:

IAM user name: user-3
Password: Lab-Password3
+   Choose the Services menu, and choose EC2.

+   In the navigation pane on the left, choose Instances.

    +   An EC2 instance is listed. As an Amazon EC2 Administrator, this user should have permissions to Stop the EC2 instance.
    +   If you cannot see an EC2 instance, then your Region might be incorrect. In the upper-right corner of the page, choose the Region name, and then choose the Region that you were in at the beginning of the lab (for example, N. Virginia).

+   Select the EC2 instance.

+   Choose the Instance state menu, and then choose Stop instance.

+   To confirm that you want to stop the instance, choose Stop.

This time, the action is successful because user-3 has permissions to stop EC2 instances. The Instance state changes to Stopping and starts to shut down.

+   Close your private browser window.