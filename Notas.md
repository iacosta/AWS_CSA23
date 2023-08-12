## Notas de AWS Associated

<details><summary> 6. Administración & Gobierno
</summary>

---
1. **AWS CloudFormation**
---

- **Infrastructure as Code (IaC)**:
  - Define and provision AWS infrastructure using code.
  - Automates resource creation, modification, and deletion.

- **Templates**:
  - JSON or YAML formatted files defining AWS resources.
  - Templates are the blueprints for stacks.

- **Stacks**:
  - A collection of AWS resources managed as a single unit.
  - Created, updated, or deleted as a whole.
  - AWS CloudFormation provides two methods for updating stacks: direct update or creating and executing change sets. When you directly update a stack, you submit changes and AWS CloudFormation immediately deploys them.
  
- **Resources**:
  - AWS services, instances, databases, etc. defined in templates.
  - Managed as a single unit within a stack.

- **Parameters**:
  - Inputs that customize template behavior.
  - Enable dynamic configuration of stacks.

- **Mappings**:
  - Key-value pairs for selecting template values based on input.
  - Useful for region-specific configurations.

- **Outputs**:
  - Values exported from the stack for reference by other stacks.
  - Can be used to pass information between stacks.

- **Nested Stacks**:
  - Embedding one CloudFormation stack within another.
  - Helps modularize complex templates.

- **Change Sets**:
  - Preview changes before applying them to a stack.
  - Safeguard against unintended modifications.

- **Stack Policies**:
  - Control update and deletion permissions for stack resources.
  - Helps prevent accidental modifications.

- **Rollback Protection**:
  - Prevents stack from being accidentally deleted.
  - Useful for critical resources.

- **Drift Detection**:
  - Identifies differences between a stack's actual and expected configuration.
  - Helps maintain infrastructure consistency.

- **Custom Resources**:
  - Invoke Lambda functions or other AWS services from a stack.
  - Extend CloudFormation capabilities.

- **StackSets**:
  - Deploy stacks across multiple AWS accounts and regions.
  - Useful for consistent multi-account management.

- **Cross-Stack References**:
  - Referencing resources from other stacks.
  - Enables decoupled resource management.

- **AWS CloudFormation Designer**:
  - Visual tool for creating, viewing, and modifying templates.

- **AWS CloudFormation CLI and SDKs**:
  - Command-line interface and software development kits for CloudFormation.

- **Lifecycle Hooks**:
  - Perform custom actions during stack creation or deletion.
  - Integrate with external systems.

- **Deletion Policies**:
  - Control what happens to resources when a stack is deleted.
  - Retain, delete, or snapshot resources.

- **Stack Notifications**:
  - Receive notifications on stack events via Amazon SNS.

- **Stack Tags**:
  - Assign metadata to stacks for better organization and management.

- **CloudFormation Stack Drift**:
  - Checks for differences between the expected and actual stack configuration.

- **CloudFormation StackSets Drift**:
  - Detects drift across multiple accounts and regions with StackSets.
---
2. **AWS OpsWoks**
---

- **AWS OpsWorks Overview:**
  - Managed configuration management service for automating infrastructure setup, deployment, and management.
  - Supports Chef and Puppet for defining and managing configurations.
  - Enables DevOps practices by automating code deployment, scaling, and monitoring.

- **OpsWorks Stacks:**
  - Fundamental organizational unit in OpsWorks.
  - Contains layers, instances, apps, and other resources.
  - Represents a single application stack or a logical grouping of related resources.

- **Layers:**
  - Defines a specific component of the stack, such as application server, database, load balancer.
  - Associates instances with a set of roles, recipes (Chef), or manifests (Puppet).
  - Granular control over configuration and software packages.

- **Instances:**
  - Virtual machines managed by OpsWorks within a stack.
  - Belong to one or more layers, facilitating modular architecture.
  - EC2 instances or instances within a Virtual Private Cloud (VPC).

- **Apps:**
  - Represents applications to be deployed and managed.
  - Supports various application types like web apps, custom apps, or frameworks.
  - Integrates with version control systems (Git, SVN) for automatic updates.

- **Lifecycle Events:**
  - Hooks triggered during instance setup, deployment, and shutdown.
  - Custom scripts can be executed at different stages.
  - Enables customization and automation of application lifecycle.

- **Configuration Management (Chef and Puppet):**
  - Chef: Uses cookbooks and recipes to define configurations.
  - Puppet: Utilizes manifests to declare desired system state.
  - Automates server configuration, reducing manual tasks.

- **Security and IAM Integration:**
  - Leverages AWS Identity and Access Management (IAM) for access control.
  - Assigns roles to instances, granting secure access to AWS resources.

- **Monitoring and Auto Healing:**
  - Integrates with Amazon CloudWatch for monitoring and metrics.
  - Auto-healing replaces failed instances based on health checks.
  - Enhances availability and performance.

- **Customization with Custom Cookbooks:**
  - Extend built-in recipes using custom cookbooks.
  - Tailor configurations to specific requirements.
  - Supports complex application setups.

- **Deployment Strategies:**
  - Time-based: Scheduled deployments at specified intervals.
  - Event-based: Triggered by repository updates or other events.
  - Ensures seamless application updates and releases.

- **Load Balancing Integration:**
  - Works with Elastic Load Balancing to distribute traffic across instances.
  - Supports high availability and scalability.

- **Data Management:**
  - Data Bags (Chef) and Hiera (Puppet) for secure configuration data storage.
  - Safely manage sensitive information like credentials.

- **CloudFormation Integration:**
  - Define OpsWorks resources using CloudFormation templates.
  - Infrastructure as Code (IaC) approach for consistent setups.

- **Stack Creation and Cloning:**
  - Create new stacks or clone existing ones.
  - Efficiently replicate configurations for different environments.

- **Cost Management:**
  - Optimize costs with automated scaling based on workload.
  - Right-size instances for efficient resource utilization.
---
3. **AWS CloudTrail**
---

- **AWS CloudTrail Overview**
  - Service that enables governance, compliance, operational auditing, and risk auditing of your AWS account.
  - Records API calls and events for your account on AWS services.
  - Captures account activity and stores it in an S3 bucket or delivers it to CloudWatch Logs.

- **Trail Configuration**
  - A trail is a configuration that specifies the types of events to be recorded.
  - Can be global or regional, capturing events for all or specific regions.
  - Can be applied to all AWS accounts or specific accounts.

- **Event Logging and Data**
  - CloudTrail logs include information such as event type, timestamp, user identity, and more.
  - Logs can include management events (actions users take), data events (resource modifications), and control plane operations.
  - Events are recorded in JSON format.

- **Integration with Other AWS Services**
  - CloudTrail can be integrated with CloudWatch Logs and CloudWatch Events for real-time monitoring and alerting.
  - Can be used with AWS Organizations to centralize logging across multiple accounts.
  - Works with AWS Config to provide more comprehensive visibility into resource changes.

- **Security and Compliance**
  - Provides a valuable tool for security analysis, resource change tracking, and compliance auditing.
  - Supports auditing of identity and access management (IAM) actions.
  - Helps in investigating security incidents and potential unauthorized activities.

- **Data Encryption and Retention**
  - CloudTrail logs are encrypted at rest using S3 server-side encryption (SSE).
  - Data events can include attributes for the changed data.
  - You can configure log file retention period.

- **Log File Integrity Validation**
  - CloudTrail logs are designed to ensure log file integrity and validate the origin of events.
  - Logs are digitally signed using AWS Key Management Service (KMS) signatures.

- **Use Cases**
  - Monitoring changes to resources for operational and security purposes.
  - Meeting compliance requirements and regulatory audits.
  - Tracking who accessed specific resources and when.

- **Key Terminology**
  - Event: A record of an action that occurs in your AWS environment.
  - Trail: A configuration that logs events and delivers them to a specified destination.
  - Event Selector: Configures which events are recorded in a trail.
  - Multi-Region Trail: Captures events across multiple AWS regions.

- **Benefits**
  - Provides an audit trail of API requests made on your AWS account.
  - Offers insights into resource history and changes.
  - Helps with troubleshooting operational issues.
---
4. **AWS Trusted Advisor**
---

- **AWS Trusted Advisor Overview**:
  - Service provided by AWS to optimize and improve your AWS environment.
  - Analyzes your resources and provides recommendations for cost optimization, security, performance, and fault tolerance.

- **Core Categories**:
  - **Cost Optimization**:
    - Identifies cost-saving opportunities by analyzing resource utilization and suggesting reserved instances, right-sizing, etc.
    - Recommends ways to reduce unnecessary spending.

  - **Performance**:
    - Analyzes performance bottlenecks and suggests optimizations for EC2 instances, RDS databases, and more.
    - Helps enhance application responsiveness and reduce latency.

  - **Security**:
    - Scans for security vulnerabilities, open ports, IAM permission issues, and other potential security risks.
    - Provides recommendations to enhance your overall security posture.

  - **Fault Tolerance**:
    - Evaluates your architecture for high availability and fault tolerance.
    - Recommends strategies to improve reliability, such as multi-AZ deployments, load balancing, and backup configurations.

  - **Service Limits**:
    - Monitors your resource usage against AWS service limits.
    - Helps prevent unexpected service disruptions due to exceeding resource quotas.

- **Accessing Trusted Advisor**:
  - Available through the AWS Management Console.
  - Provides a dashboard with an overview of your checks and recommendations.

- **Check Categories**:
  - **Core Checks**:
    - Available to all AWS customers.
    - Cover foundational best practices and recommendations.

  - **Business**:
    - Available for Business and Enterprise support plans.
    - Focuses on helping you achieve business outcomes and operational excellence.

  - **Enterprise**:
    - Available for Enterprise support plans.
    - Tailored for larger enterprises with more complex environments.

- **Recommendation Levels**:
  - **Actionable Recommendations**:
    - Immediate actions that can be taken to improve your environment.

  - **Optimization Plans**:
    - Detailed plans for making improvements over time.

- **Integration with AWS Organizations**:
  - Centralized management of Trusted Advisor across multiple AWS accounts.
  - Allows organization-wide visibility and management of recommendations.

- **Automated Checks**:
  - Trusted Advisor runs automated checks to continuously evaluate your environment.
  - Provides real-time recommendations based on changes in your resources.

- **Customization**:
  - Ability to enable or disable specific checks.
  - Tailor Trusted Advisor's focus to your organization's priorities.

- **AWS Trusted Advisor API**:
  - Programmatically access and integrate Trusted Advisor data into your applications or systems.
  - Retrieve recommendations and automate actions based on the API.

---
5. **AWS CloudWatch**
---

- **Monitoring and Observability:**
  - CloudWatch is a monitoring and observability service provided by AWS.
  - It collects and tracks metrics, logs, and events from various AWS resources and applications.

- **Metrics:**
  - Metrics are fundamental monitoring data points like CPU utilization, network traffic, etc.
  - CloudWatch Metrics can be collected from AWS services, custom applications, and resources.
  - Metrics have dimensions (e.g., instance ID, environment) for more granular analysis.

- **Dashboards:**
  - Dashboards provide customizable visualizations of metrics and alarms.
  - They can display multiple metrics from different resources on a single page.

- **Alarms:**
  - Alarms monitor metric data and perform actions based on defined thresholds.
  - You can set actions like sending notifications, auto-scaling, etc., when thresholds are breached.

- **Logs:**
  - CloudWatch Logs collect, monitor, and store log data from applications and services.
  - Useful for debugging, troubleshooting, and auditing.

- **Log Groups and Log Streams:**
  - Log Groups are collections of Log Streams, representing a specific application or resource.
  - Log Streams contain the actual log events.

- **Log Retention and Insights:**
  - CloudWatch Logs can have retention policies to control how long log data is stored.
  - CloudWatch Insights enables advanced querying and analysis of log data.

- **Events and EventBridge:**
  - CloudWatch Events capture and respond to changes in AWS resources.
  - EventBridge allows you to route events to various targets for automation.

- **CloudWatch Agent:**
  - A software agent for collecting custom system and application-level metrics.
  - Can be installed on EC2 instances or on-premises servers.

- **CloudWatch Container Insights:**
  - Provides in-depth monitoring of containerized applications using Kubernetes or ECS.

- **CloudWatch Synthetics:**
  - Monitors application endpoints with synthetic traffic and alerts on deviations.

- **CloudWatch Contributor Insights:**
  - Analyzes log data to identify top contributors and patterns.

- **Integration with Other AWS Services:**
  - CloudWatch integrates with services like EC2, RDS, Lambda, etc., to provide detailed insights.

- **CloudWatch Logs Insights Query Language:**
  - A powerful query language for analyzing log data efficiently.

- **Cross-Account and Cross-Region:**
  - CloudWatch can aggregate and monitor data from multiple AWS accounts and regions.

- **Use Cases:**
  - Monitoring application performance, resource utilization, and operational health.
  - Troubleshooting issues, analyzing trends, and making informed decisions.

---
6. **AWS SAM (Serverless Application Model)**
---
- **AWS SAM Overview:**
  - Definition of AWS SAM
  - Purpose and benefits of using AWS SAM

- **Serverless Architecture:**
  - Understanding of serverless architecture
  - Comparison with traditional server-based architecture

- **AWS SAM Template:**
  - Structure and components of SAM template (SAM.yaml)
  - Defining resources: functions, APIs, event sources, and more

- **Serverless Application Definition:**
  - Defining serverless applications using SAM
  - SAM syntax for declaring serverless functions and APIs

- **Lambda Functions:**
  - Creating and deploying Lambda functions using SAM
  - Handling function configurations and event triggers

- **API Gateway:**
  - Creating RESTful APIs using SAM
  - Configuring API endpoints and methods in SAM template

- **Event Sources:**
  - Understanding event sources (e.g., S3, DynamoDB, SQS)
  - Integrating event sources with Lambda functions in SAM

- **Local Testing and Debugging:**
  - Setting up local development environment for SAM
  - Using SAM CLI for testing and debugging

- **Packaging and Deployment:**
  - Packaging SAM applications for deployment
  - Deploying applications using SAM and CloudFormation

- **AWS SAM CLI:**
  - Installing and configuring the AWS SAM CLI
  - CLI commands for creating, testing, and deploying applications

- **CloudFormation Integration:**
  - Relationship between SAM and CloudFormation
  - SAM as an extension of CloudFormation for serverless applications

- **Parameterization and Environment Variables:**
  - Defining parameters and environment variables in SAM
  - Managing configuration across different deployment stages

- **CI/CD for SAM Applications:**
  - Implementing continuous integration and deployment for SAM
  - Automating deployment pipelines using tools like AWS CodePipeline

- **Monitoring and Logging:**
  - Monitoring serverless applications in AWS
  - Integrating with CloudWatch Logs and Metrics

- **Security and Access Control:**
  - Implementing security best practices for SAM applications
  - Configuring IAM roles and permissions

- **Resource Management and Cleanup:**
  - Managing resources and avoiding resource leaks
  - Cleaning up resources after testing or development

- **Versioning and Rollback:**
  - Versioning SAM applications and APIs
  - Rollback strategies and considerations

---
7. **AWS Organizations**
---

- **AWS Organizations Overview**
  - Hierarchical structure for managing multiple AWS accounts
  - Enables centralized management of policies, billing, and resources

- **Organizational Units (OUs)**
  - Subdivisions within an organization to group accounts
  - Allows delegation of management and policies at different levels

- **Consolidated Billing**
  - Single payment method for multiple AWS accounts
  - Simplifies billing and cost tracking

- **Service Control Policies (SCPs)**
  - Set of policies that control access to AWS services
  - Applied at the organizational level to restrict actions (Ex.Create an SCP with a deny rule that denies all but the specific instance types)

- **Policy Inheritance**
  - SCPs are inherited by all OUs and accounts beneath them
  - Provides a consistent policy framework

- **Tag Policies**
  - Define rules for tagging resources across the organization
  - Enforce consistent tagging practices

- **Cross-Account Access**
  - Allow accounts within an organization to access each other's resources
  - Controlled by SCPs

- **Organizational Root Account**
  - Top-level account in an AWS organization
  - Used for billing and overall management

- **Member Accounts**
  - AWS accounts within the organization
  - Can be part of OUs and inherit policies
  - Migrate the account using the AWS Organizations console

- **Consolidated Billing Family**
  - Linked accounts for consolidated billing
  - Simplifies cost management for multiple accounts

- **Policy Evaluation**
  - SCPs are evaluated in a deny-override manner
  - Deny takes precedence over allow

- **Use Cases**
  - Centralized security management
  - Simplified billing and cost tracking
  - Controlled resource sharing and access

- **Limitations and Considerations**
  - Some AWS services have limitations with SCPs
  - SCPs might impact permissions unexpectedly if not configured carefully

---
8. **AWS Config**
---

- **AWS Config Overview**
  - Definition and purpose of AWS Config
  - Configuration items and attributes
  - Benefits of using AWS Config
  - You can use EventBridge to detect and react to changes in the status of AWS Config events

- **Configuration Recorder**
  - Enabling and configuring the AWS Config recorder
  - Recording resource configurations and changes
  - Supported resource types

- **Configuration Rules**
  - Creating custom rules and managed rules
  - Compliance and best practices evaluation
  - Remediation actions for non-compliant resources
  - AWS Config rule can be configured using the “access-keys-rotated” managed rule which checks if the active access keys are rotated within the number of days specified in maxAccessKeyAge.

- **AWS Config Aggregator**
  - Aggregating configuration data across regions and accounts
  - Use cases for aggregators
  - Aggregator types: single-account and multi-account

- **Configuration History and Snapshot**
  - Viewing historical configuration changes
  - Creating and using configuration snapshots
  - Tracking resource relationships over time

- **Delivery Channels**
  - Configuring delivery channels (Amazon S3, SNS, etc.)
  - Sending configuration change notifications
  - Managing and monitoring delivery channel status

- **Advanced Concepts**
  - AWS Config Custom Resources
  - Configuration and compliance drift
  - Using AWS Config with AWS Organizations

- **Security and Compliance**
  - Role-based access control (IAM) for AWS Config
  - Configuring encryption for stored configuration data
  - Compliance assessments and reporting

- **Integration with Other AWS Services**
  - AWS CloudTrail integration
  - AWS Config and AWS CloudFormation
  - Using AWS Config with AWS Systems Manager

- **Best Practices and Troubleshooting**
  - Implementing tagging strategies
  - Handling configuration changes in complex environments
  - Debugging common AWS Config issues

---
8. **AWS Control Tower**
---

- **AWS Control Tower Overview:**
  - Managed service to set up and govern a multi-account AWS environment.
  - Provides a baseline environment that adheres to best practices.
  - Simplifies provisioning, management, and monitoring of multiple AWS accounts.

- **Account Factory:**
  - Automates the creation of new AWS accounts with predefined configurations.
  - Ensures consistency and compliance across accounts.

- **Guardrails:**
  - Set of predefined policies to enforce compliance and prevent common misconfigurations.
  - Helps maintain security and operational best practices.
  - Can be customized to meet specific organizational needs.

- **Blueprints:**
  - Reusable templates for creating secure and compliant environments.
  - Includes predefined configurations for networking, security, and identity.

- **Centralized Logging and Monitoring:**
  - Aggregates and centralizes logs and metrics from managed accounts.
  - Simplifies troubleshooting, analysis, and compliance auditing.

- **AWS Single Sign-On (SSO) Integration:**
  - Provides centralized user access management.
  - Enables single sign-on (SSO) for various AWS accounts and services.

- **Lifecycle Event Management:**
  - Automates common operational tasks, such as scaling resources.
  - Helps maintain consistency and efficiency across accounts.

- **Customizations:**
  - Allows organization-specific policies, guardrails, and configurations.
  - Provides flexibility to adapt AWS Control Tower to unique requirements.

- **Organizational Units (OUs):**
  - Logical containers to group and manage AWS accounts.
  - Helps organize accounts based on business units or departments.

- **Cross-Account Permissions:**
  - Simplifies granting permissions across accounts.
  - Enables secure resource sharing between accounts.

- **Compliance Dashboard:**
  - Provides a centralized view of compliance status.
  - Tracks guardrail violations and overall account health.

- **AWS Control Tower Console:**
  - Web-based interface for managing and monitoring the AWS Control Tower environment.
  - Streamlines administrative tasks and provides visibility into account activities.

- **CloudTrail Integration:**
  - Captures API activity across AWS accounts for auditing and security analysis.
  - Enhances visibility into account-level actions.

- **AWS Organizations Integration:**
  - Works seamlessly with AWS Organizations for managing and organizing accounts.

- **Backup and Restore:**
  - Allows backup and restore of the AWS Control Tower configuration.
  - Helps recover from accidental changes or failures.

---
9. **AWS License Manager**
---

- **License Manager Basics:**
  - AWS License Manager is a service that helps you manage software licenses in AWS environments.
  - It allows you to set rules and enforce license usage across various AWS resources.

- **License Configuration:**
  - A license configuration defines terms for using a particular software license.
  - It specifies details such as product information, licensing terms, and allowed resources.

- **Association with Resources:**
  - License configurations are associated with EC2 instances, Amazon RDS instances, and other supported resources.
  - This association ensures that the correct licenses are applied to the corresponding resources.

- **License Tracking:**
  - AWS License Manager tracks license usage based on the license configurations associated with resources.
  - It provides visibility into license consumption and helps prevent overuse.

- **License Rules:**
  - License rules define how licenses should be allocated to resources.
  - They can be based on factors like instance attributes, tags, or custom fields.

- **License Entitlements:**
  - License entitlements represent the total number of licenses you own for a specific product.
  - AWS License Manager helps you manage and track entitlements.

- **Cross-Account Sharing:**
  - License Manager supports sharing licenses across multiple AWS accounts.
  - This allows for centralized license management and cost optimization.

- **Bring Your Own License (BYOL):**
  - BYOL allows you to use existing software licenses within the AWS environment.
  - License Manager ensures compliance with license terms and optimizes license usage.

- **Reporting and Compliance:**
  - License Manager provides reporting and compliance tools to monitor license usage and ensure adherence to licensing terms.

- **Integration with AWS Organizations:**
  - License Manager can be integrated with AWS Organizations for consistent license management across accounts.

- **API and SDK Support:**
  - License Manager offers APIs and SDKs for programmatic access, enabling automation and integration with other tools.

- **Use Cases:**
  - License Manager is useful for optimizing license costs, ensuring compliance, and simplifying license management in complex environments.

- **Supported License Vendors:**
  - AWS License Manager supports licenses from various vendors, including Microsoft, Oracle, IBM, and others.

- **Resource Visibility:**
  - The service provides visibility into license usage and allows you to take corrective actions as needed.

- **Automation and Flexibility:**
  - License Manager's automation features help streamline license provisioning and tracking, enhancing operational efficiency.

  Sure, here's a bullet list of key concepts about AWS Systems Manager for studying towards the AWS Certification. I've provided the list in Markdown format for easy readability:

---
10. **AWS System Manager**
---

- **AWS Systems Manager Overview:**
  - Centralized management for AWS resources.
  - Automates operational tasks at scale.

- **Resource Groups:**
  - Logical collections of resources with common attributes.
  - Used for grouping and organizing resources.

- **Inventory Management:**
  - Collects metadata about resources using Inventory.
  - Tracks configuration changes over time.

- **Patch Management:**
  - Automates patching of instances and OS updates.
  - Schedule patching using maintenance windows.

- **Automation:**
  - Allows for creation of custom automation workflows.
  - Simplifies operational tasks and troubleshooting.

- **Run Command:**
  - Executes commands on multiple instances simultaneously.
  - Supports one-time or recurring tasks.

- **Session Manager:**
  - Provides interactive shell access to instances.
  - No need for inbound SSH/RDP ports.

- **Parameter Store:**
  - Stores configuration and secure information.
  - Hierarchical structure for easy organization.

- **Distributed Parameter Store:**
  - Store sensitive configuration using KMS encryption.
  - Share parameters across accounts.

- **OpsCenter:**
  - Central location for managing operational issues.
  - Collaborative troubleshooting and resolution.

- **Application Manager:**
  - Package, deploy, and run applications using AppConfig.
  - Simplifies application lifecycle management.

- **State Manager:**
  - Defines and maintains desired configuration.
  - Ensures instances are in the desired state.

- **Resource Data Sync:**
  - Collects data from multiple sources into one location.
  - Supports integration with AWS Config and CloudWatch.

- **Maintenance Windows:**
  - Define windows for planned maintenance.
  - Control when automation tasks are executed.

- **Compliance:**
  - Monitor and enforce compliance policies.
  - Integrates with AWS Config for rule evaluation.

- **CloudFormation Integration:**
  - Define Systems Manager resources in CloudFormation.
  - Automate Systems Manager setup.

- **Security and Permissions:**
  - Use IAM roles and policies for access control.
  - Least privilege principle for security.

- **Troubleshooting and Logging:**
  - Utilize CloudWatch Logs for monitoring and logging.
  - Detailed execution logs for automation tasks.


---
11. **AWS OpenSearch Services**
---

- **Amazon OpenSearch Service Overview:**
  - Managed Elasticsearch service offered by AWS.
  - Built on open-source Elasticsearch and Kibana.

- **Deployment and Management:**
  - Easily deploy, manage, and scale OpenSearch clusters.
  - Supports various instance types for different use cases.

- **Data Ingestion and Storage:**
  - Ingest data from various sources using APIs or plugins.
  - Store and index data using Elasticsearch indices.

- **Search and Querying:**
  - Perform powerful full-text searches on data.
  - Utilize queries, aggregations, and filters.

- **Kibana Visualization:**
  - Integrated with Kibana for data visualization and exploration.
  - Create interactive dashboards and visualizations.

- **Security and Access Control:**
  - Implement fine-grained access controls using IAM policies.
  - Encryption at rest and in transit for data security.

- **High Availability and Fault Tolerance:**
  - Multi-AZ deployment for high availability.
  - Automated backups and snapshots for data protection.

- **Scaling and Performance:**
  - Easily scale clusters up or down based on demand.
  - Utilize dedicated master and data nodes for optimized performance.

- **Monitoring and Alerts:**
  - Monitor cluster health and performance metrics.
  - Set up alarms and notifications for proactive management.

- **Indexing and Data Lifecycle Management:**
  - Define index policies for data retention and archiving.
  - Use Index State Management for automated index actions.

- **Integration with Other AWS Services:**
  - Integrate with Amazon S3, Lambda, and other services.
  - Leverage AWS Identity and Access Management (IAM) for access control.

- **Use Cases:**
  - Log and event data analysis.
  - Full-text search and real-time analytics.
  - Business intelligence and data visualization.

- **Migration and Data Transformation:**
  - Migrate data from self-managed Elasticsearch to OpenSearch.
  - Transform and enrich data using Logstash or other tools.

- **Pricing and Cost Optimization:**
  - Understand pricing models and cost considerations.
  - Implement cost-saving strategies based on usage patterns.

---
12. **AWS Cost Managament**
---

- **AWS Cost Explorer**
  - Tool for exploring AWS cost and usage data.
  - Offers customizable reports and visualization of costs.
  - Helps analyze cost trends and identify cost-saving opportunities.

- **AWS Budgets**
  - Set cost and usage budgets for AWS resources.
  - Monitors spending against defined budgets.
  - Sends alerts when budget thresholds are breached.

- **AWS Cost and Usage Reports**
  - Provides detailed usage and cost data in a downloadable format.
  - Offers granularity and customization options for analysis.
  - Supports different time intervals and reporting levels.

- **Consolidated Billing**
  - Combines multiple AWS accounts into a single payment method.
  - Simplifies billing and provides centralized cost tracking.
  - Enables better cost allocation and management for organizations.

- **Savings Plans**
  - Flexible pricing model to save on EC2 and Fargate usage.
  - Offers cost savings compared to On-Demand instances.
  - Requires commitment to a specific monetary amount per hour for a term.

- **Reserved Instances (RIs)**
  - Pre-purchase of EC2 instances for a term (1 or 3 years).
  - Provides significant cost savings compared to On-Demand instances.
  - Offers options for Standard, Convertible, and Scheduled RIs.

- **Spot Instances**
  - Allows bid-based purchasing of spare EC2 capacity.
  - Offers significant cost savings, suitable for fault-tolerant and flexible workloads.
  - Instances can be interrupted if capacity is needed by On-Demand instances.

- **Cost Allocation Tags**
  - Custom labels applied to resources for cost tracking.
  - Enables granular analysis and allocation of costs.
  - Used to attribute costs to specific departments, projects, or teams.

- **AWS Organizations**
  - Enables management of multiple AWS accounts.
  - Provides consolidated billing and centralized cost management.
  - Offers hierarchical structure for better organization and control.

- **Trusted Advisor**
  - Analyzes AWS environment for cost optimization opportunities.
  - Provides recommendations for cost savings, performance improvement, and security enhancements.
  - Helps in identifying underutilized resources and excess spending.

- **Total Cost of Ownership (TCO)**
  - Comprehensive assessment of costs associated with running workloads on AWS.
  - Includes direct and indirect costs, such as labor and infrastructure.
  - Used to evaluate cost-effectiveness of on-premises vs. cloud deployments.

</details>

<details><summary> 10. Arquitectura & Diseño
</summary>

### AWS Cloud Disaster Recovery Scenarios

The AWS Cloud offers a range of disaster recovery (DR) approaches, providing quick and reliable recovery options for IT systems. These scenarios are arranged based on the speed at which a system can be available to users after a disaster event:

1. **Backup and Restore**
   - Simple and cost-effective approach.
   - Back up data and applications to the AWS Cloud for recovery.
   - No use of conventional tape backups.
   - Amazon EC2 instances are utilized for testing as needed.
   - Low storage costs with Amazon S3 (as low as $0.015/GB for infrequent access).

2. **Pilot Light**
   - Analogy from gas heating: a small flame ignites the entire furnace quickly.
   - Replicate a portion of your IT structure for core services.
   - AWS Cloud takes over seamlessly during a disaster.
   - Critical core elements must already be configured and running in AWS.
   - Rapidly provision a full-scale production environment around the critical core during recovery.

3. **Warm Standby**
   - A scaled-down version of a fully functional environment is always running in the cloud.
   - Extends the pilot light approach and decreases recovery time.
   - Some services are always running, improving readiness for recovery.
   - Identify and fully duplicate business-critical systems on AWS.

4. **Multi-site**
   - Run on AWS and existing on-site infrastructure in an active-active configuration.
   - Data replication method determined by Recovery Time Objective or Recovery Point Objective.
   - Ensures continuous operations with minimal downtime or data loss during the DR process.

Each of these scenarios provides flexible and efficient options for businesses to protect their critical data and applications, ensuring seamless recovery from disasters anytime, anywhere. For more information on each approach, refer to the respective links provided.

Fuente
[AWS](https://aws.amazon.com/blogs/publicsector/rapidly-recover-mission-critical-systems-in-a-disaster/)

</details>
