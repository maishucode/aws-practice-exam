# 🌟 AWS Certified Solutions Architect - Professional 🌟

Welcome to our practice exam portal! This page is designed to help you master the key concepts and best practices for AWS architecture. Whether you're preparing for your certification exam or looking to boost your practical skills, our high-quality questions and in-depth explanations are here to support you.

---

> **Quick Tip:**  
> For an even better learning experience and a wealth of additional resources, please visit our website:  
> [https://www.awsxp.com/](https://www.awsxp.com/)  
> Discover the latest case studies, expert insights, and specialized courses that will supercharge your AWS skills!

---

> **Get Started Now!**  
> Click on the "View Answer" button on any question below to reveal detailed explanations and solutions.  
> Enjoy your journey to AWS excellence and success on the AWS Certified Solutions Architect - Professional exam! 🚀

## ❓ Question 101

A company is running applications on AWS in a multi-account setup under AWS Organizations. The development team and analytics team operate in separate AWS accounts. The development team stores terabytes of sensitive data in an Amazon S3 bucket encrypted with an AWS KMS key. The analytics team uses Amazon Redshift for data processing and requires access to the development team's S3 bucket. The analytics team has already configured an IAM role for Amazon Redshift in their account. The company needs a secure cross-account solution with minimal operational overhead.

- **A.** Create a new S3 bucket in the analytics account. Configure S3 replication rules in the development account to copy data to the analytics account's bucket. Update the Redshift permissions in the analytics account to access the replicated bucket.
- **B.** Use an SCP to grant the analytics account access to the S3 bucket. Share the KMS key via AWS Resource Access Manager (AWS RAM) from the development account to the analytics account. Modify the Redshift IAM role to include permissions for the S3 bucket.
- **C.** Update the S3 bucket policy in the development account to grant the Redshift role access. Create a KMS grant for the encryption key to allow the Redshift role to decrypt data. Adjust the Redshift permissions to include the S3 bucket.
- **D.** Create an IAM role in the development account with access to the S3 bucket and KMS key. Configure the Redshift role in the analytics account to assume the development account's IAM role. Update the KMS key policy to allow the Redshift role to use the key.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. Creating an IAM role in the development account and allowing the analytics account's Redshift role to assume it ensures secure cross-account access to the S3 bucket and KMS key with minimal operational overhead. ✨
  
</details>

---

## ❓ Question 102

A company is migrating its enterprise applications from an on-premises data center to AWS. The company operates an Oracle database with Real Application Clusters (RAC) on-premises and wants to transition to Amazon Aurora PostgreSQL. A solutions architect must design a heterogeneous database migration using AWS managed services.

Which solution meets these requirements?

- **A.** Migrate the Oracle databases to Amazon Aurora PostgreSQL using Oracle Data Pump utilities (expdp/impdp) for backup and restore.
- **B.** Transfer data to Amazon S3 using an AWS Snowball Edge Storage Optimized device. Configure Amazon Aurora PostgreSQL and use S3 integration with PostgreSQL's COPY command to load data.
- **C.** Convert the database schema using the AWS Schema Conversion Tool to Amazon Aurora PostgreSQL. Migrate the data using AWS Database Migration Service (AWS DMS) from on-premises Oracle to Aurora PostgreSQL.
- **D.** Migrate data over the network using AWS DataSync from on-premises storage to Amazon S3. Set up Amazon Aurora PostgreSQL and load data using PostgreSQL's COPY command with S3 integration.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C because AWS Schema Conversion Tool (SCT) handles schema conversion from Oracle to PostgreSQL, and AWS DMS migrates the data, ensuring compatibility and minimal downtime. ✨
  
</details>

---

## ❓ Question 103

A financial company's analytics team generates reports that need to be uploaded to an Amazon S3 bucket in the company's production account. The analytics team operates in a separate development account. The company requires that the team can only access the specific S3 bucket in the production account and must not have access to any other resources.

Which combination of steps should a solutions architect take to meet these requirements? (Choose three.)

- **A.** In the production account, create an IAM policy that grants read and write access to the S3 bucket.
- **B.** In the development account, create an IAM policy that grants read and write access to the S3 bucket.
- **C.** In the production account, create an IAM role. Attach the policy to the role and specify the development account as a trusted entity.
- **D.** In the development account, create an IAM role. Attach the policy to the role and specify the production account as a trusted entity.
- **E.** In the development account, create an IAM group for the analytics team members. Attach a policy that allows the sts:AssumeRole action on the role in the production account.
- **F.** In the development account, create an IAM group for the analytics team members. Attach a policy that allows the sts:AssumeRole action on the role in the development account.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ACE**
  
  > Short Explanation: The correct answers are A, C, and E. The production account must create an IAM policy and role with S3 access, trust the development account, and the development account must allow users to assume the role via sts:AssumeRole. ✨
  
</details>

---

## ❓ Question 104

A company developed a pilot application using AWS Elastic Beanstalk with Python. To minimize costs during testing, the development team deployed the application in a single-instance environment. Recent load tests revealed that the application experiences prolonged periods of CPU utilization exceeding 90%, leading to significant latency issues.

A solutions architect must resolve the performance problems before the application is moved to production.

Which solution addresses these requirements with the LEAST operational overhead?

- **A.** Create a new Elastic Beanstalk application. Configure a load-balanced environment type across all Availability Zones. Implement a scaling policy to add instances when maximum CPU utilization exceeds 90% for 10 minutes.
- **B.** Deploy a second Elastic Beanstalk environment. Use a weighted traffic routing policy to distribute requests between environments when average CPU utilization exceeds 90% for 10 minutes.
- **C.** Update the existing environment\u2019s capacity settings to enable a load-balanced environment type across all Availability Zones. Configure a scaling policy to add instances when average CPU utilization exceeds 90% for 10 minutes.
- **D.** Rebuild the environment with load balancing enabled in a single Availability Zone. Define a scaling policy to add instances when total CPU utilization across all instances exceeds 90% for 10 minutes.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Updating the existing Elastic Beanstalk environment to enable load balancing and auto-scaling addresses high CPU utilization with minimal operational overhead. This avoids creating new environments or applications, leverages AWS-managed scaling, and ensures high availability across Availability Zones. ✨
  
</details>

---

## ❓ Question 105

An e-commerce platform runs its transaction processing system on current-generation Linux EC2 instances. The system relies on a self-managed PostgreSQL database that experiences heavy I/O operations during peak hours. While the platform handles regular traffic adequately, it struggles with performance degradation during holiday sales events, despite employing Elastic Load Balancers and Auto Scaling to manage demand. Which of the following solutions would MOST effectively address the database performance issues with minimal operational disruption?

- **A.** Scaling up all EC2 instances to larger types, pre-warming Elastic Load Balancers, and migrating all Amazon EBS volumes to Provisioned IOPS (io2) volumes with maximum IOPS.
- **B.** Migrating the database to Amazon Aurora PostgreSQL with multiple read replicas to distribute read-heavy workloads during peak periods.
- **C.** Implementing AWS Lambda-triggered scaling for Amazon EBS volumes, dynamically adjusting volume size and IOPS based on CloudWatch metrics.
- **D.** Creating nightly EBS snapshots and replacing all volumes with larger Provisioned IOPS volumes before peak events, then reverting afterward.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Migrating to Amazon Aurora PostgreSQL with read replicas (B) addresses the database's I/O bottlenecks by leveraging Aurora's high-performance storage and read scalability, minimizing operational disruption compared to other options. ✨
  
</details>

---

## ❓ Question 106

A financial services firm operates a legacy Java application hosted on-premises with intricate dependencies on specific VM configurations. The application is stable, but the firm aims to modernize their infrastructure by migrating to AWS, reducing operational overhead, and minimizing code modifications. Which solution meets these requirements with the LEAST code changes?

- **A.** Use AWS App2Container to migrate the application to Amazon ECS on AWS Fargate. Store containers in Amazon ECR. Assign the necessary permissions to the ECS task role. Set up an Application Load Balancer to route traffic to the application.
- **B.** Refactor the application into AWS Lambda functions integrated with Amazon API Gateway HTTP APIs. Use API Gateway to manage requests and responses.
- **C.** Migrate the application using AWS App2Container to Amazon EKS managed nodes. Store images in ECR. Grant node permissions to access ECR. Expose the application through an Application Load Balancer.
- **D.** Package the application into a Lambda function with an ALB as the trigger. Configure the ALB to forward traffic to the Lambda function.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. AWS App2Container allows containerization of the legacy application with minimal code changes, while ECS Fargate reduces operational overhead by managing servers. An ALB ensures traffic routing, aligning with the requirement to modernize with minimal effort. ✨
  
</details>

---

## ❓ Question 107

A company operates a serverless application where an Amazon API Gateway in the eu-west-1 region triggers an AWS Lambda function. The current setup lacks regional redundancy. A solutions architect must redesign the architecture to enable automatic failover to another AWS Region in case of an outage. Which solution meets these requirements?

- **A.** Set up a new API Gateway in eu-central-1 that invokes the existing Lambda function in eu-west-1. Use Amazon Route 53 with failover routing to direct traffic between the two API Gateways.
- **B.** Implement an Amazon SNS topic to handle incoming requests. Configure the Lambda function to process messages from the SNS topic. Replicate the SNS topic and Lambda function in eu-central-1 and use Route 53 for DNS failover.
- **C.** Deploy the Lambda function in eu-central-1 and create an API Gateway there. Use AWS Global Accelerator with an Application Load Balancer to distribute traffic across both regions.
- **D.** Deploy the Lambda function and API Gateway in eu-central-1. Configure Amazon Route 53 with a failover routing policy to route traffic between the two API Gateway endpoints in each region.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D because it deploys fully redundant API Gateway and Lambda in both regions and uses Route 53 for automatic DNS failover, ensuring regional redundancy. ✨
  
</details>

---

## ❓ Question 108

A retail company uses AWS Organizations with consolidated billing and has organized its departments into the following OUs: Finance, Sales, Human Resources (HR), Marketing, and Operations. Each OU contains multiple AWS accounts corresponding to development, test, pre-production, and production environments. The Finance department has purchased Reserved Instances (RIs) in its production AWS account for a new financial analytics platform launching soon. The Finance department needs to ensure that no other departments can utilize the RI discounts allocated to their production account. What solution meets this requirement?

- **A.** In the AWS Billing and Cost Management console for the Finance department's production account, disable RI sharing.
- **B.** Remove the Finance department's production AWS account from the organization and link it to the consolidated billing configuration separately.
- **C.** Use the AWS Billing and Cost Management console in the organization\u2019s management account to disable RI sharing for the Finance department's production AWS account.
- **D.** Apply a Service Control Policy (SCP) to the OUs of other departments to block access to the Finance department's RIs.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. To prevent other departments from using the Finance department's Reserved Instances (RIs), the organization's management account must disable RI sharing for the Finance production account via the AWS Billing console. This ensures RIs are not shared across the organization. ✨
  
</details>

---

## ❓ Question 109

A large company operates a web application hosted on Amazon EC2 Linux instances in an Auto Scaling group within a private subnet. The instances are fronted by an Application Load Balancer (ALB), and AWS Systems Manager Session Manager is configured with the SSM Agent running on all instances. After a recent update to the security group rules, some instances are failing health checks and being terminated by the Auto Scaling group. The Amazon CloudWatch logs provide insufficient details to diagnose the issue. How should the solutions architect access an EC2 instance to investigate the problem?

- **A.** Suspend the Auto Scaling group\u2019s HealthCheck scaling process. Use Session Manager to connect to an unhealthy instance.
- **B.** Enable termination protection on the instance. Use Session Manager to connect to an unhealthy instance.
- **C.** Set the Auto Scaling group\u2019s termination policy to NewestInstance. Use Session Manager to connect to an unhealthy instance.
- **D.** Suspend the Auto Scaling group\u2019s Terminate process. Use Session Manager to connect to an unhealthy instance.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. Suspending the Auto Scaling group's Terminate process prevents unhealthy instances from being terminated, allowing access via Session Manager to investigate the issue. ✨
  
</details>

---

## ❓ Question 110

A company needs to enforce AWS WAF rules across multiple AWS accounts within an organization. The solution must allow administrators to dynamically include or exclude accounts and OUs, and automatically remediate noncompliant AWS WAF rules. Which approach minimizes operational effort while meeting these requirements?

- **A.** Use AWS Firewall Manager to manage AWS WAF rules across the organization. Store target account numbers and OUs in an Amazon S3 bucket. Configure an Amazon EventBridge rule to monitor changes to the S3 bucket and invoke an AWS Lambda function to update the Firewall Manager policy with the latest accounts and OUs. Firewall Manager automatically applies rules to the specified targets and remediates deviations.
- **B.** Deploy an AWS Config rule across all accounts to check for compliance with required AWS WAF rules. Use AWS CloudFormation stack sets to deploy WAF rules to targeted OUs. Configure AWS Lambda functions triggered by AWS Config events to remediate noncompliant rules. Manage target OUs via AWS Systems Manager Documents.
- **C.** Create AWS WAF rules in the management account and use AWS Step Functions to orchestrate cross-account deployments. Store target accounts and OUs in Amazon DynamoDB. Use Amazon CloudWatch Events to detect changes to DynamoDB and trigger Step Functions to assume roles in member accounts and update WAF rules directly.
- **D.** Use AWS Control Tower to enforce AWS WAF rules across the organization. Store account and OU targets in AWS Secrets Manager. Configure AWS Service Catalog to update Control Tower blueprints whenever Secrets Manager entries change. Use AWS Lambda to synchronize WAF rules with the updated blueprints.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. AWS Firewall Manager is designed to centrally manage AWS WAF rules across accounts and OUs in an organization. It automates rule deployment and remediation, minimizing operational effort. Storing targets in S3 and using EventBridge/Lambda to update policies ensures dynamic inclusion/exclusion of accounts and OUs. ✨
  
</details>

---

## ❓ Question 111

A solutions architect is reviewing the security configuration of an AWS Lambda function that processes user transactions stored in an Amazon RDS PostgreSQL database. The Lambda function and the database reside within the same VPC. Currently, the Lambda function uses environment variables to store the database credentials. Processed data is stored in an Amazon S3 bucket encrypted with SSE-KMS. The company mandates that all data transfers must occur within the AWS network and requires a solution to minimize exposure if database credentials are leaked.

What should the solutions architect recommend to meet these requirements?

- **A.** Enable IAM database authentication for the RDS PostgreSQL database. Modify the Lambda function's IAM role to grant permissions for IAM database authentication. Deploy a gateway VPC endpoint for Amazon S3 in the VPC.
- **B.** Enable IAM database authentication for the RDS PostgreSQL database. Modify the Lambda function's IAM role to grant permissions for IAM database authentication. Enforce HTTPS on all connections to Amazon S3 during data transfers.
- **C.** Store the database credentials in AWS Systems Manager Parameter Store. Configure credential rotation in Parameter Store. Update the Lambda function's IAM role to allow access to Parameter Store. Modify the Lambda function to fetch credentials from Parameter Store. Deploy a gateway VPC endpoint for Amazon S3 in the VPC.
- **D.** Store the database credentials in AWS Secrets Manager. Configure credential rotation in Secrets Manager. Update the Lambda function's IAM role to allow access to Secrets Manager. Modify the Lambda function to fetch credentials from Secrets Manager. Enforce HTTPS on all connections to Amazon S3 during data transfers.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A is correct because it uses IAM database authentication (eliminating static credentials) and deploys a VPC endpoint for S3 to ensure data stays within the AWS network. This addresses both security and data transfer requirements. ✨
  
</details>

---

## ❓ Question 112

A media streaming company has completed migrating its infrastructure to AWS. A solutions architect is auditing the environment to ensure compliance with the Well-Architected Framework. During a cost review, the architect identifies that QA engineers are launching oversized Amazon EC2 instances for testing, contributing to unexpectedly high costs. The architect must enforce restrictions to limit the QA engineers to specific, approved EC2 instance types. Which solution meets these requirements?

- **A.** Configure an AWS Config managed rule to detect non-compliant EC2 instance types. Set up automatic remediation to terminate instances that violate the rule.
- **B.** Develop an EC2 launch template specifying approved instance types. Apply an IAM policy that grants QA engineers permissions only to launch instances using this template.
- **C.** Create an IAM policy that explicitly allows only the approved EC2 instance types. Attach this policy to the IAM group associated with the QA engineers.
- **D.** Implement AWS Systems Manager Automation to monitor and automatically downsize any EC2 instances launched by QA engineers to approved types.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Creating an IAM policy that explicitly allows only approved EC2 instance types ensures QA engineers cannot launch oversized instances. This approach enforces restrictions proactively via IAM permissions, aligning with the requirement to limit costs and comply with the Well-Architected Framework. ✨
  
</details>

---

## ❓ Question 113

A company manages multiple AWS accounts under a single AWS Organizations umbrella. Several Amazon S3 buckets across these accounts are missing the required Department tag, which is critical for cost allocation and governance. The cloud team needs to address the existing issue and ensure future compliance. Which combination of actions should be taken? (Choose three.)

- **A.** Create an AWS Config rule in each account to detect S3 buckets missing the Department tag.
- **B.** Implement an SCP at the organization level to block creation of S3 buckets without the Department tag.
- **C.** Use Amazon Inspector to scan all S3 buckets for missing Department tags.
- **D.** Apply an IAM policy in each account to deny s3:CreateBucket requests without the Department tag.
- **E.** Set up an AWS Config aggregator to compile a centralized report of non-compliant S3 buckets across the organization.
- **F.** Use AWS Security Hub to aggregate findings about S3 buckets lacking the Department tag.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ABE**
  
  > Short Explanation: The correct answers are A, B, and E. AWS Config rules detect non-compliant S3 buckets, SCPs enforce future compliance organization-wide, and Config Aggregator centralizes reporting. These steps address both existing issues and prevent future violations. ✨
  
</details>

---

## ❓ Question 114

A company has an on-premises monitoring solution using a MySQL database for event persistence. The database struggles to handle increasing data volumes and frequently encounters storage limitations.

The company aims to implement a hybrid solution with a pre-established VPN connection between its network and AWS. The solution must include the following:

- Fully managed AWS services to reduce operational overhead.
- An auto-scaling buffer requiring no administrative effort to handle fluctuating data throughput.
- A visualization tool for near-real-time dashboards to monitor events.
- Compatibility with semi-structured JSON data and evolving schemas.

Which combination of components will meet these requirements? (Choose two.)

- **A.** Use Amazon Kinesis Data Firehose to buffer events. Deploy an AWS Lambda function to process and transform the data.
- **B.** Create an Amazon Kinesis data stream to buffer events. Deploy an AWS Lambda function to process and transform the data.
- **C.** Configure an Amazon Aurora MySQL DB cluster to ingest events. Use Amazon QuickSight to build near-real-time dashboards from the database.
- **D.** Use Amazon OpenSearch Service (Amazon OS) to store events. Utilize the integrated Kibana interface to create near-real-time visualizations.
- **E.** Configure an Amazon DocumentDB cluster to ingest events. Use Amazon QuickSight to visualize data from the database in near-real time.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AD**
  
  > Short Explanation: The correct answers are A and D. Amazon Kinesis Data Firehose provides a fully managed, auto-scaling buffer, while Amazon OpenSearch Service with Kibana handles semi-structured JSON data and enables near-real-time visualizations. Other options fail due to lack of auto-scaling, schema flexibility, or real-time capabilities. ✨
  
</details>

---

## ❓ Question 115

A team manages message processing for a company's microservices. The company operates a Multi-AZ VPC environment with public subnets, private subnets, and an internet gateway. Each public subnet includes a NAT gateway. Applications in private subnets send and receive messages using Amazon SQS. The workloads run exclusively in private subnets.

A solutions architect must reduce costs while maintaining functionality. Cost Explorer reveals high EC2-Other costs driven by NatGateway-Bytes charges. 

What should the solutions architect do to address this issue?

- **A.** Enable VPC Flow Logs. Use Amazon Athena to analyze traffic patterns. Update security groups to block unnecessary traffic contributing to high NAT costs.
- **B.** Add an interface VPC endpoint for SQS to the VPC. Ensure applications have IAM permissions to access the endpoint.
- **C.** Enable VPC Flow Logs and Amazon Detective. Use Detective findings to identify non-SQS traffic. Modify security groups to restrict such traffic.
- **D.** Add an interface VPC endpoint for SQS to the VPC. Ensure the VPC endpoint policy allows traffic from the private subnets.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. Adding an interface VPC endpoint for SQS allows applications in private subnets to communicate with SQS without using the NAT gateway, reducing NAT-related costs. The VPC endpoint policy must allow traffic from the private subnets to ensure functionality. ✨
  
</details>

---

## ❓ Question 116

A manufacturing company operates an on-premises data center in Asia. The company uses a multi-Region AWS environment spanning the ap-southeast-1 and us-west-2 Regions. The company requires routing network traffic from its on-premises infrastructure to VPCs in both Regions, as well as direct traffic routing between VPCs in these Regions. The solution must eliminate single points of failure on the network.

The company has established two 1 Gbps AWS Direct Connect connections from its on-premises data center, each terminating at separate Direct Connect locations in Asia (named DX-X and DX-Y) for redundancy. Each Region uses a single AWS Transit Gateway to manage all inter-VPC traffic within the Region.

Which solution meets these requirements?

- **A.** Create a private VIF from the DX-X connection into a Direct Connect gateway. Create a private VIF from the DX-Y connection into the same Direct Connect gateway for redundancy. Associate both the ap-southeast-1 and us-west-2 transit gateways with the Direct Connect gateway. Peer the transit gateways to enable cross-Region routing.
- **B.** Create a transit VIF from the DX-X connection into a Direct Connect gateway. Associate the ap-southeast-1 transit gateway with this gateway. Create a transit VIF from the DX-Y connection into a separate Direct Connect gateway. Associate the us-west-2 transit gateway with the second gateway. Establish peering between the Direct Connect gateways for cross-Region routing.
- **C.** Create a transit VIF from the DX-X connection into a Direct Connect gateway. Create a transit VIF from the DX-Y connection into the same gateway for redundancy. Associate both the ap-southeast-1 and us-west-2 transit gateways with this Direct Connect gateway. Configure the Direct Connect gateway to route traffic between the transit gateways.
- **D.** Create a transit VIF from the DX-X connection into a Direct Connect gateway. Create a transit VIF from the DX-Y connection into the same gateway for redundancy. Associate both the ap-southeast-1 and us-west-2 transit gateways with this Direct Connect gateway. Peer the transit gateways to enable cross-Region routing.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. It uses redundant transit VIFs with a single Direct Connect gateway, associates both Transit Gateways, and enables cross-Region routing via peering. This meets redundancy, connectivity, and fault tolerance requirements. ✨
  
</details>

---

## ❓ Question 117

A company requires that any IAM user added to an administrative group must have their group membership revoked automatically, and the security team must be notified for approval. The company uses a multi-Region AWS CloudTrail trail in the AWS account. Which combination of steps will meet these requirements? (Choose three.)

- **A.** Create an Amazon EventBridge (Amazon CloudWatch Events) rule. Define a pattern with the detail-type value set to AWS API Call via CloudTrail and an eventName of AddUserToGroup.
- **B.** Configure CloudTrail to send a notification for the AddUserToGroup event to an Amazon Simple Notification Service (Amazon SNS) topic.
- **C.** Invoke an AWS Lambda function to remove the user from the administrative group.
- **D.** Invoke an AWS Step Functions state machine to remove the user from the administrative group.
- **E.** Use Amazon Simple Notification Service (Amazon SNS) to notify the security team.
- **F.** Use Amazon Simple Email Service (Amazon SES) to notify the security team.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ADE**
  
  > Short Explanation: The correct answers are A, D, and E. EventBridge detects the AddUserToGroup event via CloudTrail, triggers Step Functions to remove the user, and SNS notifies the security team. ✨
  
</details>

---

## ❓ Question 118

A company is migrating to AWS and wants to implement a multi-account structure with centralized access management and private network traffic. Multi-factor authentication (MFA) is mandatory, and roles must be assigned based on departmental groups. The company requires separate accounts for finance, HR, analytics, and shared services. The finance and HR accounts must have connectivity to each other and the shared services account. The analytics account must only access the shared services account.

Which combination of steps should a solutions architect take to meet these requirements? (Choose three.)

- **A.** Deploy a landing zone using AWS Control Tower. Enroll accounts and integrate existing accounts into the organization via AWS Organizations.
- **B.** Enable AWS Security Hub across all accounts to manage cross-account access. Use AWS CloudTrail findings to enforce MFA during login.
- **C.** Create transit gateways and transit gateway VPC attachments in each account. Establish appropriate route tables for connectivity.
- **D.** Configure AWS IAM Identity Center (AWS Single Sign-On). Define permission sets with MFA requirements for existing accounts.
- **E.** Activate AWS Control Tower in all accounts to manage inter-account routing. Use AWS CloudTrail to enforce MFA compliance.
- **F.** Set up IAM users and groups with MFA. Use Amazon Cognito user pools and identity pools to manage cross-account access.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ACD**
  
  > Short Explanation: The correct answers are A, C, and D. AWS Control Tower sets up the multi-account structure, IAM Identity Center centralizes access with MFA, and transit gateways enable required network connectivity. ✨
  
</details>

---

## ❓ Question 119

A company operates its application in the us-east-1 Region with separate accounts for development, staging, and production environments. All environments utilize stateful Amazon EC2 instances and Amazon RDS PostgreSQL databases ranging from 600 GB to 900 GB. The development and staging teams operate during business hours on weekdays, while production runs continuously. The company aims to minimize costs without increasing operational overhead. All resources are tagged with an 'Environment' key indicating their respective environment.

What should a solutions architect recommend to achieve cost reduction with the LEAST operational effort?

- **A.** Create an Amazon EventBridge rule that triggers daily. Configure it to invoke a single AWS Lambda function that starts or stops instances based on the tag, day, and time.
- **B.** Create an Amazon EventBridge rule that triggers every weekday evening to invoke an AWS Lambda function stopping instances based on the tag. Create a second rule triggering every weekday morning to invoke another Lambda function starting instances based on the tag.
- **C.** Create an Amazon EventBridge rule that triggers every weekday evening to invoke a Lambda function terminating instances based on the tag. Create a second rule triggering every weekday morning to invoke another Lambda function restoring instances from backups based on the tag.
- **D.** Create an Amazon EventBridge rule that triggers hourly. Configure it to invoke a single Lambda function that terminates or restores instances from backups based on the tag, day, and time.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B because using separate EventBridge rules and Lambda functions for starting/stopping instances based on tags and schedules minimizes costs by stopping non-production resources during off-hours while ensuring simplicity and reliability with minimal operational effort. ✨
  
</details>

---

## ❓ Question 120

A company operates a SaaS platform on AWS using Amazon API Gateway REST APIs integrated with AWS Lambda across multiple regions. They offer different subscription tiers, with premium customers allowed up to 5,000 requests per second using unique API keys. Premium users report receiving 429 errors during peak times, and logs show the Lambda functions are not being triggered. What is the most likely cause?

- **A.** The Lambda functions' reserved concurrency is exceeded.
- **B.** The regional Lambda concurrency limit is reached.
- **C.** The API Gateway account-level throttling limit is exceeded.
- **D.** The API Gateway per-client rate limit is too low.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The 429 errors occur because the API Gateway account-level throttling limit is exceeded, preventing Lambda invocations. This happens when the total requests across all regions surpass the default account limit (10,000 RPS), even if per-client limits are correctly configured. ✨
  
</details>

---

## ❓ Question 121

A financial institution is migrating its legacy web application to AWS using Amazon EC2 instances within an Auto Scaling group in a dedicated VPC. The institution relies on an on-premises intrusion detection system (IDS) that lacks cloud-native capabilities. The security team requires real-time inspection of all inbound and outbound VPC traffic using the existing IDS, ensuring no performance degradation. The solution must be highly available within a single AWS Region. Which two steps should a solutions architect take to meet these requirements? (Choose two.)

- **A.** Deploy the IDS on EC2 instances in a new Auto Scaling group within the existing VPC
- **B.** Configure a Network Load Balancer to distribute traffic to the web application instances
- **C.** Use an Application Load Balancer to route traffic through the IDS instances
- **D.** Implement a Gateway Load Balancer in each Availability Zone to redirect traffic to the IDS
- **E.** Establish a VPC peering connection to centralize traffic inspection

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AD**
  
  > Short Explanation: The correct answers are A and D. Deploying the IDS on EC2 instances in an Auto Scaling group ensures high availability, while using a Gateway Load Balancer (GWLB) in each AZ redirects traffic through the IDS for real-time inspection without performance loss. ✨
  
</details>

---

## ❓ Question 122

A logistics company uses vehicles equipped with IoT sensors from multiple manufacturers. Each sensor transmits telemetry data in a unique proprietary format to an on-premises application that converts the data into XML. The application processes the XML files daily and stores them in a relational database for reporting. The company wants to modernize the system to enable real-time analytics while reducing operational costs.

Which solution meets these requirements?

- **A.** Connect the IoT sensors to AWS IoT Core. Configure a rule to trigger an AWS Lambda function that transforms the data into Parquet format and stores it in Amazon S3. Use AWS Glue to catalog the data and Amazon Athena for querying, with Amazon QuickSight for visualization.
- **B.** Deploy the legacy application on Amazon ECS with Fargate to process sensor data. Convert the XML files into a relational format and load them into Amazon Redshift for analysis.
- **C.** Set up an Amazon Kinesis Data Firehose to ingest sensor data directly. Use Kinesis Data Analytics to convert the data into JSON and store it in Amazon DynamoDB. Use Amazon OpenSearch for dashboards.
- **D.** Install AWS Snowcone devices in vehicles to collect sensor data locally. Periodically ship the devices to AWS and import the data into Amazon RDS for centralized analysis.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A uses AWS IoT Core to ingest data, Lambda for real-time transformation to Parquet, S3 for cost-effective storage, and serverless analytics tools (Glue, Athena, QuickSight) to enable real-time analytics while reducing operational overhead. ✨
  
</details>

---

## ❓ Question 123

A company is migrating its applications to AWS and anticipates having hundreds of AWS accounts and VPCs. The company requires seamless access from its corporate network to AWS resources and full VPC communication. Additionally, all internet-bound traffic from cloud resources must route through the on-premises data center. The company has established an AWS Direct Connect connection in a central network account.

Which combination of steps will fulfill these requirements? (Choose three.)

- **A.** Create a Direct Connect gateway in the central account. In each account, create a virtual private gateway and associate it with the Direct Connect gateway via an association proposal.
- **B.** Set up a Direct Connect gateway and transit gateway in the central account. Link them using a transit VIF.
- **C.** Deploy an internet gateway in each VPC and update route tables to direct internet traffic through it.
- **D.** Use AWS Resource Access Manager to share the transit gateway with other accounts. Attach all VPCs to the shared transit gateway.
- **E.** Establish VPC peering connections between all VPCs.
- **F.** Configure VPC route tables to send default traffic to the transit gateway. Set up on-premises NAT gateways to handle internet traffic.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BDF**
  
  > Short Explanation: The correct answers are B, D, and F. These steps establish a scalable architecture using Transit Gateway and Direct Connect Gateway for cross-account VPC communication and centralized internet traffic routing through the on-premises data center. ✨
  
</details>

---

## ❓ Question 124

A company operates multiple AWS accounts and recently established a centralized process for managing RDS Reserved Instances. All business units must now submit requests to a central team to purchase new RDS Reserved Instances or modify existing ones. Previously, business units could autonomously manage RDS Reserved Instances in their own accounts. A solutions architect must enforce this new process securely. Which combination of steps should the architect take? (Choose two.)

- **A.** Ensure all AWS accounts are part of an organization in AWS Organizations with all features enabled.
- **B.** Use AWS Config to monitor compliance with IAM policies that deny the rds:PurchaseReservedDBInstances and rds:ModifyReservedDBInstances actions.
- **C.** Create an IAM policy in each account denying the rds:PurchaseReservedDBInstances and rds:ModifyReservedDBInstances actions.
- **D.** Create an SCP denying the rds:PurchaseReservedDBInstances and rds:ModifyReservedDBInstances actions, and attach it to all relevant OUs.
- **E.** Enable consolidated billing for all accounts in AWS Organizations.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AD**
  
  > Short Explanation: The correct answers are A and D. Enabling AWS Organizations with all features (A) allows the use of Service Control Policies (SCPs). Creating an SCP denying RDS Reserved Instance actions (D) enforces centralized management across all accounts. ✨
  
</details>

---

## ❓ Question 125

A company operates a mission-critical application that relies on an Amazon RDS for MySQL database configured in Multi-AZ mode. During a planned maintenance event, the database experienced a 35-second outage during failover. The solutions architect must ensure future failovers result in less than 15 seconds of downtime. Which three actions should be taken? (Choose three.)

- **A.** Deploy Amazon ElastiCache for Memcached to cache database queries.
- **B.** Implement Amazon ElastiCache for Redis to reduce read latency.
- **C.** Use RDS Proxy to manage database connections.
- **D.** Migrate the database to Amazon Aurora MySQL.
- **E.** Create an Amazon Aurora Replica.
- **F.** Configure an RDS for MySQL read replica.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CDE**
  
  > Short Explanation: The correct answers are C, D, and E. Using RDS Proxy (C) manages connections during failover, migrating to Aurora MySQL (D) leverages faster failover due to shared storage, and creating an Aurora Replica (E) ensures quick promotion. These steps collectively reduce downtime below 15 seconds. ✨
  
</details>

---

## ❓ Question 126

A third-party auditor needs to review compliance data in an AWS account owned by a financial institution. The auditor operates within their own AWS organization (audit-org), while the financial institution's account is part of a separate organization (finance-org). The financial institution must grant secure, least-privilege access using programmatic methods.

What is the MOST secure way to enable audit-org to access resources in finance-org?

- **A.** The financial institution should share their root account credentials with the auditor to allow full access during the compliance review.
- **B.** The financial institution should create an IAM user with read-only permissions and provide the access keys to the auditor for temporary use.
- **C.** The financial institution should create an IAM role with necessary permissions and allow audit-org to assume the role using its ARN without additional safeguards.
- **D.** The financial institution should create an IAM role with required permissions, configure the role's trust policy to include audit-org's account ID and a unique external ID, and provide both to the auditor for role assumption.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D because it uses an IAM role with a trust policy requiring the auditor's account ID and a unique external ID, ensuring secure cross-account access with least privilege. Other options either compromise security (A, B) or lack safeguards (C). ✨
  
</details>

---

## ❓ Question 127

A logistics company needs to migrate a third-party data processing application to AWS. The third party provides a supported Docker image from a public registry, which can run in multiple containers. The company has divided its operations into regions, each with dedicated processing nodes that handle data specific to their region. To optimize processing times, each region uses its own Docker containers with custom configurations. The company requires the ability to allocate resources cost-effectively based on the number of active containers.

Which solution will meet these requirements with the LEAST operational overhead?

- **A.** Create an Amazon Elastic Kubernetes Service (Amazon EKS) cluster on Amazon EC2. Use the Amazon EKS CLI to deploy the application in pods, using the --tags parameter to assign region-specific tags to the pods.
- **B.** Create an Amazon Elastic Kubernetes Service (Amazon EKS) cluster on AWS Fargate. Deploy the application using the Amazon EKS CLI and apply region-specific tags via the AWS CLI tag-resource API.
- **C.** Create an Amazon Elastic Container Service (Amazon ECS) cluster on Amazon EC2. Use the AWS CLI with run-task to launch containers, applying region-specific tags using the --tags parameter.
- **D.** Create an Amazon Elastic Container Service (Amazon ECS) cluster on AWS Fargate. Use the AWS CLI run-task command with enableECSManagedTags set to true and apply region-specific tags using the --tags parameter.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. Using Amazon ECS with AWS Fargate minimizes operational overhead by eliminating server management. Region-specific tags are applied via the AWS CLI, ensuring cost-effective resource allocation based on active containers. ✨
  
</details>

---

## ❓ Question 128

A software company hosts an application on AWS with resources in multiple AWS accounts and Regions. The application runs on a group of Amazon EC2 instances in an application VPC located in the us-west-1 Region with an IPv4 CIDR block of 10.20.0.0/16. In a different AWS account, a shared services VPC is located in the us-west-2 Region with an IPv4 CIDR block of 10.20.0.0/24. When a cloud engineer uses AWS CloudFormation to attempt to peer the application VPC with the shared services VPC, an error message indicates a peering failure.

Which factors could cause this error? (Choose two.)

- **A.** The IPv4 CIDR ranges of the two VPCs overlap
- **B.** The VPCs are not in the same Region
- **C.** One or both accounts do not have access to an Internet gateway
- **D.** One of the VPCs was not shared through AWS Resource Access Manager
- **E.** The IAM role in the peer accepter account does not have the correct permissions

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: {A,E}**
  
  > Short Explanation: The error occurs due to overlapping IPv4 CIDR ranges (A) and insufficient IAM permissions in the peer accepter account (E). Overlapping CIDRs prevent peering, and missing permissions block the peering acceptance. ✨
  
</details>

---

## ❓ Question 129

An external audit identifies that an organization’s AWS Lambda execution roles have excessively broad permissions, including full access to Amazon S3 and DynamoDB. The organization mandates that each Lambda function should only possess the minimum permissions necessary. A solutions architect needs to determine the required permissions with minimal effort.

What should the solutions architect do to fulfill this requirement?

- **A.** Use Amazon CodeGuru Profiler to monitor Lambda functions, identify AWS API calls, and generate IAM policies. Review the policies to ensure compliance with business requirements.
- **B.** Enable AWS CloudTrail logging. Utilize AWS Identity and Access Management Access Analyzer to generate IAM policies based on CloudTrail activity logs. Validate the policies against the organization\u2019s requirements.
- **C.** Enable AWS CloudTrail logging. Develop a custom script to parse the logs, extract API calls per Lambda role, and generate policies. Review and refine the policies manually.
- **D.** Enable AWS CloudTrail logging. Export logs to Amazon S3 and use AWS Glue to analyze API activity. Generate policies from the analysis and review them for compliance.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. AWS IAM Access Analyzer automatically generates least-privilege policies based on CloudTrail activity logs, ensuring minimal permissions for Lambda functions with reduced effort. ✨
  
</details>

---

## ❓ Question 130

A solutions architect must evaluate a company’s Amazon EC2 instances and Amazon Elastic Block Store (EBS) volumes to optimize costs for a web application experiencing unpredictable traffic patterns. The application runs on multiple large, general-purpose EC2 instances, and the company has not identified consistent utilization trends. The architect needs to analyze the environment and implement cost-effective improvements. Which solution BEST meets these requirements?

- **A.** Use AWS Systems Manager OpsCenter to create a dashboard visualizing Amazon CloudWatch metrics for the EC2 instances and EBS volumes. Periodically review the dashboard to identify usage trends, then manually rightsize instances based on observed peaks.
- **B.** Enable Amazon CloudWatch detailed monitoring for the EC2 instances and EBS volumes. Build a custom dashboard to analyze metrics, manually identify patterns, and resize instances according to peak utilization metrics.
- **C.** Install the Amazon CloudWatch agent on all EC2 instances. Activate AWS Compute Optimizer and allow it to collect data for at least 12 hours. Rightsize instances based on Compute Optimizer\u2019s automated recommendations.
- **D.** Upgrade to the AWS Enterprise Support plan. Enable AWS Trusted Advisor and wait 12 hours for analysis. Implement Trusted Advisor\u2019s recommendations to rightsize EC2 instances.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C because AWS Compute Optimizer automates cost optimization by analyzing usage patterns and providing rightsizing recommendations, which is critical for unpredictable workloads. Other options rely on manual analysis or less targeted services. ✨
  
</details>

---

## ❓ Question 131

A company uses AWS Organizations for a multi-account setup in the AWS Cloud. The company uses AWS Control Tower for governance and AWS Transit Gateway for VPC connectivity across accounts. In an AWS application account, the application team deployed a web application using AWS Lambda and Amazon RDS. The database administrators in a separate DBA account centrally manage all databases using an Amazon EC2 instance to access RDS databases in the application account. The application team stores database credentials in AWS Secrets Manager in the application account, encrypted with the default AWS managed key, and manually shares them with DBAs. A solutions architect must grant DBAs access to the database without manual secret sharing. Which solution meets these requirements?

- **A.** Use AWS RAM to share secrets from the application account with the DBA account. Create an IAM role (DBA-Admin) in the DBA account with permissions to access shared secrets. Attach the role to the EC2 instance for cross-account secret access.
- **B.** Create an IAM role (DBA-Secret) in the application account with permissions to access secrets. In the DBA account, create an IAM role (DBA-Admin) with permissions to assume the DBA-Secret role. Attach DBA-Admin to the EC2 instance for cross-account secret access.
- **C.** Create an IAM role (DBA-Admin) in the DBA account with permissions to access secrets and the default AWS managed key in the application account. Attach resource-based policies to the key in the application account to allow DBA account access. Attach DBA-Admin to the EC2 instance.
- **D.** Create an IAM role (DBA-Admin) in the DBA account with permissions to access secrets in the application account. Attach an SCP to the application account to allow DBA account access. Attach DBA-Admin to the EC2 instance.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. It involves creating an IAM role in the application account with access to secrets and allowing the DBA account's EC2 instance to assume this role via cross-account permissions, eliminating manual secret sharing. ✨
  
</details>

---

## ❓ Question 132

A company manages multiple AWS accounts using AWS Organizations. The root OU contains two OUs: Development and Production.

Due to compliance requirements, all resources in the organization must be deployed in the us-west-2 Region. Additionally, RDS instances in the Production OU must use a predefined set of database instance classes.

A solutions architect must implement a solution that enforces these restrictions while maximizing operational efficiency and minimizing ongoing maintenance.

Which combination of steps will meet these requirements? (Choose two.)

- **A.** Create an IAM role in one account under the Production OU. Use the rds:DBInstanceClass condition key in an inline policy on the role to restrict access to specific instance classes.
- **B.** Create an IAM user in all accounts under the root OU. Use the aws:RequestedRegion condition key in an inline policy on each user to restrict access to all AWS Regions except us-west-2.
- **C.** Create an SCP. Use the aws:RequestedRegion condition key to deny access to all AWS Regions except us-west-2. Apply the SCP to the root OU.
- **D.** Create an SCP. Use the rds:Region condition key to restrict access to all AWS Regions except us-west-2. Apply the SCP to the root OU, Development OU, and Production OU.
- **E.** Create an SCP. Use the rds:DBInstanceClass condition key to restrict access to specific database instance classes. Apply the SCP to the Production OU.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CE**
  
  > Short Explanation: The correct answers are C and E. SCPs applied at the root OU enforce region restrictions organization-wide, while a separate SCP on the Production OU restricts RDS instance classes, ensuring compliance with minimal maintenance. ✨
  
</details>

---

## ❓ Question 133

A company operates a serverless application in a single AWS Region. The application processes web content by retrieving external URLs and extracting site data. The company uses an Amazon Simple Notification Service (Amazon SNS) topic to send URLs to an Amazon Simple Queue Service (Amazon SQS) queue. An AWS Lambda function processes the URLs from the queue and saves results to an Amazon S3 bucket in the same Region.

The company now needs to process each URL in multiple Regions to analyze regional content variations. URLs must originate from the existing Region, and results must be stored in the original S3 bucket.

Which combination of steps will create a multi-Region deployment that fulfills these requirements? (Choose two.)

- **A.** Deploy the SQS queue and Lambda function to additional Regions.
- **B.** Subscribe the SNS topic in each Region to the local SQS queue.
- **C.** Subscribe the SQS queues in other Regions to the central SNS topic.
- **D.** Configure the SQS queue to forward URLs to SNS topics in other Regions.
- **E.** Deploy the SNS topic and Lambda function to all Regions.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AC**
  
  > Short Explanation: The correct answers are A and C. To process URLs in multiple Regions while maintaining the origin in the existing Region, deploy SQS queues and Lambda functions to additional Regions (A) and subscribe these queues to the central SNS topic (C). This ensures URLs are distributed globally, and results are stored in the original S3 bucket. ✨
  
</details>

---

## ❓ Question 134

A company operates a proprietary stateless data processing application on Amazon EC2 Linux instances. The application is a compiled Linux binary, and the source code cannot be altered. It is single-threaded, requires 4 GB of RAM, and is highly CPU-bound. The application runs every 6 hours, taking up to 30 minutes per execution. A solutions architect needs to redesign the architecture for cost efficiency and scalability. Which solution should the architect choose?

- **A.** Use AWS Lambda with 4 GB memory. Schedule the function using Amazon EventBridge every 6 hours.
- **B.** Use AWS Batch with EC2 launch type. Use an AWS Step Functions workflow to invoke the Batch job every 6 hours.
- **C.** Use AWS Fargate to run the application. Configure Amazon EventBridge to trigger the Fargate task every 6 hours.
- **D.** Use EC2 Spot Instances with an Auto Scaling group. Set up an Amazon CloudWatch Events rule to launch instances every 6 hours.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. AWS Fargate is serverless, eliminating EC2 management costs, and EventBridge triggers ensure the task runs every 6 hours. Fargate charges only for runtime, aligning with the app's intermittent usage, making it cost-efficient and scalable. ✨
  
</details>

---

## ❓ Question 135

A company is launching a global multiplayer mobile game expected to have millions of users worldwide. The current architecture in a single AWS Region includes:

- Amazon S3 bucket for storing user-generated content
- Amazon DynamoDB table for player profiles and inventory

The solutions architect must design a multi-Region architecture to minimize latency, ensure high availability, and require minimal administrative effort.

What should the solutions architect recommend?

- **A.** Create an Amazon CloudFront distribution to serve content from the S3 bucket. Configure S3 Cross-Region Replication. Create a new DynamoDB table in a new Region and configure it as a replica for DynamoDB global tables.
- **B.** Create an Amazon CloudFront distribution to serve content from the S3 bucket. Configure S3 Same-Region Replication. Create a new DynamoDB table in a new Region and set up replication using AWS DMS with CDC.
- **C.** Create a second S3 bucket in a new Region and configure S3 Cross-Region Replication. Create a CloudFront distribution with origin failover using both S3 buckets. Enable DynamoDB global tables by activating DynamoDB Streams and adding a replica table in the new Region.
- **D.** Create a second S3 bucket in the same Region and configure S3 Same-Region Replication. Create a CloudFront distribution with origin failover using both S3 buckets. Create a new DynamoDB table in a new Region and configure it as a replica for DynamoDB global tables.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C because it uses S3 Cross-Region Replication (CRR) for global content availability, CloudFront with origin failover for low-latency access and high availability, and DynamoDB global tables for automatic multi-Region replication with minimal administrative effort. ✨
  
</details>

---

## ❓ Question 136

A company operates an on-premises social media application built with a Node.js backend and a MongoDB database storing user profiles and engagement metrics. The company plans to migrate the entire application to AWS while maintaining high availability. The application cannot be modified during migration.

Which solution meets these requirements?

- **A.** Migrate the database to Amazon DynamoDB with auto-scaling enabled. Deploy the Node.js backend on Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones.
- **B.** Migrate the database to MongoDB on Amazon EC2 instances in a single Availability Zone. Deploy the Node.js backend on EC2 instances in an Auto Scaling group within the same Availability Zone.
- **C.** Configure Amazon DocumentDB (with MongoDB compatibility) with instances distributed across multiple Availability Zones for the database. Deploy the Node.js backend on EC2 instances in an Auto Scaling group spanning multiple Availability Zones.
- **D.** Use Amazon RDS for MongoDB-compatible storage with Multi-AZ deployment for the database. Deploy the Node.js backend on EC2 instances in an Auto Scaling group across multiple Availability Zones.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C because Amazon DocumentDB provides MongoDB compatibility and Multi-AZ high availability, while EC2 Auto Scaling ensures the Node.js backend is highly available—all without application modifications. ✨
  
</details>

---

## ❓ Question 137

A digital media agency uses separate AWS accounts for different departments. The design team's AWS account hosts an Amazon S3 bucket that stores high-resolution images encrypted with a custom AWS KMS key. The design team needs to share read-only access to this bucket with the marketing team's AWS account. A solutions architect created an IAM role named marketing_viewer in the Marketing account and configured the custom KMS key in the Design account. However, when marketing team members assume the IAM role and attempt to access the S3 bucket, they encounter an Access Denied error. The solutions architect must resolve this issue while ensuring minimal permissions are granted. Which combination of steps should the solutions architect take? (Choose three.)

- **A.** Create a bucket policy that grants read permissions for the S3 bucket, with the principal set to the Marketing account's ID.
- **B.** Update the custom KMS key policy in the Design account to grant decrypt permissions to the marketing_viewer IAM role.
- **C.** Modify the marketing_viewer IAM role to grant full permissions for the S3 bucket and decrypt permissions for the KMS key.
- **D.** Create a bucket policy that grants read permissions for the S3 bucket, with the principal set to an anonymous user.
- **E.** Update the custom KMS key policy in the Design account to grant encrypt permissions to the marketing_viewer IAM role.
- **F.** Update the marketing_viewer IAM role to grant read permissions for the S3 bucket and decrypt permissions for the KMS key.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ABF**
  
  > Short Explanation: The correct answers are A, B, and F. To resolve the Access Denied error, the Design account must grant read access via a bucket policy (A) and decrypt permissions via the KMS key policy (B). The Marketing account's IAM role must also have read and decrypt permissions (F). ✨
  
</details>

---

## ❓ Question 138

A proteomics research company is utilizing open-source tools and Docker containers hosted on-premises to analyze data. Data is stored on a local NAS, and processing faces capacity constraints. They plan to migrate to AWS for scalability and faster processing. They have a high-speed AWS Direct Connect connection. Each proteomic sample generates 200 GB of data, and individual jobs require several hours of compute time. Results must be stored in Amazon S3, with 10-15 job requests daily. Which solution meets these requirements?

- **A.** Use AWS Snowmobile for data transfer to Amazon S3. Upon transfer completion, S3 events trigger an AWS Lambda function to process the data using Amazon EC2 Spot Instances.
- **B.** Use AWS Transfer Family to move the proteomic data to Amazon S3. Use S3 events to trigger an Amazon EC2 Auto Scaling group to launch custom-AMI EC2 instances running the Docker containers to process the data.
- **C.** Use AWS DataSync to transfer the proteomic data to Amazon S3. Use S3 events to trigger an AWS Lambda function that starts an AWS Step Functions workflow. Store the Docker images in Amazon Elastic Container Registry (Amazon ECR) and trigger AWS Batch to run the container and process the data.
- **D.** Use AWS Storage Gateway's Volume Gateway to transfer the proteomic data to Amazon S3. Use S3 events to trigger AWS Fargate tasks to execute the Docker containers and process the data.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. AWS DataSync efficiently transfers data from on-premises NAS to Amazon S3. AWS Step Functions and AWS Batch handle scalable, long-running Docker container jobs, leveraging Spot Instances for cost efficiency. Other options use less optimal services (e.g., Lambda's 15-minute timeout, Snowmobile's overkill for small data). ✨
  
</details>

---

## ❓ Question 139

A company operates a document repository application on a single Windows Amazon EC2 instance in a staging environment. The application stores and retrieves files on a 3 TB Amazon Elastic Block Store (Amazon EBS) volume attached as the root device. The company aims to transition this application to production as a fault-tolerant and highly available system, deploying it across three EC2 instances spanning multiple Availability Zones. A solutions architect must design a solution that integrates the instances with an Active Directory domain and enforces Windows ACLs for file access control. The application requires all instances to have identical, synchronized content at all times. Which solution meets these requirements with the LEAST operational complexity?

- **A.** Create an Amazon Elastic File System (Amazon EFS) file share. Configure an Auto Scaling group spanning three Availability Zones with a minimum of three instances. Use a user data script to install the application, join the domain, and mount the EFS share.
- **B.** Generate a new AMI from the existing EC2 instance. Deploy an Amazon FSx for Lustre file system. Configure an Auto Scaling group across three Availability Zones with three instances. Use a user data script to join the domain and mount the FSx for Lustre file system.
- **C.** Deploy an Amazon FSx for Windows File Server file system. Configure an Auto Scaling group across three Availability Zones with three instances. Use a user data script to install the application and mount the FSx file system. Seamlessly join the instances to the Active Directory domain.
- **D.** Create a new AMI from the current EC2 instance. Set up an Amazon EFS file system. Configure an Auto Scaling group across three Availability Zones with three instances. Perform a seamless domain join for Active Directory integration.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Amazon FSx for Windows File Server supports Active Directory integration, Windows ACLs, and provides a fully managed shared file storage accessible across multiple EC2 instances, ensuring synchronized content with minimal operational overhead. ✨
  
</details>

---

## ❓ Question 140

A software as a service (SaaS) company provides a notification system for client alerts. The system uses a custom SMTP server to send notifications and stores alert templates within the application, which dynamically populates client-specific data before sending emails. The company wants to migrate this system to AWS Cloud while minimizing operational overhead and maintaining cost-effectiveness.

Which solution BEST meets these requirements?

- **A.** Deploy a custom SMTP server on Amazon EC2 using an AWS Marketplace AMI. Store alert templates in an Amazon S3 bucket. Use an AWS Lambda function to fetch templates from S3, merge client data, and send emails via an SDK.
- **B.** Use Amazon SES for email delivery. Store alert templates in an Amazon S3 bucket. Create a Lambda function to retrieve templates, merge client data, and send emails using an SDK.
- **C.** Deploy an SMTP server on EC2 instances via AWS Marketplace. Store templates in Amazon SES with placeholders for client data. Use Lambda to invoke SES templates, populate data, and send emails via the EC2 SMTP server.
- **D.** Configure Amazon SES for email delivery. Store templates directly in SES with client data parameters. Use Lambda to call the SendTemplatedEmail API, passing client data and destination addresses.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. Using Amazon SES with its built-in template storage and SendTemplatedEmail API minimizes operational overhead by eliminating the need for custom SMTP servers or additional S3/Lambda processing, while maintaining cost-effectiveness. ✨
  
</details>

---

## ❓ Question 141

A company is processing images in the AWS Cloud using Amazon EC2 instances in an Auto Scaling group. Each image takes 45 minutes to process. The Auto Scaling group scales based on the number of messages in an Amazon SQS queue. The SQS queue is configured with a redrive policy that specifies a dead-letter queue and a maxReceiveCount of 1. The visibility timeout for the queue is set to 1 hour. The company uses a CloudWatch alarm to notify the team when messages are in the dead-letter queue. The team receives alerts but finds no errors in the application logs. What should the company do to resolve this issue?

- **A.** Enable termination protection for the EC2 instances
- **B.** Increase the visibility timeout for the SQS queue to 2 hours
- **C.** Configure scale-in protection for the instances during processing
- **D.** Modify the redrive policy to set maxReceiveCount to 0

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The issue arises because EC2 instances are terminated (scaled-in) while processing messages, causing messages to reappear in the queue and eventually move to the dead-letter queue. Configuring scale-in protection ensures instances aren't terminated during processing, allowing them to complete and delete messages. ✨
  
</details>

---

## ❓ Question 142

A company has developed APIs using Amazon API Gateway with Edge-optimized endpoints. These APIs trigger AWS Lambda functions secured with API Gateway's authentication. During a security audit, it was found that certain APIs should not be publicly accessible. The solutions architect needs to ensure these APIs are only reachable from within the company's VPC, while still requiring authenticated access. Which solution meets these requirements with minimal effort?

- **A.** Implement an internal Network Load Balancer (NLB) linked to a target group pointing to the Lambda functions. Use the NLB's DNS name for API calls from the VPC.
- **B.** Delete the current API's public DNS record. Create a private hosted zone in Route 53 with a new CNAME record pointing to the API. Update the API Gateway configuration to use this CNAME. Access the API via the new DNS record from the VPC.
- **C.** Change the API endpoint type to private in API Gateway. Establish an interface VPC endpoint in the VPC. Apply a resource policy to the API restricting access to the VPC endpoint. Use the VPC endpoint to invoke the API from within the VPC.
- **D.** Migrate the Lambda functions to run within the VPC. Set up an EC2 instance with Nginx as a reverse proxy. Configure the Nginx server to forward requests to the Lambda functions. Use the EC2 instance's private DNS to access the API internally.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Changing the API endpoint type to private and configuring a VPC endpoint ensures APIs are only accessible within the VPC while retaining API Gateway's authentication. This approach aligns with AWS best practices for private API access with minimal effort. ✨
  
</details>

---

## ❓ Question 143

A media streaming service delivers video-on-demand content from a web application hosted on AWS in the ap-southeast-1 Region. The video files are stored in Amazon S3 and served via Amazon CloudFront. The company expanded to serve users in the eu-central-1 Region, where users report intermittent delays when streaming content.

Which combination of steps will resolve the eu-central-1 performance issues? (Choose two.)

- **A.** Configure the AWS Global Accelerator endpoint for the S3 bucket in ap-southeast-1. Set up endpoint groups for TCP ports 80 and 443 in eu-central-1.
- **B.** Create a new S3 bucket in eu-central-1. Enable S3 cross-Region replication from the ap-southeast-1 bucket.
- **C.** Use Lambda@Edge to redirect requests from Europe to use the S3 Transfer Acceleration endpoint in eu-central-1.
- **D.** Use Lambda@Edge to modify requests from Europe to use the S3 bucket in eu-central-1.
- **E.** Add the AWS Global Accelerator endpoint for eu-central-1 as an origin in the CloudFront distribution. Use Lambda@Edge to route European requests to the new origin.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BD**
  
  > Short Explanation: The correct answers are B and D. Creating a new S3 bucket in eu-central-1 with cross-region replication ensures content is locally available, while Lambda@Edge routes European users to the local bucket, reducing latency. ✨
  
</details>

---

## ❓ Question 144

A solutions architect is troubleshooting an issue where a company's Amazon Workspaces users cannot initiate new sessions. The root cause is traced to user profiles stored on an Amazon FSx for Windows File Server, which has reached its 15 TB storage limit. The architect must resolve the issue immediately and ensure it doesn't recur.

Which solution meets these requirements?

- **A.** Delete inactive user profiles and migrate profiles to Amazon S3. Configure lifecycle policies to manage storage.
- **B.** Increase the FSx file system's capacity using the update-file-system command. Implement CloudWatch alarms to monitor storage and trigger Lambda via EventBridge to auto-scale capacity.
- **C.** Use AWS Backup to restore the file system to a previous state. Schedule regular backups to prevent future capacity issues.
- **D.** Remove old profiles and deploy an additional FSx file system. Redirect half the users to the new system to balance load.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Answer B is correct because increasing the FSx file system's capacity immediately resolves the storage limit issue, and implementing auto-scaling via CloudWatch and Lambda ensures future prevention. ✨
  
</details>

---

## ❓ Question 145

An international logistics company uses a delivery tracking system on AWS. Drivers upload delivery proofs, such as timestamps and geotags, via SFTP to a single Amazon EC2 instance. Each handheld device saves files in directories named after the driver’s ID, with filenames corresponding to shipment tracking numbers. The EC2 instance enriches the files by querying a central database for shipment details before archiving them in Amazon S3. As the company grows, drivers experience connection timeouts, and the EC2 instance faces high CPU usage. The operations team implemented a cron job to restart the instance hourly, but some files are missing in S3, and the database updates are inconsistent. A solutions architect must design a scalable solution to ensure all files are archived and systems updated. The handheld devices cannot be modified. Which solution meets these requirements?

- **A.** Create an AMI of the EC2 instance. Deploy an Auto Scaling group of EC2 instances behind a Network Load Balancer. Use Amazon EFS for shared storage and configure scaling based on CPU utilization.
- **B.** Use AWS Transfer Family to create an SFTP server that stores files in Amazon EFS. Mount the EFS volume to the existing EC2 instance and update the processing script to reference the new file path.
- **C.** Use AWS Transfer Family to create an SFTP server that stores files in Amazon S3. Configure S3 event notifications via Amazon SNS to invoke an AWS Lambda function for metadata enrichment and database updates.
- **D.** Modify the handheld devices to upload files directly to Amazon S3. Use S3 event notifications with Amazon SQS to trigger an AWS Lambda function for processing and system updates.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. AWS Transfer Family replaces the EC2-based SFTP server, storing files directly in S3. S3 event notifications trigger a Lambda function for processing, ensuring scalability, reliability, and consistent database updates without modifying handheld devices. ✨
  
</details>

---

## ❓ Question 146

A company operates an application on Amazon EC2 instances, with relational data stored in Amazon RDS PostgreSQL. Regulatory compliance requires the application to recover in a separate AWS Region during an application failure without any data loss. Which solution fulfills these requirements with the LEAST operational overhead?

- **A.** Provision an RDS Read Replica in a different Region.
- **B.** Configure AWS Database Migration Service (AWS DMS) for continuous replication to another Region.
- **C.** Use RDS automated backups with frequent snapshot copies to another Region.
- **D.** Set up AWS DataSync for continuous data replication to another Region.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Provisioning an RDS Read Replica in another Region allows for asynchronous replication managed by AWS, enabling recovery with minimal operational overhead. While asynchronous replication may introduce slight lag, it aligns with the requirement to recover from an application (not database) failure without data loss. ✨
  
</details>

---

## ❓ Question 147

A healthcare services company receives regular patient data feeds from multiple clinics. Each clinic sends approximately 10,000 records every 30 minutes in CSV format via HTTPS to an Amazon S3 bucket encrypted with server-side encryption. The data contains protected health information (PHI) that must be encrypted before further processing. The company needs to automatically encrypt the PHI fields, remove unnecessary columns, merge related fields, and transform the records into JSON format. The solution must be scalable to accommodate additional data feeds in the future.

Which solution meets these requirements?

- **A.** Invoke an AWS Lambda function on file delivery that writes records to an Amazon Kinesis Data Stream. Configure another Lambda function to process records from the stream, encrypt PHI fields, and write results to a temporary S3 location. Use a final Lambda function to transform the data into JSON format and send it to another S3 bucket for processing.
- **B.** Invoke an AWS Lambda function on file delivery that triggers an AWS Step Functions workflow. Use the workflow to launch an AWS Fargate container application that processes records, encrypts PHI fields, removes columns, merges fields, and transforms data into JSON format. Scale down the Fargate containers after processing completes and send results to another S3 bucket.
- **C.** Create an AWS Glue crawler and custom classifier based on the CSV data format to build a table definition. Invoke a Lambda function on file delivery to start an AWS Glue ETL job. Configure the ETL job to encrypt PHI fields, remove and merge fields, transform records into JSON format, and send the results to another S3 bucket.
- **D.** Create an AWS Glue crawler and custom classifier for the CSV data format. Use an Amazon Athena query on file delivery to trigger an Amazon EMR cluster. Configure the EMR cluster to encrypt PHI fields, process transformations, output JSON data to another S3 bucket, and terminate the cluster after completion.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: AWS Glue ETL is the correct choice because it is purpose-built for scalable data transformations, encryption, and format conversion. It integrates seamlessly with S3 events via Lambda triggers and handles PHI encryption requirements efficiently. ✨
  
</details>

---

## ❓ Question 148

A company needs to implement a disaster recovery plan for their primary on-premises application, which uses a PostgreSQL database. The application runs on physical servers that host multiple other services. All on-premises systems use operating systems compatible with Amazon EC2. The company wants to minimize operational complexity while ensuring rapid recovery.

Which solution BEST meets these requirements?

- **A.** Deploy AWS Application Migration Service (MGN) agents on all source servers, including the PostgreSQL database server. Configure replication settings and launch templates. Conduct periodic recovery drills using non-disruptive test instances. Initiate a full cutover to AWS during a disaster.
- **B.** Install AWS Application Migration Service (MGN) agents on the on-premises servers, including the PostgreSQL server. Configure AWS Elastic Disaster Recovery with automated replication and predefined launch settings. Perform regular failover and recovery tests using the most recent synchronized data.
- **C.** Set up an AWS Database Migration Service (AWS DMS) replication instance and a target Amazon RDS for PostgreSQL DB instance. Create a DMS task for continuous data replication. Manually install and configure the application on EC2 instances using compatible AMIs. Use custom scripts to synchronize application state changes.
- **D.** Deploy an AWS Storage Gateway File Gateway on premises. Store application and database files on the gateway. Schedule regular EBS snapshots of the gateway volumes. Provision EC2 instances and restore the application and database from snapshots during a disaster, requiring manual configuration adjustments.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Answer B uses AWS Elastic Disaster Recovery (DRS) with MGN agents for automated replication and predefined settings, ensuring minimal complexity and rapid recovery through regular failover tests. Other options involve manual steps, non-DR-focused services, or slower recovery processes. ✨
  
</details>

---

## ❓ Question 149

A company must grant a third-party monitoring service read-only access to its AWS resources. The third party uses a single AWS account, and the solution must adhere to AWS security best practices while ensuring no long-term credentials are shared. A solutions architect needs to implement the most secure approach.

- **A.** In the company's AWS account, create S3 bucket policies and IAM policies granting read-only access to the third party's AWS account. Include a unique external ID in each resource policy.
- **B.** In the company's AWS account, create an IAM role that establishes a trust relationship with the third party's AWS account. Attach a read-only IAM policy to the role and include a unique external ID in the role's trust policy.
- **C.** In the company's AWS account, create an IAM user with read-only permissions. Generate access keys for the IAM user and share them securely with the third party.
- **D.** In the company's AWS account, create an IAM group with read-only permissions. Add IAM users for each third-party administrator to the group.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Creating an IAM role with a trust relationship to the third party's AWS account and using a unique external ID ensures secure cross-account access without sharing long-term credentials, adhering to AWS security best practices. ✨
  
</details>

---

## ❓ Question 150

A real-time multiplayer gaming platform uses Amazon DynamoDB as its backend database, configured in on-demand capacity mode. The development team needs to optimize the platform for minimal latency while ensuring high availability. Which solution meets these requirements with the LEAST latency?

- **A.** Create a two-node DynamoDB Accelerator (DAX) cluster. Configure the application to read and write data by using DAX.
- **B.** Create a three-node DynamoDB Accelerator (DAX) cluster. Configure the application to read data by using DAX and to write data directly to the DynamoDB table.
- **C.** Create a single-node DynamoDB Accelerator (DAX) cluster. Configure the application to read data by using DAX and to write data directly to the DynamoDB table.
- **D.** Create a three-node DynamoDB Accelerator (DAX) cluster. Configure the application to read and write data by using DAX.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Option B minimizes latency by using DAX for reads (reducing read latency) and writing directly to DynamoDB (avoiding DAX write overhead). A three-node DAX cluster ensures high availability. ✨
  
</details>