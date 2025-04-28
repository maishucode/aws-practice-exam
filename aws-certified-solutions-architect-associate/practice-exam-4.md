# 🌟 AWS Certified Developer – Associate 🌟

Welcome to our practice exam portal! This page is designed to help you master the key concepts and best practices for AWS architecture. Whether you're preparing for your certification exam or looking to boost your practical skills, our high-quality questions and in-depth explanations are here to support you.

---

> **Quick Tip:**  
> For an even better learning experience and a wealth of additional resources, please visit our website:  
> [https://www.awsxp.com/](https://www.awsxp.com/)  
> Discover the latest case studies, expert insights, and specialized courses that will supercharge your AWS skills!

---

> **Get Started Now!**  
> Click on the "View Answer" button on any question below to reveal detailed explanations and solutions.  
> Enjoy your journey to AWS excellence and success on the AWS Certified Developer – Associate exam! 🚀

## ❓ Question 151

A company has migrated an application to AWS. The frontend is a dynamic web application running on two Amazon EC2 instances behind an Application Load Balancer (ALB). The backend is a Java application running on three EC2 instances behind another ALB. The instances are large, compute-optimized On-Demand Instances sized for peak usage. The application experiences high traffic during business hours but minimal traffic during evenings and weekends. A solutions architect needs to optimize costs without affecting availability. Which two steps should be taken?

- **A.** Change all EC2 instances to Spot Instances.
- **B.** Migrate the frontend to a serverless architecture using AWS Lambda and API Gateway.
- **C.** Deploy the backend using AWS Fargate with Spot capacity providers.
- **D.** Change the backend instances to general purpose burstable instances with the same vCPU count.
- **E.** Implement Auto Scaling groups for both frontend and backend to scale in during off-peak hours.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BD**
  
  > Short Explanation: B (serverless frontend reduces EC2 costs) and D (burstable instances save costs for backend) optimize costs without affecting availability. Other options risk availability (A, C) or are less cost-effective (E). ✨
  
</details>

---

## ❓ Question 152

A company operates a video streaming platform on AWS using Amazon EKS with EC2 instances and Amazon Aurora PostgreSQL. They are migrating some services to AWS Fargate. The platform encounters sudden traffic surges during scheduled live events that occur sporadically throughout the year.

Which solution will provide the MOST cost-effective setup for the platform?

- **A.** Purchase EC2 Instance Savings Plans for the EKS cluster's baseline workload. Use Spot Instances to handle traffic surges. Buy 3-year All Upfront Reserved Instances for the Aurora database to accommodate predicted peak load. Temporarily add read replicas during events.
- **B.** Purchase Compute Savings Plans to cover the baseline usage of EKS and Fargate. Reserve On-Demand Capacity for EKS during scheduled live events to manage surges. Purchase 1-year No Upfront Reserved Instances for Aurora's baseline. Automatically scale read replicas during peak periods.
- **C.** Buy Reserved Instances for the EKS EC2 baseline capacity. Scale using Spot Instances during peaks. Purchase 3-year Partial Upfront Reserved Instances for Aurora's peak load. Manually scale the database instance vertically during events.
- **D.** Utilize Compute Savings Plans for EKS and Fargate's baseline. Scale EKS with Spot Instances for surges. Purchase 1-year All Upfront Reserved Instances for Aurora's baseline. Configure Aurora Serverless v2 to automatically adjust capacity during peaks.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Answer B combines Compute Savings Plans for baseline usage, reserves On-Demand Capacity for predictable EKS surges, and uses Aurora Reserved Instances with auto-scaling read replicas. This setup optimizes costs by leveraging flexible pricing models and automated scaling for sporadic traffic spikes. ✨
  
</details>

---

## ❓ Question 153

A company hosts a web application using AWS Elastic Beanstalk with Amazon RDS as the database. The application is fronted by an Amazon CloudFront distribution configured with an alternate domain name, using the Elastic Beanstalk environment as the origin. During monthly scheduled maintenance windows, the company wants users to see a static maintenance page instead of CloudFront errors. A solutions architect has already created an Amazon S3 bucket to host the maintenance content. What should the solutions architect do next to fulfill this requirement? (Choose three.)

- **A.** Upload the static maintenance page to the S3 bucket.
- **B.** Create a new CloudFront distribution with the S3 bucket as the origin and update DNS records to point to the new distribution during maintenance.
- **C.** Add the S3 bucket as a secondary origin in the existing CloudFront distribution and configure an origin access identity (OAI) for the bucket.
- **D.** Modify the default cache behavior in the CloudFront distribution to point to the S3 origin during maintenance, then revert it afterward.
- **E.** Create a new cache behavior in the existing distribution with a path pattern '*' and precedence 0 during maintenance, then delete it afterward.
- **F.** Configure Elastic Beanstalk to redirect traffic to the S3 bucket during maintenance using a .htaccess file.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ACD**
  
  > Short Explanation: The correct answers are A, C, and D. Upload the maintenance page to S3 (A), add S3 as a secondary origin with OAI (C), and modify the default cache behavior to point to S3 during maintenance (D). These steps ensure users see the static page without DNS changes or application-level redirects. ✨
  
</details>

---

## ❓ Question 154

A company operates a data processing pipeline using an AWS Lambda function. The function configures batch size and timeout settings through environment variables. The company frequently updates these variables to optimize performance. After validating new settings, they publish a new Lambda version and update their application to invoke the new version's ARN. This process causes application downtime during updates.

A solutions architect must streamline this process to eliminate downtime with minimal operational overhead.

Which solution meets these requirements?

- **A.** Modify the environment variables of the existing Lambda function version. Use the $LATEST version for testing new configurations.
- **B.** Store the batch size and timeout settings in an Amazon RDS database. Update the Lambda function to fetch parameters from the database.
- **C.** Hardcode the configuration parameters within the Lambda function code. Publish a new version each time parameters are updated.
- **D.** Create a Lambda function alias. Configure the application to use the alias ARN. Update the alias to point to new versions after testing.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: Using a Lambda alias allows the application to reference a consistent ARN while the alias is updated to point to new versions after testing. This eliminates downtime by decoupling version updates from the application's invocation target. ✨
  
</details>

---

## ❓ Question 155

A global e-commerce company is deploying a multi-Region application backed by Amazon DynamoDB global tables to ensure low-latency access for users across three continents. Each Region uses a public Application Load Balancer (ALB). The company manages its public DNS internally and needs to serve the application through an apex domain. Which solution meets these requirements with the LEAST effort?

- **A.** Migrate public DNS to Amazon Route 53. Create ALIAS records for the apex domain pointing to the ALBs. Use a latency-based routing policy to direct traffic to the closest Region.
- **B.** Deploy a Network Load Balancer (NLB) in front of each ALB. Migrate DNS to Route 53 and create A records for the apex domain pointing to the NLBs' static IP addresses. Configure a latency-based routing policy.
- **C.** Create an AWS Global Accelerator accelerator with endpoint groups targeting the ALBs in each Region. Use the accelerator's static IP addresses to create A records in the existing public DNS for the apex domain.
- **D.** Use Amazon CloudFront with origin groups pointing to the ALBs. Configure a Lambda@Edge function to route requests based on geographic location. Create a CNAME record for the apex domain pointing to the CloudFront distribution.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: AWS Global Accelerator provides static IPs and routes traffic to the nearest Region, allowing the company to create A records in their existing DNS without migrating to Route 53. This minimizes effort while meeting latency and apex domain requirements. ✨
  
</details>

---

## ❓ Question 156

A company is developing a serverless application using Amazon API Gateway and AWS Lambda. The Lambda functions require several common dependencies and shared libraries to be reused across multiple functions.

A solutions architect needs to ensure that the deployment process is simplified and that the common code is efficiently reused.

Which solution meets these requirements?

- **A.** Package the shared libraries into a Docker image and store it in an S3 bucket. Create a Lambda layer from this image. Deploy the Lambda functions as ZIP archives configured to use the layer.
- **B.** Package the shared libraries into a Docker image and upload it to Amazon ECR. Create a Lambda layer referencing this image. Deploy the Lambda functions as ZIP archives configured to use the layer.
- **C.** Deploy the shared libraries in a Docker container using Amazon ECS with AWS Fargate. Configure the Lambda functions to access this container as a layer via VPC networking.
- **D.** Package the shared libraries and Lambda function code into a single Docker image stored in Amazon ECR. Configure each Lambda function to use this image as its deployment package.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Packaging shared libraries into a Docker image stored in Amazon ECR and creating a Lambda layer allows efficient reuse of code. Deploying Lambda functions as ZIP archives with the layer simplifies deployment. ✨
  
</details>

---

## ❓ Question 157

A retail chain is developing a real-time inventory tracking system for its stores. The company uses ceiling-mounted cameras to monitor shelf stock levels. The company has trained an Amazon SageMaker machine learning (ML) model to detect low stock items from images. The company needs to trigger alerts for restocking via a local notification system, even during internet outages. A Linux server on premises hosts a REST API that manages the alert system.

How should the company deploy the ML model to meet these requirements?

- **A.** Configure Amazon Kinesis Data Streams to ingest images from the cameras. Use AWS Lambda to extract frames and store them in Amazon S3. Deploy a SageMaker endpoint for the ML model. Trigger a Lambda function to run inference on new images and invoke the local API via AWS Direct Connect when low stock is detected.
- **B.** Install AWS IoT Greengrass on the local server. Deploy the ML model to the Greengrass core. Create a Greengrass component to capture images from the cameras, perform local inference, and trigger the REST API directly when low stock is identified.
- **C.** Use AWS Outposts to host a SageMaker endpoint and EC2 instance locally. Capture images from the cameras, run inference on the EC2 instance via the SageMaker endpoint, and configure the instance to call the local API when low stock is detected.
- **D.** Deploy AWS Panorama Appliances on each camera. Train the ML model directly on the Panorama devices. Use Amazon EventBridge to route low stock alerts to the local API via an on-premises AWS Storage Gateway.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. AWS IoT Greengrass enables local ML inference and direct API triggering without internet, ensuring functionality during outages. ✨
  
</details>

---

## ❓ Question 158

A solutions architect is preparing a business case to migrate a company's on-premises infrastructure to AWS. The architect has a CMDB export detailing all servers and needs to analyze costs effectively. Which solution should they use?

- **A.** Use AWS Cost Explorer to import the CMDB data and generate cost reports.
- **B.** Use Migration Evaluator with the provided template to upload CMDB data for analysis.
- **C.** Deploy AWS Application Discovery Service agents to gather data and analyze with AWS Migration Hub.
- **D.** Utilize AWS Pricing Calculator by manually inputting CMDB data to estimate costs.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Migration Evaluator is designed to analyze on-premises data (like CMDB exports) using AWS-provided templates to generate cost estimates and migration recommendations, aligning with the scenario's requirements. ✨
  
</details>

---

## ❓ Question 159

A company operates a web application using Amazon EC2 instances behind an Application Load Balancer (ALB) within an Auto Scaling group. The ALB is integrated with an AWS WAF web ACL. The application frequently suffers from layer 7 DDoS attacks, resulting in abrupt traffic spikes originating from numerous distributed IP addresses. A solutions architect must design a solution to mitigate these attacks while minimizing operational complexity.

Which solution BEST meets these requirements?

- **A.** Create a CloudWatch alarm to track request rates per IP address. Configure the alarm to trigger an AWS Lambda function that dynamically updates the WAF web ACL to block IP addresses exceeding the threshold.
- **B.** Activate AWS Shield Advanced and associate it with the ALB to utilize managed DDoS protection integrated with AWS WAF.
- **C.** Deploy Amazon CloudFront with AWS WAF and implement a rate-based rule to restrict request counts from individual IP addresses.
- **D.** Analyze ALB access logs to identify attacking IP ranges and update the associated security group rules to block those ranges.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: AWS Shield Advanced provides managed DDoS protection with minimal operational complexity, specifically designed to mitigate layer 7 attacks when integrated with AWS WAF and ALB. ✨
  
</details>

---

## ❓ Question 160

A company runs a mission-critical application with its data tier deployed in a single AWS Region. The data tier consists of an Amazon DynamoDB table and an Amazon Aurora PostgreSQL DB cluster. The Aurora PostgreSQL engine version supports a global database. The application tier is already deployed across two Regions. Company policy mandates that all critical applications must have both application and data tiers deployed in two Regions, with an RTO and RPO of no more than a few minutes. A solutions architect must design a solution to align the data tier with these requirements.

Which combination of steps should be taken to meet these requirements? (Choose two.)

- **A.** Add a secondary Region to the Aurora PostgreSQL DB cluster using the global database feature
- **B.** Create a read replica of the Aurora PostgreSQL DB cluster in another Region
- **C.** Configure cross-Region automated backups for the DynamoDB table and Aurora PostgreSQL DB cluster
- **D.** Replicate the DynamoDB table to a secondary Region by enabling global tables
- **E.** Use AWS Backup to schedule cross-Region backups and automate recovery workflows

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AD**
  
  > Short Explanation: A and D are correct because Aurora Global Database provides cross-Region replication with low RTO/RPO, and DynamoDB Global Tables enable active-active replication. Backups (C, E) and read replicas (B) do not meet the strict RTO/RPO requirements. ✨
  
</details>

---

## ❓ Question 161

A telecommunications company is hosting an application on AWS using Amazon EC2 instances distributed across multiple Availability Zones behind an internal Application Load Balancer (ALB). The company utilizes AWS Direct Connect for connectivity between their on-premises data center and AWS. Clients access the application via HTTPS with TLS termination at the ALB, which employs host-based routing to direct requests to different target groups. The company now intends to deploy an on-premises firewall appliance configured with an IP-based allow list. A solutions architect must ensure uninterrupted client access to the application while complying with the firewall's IP restrictions.

Which solution meets these requirements?

- **A.** Configure the ALB to use static IP addresses across multiple Availability Zones. Register these IP addresses with the firewall appliance to permit traffic.
- **B.** Deploy a Network Load Balancer (NLB) with static IP addresses in each Availability Zone. Create an ALB target group for the NLB, integrate the existing ALB, and update client configurations to connect via the NLB. Add the NLB's IPs to the firewall allow list.
- **C.** Replace the ALB with a Network Load Balancer (NLB) using static IPs in multiple AZs. Migrate all target groups to the NLB, retire the ALB, and update clients to use the NLB. Add the NLB's IP addresses to the firewall.
- **D.** Implement a Gateway Load Balancer (GWLB) with static IP addresses in multiple AZs. Attach the ALB as a target via an ALB-type target group. Update the firewall's allow list with the GWLB's IPs and redirect clients to the GWLB.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The solution uses a Network Load Balancer (NLB) with static IPs to provide fixed addresses for the firewall allow list, while preserving the existing ALB's TLS termination and routing capabilities. ✨
  
</details>

---

## ❓ Question 162

A company hosts a web application using Amazon EC2 instances in private subnets behind an internet-facing Application Load Balancer (ALB). The ALB serves as the origin for an Amazon CloudFront distribution, which is protected by an AWS WAF web ACL with several AWS managed rules. The company wants to ensure that all incoming traffic must go through CloudFront and prevent direct access to the ALB from the internet. Which solution meets these requirements with the LEAST operational overhead?

- **A.** Create a new AWS WAF web ACL identical to the existing one and associate it with the ALB.
- **B.** Associate the existing AWS WAF web ACL with both the CloudFront distribution and the ALB.
- **C.** Modify the ALB's security group to allow inbound traffic only from the AWS managed prefix list for CloudFront.
- **D.** Update the ALB's security group to permit inbound traffic solely from the published CloudFront IP ranges.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Modifying the ALB's security group to allow inbound traffic only from the AWS managed prefix list for CloudFront ensures all traffic must go through CloudFront, blocking direct access to the ALB with minimal operational overhead. ✨
  
</details>

---

## ❓ Question 163

A company is running an application that uses an Amazon ElastiCache for Redis cluster as a caching layer. A recent security audit revealed that encryption at rest is enabled, but encryption in transit is not configured. Additionally, the cluster allows unauthenticated access. A solutions architect must enforce authentication and ensure end-to-end encryption for data in transit. Which solution meets these requirements?

- **A.** Create an AUTH token. Store the token in AWS Systems Manager Parameter Store as an encrypted parameter. Create a new cluster with encryption in transit enabled and AUTH configured. Update the application to retrieve the token from Parameter Store and use it for authentication.
- **B.** Create an AUTH token. Store the token in AWS Secrets Manager. Configure the existing cluster to enable encryption in transit and apply the AUTH token. Update the application to retrieve the token from Secrets Manager and use it for authentication.
- **C.** Generate an SSL certificate. Store the certificate in AWS Secrets Manager. Create a new cluster with encryption in transit enabled. Update the application to retrieve the certificate from Secrets Manager and use it for authentication.
- **D.** Generate an SSL certificate. Store the certificate in AWS Systems Manager Parameter Store as an encrypted advanced parameter. Update the existing cluster to enable encryption in transit. Update the application to retrieve the certificate from Parameter Store and use it for authentication.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is A. A new cluster must be created with encryption in transit and AUTH enabled, as these settings cannot be applied to an existing ElastiCache cluster. The token is securely stored in Parameter Store. ✨
  
</details>

---

## ❓ Question 164

A company is running a compute workload using Amazon EC2 Spot Instances in an Auto Scaling group. The launch template specifies a single instance type and a single Availability Zone. Recently, there have been frequent instance launch failures, causing delays. The company needs to enhance the workload's reliability.

Which solution meets this requirement?

- **A.** Replace the launch template with a launch configuration that uses multiple Availability Zones and instance types.
- **B.** Create a new launch template version using attribute-based instance type selection and configure the Auto Scaling group to use multiple Availability Zones.
- **C.** Update the Auto Scaling group to increase the number of Availability Zones while keeping the same instance type.
- **D.** Modify the launch template to use a different single instance type with higher capacity.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Using attribute-based instance selection and multiple Availability Zones increases the pool of available Spot capacity, enhancing reliability by diversifying instance options and reducing launch failures. ✨
  
</details>

---

## ❓ Question 165

A company is migrating a media processing application to AWS. The application generates video files at a rate of 10 files per second and requires low-latency local access for real-time editing. The legacy application runs on Linux and cannot be immediately updated to use the Amazon S3 API. Once processing is complete, the files must be publicly accessible via Amazon S3 within 20 minutes.

Which solution meets these requirements with the LEAST operational overhead?

- **A.** Re-architect the application to run on AWS Lambda. Use the AWS SDK for Python to process and store files directly in Amazon S3, leveraging temporary storage for real-time edits.
- **B.** Deploy an Amazon S3 File Gateway and create a file share linked to an S3 bucket. Mount the file share on an Amazon EC2 instance using NFS. Use the RefreshCache API to ensure updates in S3 are propagated to the gateway promptly.
- **C.** Configure Amazon FSx for Lustre with a linked S3 bucket. Mount the Lustre file system on an Amazon EC2 instance using the Lustre client. Use a data repository task to synchronize files between FSx and S3 every 15 minutes.
- **D.** Use AWS DataSync to continuously synchronize files between the EC2 instance's local storage and Amazon S3. Schedule DataSync tasks to run every 10 minutes to ensure timely availability.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Amazon S3 File Gateway provides low-latency local access via NFS, integrates with S3 without requiring API changes, and uses the RefreshCache API to ensure timely S3 availability, minimizing operational overhead. ✨
  
</details>

---

## ❓ Question 166

A retail company operates a serverless e-commerce platform on AWS. The platform's inventory service manages product details in an Amazon DynamoDB table. Several other microservices maintain cached copies of product data in different storage solutions. When a product is discontinued, the inventory service deletes it, and all microservices must immediately remove their cached data to prevent outdated information. Which solution ensures immediate deletion across all services?

- **A.** Enable DynamoDB Streams on the DynamoDB table. Use an AWS Lambda function triggered by the stream to send deletion events to an Amazon Simple Queue Service (Amazon SQS) queue. Configure each microservice to poll the queue and delete the product from the DynamoDB table.
- **B.** Configure DynamoDB event notifications to publish deletion events to an Amazon Simple Notification Service (Amazon SNS) topic. Subscribe each microservice to the SNS topic and delete the product from the DynamoDB table.
- **C.** Have the inventory service publish a custom event to an Amazon EventBridge event bus upon product deletion. Create an EventBridge rule for each microservice to detect the deletion event and trigger their logic to remove cached data.
- **D.** Configure the inventory service to send deletion messages to an Amazon Simple Queue Service (Amazon SQS) queue. Set up each microservice to filter events from the queue and delete the product from the DynamoDB table.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Using Amazon EventBridge allows the inventory service to publish a custom event upon deletion, which triggers each microservice to remove cached data immediately via EventBridge rules. This ensures real-time synchronization without relying on polling or redundant operations. ✨
  
</details>

---

## ❓ Question 167

A company hosts a REST API on Amazon EC2 instances behind an Application Load Balancer (ALB) with AWS WAF integration. Third-party systems require whitelisting static IP addresses to access the API. The company needs to provide fixed IP addresses to these external systems while minimizing operational complexity.

Which solution meets these requirements MOST effectively?

- **A.** Replace the ALB with a Network Load Balancer (NLB). Assign Elastic IP addresses to the NLB and share them with third parties.
- **B.** Allocate an Elastic IP address and associate it directly with the ALB. Provide the Elastic IP address to third parties.
- **C.** Create an AWS Global Accelerator standard accelerator with the ALB as its endpoint. Share the accelerator's static IP addresses with third parties.
- **D.** Set up an Amazon CloudFront distribution with the ALB as the origin. Use DNS resolution tools to identify the distribution's IP addresses periodically and update third parties.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: AWS Global Accelerator provides static IP addresses that route traffic to the ALB, eliminating the need to replace infrastructure or manage dynamic IPs. This minimizes operational complexity while meeting the requirement for fixed IPs. ✨
  
</details>

---

## ❓ Question 168

A company maintains several AWS accounts for testing and intends to migrate its production workloads to AWS. The company must enforce Amazon S3 bucket encryption at rest for existing and future production accounts exclusively. The solution should incorporate built-in blueprints and guardrails.

Which combination of steps will fulfill these requirements? (Choose three.)

- **A.** Use AWS CloudFormation StackSets to deploy AWS Config rules on production accounts.
- **B.** Create a new AWS Control Tower landing zone in an existing test account. Establish organizational units (OUs) and assign accounts to respective OUs.
- **C.** Create a new AWS Control Tower landing zone in the management account. Organize production and test accounts into their respective OUs.
- **D.** Invite existing AWS accounts to join the organization using AWS Organizations. Implement service control policies (SCPs) for compliance.
- **E.** Enable a detective guardrail from the management account to monitor S3 encryption compliance.
- **F.** Apply a preventive guardrail to the production OU mandating S3 bucket encryption.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CDF**
  
  > Short Explanation: The correct answers are C, D, and F. AWS Control Tower must be set up in the management account (C) to organize accounts into OUs. Existing accounts are invited via AWS Organizations (D), and preventive guardrails enforce S3 encryption (F). ✨
  
</details>

---

## ❓ Question 169

A company operates a stateful e-commerce platform on three Linux Amazon EC2 instances behind an Application Load Balancer (ALB) with an Amazon Aurora MySQL database. The platform uses Amazon Route 53 for DNS management. A solutions architect must design a disaster recovery solution to enhance resiliency while meeting the following requirements:

- Application tier: RPO of 90 seconds. RTO of 20 minutes
- Database tier: RPO of 3 minutes. RTO of 25 minutes

The solution must minimize architectural changes and maintain low-latency performance during failover. Which approach satisfies these criteria?

- **A.** Enable AWS Elastic Disaster Recovery for the EC2 instances. Set up a cross-Region Aurora replica for the database. Deploy an ALB in a secondary AWS Region. Configure an AWS Global Accelerator endpoint linked to both ALBs. Update Route 53 to route traffic via the Global Accelerator endpoint.
- **B.** Use Amazon Data Lifecycle Manager (DLM) to create hourly EBS snapshots of the EC2 instances. Enable Aurora automated backups with cross-Region replication. Deploy an ALB in a secondary Region. Route traffic using a weighted alias record in Route 53 pointing to both ALBs.
- **C.** Implement AWS Backup for daily EC2 snapshots and Aurora backups. Replicate backups to another Region. Launch an ALB in the secondary Region. Use Amazon CloudFront with origin failover configured for both ALBs. Update DNS to point to the CloudFront distribution.
- **D.** Configure EC2 instances with AWS Elastic Disaster Recovery. Create an Aurora cross-Region read replica. Deploy an ALB in the secondary Region. Use Route 53 latency-based routing between the ALBs without Global Accelerator.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Option A meets the RPO/RTO requirements by using Elastic Disaster Recovery (EC2), cross-region Aurora replica (database), and Global Accelerator for fast failover with low latency. Other options fail due to insufficient RPO (B, C) or slower failover (D). ✨
  
</details>

---

## ❓ Question 170

A solutions architect needs to right-size Amazon EC2 instances to optimize costs while ensuring adequate performance based on historical CPU, memory, and network utilization. Which two actions should the solutions architect take to achieve this goal? (Choose two.)

- **A.** Upgrade to AWS Enterprise Support to access advanced operational and technical guidance.
- **B.** Enable AWS Trusted Advisor and analyze the 'Idle EC2 Instances' recommendations.
- **C.** Deploy the Amazon CloudWatch agent on EC2 instances and enable memory usage monitoring.
- **D.** Activate AWS Compute Optimizer in the account to generate instance optimization insights.
- **E.** Purchase Reserved Instances for the required instance types and regions to reduce costs.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CD**
  
  > Short Explanation: The correct answers are C and D. Deploying the CloudWatch agent enables memory monitoring (not natively tracked), and Compute Optimizer provides automated right-sizing recommendations based on historical utilization. ✨
  
</details>

---

## ❓ Question 171

A company uses an AWS CodeCommit repository and requires a real-time backup of the repository data in a secondary AWS Region. Which solution fulfills this requirement?

- **A.** Configure AWS Application Migration Service to replicate the CodeCommit repository to the second Region.
- **B.** Use AWS Backup to create a daily backup of the CodeCommit repository and enable cross-Region copying to the secondary Region.
- **C.** Create an Amazon EventBridge rule triggered by repository push events to invoke an AWS Lambda function. The Lambda function clones the repository, packages it into a .zip file, and copies the file to an S3 bucket in the secondary Region.
- **D.** Set up an Amazon S3 Cross-Region Replication (CRR) rule to automatically replicate the CodeCommit repository's underlying storage to the second Region.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. An EventBridge rule triggers on CodeCommit push events, invoking a Lambda function to clone, package, and copy the repository to an S3 bucket in another Region, ensuring real-time backup. ✨
  
</details>

---

## ❓ Question 172

A company operates multiple business units, each with its own AWS account and VPCs that use overlapping CIDR ranges. The finance team has developed a shared analytics database that must be privately accessible by all business units without exposing traffic to the public internet. The solution must minimize ongoing management effort and avoid CIDR conflicts.

- **A.** Deploy a Transit Gateway in the finance account and share it with all business units. Attach each VPC to the Transit Gateway, configure route tables to prioritize specific CIDRs, and deploy NAT instances in each VPC to handle overlapping ranges.
- **B.** Set up AWS Client VPN endpoints in the finance team's VPC. Establish VPN connections from each business unit's VPC to the finance VPC and implement custom NAT rules on EC2 instances to resolve CIDR overlaps.
- **C.** Create an AWS PrivateLink endpoint service for the analytics database in the finance account. Authorize access from other business unit accounts and deploy interface VPC endpoints in each business unit's VPC to access the service via private IPs.
- **D.** Establish VPC peering connections between each business unit's VPC and the finance VPC. Configure route tables to allow communication and use security groups to restrict access to the analytics database.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: AWS PrivateLink (Option C) is the correct solution because it allows private access to the shared database without exposing traffic to the internet, avoids CIDR conflicts by using interface endpoints, and minimizes management effort. ✨
  
</details>

---

## ❓ Question 173

A company needs to audit the security posture of a newly acquired AWS account. The company’s data security team requires a notification only when an Amazon S3 bucket becomes publicly exposed. The company has already established an Amazon Simple Notification Service (Amazon SNS) topic that has the data security team's email address subscribed.

Which solution will meet these requirements?

- **A.** Create an S3 event notification on all S3 buckets for the PutBucketPolicy event. Select the SNS topic as the target for the event notifications.
- **B.** Create an analyzer in AWS Identity and Access Management Access Analyzer. Create an Amazon EventBridge rule for the event type 'Access Analyzer Finding' with a filter for 'isPublic:false.' Select the SNS topic as the EventBridge rule target.
- **C.** Create an Amazon EventBridge rule for the event type 'Bucket-Level API Call via CloudTrail' with a filter for 'PutBucketAcl.' Select the SNS topic as the EventBridge rule target.
- **D.** Activate AWS Config and add the s3-bucket-public-read-prohibited rule. Create an Amazon EventBridge rule for the event type 'Config Rules Compliance Change' with a filter for 'NON_COMPLIANT.' Select the SNS topic as the EventBridge rule target.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D because AWS Config with the s3-bucket-public-read-prohibited rule monitors both ACL and policy changes, triggering a notification via EventBridge when a bucket becomes non-compliant (public). Other options either miss detection methods, use incorrect filters, or generate false positives. ✨
  
</details>

---

## ❓ Question 174

A solutions architect is tasked with preparing a migration strategy for a company's undocumented on-premises applications and databases to AWS. The environment includes variable traffic patterns and monthly batch processes. The architect must first assess the portfolio to identify all assets, dependencies, and create a business case for migration.

Which approach meets these requirements?

- **A.** Use AWS Application Discovery Service to identify servers and dependencies. Use AWS Migration Hub to consolidate findings. Use AWS Server Migration Service (SMS) to generate migration plans and a business case.
- **B.** Deploy AWS Agents for Discovery Service on-premises. Use Migration Hub to track progress. Utilize AWS Database Migration Service (DMS) to analyze database dependencies and Storage Gateway for storage assessment.
- **C.** Employ Migration Evaluator to create a server inventory and business case. Use Migration Hub to aggregate data. Apply AWS Application Discovery Service to map application dependencies.
- **D.** Implement AWS Control Tower to establish a landing zone. Use AWS Service Catalog for dependency mapping. Leverage AWS SMS for server inventory and migration planning.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: Answer C is correct because Migration Evaluator creates the server inventory and business case, Application Discovery Service maps dependencies, and Migration Hub aggregates data—aligning with the requirements of asset identification, dependency mapping, and business case creation. ✨
  
</details>

---

## ❓ Question 175

A company operates a distributed analytics application running as a ReplicaSet of pods in an Amazon EKS cluster spanning multiple Availability Zones. The application processes large volumes of log files that must be concurrently accessible by all pods. The company requires a storage solution that supports high-throughput access to these files and ensures backups are retained for 1 year. Which solution meets these requirements with the FASTEST storage performance?

- **A.** Create an Amazon EFS file system with mount targets in each subnet hosting EKS nodes. Mount the file system to the ReplicaSet and configure the application to write logs to it. Use AWS Backup to manage 1-year retention policies for backups.
- **B.** Provision an Amazon EBS volume with Multi-Attach enabled. Mount the volume to all pods in the ReplicaSet and direct log storage to it. Use AWS Backup to retain backups for 1 year.
- **C.** Configure the application to store logs directly in an Amazon S3 bucket mounted to the ReplicaSet. Enable S3 Versioning and apply a Lifecycle policy to expire objects after 1 year.
- **D.** Use local storage on each pod's ephemeral volumes for log storage. Implement a custom backup script to archive logs to an external system and retain them for 1 year.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Amazon EFS is the correct choice because it provides a scalable, shared file system accessible across multiple Availability Zones, supporting high-throughput access required by the distributed application. AWS Backup ensures 1-year retention. Other options either lack multi-AZ support, use slower storage types, or do not meet concurrent access requirements. ✨
  
</details>

---

## ❓ Question 176

A company operates a customer support system that handles voice calls and sends post-call SMS surveys allowing customers to respond interactively. The existing on-premises infrastructure is prone to outages, prompting the company to migrate to AWS for improved reliability and reduced operational overhead.

Which solution meets these requirements with the LEAST ongoing operational overhead?

- **A.** Use Amazon Connect to manage voice calls and Amazon Pinpoint to send and manage interactive SMS surveys.
- **B.** Use Amazon Connect to manage voice calls and Amazon Simple Notification Service (Amazon SNS) to send SMS surveys to customers.
- **C.** Migrate the voice call system to Amazon EC2 instances in an Auto Scaling group and use the EC2 instances to send SMS surveys.
- **D.** Use Amazon Pinpoint to handle voice calls and send interactive SMS surveys to customers.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Amazon Connect (managed contact center) and Amazon Pinpoint (interactive SMS) are fully managed services, minimizing operational overhead. Other options use non-interactive SMS (SNS), require EC2 management, or misuse Pinpoint for voice calls. ✨
  
</details>

---

## ❓ Question 177

A company is implementing a disaster recovery (DR) strategy for its Amazon Connect contact center, which includes numerous contact flows, users, and claimed phone numbers across AWS Regions. The operations team aims to minimize the Recovery Time Objective (RTO).

Which solution provides the LOWEST RTO?

- **A.** Provision a new Amazon Connect instance with contact flows and users in a second Region. Configure an Amazon CloudWatch alarm based on a Route 53 health check for the instance URL. Use an AWS Lambda function triggered by the alarm to deploy claimed phone numbers via an AWS CloudFormation template.
- **B.** Create an Amazon EventBridge rule to invoke an AWS Lambda function every 5 minutes to check the primary instance's health. If unavailable, the Lambda function deploys a CloudFormation template to provision a new instance with users, contact flows, and claimed numbers in the second Region.
- **C.** Provision a new Amazon Connect instance with users and contact flows in a second Region. Configure a Route 53 health check and CloudWatch alarm for the instance. Use a Lambda function triggered by the alarm to deploy claimed phone numbers via a CloudFormation template.
- **D.** Pre-provision users and claimed numbers in a second Region. Use a CloudWatch alarm with a Route 53 health check to trigger a Lambda function that deploys contact flows via CloudFormation during failover.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: Answer C pre-provisions the Amazon Connect instance, users, and contact flows in the second Region, minimizing recovery steps. Only claimed phone numbers are deployed during failover via CloudFormation, reducing RTO. ✨
  
</details>

---

## ❓ Question 178

A company stores curated data in Amazon Redshift after performing ETL processes. The company currently exports data manually to files and sends them via email to clients. Due to increasing clients, manual processes are error-prone and time-consuming. The company wants to use AWS Data Exchange to automate data sharing, ensure client identities are verified, and provide access to the latest data automatically upon updates with minimal operational effort. Which solution meets these requirements?

- **A.** Use AWS Data Exchange APIs to share data. Implement subscription verification. Create an API Gateway API integrated with Redshift, requiring clients to subscribe.
- **B.** Create an AWS Data Exchange datashare linked to the Redshift cluster. Configure subscription verification and require clients to subscribe.
- **C.** Periodically export Redshift data to an S3 bucket. Use AWS Data Exchange for S3 to share data, configure subscription verification, and require subscriptions.
- **D.** Publish Redshift data as Open Data on AWS Data Exchange. Attach IAM policies to Redshift tables allowing access only to subscribed clients' AWS accounts.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. AWS Data Exchange datashares integrate directly with Amazon Redshift, enabling automated, secure data sharing with clients. This approach ensures subscription verification, automatic updates, and minimal operational effort. ✨
  
</details>

---

## ❓ Question 179

A solutions architect is designing a system to process messages that must automatically scale based on workload and redirect failed messages to a dead-letter queue after three processing attempts. Which solution meets these requirements?

- **A.** Send messages to an Amazon SNS topic. Configure an AWS Lambda function as a subscriber. Set the Lambda function's on-failure destination to an Amazon SQS queue with a retry policy of two attempts.
- **B.** Use an Amazon SQS queue to receive messages. Configure an AWS Lambda function with the queue as an event source. Set the queue's redrive policy to a max receive count of 3 and specify a dead-letter queue.
- **C.** Write messages to an Amazon Kinesis Data Stream. Configure an AWS Lambda function to process records. Set the event source mapping's retry attempts to 3 and specify a dead-letter queue.
- **D.** Publish messages to an Amazon EventBridge event bus. Configure an AWS Lambda function as a target with a retry policy of three attempts. Route failed events to an Amazon SQS queue.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Option B uses Amazon SQS with AWS Lambda, configuring the queue's redrive policy to move messages to a dead-letter queue after three processing attempts. SQS-Lambda integration ensures automatic scaling based on workload, meeting both requirements. ✨
  
</details>

---

## ❓ Question 180

A company operates a real-time energy monitoring system in the AWS Cloud. The system processes data from thousands of sensors deployed across North America to calculate energy consumption metrics. The sensors send data to the system via a RESTful API, which experiences sudden, unpredictable traffic spikes. The company must ensure all data is processed without loss, even during peak loads.

Which solution meets these requirements?

- **A.** Deploy an Application Load Balancer (ALB) for the RESTful API. Create an Amazon Simple Queue Service (Amazon SQS) queue. Configure the ALB to route traffic to the SQS queue as a target group. Use Amazon Elastic Container Service (Amazon ECS) with Fargate to process messages from the queue.
- **B.** Implement the RESTful API using Amazon API Gateway REST API. Create an Amazon Simple Queue Service (Amazon SQS) queue. Configure an API Gateway service integration to send data directly to the SQS queue. Use an AWS Lambda function to process messages from the queue automatically.
- **C.** Set up the RESTful API using Amazon API Gateway. Create an Auto Scaling group of Amazon EC2 instances. Configure API Gateway to route traffic directly to the EC2 instances. Use the EC2 instances to process incoming sensor data.
- **D.** Use Amazon CloudFront as the entry point for the RESTful API. Create an Amazon Kinesis Data Firehose delivery stream as the origin. Configure an AWS Lambda function to process data from the Kinesis Data Firehose stream.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. API Gateway integrates with SQS to buffer incoming data during traffic spikes, and Lambda automatically scales to process messages, ensuring no data loss. Other options lack seamless scalability or proper buffering. ✨
  
</details>

---

## ❓ Question 181

A company is managing its cloud infrastructure using AWS Organizations with multiple Organizational Units (OUs). There are four OUs, each containing over 150 AWS accounts. Every account has a unique VPC deployed in the same AWS Region as other VPCs within its OU. The CIDR blocks for all VPCs across OUs are non-overlapping. The company requires that VPCs within the same OU can communicate seamlessly, while cross-OU VPC communication must be entirely restricted. Which solution meets these requirements with the LEAST operational overhead?

- **A.** Deploy an AWS CloudFormation stack set to configure VPC peering connections between all accounts within each OU. Apply the stack set separately to each OU.
- **B.** Create a central networking account within each OU with a shared VPC. Use AWS Resource Access Manager (RAM) to share this VPC with all OU accounts, then establish VPC peering connections between the central VPC and each account's VPC.
- **C.** Deploy a transit gateway in a designated account within each OU. Share each transit gateway across its respective OU using AWS RAM, then attach all VPCs in the OU to the transit gateway.
- **D.** Set up a dedicated networking account per OU with a VPN hub. Establish VPN connections between this hub and all other accounts in the OU, and implement custom routing protocols using third-party software for transitive routing.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Using AWS Transit Gateway allows VPCs within the same OU to communicate seamlessly via a centralized hub, while isolating cross-OU traffic. This approach minimizes operational overhead compared to managing VPC peering or VPN connections manually. ✨
  
</details>

---

## ❓ Question 182

A company is migrating a database application to AWS and wants to use fully managed services. The database stores sensitive transaction records with the following requirements:

- The data must be highly durable and available
- The data must be encrypted at rest and in transit
- The encryption keys must be managed by the company and rotated periodically

Which solution should the solutions architect recommend?

- **A.** Use Amazon RDS with SSL connections and encryption at rest using an AWS KMS customer-managed key.
- **B.** Use Amazon DynamoDB with SSL for data in transit and server-side encryption using an AWS KMS customer-managed key.
- **C.** Deploy Amazon EC2 instances with encrypted EBS volumes using a customer-managed KMS key and configure SSL on the database application.
- **D.** Use Amazon S3 with a bucket policy enforcing HTTPS and server-side encryption using AWS KMS.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Amazon DynamoDB is a fully managed service that encrypts data in transit (SSL) and at rest using a customer-managed KMS key, ensuring high durability, availability, and compliance with key management requirements. ✨
  
</details>

---

## ❓ Question 183

A company hosts its web application using Amazon ECS tasks on AWS Fargate, which are fronted by an Application Load Balancer (ALB). The service uses ECS Service Auto Scaling based on CPU utilization to handle traffic fluctuations.

Recently, the application became unresponsive due to a surge in traffic. Investigation revealed that the traffic spike was caused by numerous SQL injection attacks, which also triggered the service to scale out to its maximum limit.

The solutions architect must design a solution to prevent SQL injection attacks from reaching the ECS tasks. The solution must ensure legitimate traffic is unaffected and maintain operational efficiency.

Which solution meets these requirements?

- **A.** Configure an AWS WAF web ACL with a rule that inspects and blocks requests matching the SQL injection rules from the AWS Managed Rules. Attach the web ACL to the ALB and set the default action to allow all other traffic.
- **B.** Implement AWS WAF Bot Control to identify and block automated bots sending malicious requests. Attach the managed rule group to the ALB's web ACL and allow all other traffic.
- **C.** Create an AWS WAF web ACL with a rate-based rule to block IP addresses exceeding a threshold of requests per minute. Associate the web ACL with the ALB to mitigate high request volumes.
- **D.** Set up an AWS Lambda function that analyzes ALB access logs for SQL injection patterns and updates an AWS WAF IP set to block offending IPs. Attach the web ACL with this rule to the ALB.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A because AWS WAF with SQL injection rules from AWS Managed Rules directly blocks malicious requests at the ALB, preventing them from reaching ECS tasks while allowing legitimate traffic. ✨
  
</details>

---

## ❓ Question 184

An enterprise needs to ensure their IoT data ingestion and storage can withstand a Region-wide outage. Their current setup uses AWS IoT Core and Amazon DynamoDB in a single Region. They want to expand to two Regions with seamless failover.

Which architecture meets these requirements?

- **A.** Deploy AWS IoT Core in both Regions with separate domain configurations. Use Amazon Route 53 weighted routing to distribute traffic. Migrate data to Amazon Aurora Global Database for cross-Region replication.
- **B.** Configure AWS IoT Core domain configurations in each Region. Set up Amazon Route 53 latency-based routing to direct traffic to the nearest IoT endpoint. Use DynamoDB global tables to synchronize data across Regions.
- **C.** Establish AWS IoT Core domain configurations in both Regions. Create an Amazon Route 53 failover routing policy with health checks monitoring each domain. Configure DynamoDB as a global table for multi-Region storage.
- **D.** Implement AWS IoT Core in two Regions with domain configurations. Use Route 53 geolocation routing for IoT endpoints. Enable DynamoDB cross-Region replication using streams and Lambda functions.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: Answer C uses Route 53 failover routing with health checks for IoT Core endpoints and DynamoDB Global Tables for cross-Region data sync, ensuring seamless failover and redundancy during a Region-wide outage. ✨
  
</details>

---

## ❓ Question 185

A company uses AWS Organizations for a multi-account setup in the AWS Cloud. The company's finance team hosts a data lake application using Amazon S3. The marketing team requires access to specific prefixes within the S3 bucket, which contains sensitive financial records. The finance team and marketing team operate in separate AWS accounts.

What should a solutions architect do to grant the marketing team access to only the required S3 prefixes while maintaining security?

- **A.** Create an SCP to allow the marketing team's AWS account access to the specified S3 prefixes. Attach the SCP to the OU containing the finance team's account.
- **B.** Create an IAM role in the finance team's account with an IAM policy restricting access to the specific S3 prefixes. Establish a trust relationship with the marketing team's account. In the marketing team's account, create an IAM role permitting assumption of the finance team's IAM role.
- **C.** Apply a bucket policy on the S3 bucket with conditions limiting access to the specific prefixes. In the marketing team's account, create an IAM role with permissions to access the S3 bucket in the finance team's account.
- **D.** Create an IAM role in the finance team's account with full S3 access. Use a permissions boundary to restrict access to the required prefixes. In the marketing team's account, create an IAM role allowing assumption of the finance team's role.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Creating an IAM role in the finance team's account with a policy restricting access to specific S3 prefixes and establishing a trust relationship ensures secure cross-account access. This method allows the marketing team to assume the role with limited permissions, maintaining security. ✨
  
</details>

---

## ❓ Question 186

A solutions architect is designing a global application that requires storing objects in Amazon S3 across two AWS Regions. Users in both regions must access the objects with minimal latency, and the data in both S3 buckets must be consistently synchronized. Which combination of steps will meet these requirements with the LEAST operational overhead? (Choose three.)

- **A.** Create an S3 Multi-Region Access Point and update the application to use it for object access
- **B.** Configure bidirectional S3 Cross-Region Replication (CRR) between the two S3 buckets
- **C.** Modify the application to write objects to both S3 buckets simultaneously
- **D.** Implement an S3 Lifecycle policy to automatically transfer objects between the buckets
- **E.** Enable S3 Versioning on both S3 buckets
- **F.** Set up S3 event notifications to trigger AWS Lambda functions for cross-bucket object replication

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ABE**
  
  > Short Explanation: The correct answers are A, B, and E. S3 Multi-Region Access Point (A) ensures low-latency access, bidirectional CRR (B) synchronizes data across regions, and S3 Versioning (E) is required for CRR. These minimize operational overhead compared to manual or Lambda-based solutions. ✨
  
</details>

---

## ❓ Question 187

A company operates an IoT solution in an on-premises environment. The solution uses MQTT for communication between IoT devices and a central server. Telemetry data is collected every 3 minutes, and device metadata is stored in a PostgreSQL database.

A custom application running on-premises executes batch jobs every hour to process and transform the telemetry and metadata into reports. These reports are accessed by users through a web application hosted on the same on-premises server. The batch jobs typically take between 100-500 seconds to complete. The web application remains operational continuously.

The company plans to migrate this solution to AWS to minimize operational overhead. Which combination of steps should they take? (Choose three.)

- **A.** Use AWS Lambda functions to establish connections with the IoT devices
- **B.** Configure IoT devices to send data to AWS IoT Core
- **C.** Store metadata in a self-managed PostgreSQL database on Amazon EC2
- **D.** Store metadata in Amazon RDS for PostgreSQL
- **E.** Utilize AWS Step Functions with Lambda tasks for report generation, storing reports in Amazon S3, and deliver them using Amazon CloudFront
- **F.** Deploy the batch jobs on an Amazon ECS cluster with Fargate tasks and use an Application Load Balancer to serve the reports

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BDE**
  
  > Short Explanation: The correct answers are B, D, and E. AWS IoT Core (B) replaces the on-premises MQTT server, reducing operational overhead. Amazon RDS for PostgreSQL (D) provides a managed database service, eliminating the need for self-managed EC2. AWS Step Functions with Lambda (E) automates batch jobs, stores reports in S3, and uses CloudFront for efficient delivery. ✨
  
</details>

---

## ❓ Question 188

A global financial services firm is migrating most applications to AWS but must retain some applications within its own data centers due to strict data sovereignty regulations and latency requirements of under 5 milliseconds. Additionally, the firm operates branch offices in remote locations with unreliable network infrastructure and needs to host certain workloads there. The company requires a consistent development environment to enable its developers to deploy applications seamlessly across on-premises, cloud, and edge locations using the same tooling and APIs. Which solution meets these requirements?

- **A.** Migrate all compliant workloads to the nearest AWS Region. Establish AWS Direct Connect between the on-premises data center and AWS. Use AWS Local Zones for latency-sensitive applications and deploy AWS Outposts in branch offices.
- **B.** Deploy AWS Snowball Edge Storage Optimized devices for applications requiring data residency or low latency. Use AWS Outposts for workloads in branch offices and migrate remaining applications to AWS Wavelength Zones.
- **C.** Install AWS Outposts for applications requiring data sovereignty or ultra-low latency. Deploy AWS Snowball Edge Compute Optimized devices to host workloads in remote branch offices with limited connectivity.
- **D.** Migrate latency-sensitive applications to AWS Wavelength. Retain data-regulated applications in the on-premises data center using AWS Outposts and deploy AWS Local Zones in branch offices.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. AWS Outposts addresses data sovereignty and low latency needs by providing AWS infrastructure on-premises, while Snowball Edge Compute Optimized devices support workloads in remote branches with unreliable networks. This setup ensures consistent AWS tooling across all environments. ✨
  
</details>

---

## ❓ Question 189

A company is enhancing an e-commerce platform hosted on Amazon ECS with DynamoDB. They've faced increased DDoS attacks and need to ensure minimal downtime during attacks cost-effectively. The setup includes a public ALB for user access.

Which two steps should they take?

- **A.** Set up CloudFront with the ALB as origin, using a custom origin header. Configure ALB to allow traffic only with that header.
- **B.** Deploy the application across multiple AWS Regions with Route 53 failover routing.
- **C.** Implement ElastiCache for DynamoDB to handle increased read traffic.
- **D.** Enable AWS Shield Advanced for DDoS protection.
- **E.** Associate an AWS WAF web ACL with the CloudFront distribution, using managed rule groups.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AE**
  
  > Short Explanation: A and E are correct. CloudFront with a custom header restricts ALB access, mitigating DDoS. AWS WAF with managed rules blocks attack patterns cost-effectively. Other options are either costly, unrelated to DDoS, or address scalability instead of attacks. ✨
  
</details>

---

## ❓ Question 190

A company hosts a web application on AWS, serving static content via an Amazon S3 bucket behind a CloudFront distribution. Dynamic content is processed by an Application Load Balancer (ALB) that routes traffic to Amazon EC2 instances in an Auto Scaling group. The domain is managed using Amazon Route 53. During peak traffic periods, users intermittently encounter HTTP 504 Gateway Timeout errors from the ALB. The company needs to immediately display a custom error page for these errors while minimizing operational overhead. Which solution meets these requirements?

- **A.** Configure a Route 53 failover routing policy with health checks on the ALB endpoint. Set up an S3 bucket hosting the custom error page as the failover target.
- **B.** Create a secondary CloudFront distribution and an S3 static website for the error page. Use Route 53 with an active-passive configuration to switch between distributions.
- **C.** Create a CloudFront origin group with the ALB as the primary origin and an S3 static website (hosting the custom error page) as the secondary origin. Enable origin failover for the distribution.
- **D.** Develop a CloudFront function to detect 504 errors from the ALB. Configure the function to redirect users to a custom error page stored in an S3 bucket.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Configuring a CloudFront origin group with ALB as the primary origin and an S3 bucket hosting the custom error page as the secondary origin enables automatic failover. This setup allows CloudFront to serve the custom error page when the ALB returns a 504 error, addressing the issue immediately with minimal overhead. ✨
  
</details>

---

## ❓ Question 191

A company is migrating a content management system (CMS) to AWS. The CMS runs as a Docker container and requires an NFS version 4.1 shared file system for user uploads. A solutions architect must design a fully managed, secure, and scalable containerized solution without infrastructure provisioning. Which solution meets these requirements?

- **A.** Deploy the CMS containers using Amazon ECS with the Fargate launch type. Configure Amazon EFS for shared storage. Specify the EFS file system ID, container mount point, and EFS access point IAM role in the ECS task definition.
- **B.** Deploy the CMS containers using Amazon ECS with the Fargate launch type. Use Amazon FSx for Windows File Server for shared storage. Reference the FSx file system ID, container mount point, and FSx authorization IAM role in the ECS task definition.
- **C.** Deploy the CMS containers using Amazon ECS with the EC2 launch type and auto scaling. Use Amazon EFS for shared storage. Mount the EFS file system on EC2 instances. Add the EFS IAM role to the EC2 instance profile.
- **D.** Deploy the CMS containers using Amazon ECS with the EC2 launch type and auto scaling. Use Amazon S3 for shared storage. Mount the S3 bucket via a third-party file gateway and reference it in the ECS task definition.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A because Amazon ECS with Fargate provides a fully managed container solution, and Amazon EFS supports NFS 4.1 for shared storage. The ECS task definition integrates EFS securely without infrastructure provisioning. ✨
  
</details>

---

## ❓ Question 192

A company hosts its application on Amazon EC2 instances within an Auto Scaling group, fronted by an Application Load Balancer (ALB). The domain api.company.com is routed to the ALB via Amazon Route 53. The company plans to deploy a new version of its application, requiring 15% of users to receive the updated version during testing. Users must consistently interact with the same version throughout the testing period. 

How should the company implement this deployment while adhering to the requirements?

- **A.** Create a second ALB and deploy the new version to EC2 instances in a new Auto Scaling group. Update the Route 53 record to use weighted routing with 15% traffic directed to the new ALB. Configure session stickiness on both ALBs.
- **B.** Create a new target group for the ALB and deploy the updated version to EC2 instances in this target group. Configure the ALB listener rule to route 15% of traffic to the new target group. Enable target group stickiness on the ALB.
- **C.** Modify the existing Auto Scaling group's launch template to include the new version. Use an instance refresh with a 15% minimum healthy percentage to gradually replace instances. Enable ALB connection draining.
- **D.** Deploy the new version to a separate Auto Scaling group and register it with the ALB. Adjust the ALB's routing algorithm to weighted least connections with 15% weight assigned to the new group. Enable session stickiness on the ALB.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Creating a new target group for the ALB and configuring listener rules with target group stickiness ensures 15% traffic routing to the new version while maintaining user consistency. This approach leverages ALB's native capabilities for traffic splitting and session stickiness. ✨
  
</details>

---

## ❓ Question 193

A large research institution uses Amazon FSx for Windows File Server to store collaborative project data. The file system is configured with HDD storage and a throughput of 8 MBps, connected to a self-managed Active Directory. Users report prolonged delays when accessing large datasets during peak hours. An analysis indicates the file system's throughput is insufficient. A solutions architect must optimize performance during a maintenance window with minimal effort.

What should the solutions architect do to meet these requirements?

- **A.** Use AWS Backup to create a backup of the file system. Restore it to a new FSx file system with SSD storage and 32 MBps throughput. Update the DNS alias after restoration and delete the original file system.
- **B.** In the Amazon FSx console, modify the file system to change the storage type to SSD and increase the throughput capacity to 32 MBps. Disconnect users during the update and reconnect afterward.
- **C.** Deploy an AWS DataSync agent on an EC2 instance. Create a task to migrate data from the existing file system to a new FSx file system with SSD storage and 32 MBps throughput. Update the DNS alias post-migration and remove the original file system.
- **D.** Enable shadow copies via PowerShell on the existing file system. Schedule a backup, restore it to a new FSx file system with SSD storage and 32 MBps throughput, then update the DNS alias and delete the original file system.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Modifying the existing FSx file system via the console to use SSD storage and higher throughput is the most efficient solution, as it avoids data migration and leverages AWS-managed updates during maintenance. ✨
  
</details>

---

## ❓ Question 194

A company hosts a data-intensive application on AWS, which uses a single Amazon S3 bucket for storing and retrieving objects. The company needs to deploy the application in two AWS Regions while ensuring consistent data access and minimizing operational complexity. Which solution meets these requirements with the LEAST operational overhead?

- **A.** Configure an Amazon CloudFront distribution with the existing S3 bucket as the origin. Deploy the application to the second Region and modify it to use CloudFront. Use S3 Transfer Acceleration to synchronize data between Regions.
- **B.** Create a new S3 bucket in the second Region. Enable bidirectional S3 Cross-Region Replication (CRR) between the original and new bucket. Configure an S3 Multi-Region Access Point referencing both buckets. Deploy the application in both Regions with the Multi-Region Access Point as the endpoint.
- **C.** Deploy the application in the second Region with a new S3 bucket. Set up unidirectional S3 Cross-Region Replication (CRR) from the original bucket to the new bucket. Modify the application to write to the original bucket and read from the nearest bucket.
- **D.** Use an S3 gateway endpoint in the second Region to access the original S3 bucket. Deploy the application in both Regions and configure it to use the gateway endpoint. Enable S3 Cross-Region Replication (CRR) for backup purposes.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. It uses S3 Multi-Region Access Point (MRAP) with bidirectional Cross-Region Replication (CRR) to ensure consistent data access across regions while minimizing operational complexity. MRAP routes requests to the nearest bucket, and CRR keeps data synchronized automatically. ✨
  
</details>

---

## ❓ Question 195

A social media analytics platform needs to migrate its real-time data processing system to AWS. The platform requires high-performance computing (HPC) capabilities and manages a dynamically updated trending topics leaderboard. An Ubuntu instance optimized for compute generation hosts a Python application for data visualization. Real-time analytics data is currently stored in an on-premises Redis instance.

The company seeks a migration strategy that maximizes application performance.

Which solution meets these requirements?

- **A.** Create an Auto Scaling group of m5.large Amazon EC2 Spot Instances behind a Network Load Balancer. Use an Amazon ElastiCache for Redis cluster to manage the trending topics leaderboard.
- **B.** Create an Auto Scaling group of c5.large Amazon EC2 Spot Instances behind a Network Load Balancer. Use an Amazon OpenSearch Service cluster to manage the trending topics leaderboard.
- **C.** Create an Auto Scaling group of c5.large Amazon EC2 On-Demand Instances behind a Network Load Balancer. Use an Amazon ElastiCache for Redis cluster to manage the trending topics leaderboard.
- **D.** Create an Auto Scaling group of m5.large Amazon EC2 On-Demand Instances behind a Network Load Balancer. Use an Amazon DynamoDB table to manage the trending topics leaderboard.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: Option C uses compute-optimized EC2 instances (c5.large) for HPC, On-Demand Instances for consistent performance, and ElastiCache for Redis to replace the on-premises Redis, ensuring real-time leaderboard efficiency. ✨
  
</details>

---

## ❓ Question 196

A solutions architect is designing an event registration system to accept submissions from users on their mobile devices. Submissions will occur daily, with peak traffic expected during promotional periods and event deadlines. The data must be stored in a format that allows event organizers to generate monthly analytics. The infrastructure must be highly available and scale to handle unpredictable traffic spikes while minimizing operational overhead. Which combination of steps meets these requirements? (Choose two.)

- **A.** Deploy the application to Amazon EC2 On-Demand Instances with load balancing across multiple Availability Zones. Use dynamic Amazon EC2 Auto Scaling based on CPU utilization to handle traffic spikes.
- **B.** Deploy the application in a container using Amazon Elastic Container Service (Amazon ECS) with load balancing across multiple Availability Zones. Use scheduled Service Auto Scaling to add capacity before anticipated traffic peaks.
- **C.** Deploy the application front end to an Amazon S3 bucket served by Amazon CloudFront. Deploy the application backend using Amazon API Gateway with an AWS Lambda proxy integration.
- **D.** Store the event registration data in Amazon Redshift. Use Amazon QuickSight to generate analytics reports using Amazon Redshift as the data source.
- **E.** Store the event registration data in Amazon S3. Use Amazon Athena and Amazon QuickSight to generate analytics reports using Amazon S3 as the data source.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BE**
  
  > Short Explanation: B and E are correct. B uses Amazon ECS with scheduled scaling to handle anticipated traffic peaks, ensuring high availability. E leverages Amazon S3, Athena, and QuickSight for serverless, scalable analytics with minimal overhead. ✨
  
</details>

---

## ❓ Question 197

A company is storing confidential documents in an Amazon S3 bucket. The company must log all access requests to objects in the S3 bucket and retain the logs for 7 years. The security team must also receive an email notification whenever there is an unauthorized access attempt detected.

Which combination of steps will meet these requirements MOST cost-effectively? (Choose three.)

- **A.** Configure AWS CloudTrail to log S3 data events.
- **B.** Configure S3 server access logging for the S3 bucket.
- **C.** Configure Amazon S3 to send object access events to Amazon Simple Email Service (Amazon SES).
- **D.** Configure Amazon S3 to send object access events to an Amazon EventBridge event bus that publishes to an Amazon Simple Notification Service (Amazon SNS) topic.
- **E.** Configure Amazon S3 to send the logs to Amazon Timestream with data storage tiering.
- **F.** Configure a new S3 bucket to store the logs with an S3 Lifecycle policy.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ADF**
  
  > Short Explanation: The correct answers are A, D, and F. Configure AWS CloudTrail to log S3 data events for comprehensive access tracking, use Amazon EventBridge with SNS for notifications, and implement an S3 Lifecycle policy for cost-effective log retention over 7 years. ✨
  
</details>

---

## ❓ Question 198

A company operates a hybrid infrastructure with on-premises servers and Amazon EC2 instances deployed across three VPCs, each in a distinct AWS Region. The company has an AWS Direct Connect connection to the nearest Region. The on-premises servers must communicate with EC2 instances in all three VPCs and access AWS public services, while minimizing costs. Which two actions should be taken? (Choose two.)

- **A.** Create a Direct Connect gateway in the connected Region, attach the Direct Connect connection, and use the gateway to link the VPCs in the other two Regions.
- **B.** Deploy additional Direct Connect connections from the on-premises data center to the other two Regions.
- **C.** Configure a private VIF and establish AWS Site-to-Site VPN connections over it to the VPCs in the other two Regions.
- **D.** Create a public VIF to enable access to AWS public services through the existing Direct Connect connection.
- **E.** Use AWS Transit Gateway to interconnect all VPCs and connect the Transit Gateway to the Direct Connect connection via a private VIF.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: {A,D}**
  
  > Short Explanation: The correct answers are A and D. Using a Direct Connect gateway (A) allows communication with EC2 instances across all VPCs via the existing Direct Connect connection, avoiding additional costs. A public VIF (D) enables cost-effective access to AWS public services through Direct Connect. ✨
  
</details>

---

## ❓ Question 199

A company is using AWS Organizations to manage multiple AWS accounts. A solutions architect needs to enforce a baseline security policy against the Open Web Application Security Project (OWASP) Top 10 web application vulnerabilities across all accounts. The architect plans to use AWS WAF for all existing and new Amazon CloudFront distributions within the organization. Which combination of steps should the solutions architect take to ensure the baseline protection? (Choose three.)

- **A.** Enable AWS Config in all accounts
- **B.** Enable Amazon Inspector in all accounts
- **C.** Enable all features for the organization
- **D.** Use AWS Firewall Manager to deploy AWS WAF rules in all accounts for all CloudFront distributions
- **E.** Use AWS Shield Advanced to manage AWS WAF rules for all CloudFront distributions
- **F.** Use AWS Security Hub to aggregate compliance findings for AWS WAF rules

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ACD**
  
  > Short Explanation: The correct answers are A, C, and D. AWS Config ensures compliance monitoring, enabling all AWS Organizations features allows Firewall Manager integration, and Firewall Manager centrally deploys AWS WAF rules across accounts. ✨
  
</details>

---

## ❓ Question 200

A solutions architect has configured a SAML 2.0 federated identity solution using their organization's on-premises identity provider (IdP) to enable user access to AWS services. Initial testing confirms federated users can authenticate via the web portal, but they are unable to access the AWS Management Console. What should the solutions architect validate to troubleshoot this issue? (Choose three.)

- **A.** The IAM roles assigned to federated users have inline policies granting the necessary permissions.
- **B.** The trust policy of the IAM roles designates the SAML provider as the trusted entity.
- **C.** The IdP is configured to invoke the AWS STS AssumeRoleWithSAML API with the correct SAML assertion, IAM role ARN, and SAML provider ARN.
- **D.** The network ACLs for the on-premises IdP permit inbound traffic from AWS VPC CIDR ranges.
- **E.** The SAML assertions from the IdP accurately map user groups to the corresponding IAM roles.
- **F.** The IAM users are granted permissions to assume roles through SAML federation.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BCE**
  
  > Short Explanation: The correct answers are B, C, and E. The SAML trust policy must designate the IdP as trusted, the IdP must correctly invoke AssumeRoleWithSAML, and SAML assertions must map user groups to IAM roles. ✨
  
</details>