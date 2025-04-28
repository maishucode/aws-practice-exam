# 🌟 AWS Certified Cloud Practitioner 🌟

Welcome to our practice exam portal! This page is designed to help you master the key concepts and best practices for AWS architecture. Whether you're preparing for your certification exam or looking to boost your practical skills, our high-quality questions and in-depth explanations are here to support you.

---

> **Quick Tip:**  
> For an even better learning experience and a wealth of additional resources, please visit our website:  
> [https://www.awsxp.com/](https://www.awsxp.com/)  
> Discover the latest case studies, expert insights, and specialized courses that will supercharge your AWS skills!

---

> **Get Started Now!**  
> Click on the "View Answer" button on any question below to reveal detailed explanations and solutions.  
> Enjoy your journey to AWS excellence and success on the AWS Certified Cloud Practitioner exam! 🚀

## ❓ Question 51

A financial institution stores sensitive data in an Amazon S3 bucket encrypted using server-side encryption with AWS KMS managed keys (SSE-KMS). To enhance security, they must ensure all current and future objects are encrypted with keys managed by their internal security team. The S3 bucket does not have versioning enabled.

Which solution meets these requirements?

- **A.** Update the S3 bucket's default encryption to SSE-KMS with a customer managed key. Apply a bucket policy denying unencrypted uploads. Re-upload all objects using the AWS CLI.
- **B.** Switch the bucket's default encryption to SSE-S3 with customer managed keys. Use the CLI to re-upload objects. Set a policy to block unencrypted PutObject requests.
- **C.** Change the default encryption to SSE-KMS using AWS managed keys. Attach a policy requiring encryption on all PutObject requests. Re-upload existing objects via CLI.
- **D.** Enable default encryption with SSE-KMS and a customer managed key. Configure an S3 bucket policy to encrypt objects during GET and PUT operations. Re-upload all objects with the AWS CLI.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A because it updates the bucket's default encryption to use a customer-managed KMS key, enforces encryption via a bucket policy, and re-uploads existing objects to apply the new encryption, meeting all requirements. ✨
  
</details>

---

## ❓ Question 52

A company hosts a web application using an Amazon API Gateway backed by AWS Lambda functions. The API Gateway is configured as the origin for an Amazon CloudFront distribution. The company uses Amazon Route 53 with an A record pointing to the CloudFront distribution. To ensure high availability and fault tolerance, which solution should be implemented?

- **A.** Deploy a secondary Lambda function and API Gateway in another AWS Region. Update the Route 53 A record to a failover record set with both CloudFront distributions as targets, and configure health checks.
- **B.** Deploy a secondary Lambda function and API Gateway in another AWS Region. Update the CloudFront distribution to add the new API Gateway as a second origin, then configure an origin group with primary and secondary failover settings.
- **C.** Deploy a secondary Lambda function in another AWS Region and add it as a target to the existing API Gateway. Configure the API Gateway to use weighted routing for regional failover.
- **D.** Deploy a secondary Lambda function and API Gateway in another AWS Region. Create a second CloudFront distribution for the new API Gateway, then use AWS Global Accelerator to route traffic to both distributions.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. CloudFront's origin groups allow automatic failover to a secondary origin if the primary fails, ensuring high availability without relying on DNS changes or additional services like Route 53 failover or Global Accelerator. ✨
  
</details>

---

## ❓ Question 53

A company uses AWS Organizations with multiple accounts, including a central security account. The security account has an AWS Network Firewall that is shared with all other accounts via AWS Resource Access Manager (RAM). The company needs to centrally manage a list of allowed domain names for outbound traffic, which developers must reference to allow access to their applications securely with the LEAST operational overhead.

- **A.** Host a JSON file in Amazon S3 that lists the allowed domain names. Configure an Amazon SNS topic in each account to trigger an AWS Lambda function when the file is updated. The Lambda function updates the Network Firewall rules in all accounts with the new domains.
- **B.** Create an AWS Config managed rule containing the allowed domain names. Use the rule to check and auto-remediate noncompliant Network Firewall policies in all accounts.
- **C.** In the security account, create a Network Firewall rule group with the allowed domain names. Share the rule group with all other accounts via RAM. Reference the shared rule group in the Network Firewall policies of the other accounts.
- **D.** In the security account, create a security group with rules allowing traffic to the allowed domain names. Configure the Network Firewall policies in other accounts to reference this security group using a nested security group reference.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. By creating a shared Network Firewall rule group in the security account and sharing it via AWS RAM, the company can centrally manage allowed domain names. This approach minimizes operational overhead, as updates to the rule group automatically apply to all accounts referencing it. ✨
  
</details>

---

## ❓ Question 54

A company hosts a static website on Amazon S3, delivered through Amazon CloudFront. The website interacts with an Amazon API Gateway REST API backed by AWS Lambda functions. The company needs a biweekly CSV report detailing each API Lambda function’s recommended memory configuration, associated cost savings, and the cost difference compared to the current setup. The reports must be stored in an S3 bucket.

Which solution meets these requirements with the LEAST development effort?

- **A.** Develop a Lambda function to collect performance metrics for each Lambda function from Amazon CloudWatch Metrics over a 2-week period. Transform the data into a CSV format and save it to S3. Use an Amazon EventBridge rule to trigger the Lambda function every 2 weeks.
- **B.** Enable AWS Compute Optimizer. Create a Lambda function that invokes the GetLambdaFunctionRecommendations API to retrieve optimization data. Format the results into a CSV file and store it in S3. Schedule the function using an Amazon EventBridge rule every 2 weeks.
- **C.** Activate AWS Compute Optimizer. Configure a recurring export job directly from the Compute Optimizer console to generate a CSV report every 2 weeks and save it to the S3 bucket.
- **D.** Upgrade to the AWS Enterprise Support plan. Use AWS Trusted Advisor to export cost optimization checks for Lambda functions into a CSV file. Schedule the export job via the Trusted Advisor console to run every 2 weeks and store the output in S3.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. AWS Compute Optimizer provides automated recommendations for Lambda memory settings and cost savings. A Lambda function can retrieve these recommendations via the API, format them into CSV, and store them in S3 with minimal development effort, scheduled via EventBridge. ✨
  
</details>

---

## ❓ Question 55

A company’s e-commerce platform and analytics services operate within a single VPC. Over 15 applications run using a mix of Amazon EC2, AWS Lambda, and Amazon DynamoDB. The company has development teams divided into three groups, each owning specific applications and responsible for their costs and performance. Each team’s resources are tagged with their application and team identifiers. Teams use IAM policies for access control. The company needs to attribute monthly AWS costs to each application or team and generate reports comparing costs over the past year while forecasting future expenses. A solutions architect must propose an AWS Billing and Cost Management solution to meet these requirements. Which combination of steps should be taken? (Choose three.)

- **A.** Activate the user-defined cost allocation tags for the application and team identifiers.
- **B.** Activate the AWS-generated cost allocation tags for the application and team identifiers.
- **C.** Define a cost category for each application in AWS Billing and Cost Management.
- **D.** Enable IAM permissions for accessing Billing and Cost Management reports.
- **E.** Configure a monthly cost budget.
- **F.** Enable AWS Cost Explorer for historical and predictive cost analysis.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ACF**
  
  > Short Explanation: The correct answers are A, C, and F. Activating user-defined tags (A) allows cost tracking by application/team. Defining cost categories (C) groups costs for reporting. Enabling Cost Explorer (F) provides historical and predictive analysis. These steps address cost attribution, reporting, and forecasting requirements. ✨
  
</details>

---

## ❓ Question 56

A company is migrating their on-premises application to AWS. The application, hosted on EC2 instances behind an Internet-facing Network Load Balancer (NLB), must access a third-party API that only permits a single public CIDR block. The EC2 instances are in private subnets and use NAT gateways for internet access. The NLB is in public subnets.

How can a solutions architect ensure the application can access the API after migration?

- **A.** Associate a customer-owned public IP block with the VPC and enable public IP assignment for instances in private subnets.
- **B.** Register a customer-owned IP block, create Elastic IPs from it, and assign them to the NAT gateways.
- **C.** Assign Elastic IPs from the customer's block directly to the NLB.
- **D.** Use AWS Global Accelerator with Elastic IPs from the customer's block, pointing to the NLB.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Assigning Elastic IPs from a customer-owned block to NAT gateways ensures all outbound traffic from EC2 instances uses a single CIDR block, meeting the third-party API's requirement. ✨
  
</details>

---

## ❓ Question 57

A company with several AWS accounts is using AWS Organizations and service control policies (SCPs). An administrator created the following SCP and has attached it to an organizational unit (OU) that contains AWS account 2222-2222-2222:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowsAllActions",
      "Effect": "Allow",
      "Action": "*",
      "Resource": "*"
    },
    {
      "Sid": "DenyConfig",
      "Effect": "Deny",
      "Action": "config:*",
      "Resource": "*"
    }
  ]
}
```

Developers working in account 2222-2222-2222 complain that they cannot create Amazon S3 buckets. How should the administrator address this problem?

- **A.** Add s3:CreateBucket with \"Allow\" effect to the SCP.
- **B.** Remove the account from the OU, and attach the SCP directly to account 2222-2222-2222.
- **C.** Instruct the developers to add Amazon S3 permissions to their IAM entities.
- **D.** Remove the SCP from account 2222-2222-2222.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The developers cannot create S3 buckets because their IAM policies lack the necessary permissions. The SCP allows all actions except AWS Config, but IAM policies must explicitly grant permissions. The correct solution is to add S3 permissions to their IAM entities. ✨
  
</details>

---

## ❓ Question 58

A financial institution operates a mission-critical monolithic application hosted on an Amazon EC2 instance running Amazon Linux 2. The compliance team mandates daily backups of the encrypted Amazon EBS volume data to an Amazon S3 bucket. The operations team lacks SSH access to the instance and cannot disrupt the application's availability. 

Which solution satisfies these requirements?

- **A.** Attach an IAM role with Amazon S3 write permissions to the instance. Use AWS Systems Manager Session Manager to access the instance and execute commands to transfer data to Amazon S3.
- **B.** Create an Amazon Machine Image (AMI) of the instance without rebooting. Launch a new EC2 instance from the AMI, attach an IAM role with S3 permissions, and copy the data to Amazon S3.
- **C.** Use Amazon Data Lifecycle Manager (DLM) to automate EBS snapshot creation. Configure a Lambda function to copy snapshot data to Amazon S3.
- **D.** Stop the instance, create an AMI, launch a new instance from the AMI with an IAM role for S3 access, and run commands to copy data to Amazon S3.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A is correct because it uses AWS Systems Manager Session Manager to execute commands without SSH access and an IAM role to write data to S3, ensuring daily backups without disrupting the application. ✨
  
</details>

---

## ❓ Question 59

A solutions architect needs to copy data from an Amazon S3 bucket in an AWS account to a new S3 bucket in a different AWS account using the AWS CLI. Which combination of steps will successfully copy the data? (Choose three.)

- **A.** Create a bucket policy to allow the source account to put objects and set object ACLs in the destination bucket. Attach the bucket policy to the destination bucket.
- **B.** Create a bucket policy to allow a user in the destination account to list the source bucket\u2019s contents and read the source bucket\u2019s objects. Attach the bucket policy to the source bucket.
- **C.** Create an IAM policy in the source account. Configure the policy to allow a user in the source account to list contents and get objects in the source bucket, and to list contents, put objects, and set object ACLs in the destination bucket. Attach the policy to the user.
- **D.** Create an IAM policy in the destination account. Configure the policy to allow a user in the destination account to list contents and get objects in the source bucket, and to list contents, put objects, and set object ACLs in the destination bucket. Attach the policy to the user.
- **E.** Run the aws s3 sync command as a user in the source account. Specify the source and destination buckets to copy the data.
- **F.** Run the aws s3 sync command as a user in the destination account. Specify the source and destination buckets to copy the data.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ACE**
  
  > Short Explanation: The correct answers are A, C, and E. To copy data between S3 buckets across accounts, the destination bucket must allow the source account to write objects (A). The user in the source account needs IAM permissions to read the source bucket and write to the destination (C). Finally, the AWS CLI command must be executed from the source account with proper credentials (E). ✨
  
</details>

---

## ❓ Question 60

A company's AWS Lambda-based application, deployed via AWS CloudFormation, experienced downtime after a recent update. To prevent this, they want to implement a canary release strategy. Which solution meets this requirement?

- **A.** Create an alias for the Lambda function and use the AWS CLI update-alias command with the --routing-config parameter to shift traffic gradually.
- **B.** Deploy the new version in a separate CloudFormation stack and use Route 53 latency-based routing.
- **C.** Publish a new version of the Lambda function and configure the function's traffic using the update-function-configuration command.
- **D.** Use AWS CodeDeploy with the CodeDeployDefault.AllAtOnce deployment configuration.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A is correct because using Lambda aliases with the --routing-config parameter allows gradual traffic shifting between versions, enabling a canary release strategy. ✨
  
</details>

---

## ❓ Question 61

A financial services firm operates an SFTP server on an Amazon EC2 instance within a public subnet of a VPC. The server uses an Amazon EFS file system for storage, and a nightly cron job transfers uploaded files to an S3 data lake. The SFTP server is accessible via sftp.finance.com through Amazon Route 53. How can the firm enhance the solution's reliability and scalability?

- **A.** Implement an Auto Scaling group for the EC2 instance and attach an Application Load Balancer (ALB). Update Route 53 to point to the ALB.
- **B.** Migrate the SFTP server to AWS Transfer for SFTP and update Route 53 to the new endpoint.
- **C.** Use a Network Load Balancer (NLB) in front of the EC2 instance and update the DNS record to the NLB.
- **D.** Replace EFS with AWS Storage Gateway's file gateway and update DNS accordingly.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Migrating to AWS Transfer for SFTP (Option B) enhances reliability and scalability by replacing the self-managed EC2 instance with a fully managed service, eliminating the need to handle server maintenance, scaling, or redundancy manually. ✨
  
</details>

---

## ❓ Question 62

A company plans to migrate a business-critical application running on an on-premises VMware environment to Amazon EC2. The solutions architect must ensure that all application configurations and installed software are retained during the migration.

What should the solutions architect do to achieve this?

- **A.** Use AWS DataSync to transfer the VMware data store to Amazon S3. Configure an IAM role for VM Import. Use the AWS CLI to import the VM from S3 into EC2.
- **B.** Export the VM as an OVF package using VMware vSphere. Upload the package to an Amazon S3 bucket. Create an IAM role with VM Import permissions. Import the VM using the AWS CLI.
- **C.** Set up AWS Storage Gateway as a file gateway. Copy the VM files to an SMB share. Use VM Import/Export to migrate the VM to EC2.
- **D.** Install the AWS Systems Manager Agent on the VM. Register it as a managed instance. Use AWS Backup to create an AMI from the VM and launch an EC2 instance.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Exporting the VM as an OVF package using VMware vSphere, uploading it to S3, and using VM Import/Export ensures all configurations and software are retained during migration. ✨
  
</details>

---

## ❓ Question 63

A data analytics company uses an AWS Lambda function written in Python to process large CSV files uploaded to an Amazon S3 bucket. The Lambda function transforms the data, stores the results in a second S3 bucket, and updates metadata in an Amazon DynamoDB table. The Lambda function is triggered when new CSV files are uploaded. Recently, CSV file sizes have increased substantially, causing frequent Lambda timeouts even at the maximum duration. A solutions architect must redesign the architecture to prevent timeouts without managing infrastructure.

- **A.** Package the application code into a Docker container image and upload it to Amazon Elastic Container Registry (Amazon ECR).
- **B.** Create an Amazon ECS task definition with AWS Fargate compatibility. Configure the task to use the ECR image. Modify the Lambda function to trigger the ECS task via the AWS SDK when new files arrive in S3.
- **C.** Use AWS Step Functions to orchestrate multiple Lambda invocations in parallel. Increase the Lambda memory allocation to the maximum.
- **D.** Create an Amazon ECS task definition with EC2 compatibility. Configure the task to use the ECR image. Modify the Lambda function to trigger the ECS task via the AWS SDK when new files arrive in S3.
- **E.** Migrate the CSV files to Amazon FSx for Lustre and process them using an Amazon EC2 Auto Scaling group. Update the Lambda function to trigger EC2 instances.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AB**
  
  > Short Explanation: The correct answers are A and B. Using a Docker container with ECS Fargate allows longer processing times without infrastructure management, resolving Lambda timeouts. Other options either retain Lambda's 15-minute limit or require managing servers. ✨
  
</details>

---

## ❓ Question 64

A company has an organization in AWS Organizations and uses AWS Control Tower to manage its landing zone. The company needs to enforce governance by detecting Amazon S3 buckets that do not have versioning enabled within their production OU. Which solution will meet this requirement?

- **A.** Enable mandatory guardrails in AWS Control Tower and apply them to the production OU.
- **B.** Activate the relevant guardrail from the strongly recommended guardrails in AWS Control Tower and apply it to the production OU.
- **C.** Create a custom AWS Config rule as a new mandatory guardrail and deploy it to all accounts in the production OU.
- **D.** Develop a custom SCP in AWS Control Tower and attach it to the production OU.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. AWS Control Tower's strongly recommended guardrails include checks for S3 bucket versioning. Activating these guardrails ensures detection of non-compliant buckets in the production OU. ✨
  
</details>

---

## ❓ Question 65

A financial institution hosts a fleet of Amazon EC2 instances in private subnets using the latest Amazon Linux 2 AMI. The engineers require SSH access for system maintenance and compliance audits.

The existing architecture includes:
- A VPC with private and public subnets, a NAT gateway, and AWS Direct Connect for hybrid connectivity.
- EC2 security groups configured to allow inbound SSH traffic from the on-premises network.

The institution needs to eliminate inbound SSH port exposure while ensuring all SSH sessions are logged and auditable.

Which solution should a solutions architect recommend?

- **A.** Deploy EC2 Instance Connect for SSH access. Remove existing security group rules allowing inbound SSH traffic. Instruct engineers to use EC2 Instance Connect with AWS CLI, logging all sessions via Amazon CloudWatch Logs.
- **B.** Restrict security group rules to allow SSH only from the Direct Connect public IPs. Install the AWS CloudWatch agent on instances to stream SSH logs to CloudWatch Logs. Enable AWS Config to monitor security group changes.
- **C.** Update security groups to restrict SSH access to IAM-authorized users via AWS Identity and Access Management. Enable AWS CloudTrail to log SSH session commands and enforce MFA for SSH access.
- **D.** Attach an IAM role with the AmazonSSMManagedInstanceCore policy to all EC2 instances. Remove all inbound SSH security group rules. Direct engineers to use AWS Systems Manager Session Manager with the AWS CLI to establish SSH sessions, leveraging AWS CloudTrail for auditing.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. AWS Systems Manager Session Manager allows SSH access without inbound port exposure by using secure outbound connections. It integrates with CloudTrail for auditing, meeting the requirements of eliminating SSH exposure and ensuring auditability. ✨
  
</details>

---

## ❓ Question 66

A company using AWS Organizations provides developers with sandbox accounts for testing. Developers request accounts using their corporate email, and the company wants to enforce cost controls by preventing the use of expensive services and implementing a fixed quarterly budget that automatically stops resources when exceeded. 

Which combination of steps will meet these requirements? (Choose three.)

- **A.** Create an SCP to enforce a quarterly spending limit. Apply the SCP to the sandbox accounts.
- **B.** Use AWS Budgets to configure a fixed quarterly budget for each sandbox account during account provisioning.
- **C.** Create an SCP to block access to high-cost services. Apply the SCP to the sandbox accounts.
- **D.** Develop an IAM policy to restrict access to costly services. Attach the policy to sandbox account roles.
- **E.** Configure an AWS Budgets action to stop all resources directly when the budget is exceeded.
- **F.** Set up an AWS Budgets alert to trigger an Amazon SNS notification at the budget threshold. Use AWS Lambda to terminate all sandbox resources.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BCF**
  
  > Short Explanation: The correct answers are B, C, and F. AWS Budgets sets quarterly budgets (B), SCPs block high-cost services (C), and Budgets alerts with Lambda terminate resources when exceeded (F). Other options either misuse SCPs for budgets (A), rely on less scalable IAM policies (D), or assume Budgets can stop resources directly (E). ✨
  
</details>

---

## ❓ Question 67

A company has applications in an AWS account named Source, which is part of an AWS Organizations organization. The applications utilize AWS Lambda functions deployed via a deployment package and store transactional data in an Amazon Aurora database configured with automated backups. The company needs to migrate these resources to a new AWS account named Target while ensuring minimal downtime due to the critical nature of the data processing.

Which solution meets these requirements?

- **A.** Download the Lambda deployment package from the Source account, redeploy the Lambda functions in the Target account, and share the automated Aurora snapshot with the Target account for restoration.
- **B.** Download the Lambda deployment package from the Source account, redeploy the Lambda functions in the Target account, and use AWS Resource Access Manager (AWS RAM) to share the Aurora cluster with the Target account, granting permissions to clone the database.
- **C.** Use AWS Resource Access Manager (AWS RAM) to share both the Lambda functions and the Aurora cluster with the Target account, allowing the Target account to clone the Aurora database.
- **D.** Use AWS Resource Access Manager (AWS RAM) to share the Lambda functions with the Target account and share the automated Aurora snapshot with the Target account for database restoration.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Redeploying Lambda via the deployment package and sharing the Aurora cluster via AWS RAM allows cloning, ensuring minimal downtime. Other options incorrectly use AWS RAM for Lambda or rely on non-shareable automated snapshots. ✨
  
</details>

---

## ❓ Question 68

A company uses a Python application on an Amazon EC2 instance to handle data transformation tasks. The application checks an Amazon S3 bucket every 15 minutes and processes files, with each file taking roughly 7 minutes to complete. The application skips files that have already been processed. CloudWatch metrics reveal the EC2 instance is idle 50% of the time due to processing delays. The company aims to improve scalability, ensure high availability, and minimize operational management.

Which solution MOST cost-effectively meets these requirements?

- **A.** Convert the data transformation application into an AWS Lambda function. Configure S3 event notifications to trigger the Lambda function automatically when new files are uploaded to the S3 bucket.
- **B.** Set up an Amazon Simple Queue Service (SQS) queue. Enable S3 event notifications to send messages to the queue. Deploy an EC2 Auto Scaling group starting with one instance. Modify the application to poll the SQS queue and process files based on received messages.
- **C.** Containerize the data transformation application and deploy it on the existing EC2 instance. Configure the container to continuously poll the S3 bucket for new files and process them as they arrive.
- **D.** Migrate the application to a container running on Amazon Elastic Container Service (ECS) with AWS Fargate. Use an Amazon EventBridge rule to invoke the Fargate task via the RunTask API whenever a new file is uploaded to the S3 bucket.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. Using AWS Lambda triggered by S3 events eliminates idle time, scales automatically, and minimizes operational overhead. Lambda processes files immediately upon upload, ensuring cost-efficiency and high availability without EC2 management. ✨
  
</details>

---

## ❓ Question 69

An e-commerce company in North America is deploying a new web application on AWS. The application will be hosted in the us-east-1 Region on Amazon EC2 instances and must be highly available with dynamic scaling. The company also requires a disaster recovery environment in the us-west-1 Region using an active-passive failover strategy. Which solution meets these requirements?

- **A.** Create a VPC in us-east-1 and a VPC in us-west-1. Configure VPC peering. In the us-east-1 VPC, deploy an Application Load Balancer (ALB) spanning multiple Availability Zones in both VPCs. Create an Auto Scaling group distributing EC2 instances across Availability Zones in both VPCs. Place the Auto Scaling group behind the ALB. Use Amazon Route 53 with a simple routing policy pointing to the ALB.
- **B.** Create a VPC in us-east-1 and a VPC in us-west-1. In each VPC, deploy an ALB across multiple Availability Zones within the respective Region. Configure an Auto Scaling group in each VPC behind its ALB. Set up Amazon Route 53 with weighted routing policies for both ALBs, distributing traffic evenly between Regions without health checks.
- **C.** Create a VPC in us-east-1 and a VPC in us-west-1. In each VPC, deploy an ALB across multiple Availability Zones within the respective Region. Configure an Auto Scaling group in each VPC behind its ALB. Set up Amazon Route 53 with health checks for both ALBs and configure an active-passive failover routing policy, directing traffic to the standby us-west-1 ALB only if us-east-1 fails.
- **D.** Create a VPC in us-east-1 and a VPC in us-west-1. Configure VPC peering. Deploy a single ALB in us-east-1 across multiple Availability Zones. Create an Auto Scaling group in us-east-1 behind the ALB. In us-west-1, deploy a standby EC2 instance without an ALB or Auto Scaling. Use Route 53 with a failover policy pointing to the ALB and the standalone instance.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: Option C meets the requirements by deploying ALBs and Auto Scaling groups in both regions, using Route 53 with health checks and active-passive failover to ensure traffic shifts to the standby region only if the primary fails. ✨
  
</details>

---

## ❓ Question 70

A company operates with a single AWS account and uses an on-premises Active Directory for user authentication. The development team requires access to the AWS Management Console using their existing Active Directory credentials, eliminating the need to manage separate IAM user accounts. The solutions architect must implement this using AWS IAM Identity Center (AWS Single Sign-On) in the most cost-effective way. Which solution BEST meets these requirements?

- **A.** Create an organization in AWS Organizations. Enable the IAM Identity Center feature. Provision a directory in AWS Directory Service for Microsoft Active Directory (AWS Managed Microsoft AD) with a two-way trust to the on-premises Active Directory. Configure IAM Identity Center to use the AWS Managed Microsoft AD as the identity source. Assign permission sets mapped to groups in the AWS Managed Microsoft AD directory.
- **B.** Create an organization in AWS Organizations. Enable the IAM Identity Center feature. Deploy an AD Connector linked to the on-premises Active Directory. Configure IAM Identity Center to use the AD Connector as the identity source. Assign permission sets mapped to groups in the on-premises Active Directory.
- **C.** Create an organization in AWS Organizations and enable all features. Provision a directory in AWS Directory Service for Microsoft Active Directory (AWS Managed Microsoft AD) with a two-way trust to the on-premises Active Directory. Configure IAM Identity Center to use the AWS Managed Microsoft AD as the identity source. Assign permission sets mapped to groups in the AWS Managed Microsoft AD directory.
- **D.** Create an organization in AWS Organizations and enable all features. Deploy an AD Connector linked to the on-premises Active Directory. Configure IAM Identity Center to use the AD Connector as the identity source. Assign permission sets mapped to groups in the on-premises Active Directory.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D because it uses AD Connector linked to on-premises Active Directory, avoiding the cost of AWS Managed Microsoft AD. AWS Organizations must enable all features for IAM Identity Center integration. ✨
  
</details>

---

## ❓ Question 71

A video streaming service operates a mobile app that uploads large video files (5 GB to 15 GB) to an Amazon S3 bucket in the us-west-2 Region. Users in Europe report slow upload speeds and frequent failures. Which two solutions should a solutions architect implement to address these issues? (Choose two.)

- **A.** Enable S3 Transfer Acceleration for the bucket and direct uploads to the acceleration endpoint.
- **B.** Deploy S3 buckets in each European Region and use Cross-Region Replication to sync with the main bucket.
- **C.** Use Amazon CloudFront with geographic routing to cache uploads closer to users.
- **D.** Implement multipart uploads in the app to split files into parts.
- **E.** Apply S3 server-side encryption to reduce upload time.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AD**
  
  > Short Explanation: A and D are correct. S3 Transfer Acceleration optimizes uploads via CloudFront's edge, reducing latency for European users. Multipart uploads improve reliability and speed by splitting files into parallel parts. ✨
  
</details>

---

## ❓ Question 72

An application is using an Amazon RDS for PostgreSQL Multi-AZ DB instance in the us-west-2 Region. After a failover event, the application lost connections to the database and could not reconnect until it was manually restarted. A solutions architect must ensure the application can automatically re-establish connections to the database without requiring a restart.

Which solution will meet these requirements?

- **A.** Create an Amazon Aurora PostgreSQL Serverless v2 DB cluster. Migrate the RDS DB instance to the Aurora Serverless v2 cluster. Update the application's connection settings to use the Aurora reader endpoint.
- **B.** Create an RDS Proxy. Configure the existing RDS endpoint as a target. Update the application's connection settings to point to the RDS Proxy endpoint.
- **C.** Create a Multi-AZ Amazon Aurora PostgreSQL DB cluster. Migrate the RDS DB instance to the Aurora cluster. Configure an RDS Proxy with the Aurora cluster as the target. Update the application's connection settings to use the RDS Proxy endpoint.
- **D.** Use AWS Database Migration Service (AWS DMS) to replicate the database to an Amazon DynamoDB table. Update the application to use the AWS SDK to connect to DynamoDB for all database operations.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Using RDS Proxy allows the application to automatically reconnect to the database after a failover by managing connections transparently, eliminating the need for manual restarts. ✨
  
</details>

---

## ❓ Question 73

A company is deploying an IoT fleet management system on AWS. Each vehicle-mounted device must transmit and receive real-time telemetry data using the MQTT protocol while authenticating via unique X.509 certificates. The solution must ensure secure communication with minimal administrative effort.

Which architecture best satisfies these requirements?

- **A.** Deploy Amazon MQ with ActiveMQ. Create a dedicated message queue for each device, generate X.509 certificates per device, and configure devices to connect to Amazon MQ brokers.
- **B.** Launch an Application Load Balancer (ALB) with TLS listener. Implement a custom certificate validation Lambda function. Deploy MQTT brokers on EC2 instances behind the ALB in an Auto Scaling group. Attach device certificates during ALB authentication.
- **C.** Implement AWS IoT Core. Register each device as an AWS IoT thing with a unique X.509 certificate. Establish MQTT communication between devices and AWS IoT Core endpoints.
- **D.** Configure Amazon API Gateway WebSocket API with mutual TLS authentication. Integrate with a backend service running MQTT brokers on ECS Fargate containers behind a Network Load Balancer. Manage device certificates through API Gateway.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: AWS IoT Core is designed for IoT use cases requiring secure MQTT communication with X.509 certificate authentication. It minimizes administrative effort by natively managing device registration, certificates, and secure communication. ✨
  
</details>

---

## ❓ Question 74

A company operates multiple workloads in a single AWS account. A new security policy mandates that engineers must deploy resources exclusively through AWS CloudFormation and can only provision resources from an approved list. A solutions architect must design a solution to enforce these restrictions on the IAM role used by engineers. What should the solutions architect implement?

- **A.** Store approved AWS CloudFormation templates in an Amazon S3 bucket. Modify the engineers\u2019 IAM policy to restrict access to only Amazon S3 and AWS CloudFormation. Require engineers to deploy resources using the stored templates.
- **B.** Update the engineers\u2019 IAM policy to allow AWS CloudFormation actions and restrict resource creation to approved resources. Use AWS CloudFormation templates that include only approved resources for deployments.
- **C.** Modify the engineers\u2019 IAM policy to permit only AWS CloudFormation actions. Create a separate IAM service role with permissions to provision approved resources. Configure AWS CloudFormation to use this service role during stack creation.
- **D.** Deploy all resources via AWS CloudFormation stacks. Restrict the engineers\u2019 IAM policy to allow access only to stacks they create, preventing modifications to other resources.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. By restricting the engineers' IAM policy to only CloudFormation actions and using a separate service role with limited permissions, the solution ensures engineers can only deploy approved resources via CloudFormation. ✨
  
</details>

---

## ❓ Question 75

A solutions architect is designing the storage layer for a social media analytics platform that processes millions of small user-generated posts per hour from global sources. Each post is under 4 KB in size and must be stored durably while enabling low-latency retrieval. The data is temporary and must be retained for only 90 days before automatic deletion. The architect estimates annual storage needs will range between 8-12 TB. Which solution is MOST cost-effective and meets the requirements?

- **A.** Store each post as a separate .txt file in an Amazon S3 bucket. Use S3 Inventory to track objects and configure a lifecycle policy to delete files older than 90 days.
- **B.** Store posts in an Amazon DynamoDB table with partitioning configured for scalability. Enable DynamoDB Time to Live (TTL) to expire records after 90 days.
- **C.** Store posts in an Amazon Aurora MySQL database table. Schedule a daily Lambda function to delete rows older than 90 days using SQL queries.
- **D.** Batch posts into larger files and store them in Amazon S3. Use S3 object tags to categorize batches and configure lifecycle policies for expiration after 90 days.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: DynamoDB with TTL is chosen because it efficiently handles high-volume, small-item storage with automatic expiration, low-latency retrieval, and scalable partitioning, making it cost-effective for temporary data. ✨
  
</details>

---

## ❓ Question 76

A financial services firm hosts its transaction processing system on AWS across multiple Regions. The system must remain operational continuously, with data stored in an Amazon RDS for MySQL database. Which solution ensures the HIGHEST availability for the database?

- **A.** Configure automated backups on Amazon RDS. During a disruption, promote an automated backup to a standalone DB instance. Redirect database traffic to the promoted instance. Create a new read replica using the promoted instance as the source.
- **B.** Enable global tables and read replicas on Amazon RDS. Use AWS Lambda to replicate read replicas across Regions during a disruption.
- **C.** Configure global tables with automated backups on Amazon RDS. During a disruption, use AWS Lambda to copy read replicas between Regions.
- **D.** Configure cross-Region read replicas on Amazon RDS. During a disruption, promote a cross-Region read replica to a standalone DB instance. Redirect database traffic to the promoted instance. Create a new read replica using the promoted instance as the source.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D because cross-Region read replicas provide asynchronous replication to another AWS Region. Promoting a read replica to a standalone instance during a disruption ensures minimal downtime and maintains high availability. Other options rely on slower backups or incorrect features (e.g., global tables for RDS). ✨
  
</details>

---

## ❓ Question 77

Example Corp. has an on-premises data center connected to VPC Main in their AWS account via a Site-to-Site VPN. They acquire NewCorp, which has VPC New. There is no IP address overlap between the networks. VPC Main and VPC New are peered. Example Corp. wants its on-premises servers to access VPC New. Network ACLs and security groups are properly configured.

Which solution will meet this requirement with the LEAST operational effort?

- **A.** Create a transit gateway. Attach the Site-to-Site VPN, VPC Main, and VPC New to the transit gateway. Update the transit gateway route tables for all networks to add IP range routes for all other networks.
- **B.** Create a transit gateway. Establish a new Site-to-Site VPN connection between the on-premises network and VPC New, and connect the VPN connection to the transit gateway. Add a route to direct traffic to the peered VPCs and an authorization rule to grant access to VPC Main and VPC New.
- **C.** Update the route tables for the Site-to-Site VPN, VPC Main, and VPC New to include routes for all three networks. Enable BGP propagation for all networks and wait up to 5 minutes for propagation to complete.
- **D.** Modify the existing Site-to-Site VPN\u2019s virtual private gateway to include both VPC Main and VPC New. Split the virtual private gateway\u2019s routers between the two VPCs.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Using a Transit Gateway (TGW) centralizes routing between the on-premises network, VPC Main, and VPC New. By attaching all networks to the TGW and updating route tables once, transitive routing is enabled with minimal effort. ✨
  
</details>

---

## ❓ Question 78

A company has migrated their on-premises infrastructure to AWS using a replatforming strategy. A legacy application relies on an SMTP service that operates without encryption and uses TCP port 25. The application cannot be modified to use anything other than SMTP. The company has decided to use Amazon SES, validated their domain, and adjusted SES limits. What should the company do to enable the application to send emails through Amazon SES?

- **A.** Configure the application to connect to Amazon SES using TLS encryption. Create an IAM role with ses:SendEmail and ses:SendRawEmail permissions and attach it to an Amazon EC2 instance.
- **B.** Configure the application to connect to Amazon SES using STARTTLS. Generate Amazon SES SMTP credentials and use them to authenticate with Amazon SES.
- **C.** Modify the application to use the SES API. Create an IAM role with ses:SendEmail and ses:SendRawEmail permissions and assign it as a service role for Amazon SES.
- **D.** Update the application to use AWS SDKs. Create an IAM user for Amazon SES, generate API access keys, and use the keys for authentication.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. The legacy application must use STARTTLS encryption and authenticate with Amazon SES using SMTP credentials, as it cannot be modified to use APIs or SDKs. SES requires STARTTLS for SMTP connections, and SMTP credentials are generated via IAM for authentication. ✨
  
</details>

---

## ❓ Question 79

A large enterprise merged multiple departments, each operating in separate AWS accounts with distinct billing setups. After consolidating all accounts into a single AWS Organizations structure, the finance team struggles to produce consolidated cost reports with custom business-specific groupings. The team requires a self-service solution to analyze costs across all departments efficiently. Which approach addresses these requirements?

- **A.** Generate an AWS Cost and Usage Report for the organization. Configure cost allocation tags and cost categories. Build an Amazon Athena table from the report data. Develop an Amazon QuickSight dataset using the Athena table and grant the finance team access.
- **B.** Generate an AWS Cost and Usage Report for the organization. Configure cost allocation tags and cost categories. Design a custom dashboard template in AWS Cost Explorer for the finance team to generate reports.
- **C.** Develop a custom application that pulls cost data via the AWS Price List Query API. Build an Amazon QuickSight dataset using this data and share it with the finance team.
- **D.** Use AWS Budgets to aggregate cost data across the organization. Create a custom Amazon QuickSight dashboard connected to the Budgets API for the finance team.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A is correct because it uses AWS Cost and Usage Report (CUR) with cost allocation tags and cost categories to enable custom groupings. Athena and QuickSight provide a self-service analytics solution for consolidated cost reporting across the organization. ✨
  
</details>

---

## ❓ Question 80

A company operates an IoT platform on AWS where sensors transmit data to Python-based API servers hosted on Amazon EC2 instances behind an Application Load Balancer. The data is stored in an Amazon RDS PostgreSQL DB instance utilizing a 5 TB General Purpose SSD volume. As the number of sensors expands, the API servers experience consistent overload, and RDS metrics indicate elevated write latency.

Which of the following steps together will permanently resolve these issues and support future growth cost-effectively? (Choose two.)

- **A.** Increase the RDS PostgreSQL storage to 8 TB to enhance the volume's IOPS.
- **B.** Migrate the database to Amazon Aurora with read replicas to distribute read workloads.
- **C.** Implement Amazon Kinesis Data Firehose and AWS Lambda to ingest and process sensor data.
- **D.** Utilize Amazon CloudWatch for detailed monitoring and auto-scale EC2 instances to manage API load.
- **E.** Re-architect the database tier to use Amazon DynamoDB instead of RDS PostgreSQL.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CE**
  
  > Short Explanation: The correct answers are C and E. Implementing Kinesis Data Firehose and Lambda offloads data ingestion from EC2, reducing API server load. Migrating to DynamoDB addresses RDS write latency with scalable NoSQL throughput. ✨
  
</details>

---

## ❓ Question 81

A company operates a serverless document management system on AWS in the us-east-1 Region. The system uses Amazon CloudFront with an S3 origin for a web application, Amazon API Gateway Regional endpoints that trigger AWS Lambda functions, and an Amazon Aurora Serverless database for metadata. Documents are stored in an S3 bucket. The company is expanding to Asia-Pacific and needs to reduce latency for users in that region.

Which combination of actions will address this requirement? (Choose two.)

- **A.** Enable S3 Transfer Acceleration on the S3 bucket and update the web application to use Transfer Acceleration signed URLs.
- **B.** Deploy an AWS Global Accelerator endpoint for the CloudFront distribution to optimize routing.
- **C.** Convert the API Gateway Regional endpoints to edge-optimized endpoints to leverage CloudFront's global network.
- **D.** Replicate the entire stack in the ap-southeast-1 Region and use Aurora Global Database for cross-region data access.
- **E.** Implement an Amazon ElastiCache cluster in front of the Aurora Serverless database to reduce query latency.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AC**
  
  > Short Explanation: A and C are correct. S3 Transfer Acceleration reduces latency for uploads via CloudFront's edge. Edge-optimized API Gateway endpoints leverage CloudFront's global network for lower API latency. ✨
  
</details>

---

## ❓ Question 82

An e-learning platform stores user-generated course materials, including high-resolution images and tutorial videos, in an Amazon S3 Standard bucket. These materials are distributed globally via Amazon CloudFront. The platform's operations team observes that over 60% of the materials are rarely accessed after 45 days, though a small subset remains frequently accessed. The team needs a cost-effective storage solution that ensures immediate access to all materials, even if they become active again after periods of inactivity.

Which solution meets these requirements while minimizing costs?

- **A.** Enable S3 Intelligent-Tiering for the S3 bucket to automatically move objects between access tiers based on usage patterns.
- **B.** Create an S3 Lifecycle policy to transition objects to S3 Glacier Flexible Retrieval 45 days after upload.
- **C.** Migrate the data to Amazon FSx for Lustre and integrate it with Amazon EC2 instances for low-latency access.
- **D.** Configure an S3 Object Expiration rule to delete objects after 45 days and use CloudFront signed URLs for temporary access.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: S3 Intelligent-Tiering automatically moves objects between access tiers based on usage, ensuring cost savings for rarely accessed data while maintaining immediate availability. This meets the requirement of minimizing costs without sacrificing accessibility. ✨
  
</details>

---

## ❓ Question 83

A company uses Amazon S3 to store large volumes of data across multiple storage classes. Over the past year, their S3 costs have risen unexpectedly, and they need to analyze storage usage patterns to optimize storage class assignments.

A solutions architect must evaluate historical storage metrics over the last 12 months and determine the most cost-effective storage classes for the objects.

Which solution will best address these requirements?

- **A.** Use AWS Cost Explorer to generate S3 cost reports for the past year. Filter the data by storage class and apply AWS Trusted Advisor cost optimization recommendations.
- **B.** Enable S3 Inventory to produce daily CSV reports. Use Amazon Athena to query the inventory data and identify storage usage trends.
- **C.** Activate Amazon S3 Storage Lens and upgrade to the advanced metrics tier to gain insights into storage activity and usage patterns across all buckets.
- **D.** Configure Amazon CloudWatch to collect S3 storage metrics. Build custom dashboards to visualize storage class utilization trends over time.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Amazon S3 Storage Lens advanced metrics tier provides comprehensive storage activity and usage pattern insights across all buckets, enabling cost-effective storage class optimization by analyzing historical data over 12 months. ✨
  
</details>

---

## ❓ Question 84

A company uses AWS for its cloud infrastructure and needs to manage deployments across several AWS accounts and Regions as part of a global expansion strategy. The solutions architect must implement infrastructure as code to ensure consistency and scalability.

What should the solutions architect do to efficiently deploy the infrastructure across multiple accounts and Regions?

- **A.** Create AWS CloudFormation templates with cross-account IAM roles. Manually deploy the templates in each Region and account.
- **B.** Use AWS Organizations to link accounts. Deploy AWS CloudFormation templates via AWS Service Catalog and manage Regions using AWS Config.
- **C.** Use AWS Organizations and AWS CloudFormation StackSets. Configure a template with appropriate IAM roles for cross-account and cross-Region deployments.
- **D.** Implement AWS CloudFormation nested stacks with parameters to switch Regions. Share templates across accounts using AWS Resource Access Manager.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. AWS CloudFormation StackSets with AWS Organizations enables automated, scalable deployments across multiple accounts and Regions, ensuring consistency without manual intervention. Other options involve manual steps or use services not designed for cross-account/Region IaC. ✨
  
</details>

---

## ❓ Question 85

A company is expanding its AWS infrastructure to support global operations, requiring deployments across multiple AWS accounts and Regions. The solutions architect must implement a scalable solution to provision standardized resources consistently while ensuring centralized management. Which approach should be taken?

- **A.** Use AWS CloudFormation templates with cross-account IAM roles. Manually deploy the templates in each Region and account.
- **B.** Use AWS Control Tower to set up a landing zone. Configure AWS Service Catalog for standardized templates and deploy them via AWS Organizations.
- **C.** Use AWS Organizations and AWS CloudFormation StackSets. Deploy templates from a central account with appropriate IAM permissions.
- **D.** Create AWS CloudFormation macros to modify templates dynamically. Use AWS Config to enforce deployments across accounts.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. AWS Organizations and CloudFormation StackSets enable centralized deployment of standardized resources across multiple accounts and Regions, ensuring scalability and consistency. ✨
  
</details>

---

## ❓ Question 86

A company is refactoring their monolithic application into microservices deployed on Amazon ECS. The CI/CD pipeline must support multiple daily deployments and allow immediate rollback. Which design meets these requirements?

- **A.** Use AWS CodeBuild to build new Docker images and push to Amazon ECR. Update the ECS task definition with the new image and perform a rolling update.
- **B.** Configure AWS CodeDeploy to handle blue/green deployments with ECS. Route traffic to the new environment and automatically roll back if health checks fail.
- **C.** Deploy new tasks using AWS Fargate and use Amazon Route 53 weighted routing to shift traffic gradually to the new tasks.
- **D.** Utilize AWS Elastic Beanstalk to manage ECS environments and swap environment URLs after deployment.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Answer B is correct because AWS CodeDeploy's blue/green deployment strategy with ECS allows immediate rollback by rerouting traffic to the original environment if health checks fail, ensuring minimal downtime and safe deployments. ✨
  
</details>

---

## ❓ Question 87

A company has an application running on Amazon EC2 instances. A solutions architect is designing VPC infrastructure in an AWS Region where the application needs to access an Amazon ElastiCache Redis cluster. The EC2 instances are all associated with the same security group. The ElastiCache cluster is associated with its own security group. The solutions architect needs to add rules to the security groups to provide the application with least privilege access to the ElastiCache cluster. Which combination of steps will meet these requirements? (Choose two.)

- **A.** Add an inbound rule to the EC2 instances' security group. Specify the ElastiCache cluster's security group as the source over the default Redis port.
- **B.** Add an outbound rule to the EC2 instances' security group. Specify the ElastiCache cluster's security group as the destination over the default Redis port.
- **C.** Add an inbound rule to the ElastiCache cluster's security group. Specify the EC2 instances' security group as the source over the default Redis port.
- **D.** Add an outbound rule to the ElastiCache cluster's security group. Specify the EC2 instances' security group as the destination over the default Redis port.
- **E.** Add an outbound rule to the ElastiCache cluster's security group. Specify the EC2 instances' security group as the destination over the ephemeral ports.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BC**
  
  > Short Explanation: The correct answers are B and C. To enable least privilege access, the EC2 instances' security group must allow outbound traffic to the ElastiCache cluster on the Redis port, and the ElastiCache cluster's security group must allow inbound traffic from the EC2 instances' security group on the same port. ✨
  
</details>

---

## ❓ Question 88

A company aims to modify its internal cloud billing approach for each department. The cloud governance team currently provides overall cloud expenditure reports to each department head. The company utilizes AWS Organizations to manage separate AWS accounts for each department. Existing tagging standards include department, environment, and project. The team seeks a centralized solution to deliver monthly department-specific spending reports and notifications when expenditures surpass predefined thresholds.

Which solution is the MOST cost-effective way to fulfill these requirements?

- **A.** Configure AWS Budgets in each account with alerts grouped by department, environment, and project. Subscribe each department to an Amazon SNS topic per alert. Use Cost Explorer in each account to generate monthly department reports.
- **B.** Configure AWS Budgets in the organization's management account with alerts grouped by department, environment, and project. Subscribe each department to an Amazon SNS topic per alert. Use Cost Explorer in the management account to generate monthly department reports.
- **C.** Configure AWS Budgets in each account with alerts grouped by department, environment, and project. Subscribe each department to an Amazon SNS topic per alert. Use the AWS Billing and Cost Management dashboard in each account to generate monthly department reports.
- **D.** Enable AWS Cost and Usage Reports in the management account, grouped by department, environment, and project. Develop an AWS Lambda function to process reports, send alerts, and distribute monthly reports to departments via email.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B because configuring AWS Budgets in the management account allows centralized tracking of costs across all departments using tags. Combined with Cost Explorer, it provides consolidated reports and alerts via SNS, ensuring cost-effectiveness and alignment with AWS Organizations. ✨
  
</details>

---

## ❓ Question 89

A company uses AWS CloudFormation to manage its infrastructure. To comply with data retention policies, the company must ensure that critical Amazon RDS instances and Amazon EBS volumes are preserved even if the associated CloudFormation stack is deleted. 

Which solution guarantees that these resources are retained without relying on IAM policies or external AWS services?

- **A.** Update the CloudFormation templates to specify a DeletionPolicy attribute set to \"Retain\" for the RDS and EBS resources.
- **B.** Apply a stack policy that explicitly blocks deletion of RDS and EBS resources during stack operations.
- **C.** Use IAM policies to restrict deletion of resources with a specific \"aws:cloudformation:stack-id\" tag.
- **D.** Enable AWS Backup to create backups of RDS and EBS resources before stack deletion.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. Setting the DeletionPolicy attribute to 'Retain' in the CloudFormation templates ensures RDS and EBS resources are preserved when the stack is deleted, aligning with data retention policies. ✨
  
</details>

---

## ❓ Question 90

A company has VPC flow logs enabled for its NAT gateway. The company is observing Action = ACCEPT for inbound traffic originating from public IP address 203.0.100.5 destined for a private Amazon EC2 instance. A solutions architect needs to determine if this traffic represents unsolicited inbound connections from the internet. The first two octets of the VPC CIDR block are 192.168. Which set of steps should the solutions architect take to meet these requirements?

- **A.** Open the AWS CloudTrail console. Select the log group containing the NAT gateway's elastic network interface and the private instance's elastic network interface. Run a query to filter with the destination address set as \"like 192.168\" and the source address set as \"like 203.0.100.5\". Run the stats command to filter the sum of bytes transferred by the source and destination addresses.
- **B.** Open the Amazon CloudWatch console. Select the log group containing the NAT gateway's elastic network interface and the private instance's elastic network interface. Run a query to filter with the destination address set as \"like 192.168\" and the source address set as \"like 203.0.100.5\". Run the stats command to filter the sum of bytes transferred by the source and destination addresses.
- **C.** Open the AWS CloudTrail console. Select the log group containing the NAT gateway's elastic network interface and the private instance's elastic network interface. Run a query to filter with the destination address set as \"like 203.0.100.5\" and the source address set as \"like 192.168\". Run the stats command to filter the sum of bytes transferred by the source and destination addresses.
- **D.** Open the Amazon CloudWatch console. Select the log group containing the NAT gateway's elastic network interface and the private instance's elastic network interface. Run a query to filter with the destination address set as \"like 203.0.100.5\" and the source address set as \"like 192.168\". Run the stats command to filter the sum of bytes transferred by the source and destination addresses.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. VPC Flow Logs are stored in Amazon CloudWatch, not AWS CloudTrail. The query filters traffic with the source as the public IP (203.0.100.5) and destination as the private VPC CIDR (192.168.x.x), ensuring analysis of unsolicited inbound traffic. ✨
  
</details>

---

## ❓ Question 91

A company has multiple departments, each operating within their own AWS account under a single AWS Organizations setup. Each department maintains an Amazon S3 bucket configured for cross-account access to share sensitive data. The S3 buckets contain millions of objects. A recent audit revealed that server-side encryption is not enabled on any of the buckets, violating company policy requiring encryption at rest. The company wants to enforce server-side encryption using Amazon S3 managed keys (SSE-S3).

What is the MOST operationally efficient solution to meet these requirements?

- **A.** Enable SSE-S3 on all S3 buckets. Use S3 Batch Operations to copy and encrypt existing objects in place.
- **B.** Create AWS KMS keys in each account. Enable SSE-KMS on each bucket using its account's KMS key. Encrypt existing objects via an S3 copy command in the AWS CLI.
- **C.** Enable SSE-S3 on all S3 buckets. Encrypt existing objects using an S3 copy command in the AWS CLI.
- **D.** Create AWS KMS keys in each account. Enable SSE-KMS on each bucket using its account's KMS key. Use S3 Batch Operations to copy and encrypt existing objects.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A because enabling SSE-S3 on all buckets and using S3 Batch Operations efficiently encrypts existing objects at scale, aligning with the requirement to use SSE-S3. ✨
  
</details>

---

## ❓ Question 92

A company stores medical imaging data in an Amazon S3 bucket, which accumulates several petabytes over time. The data grows by hundreds of gigabytes daily. The company regularly analyzes data from the past 18 months for research purposes but must retain all data indefinitely to meet regulatory requirements. Which approach provides the MOST cost-effective solution while meeting these needs?

- **A.** Use S3 Select to query the data. Create an S3 Lifecycle policy to transition data older than 18 months to S3 Glacier Flexible Retrieval.
- **B.** Use Amazon Redshift Spectrum to query the data. Create an S3 Lifecycle policy to transition data older than 18 months to S3 Intelligent-Tiering.
- **C.** Use an AWS Glue Data Catalog and Amazon Athena to query the data. Create an S3 Lifecycle policy to transition data older than 18 months to S3 Glacier Deep Archive.
- **D.** Use Amazon EMR with Hive to query the data. Create an S3 Lifecycle policy to transition data older than 18 months to S3 Standard-Infrequent Access.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Using AWS Glue Data Catalog and Amazon Athena allows cost-effective querying of recent data, while transitioning older data to S3 Glacier Deep Archive minimizes storage costs for indefinite retention, meeting regulatory requirements. ✨
  
</details>

---

## ❓ Question 93

A genomics research firm needs to transfer 500 TB of compressed genomic data stored on-premises to AWS for machine learning analysis. The firm lacks on-premises compute resources for ML and must complete the transfer within 3 weeks. The data must be encrypted in transit, and the company's shared internet connection has a measured upload speed of 100 Mbps. Which solution is MOST cost-effective?

- **A.** Order multiple AWS Snowball Edge Storage Optimized devices via the AWS Management Console. Configure the devices with a target S3 bucket, copy the data, and return the devices to AWS.
- **B.** Establish a 10 Gbps AWS Direct Connect link to the nearest AWS Region. Transfer the data directly to Amazon S3 over the dedicated connection.
- **C.** Create a VPN tunnel between the on-premises storage and AWS. Transfer the data over the VPN connection to Amazon S3.
- **D.** Deploy an AWS Storage Gateway file gateway on premises. Configure it to sync data to an S3 bucket.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A because transferring 500 TB over a 100 Mbps connection would take over a year. AWS Snowball Edge devices are designed for large data transfers, ensuring completion within 3 weeks while encrypting data in transit. ✨
  
</details>

---

## ❓ Question 94

A company has migrated its invoice-processing application to AWS. Users upload scanned invoices through a web application, which stores metadata in an Amazon RDS for PostgreSQL database and files in Amazon S3. The web application runs on Amazon EC2 instances. When invoices are uploaded, notifications are sent via Amazon SNS, requiring manual validation and data entry into another system via an API. A solutions architect must automate this process with accurate extraction, minimal time to market, and low operational overhead. Which solution meets these requirements?

- **A.** Develop custom OCR libraries and deploy them on an Amazon EKS cluster. Process invoices upon upload, store output in S3, parse into DynamoDB, and submit via API using EC2-hosted tiers.
- **B.** Use AWS Step Functions and Lambda with EC2-hosted AI/ML models for OCR. Store output in S3, parse within the tier, and submit data via API.
- **C.** Host EC2 instances to call SageMaker-hosted AI/ML models for OCR. Store output in Amazon ElastiCache, parse within the tier, and submit via API.
- **D.** Implement AWS Step Functions and Lambda with Amazon Textract and Comprehend for OCR. Store output in S3, parse within the tier, and submit data via API.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: Answer D uses AWS-managed services (Textract for OCR, Comprehend for data extraction, Step Functions for orchestration, and Lambda for serverless processing) to automate invoice processing with minimal operational overhead and fast implementation. ✨
  
</details>

---

## ❓ Question 95

A company is migrating its on-premises payment-processing system to the AWS Cloud. The system includes a web frontend hosted on virtual machines, ActiveMQ for messaging between the frontend and backend, and a Kubernetes cluster running a containerized backend to handle payment transactions. The company wants to minimize application changes and reduce operational overhead.

Which solution meets these requirements with the LEAST operational overhead?

- **A.** Create an AMI of the web server VM. Deploy it using an Amazon EC2 Auto Scaling group and an Application Load Balancer. Replace ActiveMQ with Amazon MQ. Migrate the Kubernetes backend to Amazon Elastic Kubernetes Service (Amazon EKS).
- **B.** Replatform the web frontend using AWS Lambda with a custom runtime and Amazon API Gateway. Replace ActiveMQ with Amazon MQ. Migrate the Kubernetes backend to Amazon EKS.
- **C.** Create an AMI of the web server VM. Deploy it using an Amazon EC2 Auto Scaling group and an Application Load Balancer. Replace ActiveMQ with Amazon MQ. Install Kubernetes on EC2 instances for the backend.
- **D.** Create an AMI of the web server VM. Deploy it using an Amazon EC2 Auto Scaling group and an Application Load Balancer. Replace ActiveMQ with Amazon Simple Queue Service (SQS). Migrate the Kubernetes backend to Amazon EKS.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A minimizes application changes by using an AMI for the web frontend, replaces ActiveMQ with Amazon MQ (a managed service), and migrates Kubernetes to Amazon EKS (managed Kubernetes), reducing operational overhead. ✨
  
</details>

---

## ❓ Question 96

A solutions architect implemented client-side encryption using a customer master key (CMK) from AWS Key Management Service (KMS) for objects stored in a new Amazon S3 bucket. The solutions architect created an IAM policy and attached it to an IAM role. During testing, uploading new objects to the S3 bucket was successful, but attempts to download existing objects resulted in an error stating the action was forbidden. Which action must the solutions architect add to the IAM policy to resolve this issue?

- **A.** kms:Decrypt
- **B.** kms:Encrypt
- **C.** kms:GetParametersForImport
- **D.** kms:Verify

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. The IAM policy requires the kms:Decrypt action to allow decryption of client-side encrypted objects during download. Without this permission, the role cannot access the KMS CMK to decrypt the data, causing the forbidden error. ✨
  
</details>

---

## ❓ Question 97

A company is deploying a new web application on Amazon EC2 instances behind an Application Load Balancer. They want to implement AWS WAF to protect against common web exploits while ensuring legitimate users are not blocked. The solution must minimize disruption during the initial deployment phase.

How should the solutions architect configure the web ACLs to meet these requirements?

- **A.** Set the action of the web ACL rules to Count. Enable AWS WAF logging. Analyze the requests for false positives. Modify the rules to avoid any false positive. Over time, change the action of the web ACL rules from Count to Block.
- **B.** Use rate-based rules in the web ACLs with a high throttle limit. Temporarily block requests exceeding the limit. Define nested conditions to refine the rate-tracking scope.
- **C.** Set the action of the web ACL rules to Block. Use AWS managed rule groups exclusively. Evaluate the rules using Amazon CloudWatch metrics and AWS WAF logs.
- **D.** Create custom rule groups with Allow actions. Enable AWS WAF logging. Analyze requests for false positives, adjust rules, and gradually change the action from Allow to Block.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. Setting the web ACL rules to 'Count' initially allows monitoring and analysis of traffic without blocking, minimizing disruption. After verifying no legitimate traffic is blocked (via logs), rules can safely transition to 'Block'. ✨
  
</details>

---

## ❓ Question 98

A company with multiple AWS accounts in AWS Organizations needs a centralized way to manage common security group rules that allow inbound traffic from a dynamic set of IP CIDR ranges. The security team, operating from a dedicated AWS account, updates the IP allow list frequently. Developers in each account currently manually update their security groups based on notifications from the security team. The solutions architect must automate the distribution of these CIDR updates across all accounts with minimal ongoing effort.

Which solution meets these requirements with the LEAST operational overhead?

- **A.** Deploy an Amazon EventBridge rule in the security team's account to detect changes to an Amazon S3 bucket containing the CIDR list. Use AWS Lambda functions in each account, triggered by cross-account EventBridge events, to update security groups with the latest CIDR ranges from the S3 bucket.
- **B.** Create separate customer-managed prefix lists in every AWS account. Configure the security team to update each prefix list directly via AWS CLI across all accounts. Notify developers to reference their account-specific prefix list in security group rules.
- **C.** Create a single customer-managed prefix list in the security team's account with the approved CIDR ranges. Share the prefix list across the organization using AWS Resource Access Manager (RAM). Instruct all accounts to reference this shared prefix list in their security group rules.
- **D.** Implement a cross-account IAM role granting the security team write access to all security groups. Deploy a Lambda function in the security team's account to programmatically update security groups in all target accounts directly when CIDR ranges change.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Using a shared customer-managed prefix list via AWS Resource Access Manager (RAM) allows centralized updates by the security team, automatically propagating changes to all accounts. This minimizes operational overhead compared to cross-account Lambdas, manual CLI updates, or direct security group modifications. ✨
  
</details>

---

## ❓ Question 99

A company uses a transit gateway in their main AWS account to connect VPCs across multiple AWS accounts. Their on-premises network is connected via an AWS Site-to-Site VPN through the transit gateway. The company wants to implement a scalable AWS Client VPN solution for remote employees. What is the MOST cost-effective solution?

- **A.** Create a Client VPN endpoint in each AWS account and configure routing to allow access.
- **B.** Create a Client VPN endpoint in the main account and configure routing through VPC peering connections.
- **C.** Create a Client VPN endpoint in the main account, attach it to the existing transit gateway, and configure routing.
- **D.** Establish connectivity between a Client VPN endpoint in the main account and the AWS Site-to-Site VPN.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Creating a Client VPN endpoint in the main account and attaching it to the existing transit gateway leverages the existing infrastructure, enabling scalable and cost-effective routing to all connected VPCs and on-premises networks. ✨
  
</details>

---

## ❓ Question 100

A company's e-commerce platform experiences prolonged delays during peak traffic due to synchronous calls to a third-party payment gateway. The current architecture directly invokes an AWS Fargate task for each transaction, leading to bottlenecks and failed payments. A solutions architect must decouple the payment processing system and ensure all transactions are eventually processed without dropping requests. Which solution meets these requirements?

- **A.** Use an Amazon Simple Queue Service (Amazon SQS) queue to buffer payment requests and asynchronously trigger the Fargate tasks.
- **B.** Use an AWS Step Functions state machine to orchestrate the payment processing workflow with the Fargate tasks.
- **C.** Use an Amazon EventBridge rule to schedule the Fargate tasks for processing payment requests.
- **D.** Use an Amazon Simple Notification Service (Amazon SNS) topic to fan out payment requests to multiple Fargate tasks.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Using Amazon SQS decouples payment processing by buffering requests, allowing asynchronous handling by Fargate tasks. This prevents bottlenecks and ensures eventual processing without dropping requests. ✨
  
</details>