## Notas de Servicios de AWS (Resumen)

<details><summary> 1. AWS Machine Learning Services
</summary>

AWS offers a broad family of Machine Learning (ML) services with various applications to enhance your applications and customer experiences.

### AWS Rekognition
- Add image and video analysis to applications.
- Identify objects, people, text, scenes, and activities in images and videos.
- Process videos stored in an Amazon S3 bucket.
- Publish completion status to Amazon SNS Topic.

### AWS Transcribe
- Add speech to text capabilities to applications.
- Convert recorded speech to text using automatic speech recognition (ASR) for quick and accurate results.

### AWS Translate
- Neural machine translation service for fast, high-quality, and affordable language translation.
- Uses deep learning models for accurate and natural sounding translation.
- Localize content such as websites and applications for diverse users.

### Amazon SageMaker
- Help data scientists and developers prepare, build, train, and deploy high-quality ML models.
- Activities include data preparation, feature engineering, statistical bias detection, auto-ML, training, and tuning.

### Amazon Comprehend
- Natural-language processing (NLP) service that uncovers information in unstructured data.
- Identifies critical elements in data, including language, people, places, and categorizes text files by relevant topics.
- Real-time customer sentiment detection in content.

### Amazon Forecast
- Fully managed service using statistical and ML algorithms for highly accurate time-series forecasts.
- No machine learning experience required.
- Useful in retail, finance, logistics, healthcare, and other fields to predict future data and domain-specific metrics.

### Amazon Lex
- Conversational AI for Chatbots.
- Build voice and text-based conversational interfaces into applications.
- Increase contact center productivity, automate tasks, and improve operational efficiencies.

### Amazon Polly
- Text-to-Speech (TTS) service that turns text into lifelike speech.
- Create applications with speech-enabled products using advanced deep learning technologies.

</details>

<details><summary> 2. AWS CloudFormation
</summary>

AWS CloudFormation is a powerful service that enables you to manage and provision your AWS infrastructure using code. It offers a common language in the form of JSON or YAML templates to describe and deploy all the resources in your cloud environment. With CloudFormation, you can provision a wide range of AWS resources efficiently.

Key Benefits:

- **Consistent Infrastructure Provisioning:** CloudFormation ensures consistent and reliable infrastructure provisioning, minimizing human errors in the process.

- **Time and Effort Savings:** By automating the provisioning process, CloudFormation saves time and effort compared to manual configuration of resources.

- **Version Control and Peer Review:** You can use version control systems and peer review for your CloudFormation templates, promoting collaboration and transparency.

- **Cost-Effective:** AWS CloudFormation is free to use, and you only incur charges for the resources it provisions.

- **Updates and Dependencies Management:** CloudFormation allows you to manage updates and dependencies between resources, ensuring smooth operations.

- **Rollback and Deletion:** In case of issues, CloudFormation facilitates easy rollback to previous stack versions and can delete entire stacks when needed.

Key Concepts:

1. **Templates:** These YAML or JSON files describe the desired AWS infrastructure. You upload the templates to CloudFormation, which interprets them and creates the specified resources, known as a "Stack."

2. **Stacks:** Stacks represent the entire environment described in the template. You can create, update, and delete stacks as a single unit.

3. **StackSets:** CloudFormation StackSets extend stack functionality, enabling you to create, update, or delete stacks across multiple AWS accounts and regions with a single operation.

4. **Change Sets:** Before implementing changes, you can preview their impact on existing resources with Change Sets. They provide a summary of proposed alterations to the stack.

Template Components:

Mandatory:
- List of resources with associated configuration values.

Optional:
- Template parameters (up to 60).
- Output values (up to 60).
- List of data tables.

Resources:

- The Resources section in the template declares the AWS resources to be included in the stack, such as EC2 instances or S3 buckets.
- These resources are declared and can reference each other within the template.

In summary, AWS CloudFormation simplifies infrastructure management by treating it as code. It offers a wide array of benefits and key concepts to efficiently handle your AWS resources with ease.

</details>

<details><summary> 3. AWS CloudTrail
</summary>

- AWS CloudTrail is a web service that records activity made on your account.
- A CloudTrail trail can be created which delivers log files to an Amazon S3 bucket.
- CloudTrail is about logging and saves a history of API calls for your AWS account.
- CloudTrail enables governance, compliance, and operational and risk auditing of your AWS account.
- Events include actions taken in the AWS Management Console, AWS Command Line Interface, and AWS SDKs and APIs.
- CloudTrail provides visibility into user activity by recording actions taken on your account.
- API history enables security analysis, resource change tracking, and compliance auditing.
- Logs API calls made via:
  - AWS Management Console.
  - AWS SDKs.
  - Command line tools.
  - Higher-level AWS services (such as CloudFormation).
- CloudTrail records account activity and service events from most AWS services and logs the following records:
  - The identity of the API caller.
  - The time of the API call.
  - The source IP address of the API caller.
  - The request parameters.
  - The response elements returned by the AWS service.
- CloudTrail is enabled on your AWS account when you create it.
- CloudTrail is per AWS account.

# Types of Trails

You can create two types of trails for an AWS account:

- A trail that applies to all regions – records events in all regions and delivers to an S3 bucket.
- A trail that applies to a single region – records events in a single region and delivers to an S3 bucket. Additional single trails can use the same or a different S3 bucket.

# Logging Configuration

Trails can be configured to log data events and management events:

- Data events: These events provide insight into the resource operations performed on or within a resource. These are also known as data plane operations.
- Management events: Management events provide insight into management operations that are performed on resources in your AWS account. These are also known as control plane operations. Management events can also include non-API events that occur in your account.

# Examples of Events

Example data events include:

- Amazon S3 object-level API activity (for example, GetObject, DeleteObject, and PutObject API operations).
- AWS Lambda function execution activity (the Invoke API).

Example management events include:

- Configuring security (for example, IAM AttachRolePolicy API operations).
- Registering devices (for example, Amazon EC2 CreateDefaultVpc API operations).
- Configuring rules for routing data (for example, Amazon EC2 CreateSubnet API operations).
- Setting up logging (for example, AWS CloudTrail CreateTrail API operations).

# Log File Encryption

- CloudTrail log files are encrypted using S3 Server Side Encryption (SSE).
- You can also enable encryption using SSE KMS for additional security.
- A single KMS key can be used to encrypt log files for trails applied to all regions.

# Consolidating Logs

You can consolidate logs from multiple accounts using an S3 bucket:

1. Turn on CloudTrail in the paying account.
2. Create a bucket policy that allows cross-account access.
3. Turn on CloudTrail in the other accounts and use the bucket in the paying account.

# Integration with CloudWatch Logs

You can integrate CloudTrail with CloudWatch Logs to deliver data events captured by CloudTrail to a CloudWatch Logs log stream.

# Log File Integrity Validation

CloudTrail log file integrity validation feature allows you to determine whether a CloudTrail log file was unchanged, deleted, or modified since CloudTrail delivered it to the specified Amazon S3 bucket.

# CloudWatch vs CloudTrail

| CloudWatch                                      | CloudTrail                                      |
|-------------------------------------------------|-------------------------------------------------|
| Performance monitoring                          | Auditing                                        |
| Log events across AWS services – think operations | Log API activity across AWS services – think activities |
| Higher-level comprehensive monitoring and events | More low-level granular                         |
| Log from multiple accounts                      | Log from multiple accounts                      |
| Logs stored indefinitely                        | Logs stored to S3 or CloudWatch indefinitely    |
| Alarms history for 14 days                      | No native alarming; can use CloudWatch alarms   |

</details>


<details><summary> 4. AWS Trusted Advisor
</summary>

- **What is AWS Trusted Advisor?**
  - AWS Trusted Advisor is an online tool offered by Amazon Web Services (AWS) that helps customers optimize their AWS infrastructure, enhance performance, security, and cost-efficiency.

- **Key Features:**
  - **Cost Optimization:** It provides recommendations to save costs by identifying unused or underutilized resources, suggesting reserved instance purchases, and optimizing data transfer costs.
  - **Performance Improvement:** Trusted Advisor analyzes the performance of AWS resources and offers guidance to improve their responsiveness and overall performance.
  - **Security Enhancement:** It identifies potential security vulnerabilities, such as open security groups or inactive access keys, and suggests ways to enhance security.
  - **Fault Tolerance:** The tool evaluates the reliability of a customer's infrastructure and suggests ways to enhance fault tolerance and high availability.
  - **Service Limits:** It checks for AWS service limits and helps customers request limit increases when needed.
  
- **Categories:**
  - Trusted Advisor covers several categories, including Cost Optimization, Performance, Security, Fault Tolerance, and Service Limits.

- **Support Tiers:**
  - Different Trusted Advisor checks are available based on the customer's AWS Support plan. Some checks are available to all customers, while others require a higher support tier.

- **How to Access:**
  - AWS customers can access Trusted Advisor through the AWS Management Console or AWS Support Center.

- **Benefits:**
  - Using AWS Trusted Advisor can lead to cost savings, improved performance, increased security, and better adherence to AWS best practices.

- **Additional Resources:**
  - Customers can explore more about AWS Trusted Advisor through the provided link.

For more details, visit [AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/).

</details>

<details><summary> 5. Amazon CloudWatch
</summary>

Amazon CloudWatch is a monitoring service for AWS cloud resources and applications. It allows you to collect and track metrics, monitor log files, and set alarms. With CloudWatch, you can gain system-wide visibility into resource utilization, monitor application performance and operational health.

## Features

- CloudWatch Logs: Centralizes logs from systems, applications, and AWS services.
- CloudWatch Events: Delivers a stream of system events that describe changes in AWS resources.
- CloudWatch Alarms: Monitor metrics and configure automatic actions based on predefined thresholds.
- Metrics: Represent time-ordered sets of data points published to CloudWatch by AWS services or custom applications.
- High-Resolution Metrics: Offer more immediate insight with data at a granularity of one second.
- Namespace: A container for CloudWatch metrics, isolating metrics from different applications.
- Dimensions: Further clarify metrics by defining up to 10 dimensions for one metric.
- Statistics: Provides various aggregations over specified periods of time for metric data.
- CloudWatch Logs Agent: Provides an automated way to send log data from Amazon EC2 instances to CloudWatch Logs.
- CloudWatch Events: Delivers a near real-time stream of system events for AWS resource changes and automated actions.
- Useful API Actions: Includes GetMetricData, PutMetricData, GetMetricStatistics, and PutMetricAlarm.

## Resource Monitoring

CloudWatch can monitor various AWS resources, including:

- EC2 instances
- DynamoDB tables
- RDS DB instances
- Custom metrics generated by applications and services
- Log files generated by applications

## Metric Data Retention

CloudWatch retains metric data based on the period as follows:

- Data points with a period of less than 60 seconds: Available for 3 hours (high-resolution custom metrics).
- Data points with a period of 60 seconds (1 minute): Available for 15 days.
- Data points with a period of 300 seconds (5 minutes): Available for 63 days.
- Data points with a period of 3600 seconds (1 hour): Available for 455 days (15 months).

## CloudWatch vs. AWS CloudTrail

CloudWatch:
- Performance monitoring and higher-level comprehensive monitoring and event service.
- Monitors log events across AWS Services.
- Supports alarms and log retention.

AWS CloudTrail:
- Auditing and more low-level, granular log API activity across AWS services.
- Logs are stored to S3 or CloudWatch indefinitely.
- No native alarming but can use CloudWatch alarms.

## Publishing Custom Metrics

- Custom Metrics can be published using the AWS CLI or an API.
- High-resolution metrics offer more immediate insight but may lead to higher charges.
- Unified CloudWatch agent collects both logs and metrics.

## CloudWatch Events

- Delivers near real-time stream of system events for AWS resource changes.
- Used to schedule automated actions that self-trigger at specific times using cron or rate expressions.
- Supports various target functions or streams for events, including EC2 instances, Lambda functions, Kinesis Data Streams, and more.

## Useful API Actions

- GetMetricData: Retrieve up to 500 different metrics in a single request.
- PutMetricData: Publish metric data points to CloudWatch, associating them with specified metrics.
- GetMetricStatistics: Get statistics for a specified metric with data aggregation.
- PutMetricAlarm: Create or update an alarm associated with a metric or anomaly detection model.

</details>

<details><summary> 6. AWS Organizations
</summary>

AWS Organizations is a powerful service that enables centralized management and governance of your AWS environment as you grow and scale your resources. It provides features such as multi-account environment management, account grouping, tag policies, service control policies (SCPs), and more. Some key points to understand are:

## Features of AWS Organizations:

- Simplify account creation: You can programmatically create new accounts using CLI, SDKs, or APIs.
- Organizational Units (OUs): Group accounts into OUs, allowing you to create hierarchies.
- Tag policies: Classify and track resources with attribute-based access control.
- Delegation: Delegate responsibilities for supported AWS services to accounts.
- Security management: Centrally provide tools and access for the security team.
- Amazon Single Sign-On (SSO): Provide access to AWS accounts and resources using your active directory.
- Service Control Policies (SCPs): Control access to AWS resources, services, and Regions within your organization.
- AWS Resource Allocation Management (RAM): Share AWS resources within your organization.
- AWS CloudTrail: Activate CloudTrail across accounts to create a log of all activity in your cloud environment.
- Consolidated billing: Get a single consolidated bill for all AWS accounts in your organization.

## Key Concepts:

- AWS Organization: A collection of AWS accounts that can be organized into a hierarchy and managed centrally.
- AWS Account: A container for AWS resources.
- Management Account: The AWS account used to create the organization.
- Member Account: An AWS account that is part of the organization.
- Administrative Root: The top-most container in the organization's hierarchy.
- Organizational Unit (OU): A group of AWS accounts within the organization, forming hierarchies.
- Policy: Controls applied to groups of AWS accounts, including Service Control Policies (SCPs).

## Best practices for the management account:

- Use the management account only for management tasks.
- Secure the root user with MFA and a complex password.
- Review and monitor access to the root user credentials.
- Apply controls to manage access to the root user credentials.

## Migrating accounts between organizations:

- Accounts can be migrated between organizations.
- Use the AWS Organizations console for a few accounts, API or CLI for many accounts.
- Billing history and reports stay with the management account after migration.

## Service Control Policies (SCPs):

- SCPs manage permissions in the organization and provide central control over permissions.
- SCPs affect only member accounts and restrict permissions for IAM users and roles.
- They do not affect resource-based policies or users/roles outside the organization.
- SCPs are not sufficient to grant permissions and must be combined with IAM policies.

## Resource Groups:

- Resource groups help organize and automate tasks on AWS resources.
- Tag-based and AWS CloudFormation stack-based queries can be used to build groups.

AWS Organizations is available to all AWS customers at no additional charge and offers a flexible and robust way to manage and scale your AWS resources effectively.

</details>

<details><summary>7. AWS Config
</summary>

AWS Config is a fully managed service that plays a crucial role in managing and securing AWS resources. It offers several features and capabilities to enable better security, governance, compliance, and configuration management in an AWS environment.

Key Features:
- **Resource Inventory:** AWS Config provides a comprehensive inventory of all the AWS resources present in your account. This includes detailed configuration information for each resource, such as Amazon Resource Names and tags.

- **Configuration History:** With AWS Config, you can track the configuration changes made to your resources over time. It records the configuration details as Configuration Items (CIs), allowing you to see how a resource was configured at any specific point in time.

- **Configuration Change Notifications:** AWS Config sends notifications when configuration changes occur, enabling you to stay informed about any modifications to your resources.

- **Compliance Auditing:** AWS Config Rules enable you to define desired configurations for resources and check whether they comply with these configurations. Non-compliant resources are flagged, making it easier to maintain compliance with organizational standards.

- **Security Analysis:** By having a historical view of resource configurations, AWS Config aids in security analysis, helping you identify potential security risks and vulnerabilities.

- **Troubleshooting:** When issues arise, AWS Config can be an invaluable tool for troubleshooting. It allows you to compare the current state of a resource with past configurations, helping pinpoint when and what changes might have caused the problem.

- **Cost Structure:** AWS Config charges are based on the number of Configuration Items (CIs) recorded for supported resources in your AWS account. CIs are created whenever a change to a recorded resource type is detected.

AWS Config vs AWS CloudTrail:
- AWS CloudTrail focuses on recording user API activity, providing information about "who" made specific API calls to modify resources.
- AWS Config, on the other hand, focuses on recording and storing "what" the resource configuration looked like at various points in time.

Configuration Items (CIs):
- CIs represent the configurations of resources at specific points in time.
- Each CI includes basic resource information, resource-specific data, relationships with other resources, related AWS CloudTrail event IDs, and metadata for identification.

AWS Config Rules:
- AWS Config Rules are used to define and evaluate desired configurations for resources.
- These rules check resources for compliance with desired conditions, flagging resources as "noncompliant" if violations are found.

In conclusion, AWS Config is a powerful service that enhances the security, governance, and management of AWS resources. By providing detailed configuration tracking, compliance checks, and resource inventory, it becomes an essential component of any well-managed AWS environment.

</details>