#   Getting Started with Cloud Operations
### This is the beginning of cloud practitioner journey.
We begin our journey from AWS educate course. Click [Getting Started with Cloud Operations](https://awseducate.instructure.com/courses/889) to start learning.

## Objectives
By the end of this course you will be able to do the following:

+      Describe cloud operation fundamental concepts.

+      Explain the Amazon Well-Architected Framework.

+      Describe AWS cost and free tier structures.

+      Describe the AWS cost management tools that are available.

+      Identify support plans and explain the differences between them.

+      Discuss AWS cloud operations services that are available to you, including AWS Trusted Advisor, AWS Health  Dashboard, Amazon CloudWatch, AWS CloudTrail, AWS Organizations, AWS Systems Manager, and AWS Config.

## Getting Started learning pathway
This is a course that’s a part of a series of courses designed to give you foundational knowledge about cloud computing.  
Each of the courses are focused on a specific domain of cloud computing.

Although you can take any of the courses at any time, we suggest that you take the courses in the following order:

1. Getting Started with Storage
2. Getting Started with Compute
3. Getting Started with Networking 
4. Getting Started with Databases 
5. Getting Started with Cloud Operations 
6. Getting Started with Security 
7. Getting Started with Serverless   

## Learning
<img src="assets/Learning_Module1.png" alt="Guide Video" style="height: 100%; width:100%;"/>

## Getting Started with Cloud Operations Lab  
This hands-on lab guides you through the steps to estimate Amazon Web Services (AWS) costs for a sample workload. The workload that you evaluate is for a three-tier web application that consists of :  
+       An Application Load Balancer  
+       An Amazon Elastic Compute Cloud (Amazon EC2) instance  
+       An Amazon Relational Database Service (Amazon RDS) instance 

The skills will help you to use AWS Pricing Calculator to estimate costs for your workloads.

###     Introduction to the Well-Architected Framework
<b>Cloud Environment</b>

+   Security
+   Operation
+   Performance
+   Scalability
+   Cost


### What is cloud operations?
+   Innovation
+   Cost
+   Compliance
+   Security



### Benefits of Cloud Operations
+       Innovation
    AWS helps you use the cloud to turn ideas into opportunities, creating new ways to grow, increase efficiency, and serve customers better. AWS has industry leading cloud services to help customers solve problems and explore possibilities.

+       Scale
    AWS management and governance services are built to manage highly dynamic cloud resources at massive scale.

+       Simplicity
    AWS reduces complexity, offering a single control plane for customers to manage and govern their resources on AWS and on-premises.

+       Cost savings
    Customers can use AWS management and governance services to assess their resource utilization and identify ways to reduce costs.

### AWS WA Framework Introduction
Foundation should be strong    
<img src="assets/WA intro.PNG" alt="WA" style="height:100%; width:100%">

### WA Framework pillars
<img src="assets/pillar.PNG" alt="pillar" style="height:100%; width:100%">

### AWS WA Framework: six pillars
+       Operational excellence
    The operational excellence pillar focuses on running and monitoring systems and continually improving processes and procedures. Key topics include automating changes, responding to events, and defining standards to manage daily operations.
    
+       Security
    The security pillar focuses on protecting information and systems. Key topics include confidentiality and integrity of data, managing user permissions, and establishing controls to detect security events.

+       Reliability
    The reliability pillar focuses on workloads performing their intended function and how to recover quickly from failure to meet demands. Key topics include distributed system design, recovery planning, and adapting to changing requirements.

+       Performance efficiency
    This pillar focuses on structured and streamlined allocation of IT and computing resources. Key topics include selecting resource types and sizes optimized for workload requirements, monitoring performance, and maintaining efficiency as business need evolve.

+       Cost optimization
    The cost optimization pillar focuses on avoiding unnecessary costs. Key topics include understanding spending over time and controlling fund allocation, selecting resources of the right type and quantity, and scaling to meet business needs without overspending.

+       Sustainability
    It focuses on minimizing the environmental impacts of running cloud workloads. key topics include a shared responsibility model for sustainability, understanding impact, and maximizing utilization to minimize required resources and reduce downstream impacts.


### AWS WA Tool
<img src="assets/wa tool.PNG" alt="tool" style="height:100%; width:100%">


### Introduction to AWS Cost Management

(Access, Organize, Understand, Control, Optimize) the costs

### AWS payment models
+       pay-as-you-go
    It allows you to easily adapt to changing business needs without over committing budgets and improves your responsiveness to changes.

+        save when you commit
    It is a flexible pricing model that provides significant savings on your AWS usage.
    You can sign up for Savings Plans for a 1 or 3 year team and easily manage your plans by taking advantages of recommendations, performance reporting, and budget alert in AWS Cost Explorer.

+       pay less by using more
    With AWS, you can get volume-based discounts and realize important savings as your usage increases. As your AWS usage needs increase you benefit from the economies of scale that allow you to increase adoption and keep costs under control.
    To optimize your savings, choose the right combinations of storage solutions that help you reduce costs while preserving performance and security.

### AWS Free Tier
    It offers a free usage tier for up to 1 year
    Save money as you learn and experiment with AWS Free Tier.    

<img src="assets/free tier.PNG" alt="AWS" style="height:100%; width:100%">

### Total costs of ownership(TCO)
<img src="assets/tco.PNG" alt="AWS" style="height:100%; width:100%"> <br>
<img src="assets/tco tools.PNG" alt="AWS" style="height:100%; width:100%">

TCO tools help to manage TCO, AWS offers pricing tools like the AWS Pricing Calculator and the AWS Migration Evaluator

### AWS Pricing Calculator
<img src="assets/awspricing calculator.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Migration Evaluator
<img src="assets/migration evaluator.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Cost Management tools
+       AWS Billing console
    Resources to manage your ongoing payments and payment methods registered to your AWS account.

+       AWS Cost Management console
    Features for budgeting and forecasting costs and methods for you to optimize your pricing to reduce your AWS bill.

<img src="assets/cost explorer.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Cost Explorer benefits
+       View cost charts
    You can view charts to see how your costs are being accumulated.

+       13 month review of costs
    You can review costs from the past 13 months to evaluate trends.

+       Forecast costs
    You can forecast what your costs will be over the next 3 months based on current configurations and estimated usage data.

+       Discover patterns
    You can use AWS Cost Explorer to discover how much you're spending on AWS resources over time and identity cost problem areas.

+       Favorite services
    With AWS Cost Explorer, you can identity the services that you use the most and their associated costs.

+       View metrics
    AWS Cost Explorer gives you access to metrics like which Availability Zones have the most traffic or which linked AWS account is used the most.

### AWS Budgets
Improve planning and cost control with flexible budgeting and forecasting.
+   Create a budget
+   Get altered
+   Respond with actions.

### AWS Billing Dashboard
+   View the status of your month-to-date AWS expenditure.
+   Identify the services that account for the majority of your overall expenditure. 
+   Understand at a high level how costs are trending.

<b>Spend Summary Example</b>
<img src="assets/spend summary.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Billing Dashboard examples
+   Amazon EC2
<img src="assets/ec2.1.PNG" alt="AWS" style="height:100%; width:100%">
<img src="assets/ec2.2.PNG" alt="AWS" style="height:100%; width:100%">

+   Amazon S3
<img src="assets/s3.1.PNG" alt="AWS" style="height:100%; width:100%">
<img src="assets/s3.2.PNG" alt="AWS" style="height:100%; width:100%">

+   AWS Lambda
<img src="assets/lambda1.PNG" alt="AWS" style="height:100%; width:100%">
<img src="assets/lambda2.PNG" alt="AWS" style="height:100%; width:100%">

### Introduction to Managing Your AWS Account
+   Performance
+   Manage Risk
+   Cost

### AWS Support Plans
<img src="assets/support1.PNG" alt="AWS" style="height:100%; width:100%">
<img src="assets/support2.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Support Benefits
Designed to proactively help you optimize performance, lower costs, and innovate faster.
+       Move faster with AWS
    Use AWS experts to quickly build up knowledge and expertise. It helps you stay agile with architectural guidance as you build applications and solutions.

+       Automate management of your environment
    Proactively monitor your environment and automate remediation. AWS Support provides tools such as AWS Personal Health Dashboard and AWS Trusted Advisor to help you keep your environment running optimally.

+       Focus on what matters
You can put your energy where it belong: with your customers and your business. We will take care of the infrastructure for you and help you to keep it running efficiently, securely and in a manner your business demands.

+       Manage and mitigate risks
    It can help you maintain strict security standards and proactively alert you to issues. We can help you plan to meet the demands of your customers with architectural and operational guidance to optimize performance.

+       Highly-trained engineers, large network of subject-matter experts
    AWS has cloud support Engineers well versed in DevOps Technologies, automation, infrastructure, configuration management and continuous integration, and subject-matter experts ranging from Solutions Architects to product managers.

+       Engineer empowered to help you achieve your goals
    AWS engineers stay with AWS support cases from the start to resolution. This eliminates the need for customers to interact with multiple support engineers, which can slow down the time to resolution, and helps you continue your cloud journey.

### AWS Service Quotes
<img src="assets/quotes.PNG" alt="AWS" style="height:100%; width:100%">

### Tagging
<img src="assets/tagging.PNG" alt="AWS" style="height:100%; width:100%">

### Common Tagging Strategies

<img src="assets/tagging strategies.PNG" alt="AWS" style="height:100%; width:100%">

+   Resource organization
<img src="assets/resource.PNG" alt="AWS" style="height:100%; width:100%">

+   Cost allocation
<img src="assets/cost.PNG" alt="AWS" style="height:100%; width:100%">

+   Automation
<img src="assets/automation.PNG" alt="AWS" style="height:100%; width:100%">

+   Access Control
<img src="assets/access control.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Trust Advisor
<img src="assets/advisor.PNG" alt="AWS" style="height:100%; width:100%">

### Benefits of AWS Trusted Advisor
+   Cost optimization
<img src="assets/cost optimization.PNG" alt="AWS" style="height:100%; width:100%">

+   Performance
<img src="assets/performance.PNG" alt="AWS" style="height:100%; width:100%">

+   Security
<img src="assets/security.PNG" alt="AWS" style="height:100%; width:100%">

+   Fault Tolerance
<img src="assets/fault tolerance.PNG" alt="AWS" style="height:100%; width:100%">

+   Service quotas
<img src="assets/service quotas.PNG" alt="AWS" style="height:100%; width:100%">

### Trusted Advisor's five checks

<img src="assets/five checks.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Health Dashboard
+       Personalize view
    When you sign into the Health Dashboard, you have a personalized view of the AWS service status that powers your application. Use the Health Dashboard to learn about specific operational issues that affect your account.

+       Proactive notifications
    In addition to enabling emails to receive important Health events, you can configure AWS Health Aware to receive information in your slack channel or other operational tooling.

+       Troubleshooting
    When you get a Health event, it includes remediation details and specific guidance so that you can take action for events that affect your resources. For example, if a hardware issue affects one of your Amazon EBS volumes, the alert includes a list of affected resources, recommendations, and help links o restore your volume from a snapshot. This helps you reduce the amount of time it takes to resolve issues.

+       Integration and automation
<img src="assets/integration.PNG" alt="AWS" style="height:100%; width:100%">
    
+       Access control
<img src="assets/access control2.PNG" alt="AWS" style="height:100%; width:100%">

+       Aggregate health events
<img src="assets/aggregate.PNG" alt="AWS" style="height:100%; width:100%">

### Additional Cloud operation Services
+   Change management
+   Application management
+   Storage, analysis, and remediation
+   Event-driven application

### Amazon CloudWatch
<img src="assets/amazon cloudwatch.PNG" alt="AWS" style="height:100%; width:100%">

### CloudWatch use cases
+       Monitor application performance
    Visualize performance data, create alarms, and correlate data to understand and resolve the root cause of performance issues in your AWS resources

+       Perform root cause analysis
    Analyze metrics, logs, logs analytics, and user requests to speed up debugging and reduce overall mean time to resolution.

+       Optimize resources proactively
    Automate resource planning and lower costs by setting actions to occur when thresholds are met based on your specifications or machine learning models.

+       Test website impacts
    Find out exactly when your website is impacted and for how ling by viewing screenshots, logs, and web requests at any point in time.

### How CLoudWatch works with other AWS services
<img src="assets/cloudwatch service.PNG" alt="AWS" style="height:100%; width:100%">

+   Amazon Simple Notification Service(Amazon SNS) 
<img src="assets/amazon sns.PNG" alt="AWS" style="height:100%; width:100%">
+   Amazon EC2 Auto Scaling
<img src="assets/cloudwatch ec2.PNG" alt="AWS" style="height:100%; width:100%">

+   AWS CloudTrail
<img src="assets/cloud trail.PNG" alt="AWS" style="height:100%; width:100%">

+   AWS Identity and Access Management (IAM)    
<img src="assets/IAM.PNG" alt="AWS" style="height:100%; width:100%">

### AWS CloudTrail
<img src="assets/aws cloud trail.PNG" alt="AWS" style="height:100%; width:100%">

### AWS CloudTrail Benefits
+   Always on
    CLoudTrail is enabled on all AWS accounts and records management events across AWS services without the need for any manual setup. With AWS Free Tier, you can view, search, and download the most recent 90-day history of your account's management events at no charge using the CloudTrail console or by using the CloudTrail lookup-events API.

+   Storage and monitoring
    Deliver you ongoing management and data events to S3 and optionally to CloudWatch Logs by creating trails and then you can export and store events. Because CloudTrail Lake is a manage audit, and security lake, your events are stored automatically within the lake. You must fire enable AWS config recording to ingest Configuration items in CloudTrail lake.

+   Immutable and encrypted activity logs
    You can validate the integrity of CloudTrail log files stored in your S3 bucket and detect whether the log files were unchanged, modified, or deleted since CloudTrail delivered them to your S3 bucket. You can use log file integrity validation in your IT security and auditing processes. CloudTrail Lake encrypts all logs automatically.

+   Insights and analytics
    With CloudTrail Lake, you can run SQL-based queries on activity logs for auditing within the lake. You can also enable CLoudTrail insights in your rail to identify unusual activity in your AWS. Example of this are burst AWS identity and IAM or gaps in periodic maintenance activity. You can enable CLoudTrails insights events in your trail.

+   Multi-region
    You can configure CLoudTrail to capture and store events from multiple AWS Regions in a single location. This configuration certifies that all settings apply consistently across existing and newly launched Regions.

+   Multi-account
    You can configure it to capture and store events from multiple AWS accounts in a single location. This configuration verifies that all settings apply consistently across all existing and newly created accounts.

### AWS CloudTrail use cases
<img src="assets/cloud trail usecase.PNG" alt="AWS" style="height:100%; width:100%">

+   Audit activity
    Monitor, store, and validate activity events for authenticity. Easily generate audit reports required by internal policies and external regulations.

+   Identify security incidents
    Detect unauthorized access using the Who, What and When information in CloudTrail Events. Respond with rules-based EventBridge alerts and automated workflows.

+   Troubleshoot operational issues
    Continuously monitor API usage history using machine learning (ML) models to spot unusual activity in your AWS accounts and determine root cause.

### AWS System Manager
<img src="assets/cloud trail usecase.PNG" alt="AWS" style="height:100%; width:100%">    

### AWS System Manager use case
+       Centralize operational data
    Visualize performance data, create alarms, and correlate data to understand and resolve the root cause of performance issues in your AWS resources.

+       Automatically resolve application issues
    Analyze metric, logs, logs analytics, and user requests to speed up debugging and reduce overall mean time to resolution.

+       Implement best practices
    Automate resource planning and lower costs by setting actions to occur when thresholds are met based on your specifications or machine learning models.

+       Remediate security events
    Find out exactly when your website is impacted and for how long by viewing screenshots, logs, and web requests at any point in time.

### AWS config
<img src="assets/aws config.PNG" alt="AWS" style="height:100%; width:100%"> 

### AWS Config use cases
+   Streamline operational troubleshooting and change management
    Discover resources that exist in your account, record their configurations, and capture any changes, This allows you to quickly troubleshoot operational issues.

+   Deploy a compliance-as-code framework
    Codify your compliance requirements as AWS Config rules and author remediation actions, automating the assessment of your resource configuration across your organization.

+   Continually audit security monitoring and analysis
    Evaluate resource configurations for potential vulnerabilities, and review your configuration history after potential incidents to examine your security posture.

### AWS EventBridge

<img src="assets/event bridge.PNG" alt="AWS" style="height:100%; width:100%"> 

### AWS Organization
<img src="assets/organization.PNG" alt="AWS" style="height:100%; width:100%">

### AWS Organizations benefits
<b>Centrally manage and govern your cloud environment.</b>
+   Manage and organize your accounts under a single bill.
+   Set central policies and configuration requirements.
+   Create custom permissions or capabilities.
+   Delegate responsibilities to other accounts.

### AWS Organizations use cases
+       Automate AWS account creation
    Create AWS accounts and add them to user-defined groups for instant security policy application, touchless infrastructure deployments, and auditing.

+       Enable proactive protection with a dedicated security group
    Create a security group and provide users with read-only access to your resources to actively monitor, identify, and mitigate security concerns.

+       Ensure user access to designated resources
    Enable single sign-on access and apply service control policies to allow only user actions that meet your security anc compliance requirements.

+       Share common resources across accounts
    More easily share central resources, software applications, directories, and services within your organizations.


