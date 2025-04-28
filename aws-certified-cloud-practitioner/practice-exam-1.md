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

## ❓ Question 1

A company needs to design a hybrid DNS solution using an Amazon Route 53 private hosted zone for the domain cloud.newdomain.com to support resources across multiple VPCs. The solution must meet the following requirements:

- On-premises systems must resolve and connect to cloud.newdomain.com.
- All VPCs must resolve cloud.newdomain.com.

The company uses AWS Direct Connect and AWS Transit Gateway to link its on-premises network to AWS.

Which architecture ensures the HIGHEST performance while fulfilling these requirements?

- **A.** Associate the private hosted zone with all VPCs. Deploy a Route 53 inbound resolver in the shared services VPC. Connect all VPCs to the transit gateway and configure on-premises DNS to forward cloud.newdomain.com requests to the inbound resolver.
- **B.** Associate the private hosted zone with all VPCs. Set up an EC2-based conditional forwarder in the shared services VPC. Attach all VPCs to the transit gateway and direct on-premises DNS to forward cloud.newdomain.com queries to the conditional forwarder.
- **C.** Associate the private hosted zone with the shared services VPC. Create a Route 53 outbound resolver in the shared services VPC. Link all VPCs to the transit gateway and configure on-premises DNS to forward cloud.newdomain.com requests to the outbound resolver.
- **D.** Associate the private hosted zone with the shared services VPC. Deploy a Route 53 inbound resolver in the shared services VPC. Connect the shared services VPC to the transit gateway and set up on-premises DNS to forward cloud.newdomain.com queries to the inbound resolver.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A is correct because it associates the private hosted zone with all VPCs and uses a Route 53 inbound resolver for on-premises DNS forwarding, ensuring all VPCs resolve the domain and on-premises systems can connect via the transit gateway. ✨
  
</details>

---

## ❓ Question 2

A company is providing traffic data through a REST API hosted on Amazon API Gateway, integrated with AWS Lambda functions for each operation. They use Amazon Route 53 for DNS with a record for traffic.example.com and store data in Amazon DynamoDB. The company needs to enable cross-Region failover for the API. Which solution meets these requirements?

- **A.** Deploy Lambda functions in a new Region. Update API Gateway to use an edge-optimized endpoint with Lambda functions from both Regions. Convert DynamoDB tables to global tables.
- **B.** Deploy a new API Gateway and Lambda functions in another Region. Configure Route 53 with a multivalue answer record pointing to both APIs. Enable health checks. Convert DynamoDB to global tables.
- **C.** Deploy a new API Gateway and Lambda functions in another Region. Update Route 53 with a failover routing policy and enable health monitoring. Convert DynamoDB tables to global tables.
- **D.** Deploy a new API Gateway in another Region. Use global Lambda functions. Configure Route 53 with a multivalue answer record. Enable health checks. Convert DynamoDB to global tables.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C because it deploys API Gateway and Lambda in another Region, uses Route 53 failover routing with health checks, and converts DynamoDB to global tables, ensuring cross-Region failover with data replication. ✨
  
</details>

---

## ❓ Question 3

A company uses AWS Organizations with a single OU named Main to manage all accounts. Deny list SCPs at the organization root block access to Amazon S3. A newly acquired business unit’s account, placed in the Main OU, cannot update existing Amazon S3 bucket policies to comply with company standards.

Which solution enables the administrators to make the necessary changes while maintaining existing policies without long-term maintenance overhead?

- **A.** Remove the root SCPs blocking Amazon S3. Use AWS Service Catalog to distribute standardized S3 bucket policies across the organization, including the new account.
- **B.** Create a temporary OU named TempAccess. Apply an SCP to TempAccess allowing Amazon S3 actions. Move the new account to the Main OU after completing the policy updates.
- **C.** Convert the root SCPs from deny lists to allow lists, permitting only required services. Temporarily add an SCP at the root allowing Amazon S3 actions for the new account.
- **D.** Create a temporary OU named TempAccess. Move the root SCP to the Main OU. Apply an SCP to TempAccess allowing Amazon S3 actions. Move the new account to TempAccess, then back to Main after updates.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The solution involves creating a temporary OU with an SCP allowing S3 access, moving the account there, and then back to Main after updates. This ensures temporary access without altering root policies. ✨
  
</details>

---

## ❓ Question 4

A company is migrating a stateful three-tier web application from on-premises to AWS. The application layer uses EC2 instances with Auto Scaling, and the database is Amazon Aurora PostgreSQL. They need to ensure both tiers scale effectively while maintaining session persistence.

Which solution provides scalable infrastructure with consistent user experience?

- **A.** Enable Aurora Auto Scaling for read replicas. Use an Application Load Balancer with least outstanding requests routing and sticky sessions.
- **B.** Configure Aurora to scale the writer instance. Use a Network Load Balancer with round robin routing and sticky sessions.
- **C.** Enable Aurora Auto Scaling for read replicas. Use a Network Load Balancer with least connections routing and sticky sessions enabled.
- **D.** Enable Aurora Auto Scaling for read replicas. Use an Application Load Balancer with round robin routing and sticky sessions enabled.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: Answer D is correct because it uses Aurora Auto Scaling for read replicas to handle database scaling and an Application Load Balancer (ALB) with sticky sessions to ensure session persistence. ALB's layer 7 routing and round robin distribute traffic effectively while maintaining user sessions. ✨
  
</details>

---

## ❓ Question 5

A company operates a content delivery platform hosted on-premises, serving various client devices including legacy systems that fail when encountering specific HTTP headers in responses. These legacy devices are identified by their User-Agent headers. The company uses a middleware component to strip these headers from responses directed to such devices. They aim to migrate the platform to AWS using serverless technologies while continuing support for legacy devices. The application backend has been transitioned to AWS Lambda functions.

Which solution fulfills these requirements?

- **A.** Set up an Amazon CloudFront distribution for the content service. Create an Amazon API Gateway REST API. Configure CloudFront to route requests to the API Gateway. Set up the API Gateway to trigger the appropriate Lambda function for each request. Implement a CloudFront function to remove the problematic headers based on the User-Agent header.
- **B.** Deploy an Amazon API Gateway HTTP API for the content service. Configure the API Gateway to invoke the corresponding Lambda functions. Develop a response mapping template in API Gateway to eliminate the problematic headers conditioned on the User-Agent header. Associate this template with the HTTP API.
- **C.** Create an Amazon CloudFront distribution pointing to an Application Load Balancer (ALB). Configure the ALB to route to the Lambda functions. Use a Lambda@Edge function attached to the CloudFront distribution to strip the headers from responses when the User-Agent matches legacy devices.
- **D.** Utilize Amazon API Gateway REST API for the content service, integrating it with the Lambda functions. Adjust the integration responses in API Gateway to remove the problematic headers dynamically by inspecting the User-Agent header from incoming requests.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. CloudFront Functions can efficiently strip problematic headers at the edge based on User-Agent, ensuring legacy device compatibility while using serverless AWS services. ✨
  
</details>

---

## ❓ Question 6

A healthcare organization needs to grant an external research partner access to clinical trial data stored in an Amazon S3 bucket under Account M. The research partner's AWS account (Account N) has an IAM user named Researcher_User that requires access to the data. Which combination of steps should the organizations take to enable Researcher_User to access the S3 bucket? (Choose two.)

- **A.** Enable cross-origin resource sharing (CORS) for the S3 bucket in Account M.
- **B.** In Account M, configure the S3 bucket policy as follows:\n\n```json\n{\n  \"Effect\": \"Allow\",\n  \"Action\": [\n    \"s3:GetObject\",\n    \"s3:ListBucket\"\n  ],\n  \"Resource\": \"arn:aws:s3:::AccountMBucketName/*\"\n}\n```
- **C.** In Account M, configure the S3 bucket policy as follows:\n\n```json\n{\n  \"Effect\": \"Allow\",\n  \"Principal\": {\n    \"AWS\": \"arn:aws:iam::AccountN:user/Researcher_User\"\n  },\n  \"Action\": [\n    \"s3:GetObject\",\n    \"s3:ListBucket\"\n  ],\n  \"Resource\": \"arn:aws:s3:::AccountMBucketName/*\"\n}\n```
- **D.** In Account N, assign the following permissions to Researcher_User:\n\n```json\n{\n  \"Effect\": \"Allow\",\n  \"Action\": [\n    \"s3:GetObject\",\n    \"s3:ListBucket\"\n  ],\n  \"Resource\": \"arn:aws:s3:::AccountMBucketName/*\"\n}\n```
- **E.** In Account N, assign the following permissions to Researcher_User:\n\n```json\n{\n  \"Effect\": \"Allow\",\n  \"Principal\": {\n    \"AWS\": \"arn:aws:iam::AccountN:user/Researcher_User\"\n  },\n  \"Action\": [\n    \"s3:GetObject\",\n    \"s3:ListBucket\"\n  ],\n  \"Resource\": \"arn:aws:s3:::AccountMBucketName/*\"\n}\n```

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CD**
  
  > Short Explanation: The correct answers are C and D. To enable cross-account access, Account M's S3 bucket policy must explicitly allow the external user (C), and Account N must grant the user permissions to access the bucket (D). ✨
  
</details>

---

## ❓ Question 7

A company is migrating a monolithic web application to a microservices architecture using containers. They require separate environments for production and staging, each handling variable loads with known minimum and maximum demands. The solution must use a serverless approach to minimize management overhead while ensuring cost-effectiveness. Which design meets these requirements?

- **A.** Deploy containers as AWS Lambda functions with configured concurrency limits. Use Amazon API Gateway with separate stages for each environment.
- **B.** Use Amazon ECR for container images. Set up two Amazon ECS clusters with Fargate launch type, configured auto-scaling, and separate Application Load Balancers for each environment.
- **C.** Utilize Amazon EKS with Fargate profiles for orchestration. Deploy containers from ECR, configure auto-scaling, and use separate Network Load Balancers for each environment.
- **D.** Deploy using AWS Elastic Beanstalk with separate environments. Configure auto-scaling groups and Application Load Balancers for each environment.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Amazon ECS with Fargate provides a serverless approach, auto-scaling for variable loads, and separate ALBs for production/staging environments, ensuring minimal management and cost-effectiveness. ✨
  
</details>

---

## ❓ Question 8

A company operates a multi-tier web application on Amazon EC2 instances behind an Application Load Balancer (ALB) in an Auto Scaling group. The infrastructure is replicated in a backup AWS Region, where the Auto Scaling group's minimum and maximum capacity are set to zero. The application uses an Amazon RDS Multi-AZ DB instance with a read replica in the backup Region. End users access the application via an Amazon Route 53 record pointing to the primary Region. The company needs to reduce RTO to less than 15 minutes by enabling automated failover to the backup Region without the cost of an active-active setup. What should a solutions architect recommend?

- **A.** Reconfigure Route 53 with a weighted routing policy distributing traffic between both ALBs. Create a Lambda function in the backup Region to promote the read replica and update the Auto Scaling group's capacity. Set up a CloudWatch alarm based on the HealthyHostCount metric for the primary ALB to trigger the Lambda function.
- **B.** Create a Lambda function in the backup Region to promote the read replica and adjust the Auto Scaling group's capacity. Configure Route 53 with a health check monitoring the primary ALB and a failover routing policy. Link the health check to an SNS topic that invokes the Lambda function upon failure.
- **C.** Set the backup Auto Scaling group's capacity to match the primary Region. Use Route 53 geolocation routing to direct traffic to the nearest ALB. Replace the read replica with a new RDS instance configured for cross-region replication using AWS DMS and S3 for data transfer.
- **D.** Deploy an AWS Global Accelerator endpoint with both ALBs as targets. Create a Lambda function to promote the read replica and modify the Auto Scaling group. Use a CloudWatch alarm based on the UnHealthyHostCount metric to trigger the Lambda function.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer configures Route 53 with a health check and failover routing policy to detect primary ALB failure, triggers a Lambda function via SNS to promote the RDS read replica and scale up the backup Auto Scaling group, enabling automated failover without active-active costs. ✨
  
</details>

---

## ❓ Question 9

A company is hosting a crucial application on a single Amazon EC2 instance. The application utilizes an Amazon ElastiCache for Redis single-node cluster for session storage and an Amazon RDS for MySQL DB instance as the relational database. The application requires all components to be healthy and active to function properly.

A solutions architect needs to redesign the architecture to ensure automatic recovery from failures with minimal downtime.

Which combination of steps should the architect take? (Choose three.)

- **A.** Deploy an Application Load Balancer to distribute traffic across multiple EC2 instances placed in an Auto Scaling group with a minimum size of two.
- **B.** Configure a Network Load Balancer to direct traffic to EC2 instances and set up an Auto Scaling group with instance health checks.
- **C.** Modify the RDS MySQL instance to enable a read replica in a different Availability Zone and configure automatic promotion during failures.
- **D.** Convert the RDS MySQL instance to a Multi-AZ deployment to enable automatic failover to a standby replica.
- **E.** Create a replication group for the ElastiCache Redis cluster with automatic failover enabled and configure it to span multiple Availability Zones.
- **F.** Set up an ElastiCache Redis cluster with an Auto Scaling group to automatically adjust the number of nodes based on demand.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ADE**
  
  > Short Explanation: The correct answers are A, D, and E. These steps ensure high availability and automatic failover for all components: EC2 (via ALB and Auto Scaling), RDS (Multi-AZ), and ElastiCache (replication group with multi-AZ). ✨
  
</details>

---

## ❓ Question 10

A retail company operates its ecommerce application on AWS. The application runs on Amazon EC2 instances behind an Application Load Balancer (ALB), with Amazon RDS as the database backend. Amazon CloudFront is configured with the ALB as its origin, caching static content. Amazon Route 53 manages DNS. After an update, the ALB intermittently returns a 504 status code (Gateway Timeout) due to backend latency. Users see the default ALB error page, but reloading the page resolves the issue temporarily. The solutions architect must implement a custom error page with minimal operational overhead.

- **A.** Create an Amazon S3 bucket to host a static error page. Upload the custom error page to S3.
- **B.** Configure a CloudWatch alarm for the ALB's HTTPCode_Target_Timeout_Count metric. Use a Lambda function to redirect traffic to a backup server.
- **C.** Modify Route 53 health checks to route traffic to an S3-hosted error page when health checks fail.
- **D.** Use Lambda@Edge to intercept 504 errors and redirect requests to a static error page hosted on S3.
- **E.** Configure CloudFront to return a custom error page for HTTP 504 status codes, pointing to the S3-hosted error page.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AE**
  
  > Short Explanation: The correct answers are A and E. Hosting a custom error page on S3 (A) and configuring CloudFront to return it for 504 errors (E) provides a low-overhead solution. Other options involve unnecessary complexity or slower health-check-based routing. ✨
  
</details>

---

## ❓ Question 11

A company uses AWS Organizations to manage multiple accounts and wants to share a centralized VPC hosted in a network account managed by the network team. The network team must retain full control over the VPC configuration, while other accounts should only be able to deploy resources into the shared subnets without modifying the network settings. Which combination of steps should be taken to meet these requirements? (Choose two.)

- **A.** Deploy a transit gateway in the network account and attach all VPCs from individual accounts to it.
- **B.** Enable resource sharing through AWS Organizations in the management account.
- **C.** Create VPCs in each account with identical CIDR ranges and subnets as the central VPC. Establish VPC peering connections between each account's VPC and the central VPC.
- **D.** Use AWS Resource Access Manager in the network account to create a resource share. Specify the relevant AWS Organizations OU and associate the subnets to be shared.
- **E.** Use AWS Resource Access Manager in the network account to create a resource share. Specify the relevant AWS Organizations OU and associate route tables instead of subnets.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BD**
  
  > Short Explanation: The correct answers are B and D. Enabling resource sharing via AWS Organizations (B) allows centralized resource management. Using AWS Resource Access Manager (RAM) to share subnets (D) enables other accounts to deploy resources without modifying network settings, ensuring the network team retains control. ✨
  
</details>

---

## ❓ Question 12

A company needs to integrate a third-party SaaS solution hosted on AWS within the third-party's VPC. The company's security policies mandate that all communication must occur over private AWS networks without internet exposure. Additionally, no resources in the company's VPC can be accessible from outside the VPC, and all permissions must follow the principle of least privilege.

Which solution meets these requirements?

- **A.** Create an AWS PrivateLink interface VPC endpoint in the company's VPC. Connect this endpoint to the third-party SaaS provider's endpoint service. Configure a security group to restrict access to the endpoint and associate it with the endpoint.
- **B.** Establish an AWS Transit Gateway to connect the company's VPC and the third-party SaaS provider's VPC. Use VPN attachments for encryption and update route tables to enable communication between the VPCs.
- **C.** Deploy an AWS Direct Connect connection with a private virtual interface (VIF) to link the company's VPC to the third-party SaaS provider's VPC. Use BGP routing to manage traffic paths.
- **D.** Set up a VPC peering connection between the company's VPC and the third-party SaaS provider's VPC. Configure route tables to allow bidirectional traffic and apply network ACLs to restrict access.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: AWS PrivateLink (Option A) ensures private communication between the company's VPC and the third-party SaaS provider's VPC without internet exposure. It uses interface VPC endpoints with security groups to enforce least privilege, preventing external access to the company's resources. ✨
  
</details>

---

## ❓ Question 13

A company operates a hybrid environment with on-premises servers and Amazon EC2 instances. They need a unified patch management strategy that ensures compliance across all systems and provides a consolidated view of patch status. Which solution should a solutions architect recommend to meet these requirements?

- **A.** Use AWS Systems Manager Patch Manager to handle patching for both on-premises servers and EC2 instances. Generate compliance reports directly from Systems Manager.
- **B.** Deploy AWS OpsWorks to manage patches across all servers and instances. Use AWS CloudTrail logs integrated with Amazon Athena to generate compliance reports.
- **C.** Configure AWS Config to enforce patch compliance rules across on-premises servers and EC2 instances. Use AWS Lambda to aggregate patch status data into Amazon S3 for reporting.
- **D.** Utilize AWS CloudFormation to automate patching workflows for all servers. Use Amazon CloudWatch dashboards to visualize patch compliance metrics.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: AWS Systems Manager Patch Manager (Option A) is the correct choice because it supports hybrid environments, automates patching for both on-premises servers and EC2 instances, and provides built-in compliance reporting for a unified view. ✨
  
</details>

---

## ❓ Question 14

A company operates an application on Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer. The instances scale in and out frequently due to variable demand. Logs are uploaded to an Amazon S3 bucket every 15 minutes, but the security team identifies missing logs from terminated instances. Which solution ensures all logs are copied to S3 before instance termination?

- **A.** Create a script to copy logs to S3 and store it on each EC2 instance. Configure an Auto Scaling lifecycle hook with an Amazon EventBridge rule to detect termination events. Trigger an AWS Lambda function on the autoscaling:EC2_INSTANCE_TERMINATING transition to send ABANDON, execute the script, and terminate the instance using the AWS SDK.
- **B.** Create an AWS Systems Manager document with a log-copy script. Configure an Auto Scaling lifecycle hook that publishes notifications to an Amazon SNS topic. Invoke an AWS Lambda function via the SNS topic to execute the Systems Manager document using SendCommand, then send CONTINUE to the Auto Scaling group to terminate the instance.
- **C.** Increase log upload frequency to every 5 minutes. Add a script to the EC2 instance user data to copy logs. Create an Amazon EventBridge rule to trigger an AWS Lambda function on instance termination, which runs the user-data script via the AWS CLI before terminating the instance.
- **D.** Develop an AWS Systems Manager document for log copying. Create an Auto Scaling lifecycle hook integrated with Amazon EventBridge to invoke an AWS Lambda function on termination events. The Lambda function executes the document, sends ABANDON to delay termination, and terminates the instance via the AWS SDK after the upload.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. It uses Auto Scaling lifecycle hooks with Systems Manager to execute a log-copy script reliably before instance termination. Other options fail to ensure logs are uploaded due to reliance on instance storage, delayed uploads, or improper termination handling. ✨
  
</details>

---

## ❓ Question 15

A company uses multiple AWS accounts. The DNS records for internal services are stored in a private hosted zone for Amazon Route 53 in Account X. Applications running in a VPC in Account Y cannot resolve the backend.example.com CNAME record pointing to an Amazon ElastiCache endpoint. The solutions architect verified that the record set was correctly created in Route 53.

Which combination of steps should the solutions architect take to resolve the resolution failure? (Choose two.)

- **A.** Migrate the ElastiCache cluster to the VPC in Account Y. Create a new record set for the cluster's endpoint in the existing private hosted zone.
- **B.** Use a bastion host to access the application instances. Update the /etc/hosts file with the ElastiCache endpoint IP address.
- **C.** Create an authorization in Account X to associate the private hosted zone with the VPC in Account Y.
- **D.** Create a new private hosted zone for example.com in Account Y. Configure Route 53 Resolver inbound endpoints for cross-account DNS queries.
- **E.** Associate the VPC in Account Y with the private hosted zone in Account X. Remove the authorization record in Account X after association.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CE**
  
  > Short Explanation: The correct answers are C and E. To resolve cross-account DNS resolution, Account X must authorize the VPC in Account Y to associate with its private hosted zone (C). After association, the authorization can be safely removed (E). ✨
  
</details>

---

## ❓ Question 16

A company uses Amazon EC2 instances deployed behind an Application Load Balancer (ALB) in an Auto Scaling group to host a photo-sharing platform. All user-uploaded images are stored on an Amazon EFS volume. After introducing a feature allowing high-resolution image uploads, the platform experiences 15 times more traffic during peak hours, resulting in slow page loads and image rendering failures for users.

Which solution is the MOST cost-efficient and scalable to resolve these performance issues?

- **A.** Increase the Amazon EFS provisioned throughput to handle higher I/O demands.
- **B.** Modify the application to store images on instance store volumes. Use lifecycle policies to back up images to Amazon S3 periodically.
- **C.** Create an Amazon CloudFront distribution linked to an S3 bucket, and migrate all images from EFS to Amazon S3.
- **D.** Configure an Amazon CloudFront distribution to cache all website content, directing traffic through the ALB.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Migrating images to Amazon S3 and using CloudFront leverages S3's scalability and cost-efficiency for static content, while CloudFront's CDN reduces latency and offloads traffic from the backend, resolving performance issues during peak traffic. ✨
  
</details>

---

## ❓ Question 17

A company uses a single AWS Direct Connect connection with a private virtual interface to link their on-premises network to a VPC in one AWS Region. They need to add a redundant Direct Connect connection in the same Region while ensuring future connectivity to other Regions through the same pair of connections. The solution must minimize reconfiguration as the company expands.

Which solution meets these requirements?

- **A.** Create a second Direct Connect connection. Provision a Direct Connect gateway, attach both connections' private virtual interfaces to the gateway, and associate the gateway with the VPC. This setup allows future expansion to other Regions via the same gateway.
- **B.** Retain the existing private virtual interface. Establish a second Direct Connect connection and attach a new private virtual interface directly to the same VPC. This provides redundancy but does not support multi-Region connectivity.
- **C.** Replace the existing private virtual interface with a public virtual interface. Create a second Direct Connect connection with a public virtual interface to access AWS public services across Regions.
- **D.** Deploy a transit gateway. Delete the existing private virtual interface, create a second Direct Connect connection, attach both connections to the transit gateway, and associate the transit gateway with the VPC.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A uses a Direct Connect gateway to attach both connections and associate with the VPC, enabling redundancy and future multi-Region expansion without reconfiguration. ✨
  
</details>

---

## ❓ Question 18

A company operates a photo-sharing platform where users upload images. The images are stored on Amazon EBS volumes and analyzed by a third-party image recognition tool for tagging. The frontend is hosted on Amazon EC2 instances in an Auto Scaling group, and another set of EC2 instances processes an Amazon SQS queue for image analysis. The company wants to minimize operational overhead by using AWS managed services and eliminate third-party dependencies.

Which solution meets these requirements?

- **A.** Use Amazon ECS containers for the frontend and Spot instances for the Auto Scaling group that processes the SQS queue. Replace the third-party tool with Amazon Rekognition for image tagging.
- **B.** Store the uploaded images in Amazon EFS and mount the file system to the EC2 instances for the frontend. Process the SQS queue with an AWS Lambda function that calls the Amazon Rekognition API for image tagging.
- **C.** Host the frontend in Amazon S3. Store the uploaded images in Amazon S3. Use S3 event notifications to publish events to the SQS queue. Process the SQS queue with an AWS Lambda function that calls the Amazon Rekognition API for image tagging.
- **D.** Use AWS Elastic Beanstalk to launch EC2 instances in an Auto Scaling group for the frontend and launch a worker environment to process the SQS queue. Replace the third-party tool with Amazon Rekognition for image tagging.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer replaces EC2 instances with serverless AWS services (S3, Lambda, Rekognition) to minimize operational overhead and eliminate third-party dependencies. ✨
  
</details>

---

## ❓ Question 19

A company operates a serverless application using Amazon CloudFront, Amazon API Gateway, and AWS Lambda functions. The current deployment process involves manually creating a new Lambda version and executing CLI scripts to update it. If errors occur, another CLI script reverts to the previous version. The company wants to accelerate deployment times for Lambda function updates and improve error detection and rollback efficiency. How should they achieve this?

- **A.** Deploy AWS CloudFormation templates with separate stacks for CloudFront, API Gateway, and Lambda. Use change sets to update Lambda versions and roll back via stack updates if errors are detected.
- **B.** Implement AWS SAM with AWS CodeDeploy to automate Lambda deployments, shift traffic incrementally, and use pre/post-traffic test functions. Automatically roll back if CloudWatch alarms activate during deployment.
- **C.** Develop a consolidated CLI script that deploys the new Lambda version, runs automated tests post-deployment, and reverts to the prior version if errors are identified.
- **D.** Create a new API Gateway endpoint linked to the updated Lambda version using CloudFormation. Update the CloudFront origin to this endpoint and revert the origin if errors arise.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. AWS SAM with CodeDeploy automates Lambda deployments, enables incremental traffic shifting, and uses pre/post-traffic tests for error detection. It automatically rolls back if CloudWatch alarms trigger, improving deployment speed and rollback efficiency. ✨
  
</details>

---

## ❓ Question 20

A company needs to securely store backups of legacy financial records and provide access to employees via the corporate intranet. Employees connect through a client VPN linked to a VPC. The data must remain private and not exposed to the public internet. The backups are duplicates of physical records and will be accessed rarely. Retrieval speed and high availability are not critical requirements.

Which solution fulfills these requirements at the LOWEST cost?

- **A.** Create an Amazon S3 bucket configured with the S3 One Zone-Infrequent Access (S3 One Zone-IA) storage class as default. Enable S3 website hosting. Establish an S3 Gateway endpoint and restrict bucket access exclusively to the endpoint.
- **B.** Deploy an Amazon EC2 instance hosting a web server with an Amazon EFS file system using the EFS One Zone-Infrequent Access (EFS One Zone-IA) storage class. Configure security groups to permit access only from the VPC.
- **C.** Launch an Amazon EC2 instance running a web server with an Amazon EBS volume using the Cold HDD (sc1) storage class. Restrict instance access via security groups to private network traffic.
- **D.** Configure an Amazon S3 bucket with the S3 Glacier Deep Archive storage class as default. Enable website hosting and create an S3 interface endpoint. Restrict bucket access to the endpoint only.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Option A uses S3 One Zone-IA, which is cost-effective for rarely accessed data. A Gateway endpoint ensures private VPC access without public exposure. Other options involve higher costs (EC2/EFS/EBS) or incompatible storage (Glacier Deep Archive). ✨
  
</details>

---

## ❓ Question 21

A company uses an on-premises Active Directory service for user authentication and wants to extend this authentication to their AWS accounts managed under AWS Organizations. A Site-to-Site VPN is already established between the on-premises environment and all AWS accounts. The company's security policy mandates centralized identity management and conditional access to AWS accounts based on user attributes and roles. Which solution meets these requirements?

- **A.** Configure AWS IAM Identity Center (AWS Single Sign-On) to integrate with Active Directory via SAML 2.0. Enable automatic user provisioning using SCIM v2.0. Implement attribute-based access controls (ABACs) to manage permissions across AWS accounts.
- **B.** Set up AWS IAM Identity Center using its built-in identity source. Enable SCIM v2.0 for provisioning. Assign access to AWS accounts through IAM Identity Center permission sets based on predefined roles.
- **C.** In a designated AWS account, configure IAM with a SAML 2.0 identity provider linked to Active Directory. Create IAM users mapped to federated identities and assign permissions aligned with Active Directory groups. Use cross-account IAM roles for access to other accounts.
- **D.** In a primary AWS account, establish an OpenID Connect (OIDC) identity provider for Active Directory integration. Provision IAM roles granting access to federated users based on Active Directory groups. Utilize cross-account IAM roles for inter-account access.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A is correct because AWS IAM Identity Center integrates with on-premises Active Directory via SAML 2.0, supports SCIM for automated user provisioning, and enables attribute-based access control (ABAC) to meet centralized identity management and conditional access requirements. ✨
  
</details>

---

## ❓ Question 22

A social media platform uses Amazon API Gateway, AWS Lambda, and Amazon DynamoDB for its backend services. Users have reported intermittent errors during POST requests, especially during peak hours. Investigation reveals that a few clients with high traffic are responsible for the majority of the errors. The platform's operations team notes that the errors are directly shown to end-users, leading to a poor user experience. The platform can tolerate occasional retries but needs to prevent user-facing errors.

What should the solutions architect do to mitigate this issue?

- **A.** Implement retry logic with jitter and exponential backoff in the client SDK, ensuring errors are logged but not shown to users.
- **B.** Configure API throttling using a usage plan in API Gateway and update clients to handle 429 HTTP status codes gracefully.
- **C.** Enable DynamoDB auto-scaling to adjust capacity based on the traffic load and implement a backoff strategy in the Lambda functions.
- **D.** Set up reserved concurrency for the Lambda functions to ensure consistent performance during traffic spikes.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B because configuring API throttling via usage plans in API Gateway limits excessive requests from high-traffic clients, and handling 429 errors gracefully ensures users don't see errors. This targets the root cause of intermittent errors during peak hours. ✨
  
</details>

---

## ❓ Question 23

A company operates a machine learning training workload on AWS using hundreds of Amazon EC2 instances. The training data is stored on a shared file system hosted on multiple EC2 instances, totaling 150 TB. The training job runs monthly, processes a subset of the data, and completes in 72 hours. The compute instances are managed by an Auto Scaling group, while the storage instances run continuously. All resources are in the same AWS Region.

The solutions architect must reduce costs by replacing the shared file system. The solution must provide high-performance access to the required data during the 72-hour training job.

Which solution will achieve the GREATEST cost reduction while meeting the requirements?

- **A.** Migrate the data to an Amazon S3 bucket using S3 Intelligent-Tiering. Before each job, create an Amazon FSx for Lustre file system with lazy loading from S3. Use the file system during the job and delete it afterward.
- **B.** Migrate the data to a large Amazon EBS volume with Multi-Attach. Attach the volume to compute instances via the Auto Scaling launch template. Use the volume during the job and detach it afterward.
- **C.** Migrate the data to an Amazon S3 bucket using S3 Standard. Before each job, create an Amazon FSx for Lustre file system with batch loading from S3. Use the file system during the job and delete it afterward.
- **D.** Migrate the data to Amazon S3. Before each job, deploy an AWS Storage Gateway file gateway. Use the gateway during the job and decommission it afterward.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Option A uses S3 Intelligent-Tiering for cost-effective storage and FSx for Lustre with lazy loading, which is provisioned only during the monthly job and deleted afterward. This eliminates the need for continuously running storage instances, reducing costs while maintaining high performance. ✨
  
</details>

---

## ❓ Question 24

A company is deploying a globally accessible TCP service on a static port. The solutions architect must design a solution that ensures high availability, spans multiple Availability Zones, and uses the DNS name global.service.com, which is publicly resolvable. The service requires fixed IP addresses to allow external partners to whitelist them. All resources are deployed in a single AWS Region.

Which architecture meets these requirements?

- **A.** Deploy Amazon EC2 instances with individual Elastic IP addresses. Configure a Network Load Balancer (NLB) with the static TCP port, register the EC2 instances with the NLB, and create an A record for global.service.com pointing to the EC2 instances' Elastic IP addresses. Share these Elastic IPs with partners for allow lists.
- **B.** Use an Amazon ECS cluster with tasks assigned public IPs. Set up a Network Load Balancer (NLB) with the TCP port, link the ECS service to the NLB via a target group, and create an A record for global.service.com mapping to the ECS tasks' public IPs. Provide these IPs to partners.
- **C.** Deploy EC2 instances across Availability Zones. Assign one Elastic IP per Availability Zone and attach them to a Network Load Balancer (NLB) configured with the static TCP port. Register the instances with the NLB's target group. Create an A (alias) record for global.service.com pointing to the NLB's DNS name. Share the NLB's fixed Elastic IPs with partners.
- **D.** Host the service on an Amazon ECS cluster with public IPs for each host. Configure an Application Load Balancer (ALB) for the TCP port, associate the ECS service with the ALB via a target group, and create a CNAME record for global.service.com linked to the ALB's DNS name. Provide the ALB's IPs to partners.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. It uses a Network Load Balancer (NLB) with Elastic IPs per Availability Zone (AZ), ensuring high availability, fixed IPs for whitelisting, and a DNS alias pointing to the NLB. Other options fail to provide static IPs or misuse load balancer types. ✨
  
</details>

---

## ❓ Question 25

A company operates an on-premises data processing system configured with full redundancy across 15 servers in their data center. The system executes scheduled jobs that run every 4 hours and daily, in addition to ad-hoc user requests. Scheduled jobs require between 30 minutes and 3 hours to complete and must adhere to strict SLAs, accounting for 70% of system usage. User jobs typically finish within 10 minutes and can tolerate delays during system issues, making up the remaining 30% of usage. During outages, scheduled jobs must still meet their SLAs, while user jobs can be postponed.

The company aims to migrate this system to Amazon EC2 instances, adopting a consumption-based pricing model to minimize costs without long-term commitments. The solution must ensure high availability and uphold the SLAs for scheduled jobs.

Which solution MOST cost-effectively meets these requirements?

- **A.** Distribute the 15 instances across three Availability Zones. In each zone, run three On-Demand Instances with Capacity Reservations and two Spot Instances.
- **B.** Distribute the 15 instances across two Availability Zones. Run five On-Demand Instances with Capacity Reservations in each zone, and five Spot Instances in a third zone.
- **C.** Distribute the 15 instances across three Availability Zones. In each zone, run four On-Demand Instances with Capacity Reservations and one Spot Instance.
- **D.** Distribute the 15 instances across three Availability Zones. Use Savings Plans for six On-Demand Instances spread equally across zones, and deploy the remaining nine as Spot Instances.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: Option C distributes 15 instances across three AZs with 4 On-Demand (Capacity Reservations) and 1 Spot per zone. This ensures HA, meets SLAs for scheduled jobs via reserved capacity, and minimizes costs using Spot for interruptible user jobs. ✨
  
</details>

---

## ❓ Question 26

A solutions architect is designing a new version of an application that currently hardcodes credentials for an Amazon RDS for PostgreSQL database. The security team mandates the following enhancements:

- Credentials must be stored securely using an AWS managed service without hardcoding.
- Deployment must be automated through AWS CloudFormation.
- Database credentials must be automatically rotated every 90 days.

Which combination of resources in the CloudFormation template will meet these requirements with the LEAST operational effort?

- **A.** Generate the database password as a secret resource using AWS Secrets Manager. Create an AWS Lambda function resource to rotate the database password. Specify a Secrets Manager RotationSchedule resource to rotate the database password every 90 days.
- **B.** Generate the database password as a SecureString parameter type using AWS Systems Manager Parameter Store. Create an AWS Lambda function resource to rotate the database password. Specify a Parameter Store RotationSchedule resource to rotate the database password every 90 days.
- **C.** Generate the database password as a secret resource using AWS Secrets Manager. Create an AWS Lambda function resource to rotate the database password. Create an Amazon EventBridge scheduled rule resource to trigger the Lambda function password rotation every 90 days.
- **D.** Generate the database password as a SecureString parameter type using AWS Systems Manager Parameter Store. Specify an AWS Step Functions state machine resource to orchestrate password rotation every 90 days.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Answer A uses AWS Secrets Manager to securely store credentials and automate rotation every 90 days via CloudFormation, meeting all requirements with minimal effort. Secrets Manager natively supports credential rotation, unlike other options requiring manual scheduling. ✨
  
</details>

---

## ❓ Question 27

A company is using Amazon DynamoDB to store data and requires a serverless solution to expose this data through a public HTTPS API that automatically scales. Which two architectures meet these requirements? (Choose two.)

- **A.** Design an Amazon API Gateway REST API with direct integrations to DynamoDB using API Gateway's AWS service integration.
- **B.** Implement an Amazon API Gateway HTTP API configured with direct integrations to DynamoDB using AWS service integration.
- **C.** Develop an Amazon API Gateway HTTP API integrated with AWS Lambda functions that retrieve data from DynamoDB tables.
- **D.** Deploy AWS Lambda@Edge functions with Amazon CloudFront to serve DynamoDB data globally.
- **E.** Configure an Application Load Balancer to route requests to Lambda functions that access DynamoDB.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BC**
  
  > Short Explanation: Options B and C are correct because they use serverless components (API Gateway HTTP API with direct DynamoDB integration or Lambda) that provide a public HTTPS API with automatic scaling. Other options either lack serverless design, introduce unnecessary complexity, or do not fully meet the requirements. ✨
  
</details>

---

## ❓ Question 28

A company has registered 15 new domain names for a global marketing campaign. Each domain must redirect visitors to a unique URL specified in a JSON configuration. DNS is managed by Amazon Route 53, and the solution must support both HTTP and HTTPS with minimal maintenance.

Which combination of steps should a solutions architect take to meet these requirements with the LEAST operational effort? (Choose three.)

- **A.** Develop a dynamic web application hosted on an Amazon EC2 instance that reads the JSON configuration to redirect requests.
- **B.** Set up an Application Load Balancer with HTTP and HTTPS listeners to route traffic based on the domain.
- **C.** Implement an AWS Lambda@Edge function integrated with the JSON document to determine the redirect URL for each request.
- **D.** Use Amazon API Gateway with custom domain names to trigger a Lambda function that processes redirects.
- **E.** Configure an Amazon CloudFront distribution to handle incoming requests and use Lambda@Edge for URL redirection.
- **F.** Request an SSL/TLS certificate from AWS Certificate Manager (ACM) covering all domains as Subject Alternative Names.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: CEF**
  
  > Short Explanation: The correct answers are C, E, and F. Lambda@Edge (C) dynamically redirects using the JSON config. CloudFront (E) handles HTTP/HTTPS globally. ACM (F) simplifies SSL/TLS for all domains. Together, they provide a serverless, low-maintenance solution. ✨
  
</details>

---

## ❓ Question 29

A company with multiple AWS accounts uses AWS Organizations. The accounts host EC2 instances, Amazon RDS databases, and serverless applications. The development team has deployed testing environments across these accounts, tagged with a key of 'environment' and a value of 'testing'. The company wants to accurately calculate the cost of these testing resources to charge the development team's AWS account. What should a solutions architect do to meet these requirements?

- **A.** In the management account, activate the 'environment' user-defined tag. Configure monthly AWS Cost and Usage Reports to an Amazon S3 bucket in the management account. Use the tag breakdown in the report to obtain the total cost for 'environment:testing' resources.
- **B.** In the member accounts, activate the 'environment' user-defined tag. Configure monthly AWS Cost and Usage Reports to an S3 bucket in the management account. Schedule a Lambda function to parse the reports and calculate the total cost for 'environment:testing' resources.
- **C.** In the member accounts, activate the 'environment' user-defined tag. From the management account, enable AWS Budgets with custom reports filtered by the 'environment:testing' tag to track monthly costs.
- **D.** Use AWS Resource Groups in the management account to create a group filtered by the 'environment:testing' tag. Configure Amazon QuickSight to visualize the aggregated costs from all member accounts.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. Activating the 'environment' tag in the management account and using AWS Cost and Usage Reports (CUR) with tag breakdown allows accurate cost tracking for 'environment:testing' resources across all accounts in the organization. ✨
  
</details>

---

## ❓ Question 30

A company manages multiple AWS accounts under an organization in AWS Organizations. Each account has several VPCs that need to communicate with each other using AWS Transit Gateway. The company aims to automate the deployment of a new VPC and its attachment to the Transit Gateway whenever a new member account is added.

Which combination of steps should be taken to fulfill these requirements? (Choose two.)

- **A.** Share the Transit Gateway from the management account to member accounts using AWS Resource Access Manager.
- **B.** Apply an AWS Organizations SCP from the management account to allow member accounts to access the Transit Gateway.
- **C.** Deploy an AWS CloudFormation stack set from the management account to automatically provision a new VPC and a Transit Gateway attachment in the new member account, referencing the Transit Gateway ID.
- **D.** Use AWS Service Catalog in the management account to share a product that creates a VPC and a Transit Gateway peering attachment in the member account.
- **E.** Create a Transit Gateway peering connection in each member account and share it with the management account using a service-linked role.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: AC**
  
  > Short Explanation: The correct answers are A and C. Sharing the Transit Gateway via AWS RAM (A) allows cross-account access, and using CloudFormation stack sets (C) automates VPC deployment and attachment. ✨
  
</details>

---

## ❓ Question 31

An enterprise company wants to allow its developers to subscribe to third-party SaaS products through AWS Marketplace. The company uses an AWS Organizations account structure with full features enabled and has a central procurement account in each organizational unit (OU) managed by procurement teams. The procurement policy mandates that developers can only access an approved list of products via Private Marketplace. Administration of Private Marketplace must be restricted to a role named procurement-manager-role, assumable by authorized procurement personnel. All other IAM users, roles, groups, and account administrators must be explicitly denied administrative access to Private Marketplace.

What is the MOST efficient way to design an architecture that meets these requirements?

- **A.** Create an IAM role named procurement-manager-role in all AWS accounts. Attach the PowerUserAccess managed policy to the role. Apply an inline policy to all IAM users and roles in every account to explicitly deny permissions associated with the AWSPrivateMarketplaceAdminFullAccess managed policy.
- **B.** Create an IAM role named procurement-manager-role in all AWS accounts. Attach the AdministratorAccess managed policy to the role. Define a permissions boundary using the AWSPrivateMarketplaceAdminFullAccess managed policy and apply it to all developer roles.
- **C.** Create an IAM role named procurement-manager-role in all central procurement accounts. Attach the AWSPrivateMarketplaceAdminFullAccess managed policy to the role. Create an organization root-level SCP to deny Private Marketplace administrative actions to all principals except the procurement-manager-role. Create another root-level SCP to deny permissions to create IAM roles named procurement-manager-role across the organization.
- **D.** Create an IAM role named procurement-manager-role in all developer accounts. Attach the AWSPrivateMarketplaceAdminFullAccess managed policy to the role. Create an SCP to deny Private Marketplace administrative access to everyone except the role. Apply the SCP to all central procurement accounts.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer leverages AWS Organizations SCPs to enforce centralized governance. By creating SCPs at the root level, it restricts Private Marketplace administrative actions to the procurement-manager-role while preventing unauthorized role creation, aligning with procurement policies and AWS Organizations best practices. ✨
  
</details>

---

## ❓ Question 32

A company is using AWS Organizations to restrict its developers to only use Amazon RDS, AWS Lambda, and AWS CloudFormation. The developers' account is placed in a separate organizational unit (OU). The solutions architect has applied the following SCP to the developers' OU:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowRDS",
      "Effect": "Allow",
      "Action": "rds:*",
      "Resource": "*"
    },
    {
      "Sid": "AllowLambda",
      "Effect": "Allow",
      "Action": "lambda:*",
      "Resource": "*"
    },
    {
      "Sid": "AllowCloudFormation",
      "Effect": "Allow",
      "Action": "cloudformation:*",
      "Resource": "*"
    }
  ]
}
```

Despite this policy, IAM users in the developers' account can still access AWS services not listed in the SCP. What should the solutions architect do to enforce the restriction?

A. Add explicit deny statements for all AWS services except RDS, Lambda, and CloudFormation.
B. Detach the FullAWSAccess SCP from the developers' OU.
C. Update the FullAWSAccess SCP to explicitly deny all services not listed.
D. Include a wildcard deny statement at the end of the existing SCP.

- **A.** Add explicit deny statements for all AWS services except RDS, Lambda, and CloudFormation.
- **B.** Detach the FullAWSAccess SCP from the developers' OU.
- **C.** Update the FullAWSAccess SCP to explicitly deny all services not listed.
- **D.** Include a wildcard deny statement at the end of the existing SCP.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The developers' OU still has the FullAWSAccess SCP attached, which allows all services. Detaching it ensures only the custom SCP (allowing RDS, Lambda, CloudFormation) applies, enforcing the restriction. ✨
  
</details>

---

## ❓ Question 33

A company hosts a monolithic REST API on Amazon EC2 instances behind an Application Load Balancer (ALB) within a VPC. The ALB is registered in Route 53 with an alias record. During peak traffic periods, the API experiences latency and timeouts despite the EC2 instances scaling based on CPU utilization. The operations team wants a solution that minimizes management effort while ensuring scalability.

Which solution meets these requirements MOST effectively?

- **A.** Refactor the API into AWS Lambda functions and use Amazon API Gateway as the frontend. Update Route 53 to point to the API Gateway endpoint.
- **B.** Migrate the API to Amazon ECS with Fargate launch type, using an ALB for load balancing. Update the Route 53 record to the new ALB.
- **C.** Implement Amazon EC2 Auto Scaling policies based on Application Load Balancer request counts. Configure scaling policies to react more quickly to traffic changes.
- **D.** Use Amazon CloudFront with Lambda@Edge to cache responses and distribute traffic globally. Point Route 53 to the CloudFront distribution.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. Refactoring the API into AWS Lambda with API Gateway eliminates EC2 management, auto-scales seamlessly, and reduces latency. Other options still require infrastructure management or do not fully address scalability. ✨
  
</details>

---

## ❓ Question 34

A large enterprise uses AWS Organizations to manage its infrastructure, with separate Organizational Units (OUs) representing different departments. Each OU contains dozens of AWS accounts. The finance team needs a solution to monitor and analyze the aggregated costs for each department's OU without granting cross-departmental access. Which approach satisfies these requirements?

- **A.** Configure AWS Cost and Usage Reports (CUR) per OU using AWS Service Catalog. Enable each department to access their CUR via AWS Cost Explorer.
- **B.** Generate a single AWS Cost and Usage Report (CUR) from the AWS Organizations management account. Provide each department access to visualize their OU's costs using Amazon QuickSight dashboards.
- **C.** Deploy an AWS Cost and Usage Report (CUR) in every member account within each OU. Allow departments to consolidate their data using Athena queries.
- **D.** Use AWS Control Tower to create CURs for each OU. Share the reports via AWS Lake Formation for departmental analysis.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. Generating a single CUR from the management account and using Amazon QuickSight with row-level security allows departments to view their OU's aggregated costs without cross-access. Other options involve inefficient CUR management or incorrect service usage. ✨
  
</details>

---

## ❓ Question 35

A company operates an on-premises Windows file server that generates 7 GB of new data daily. The company has partially migrated its Windows applications to AWS and requires the data to be accessible on a cloud-based file system compatible with Windows. They have an established AWS Direct Connect connection for reliable network connectivity.

Which data migration strategy should the company implement?

- **A.** Deploy a volume gateway using AWS Storage Gateway to replace the existing file server and configure applications to access the gateway.
- **B.** Use AWS DataSync to schedule daily transfers to replicate data between the on-premises file server and Amazon FSx for Windows File Server.
- **C.** Configure AWS Transfer Family to automate daily SFTP transfers from the on-premises server to an Amazon S3 bucket, then mount the bucket as a file system.
- **D.** Use AWS Backup to create daily backups of the on-premises file server and restore them to an Amazon Elastic File System (Amazon EFS).

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. AWS DataSync efficiently automates daily data transfers between on-premises and Amazon FSx for Windows File Server, ensuring compatibility and leveraging Direct Connect for reliable connectivity. ✨
  
</details>

---

## ❓ Question 36

A company’s solutions architect is designing a web application that stores user-uploaded files in an Amazon S3 bucket in the eu-west-1 Region. The company requires high availability across multiple AWS Regions and has already provisioned a second S3 bucket in another Region. Which solution provides multi-region resiliency with the LEAST operational overhead?

- **A.** Configure the application to upload each file to both S3 buckets. Use Amazon Route 53 with a failover routing policy pointing to each bucket. Update the application to reference the Route 53 DNS name.
- **B.** Create an AWS Lambda function triggered on upload to copy objects to the second S3 bucket. Set up an Amazon CloudFront distribution with an origin group that includes both S3 buckets as origins.
- **C.** Enable S3 replication from the primary bucket to the secondary bucket. Configure an Amazon CloudFront distribution with an origin group that uses both S3 buckets as origins.
- **D.** Configure S3 replication from the primary bucket to the secondary bucket. Modify the application code to switch to the secondary bucket during failover events.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. Enabling S3 replication automates cross-region data synchronization, while CloudFront's origin group provides automatic failover, minimizing operational overhead. ✨
  
</details>

---

## ❓ Question 37

A company is migrating a three-tier Java web application from an on-premises environment to AWS after experiencing downtime due to a traffic surge. The application has a dependency on a PostgreSQL database. A solutions architect must design a scalable and highly available solution to support 250,000 daily users. Which steps should the solutions architect take?

- **A.** Use AWS Elastic Beanstalk to deploy the web tier with an environment configured with an Application Load Balancer (ALB) and an Amazon EC2 Auto Scaling group across two Availability Zones. Provision an Amazon RDS PostgreSQL Multi-AZ DB instance. Configure an Amazon Route 53 alias record to route traffic from the company\u2019s domain to the ALB.
- **B.** Use AWS CloudFormation to deploy a stack that includes an Application Load Balancer (ALB) in front of an Amazon EC2 Auto Scaling group spanning three Availability Zones. The stack provisions a Multi-AZ Amazon Aurora PostgreSQL DB cluster with a Retain deletion policy. Use an Amazon Route 53 alias record to direct traffic from the company\u2019s domain to the ALB.
- **C.** Use AWS Elastic Beanstalk to create a web server environment spanning two AWS Regions, each with an Application Load Balancer (ALB). Deploy a Multi-AZ Amazon Aurora PostgreSQL DB cluster with a cross-Region read replica. Use Amazon Route 53 with a latency-based routing policy to distribute traffic between the two Regions.
- **D.** Use Amazon EC2 instances in an Auto Scaling group behind a Network Load Balancer (NLB) deployed across two Availability Zones for the web tier. Use Amazon RDS for PostgreSQL in a Single-AZ configuration with automated backups enabled. Configure an Amazon Route 53 weighted routing policy to distribute traffic between EC2 instances.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Answer B is correct because it uses Aurora PostgreSQL (scalable), spans three AZs (high availability), and includes a Retain policy to prevent accidental DB deletion. Other options use fewer AZs (A) or unnecessary multi-region complexity (C). ✨
  
</details>

---

## ❓ Question 38

A company is using AWS Organizations to manage multiple AWS accounts. To ensure compliance, they must deploy an AWS Config rule across all member accounts. Trusted access is enabled. What should the solutions architect do to deploy the Config rule using CloudFormation StackSets?

- **A.** Create a stack set in member accounts with service-managed permissions. Deploy to the organization. Use drift detection.
- **B.** Create individual stacks in each member account using self-service permissions. Deploy to the organization. Enable automatic deployment.
- **C.** Create a stack set in the management account using service-managed permissions. Deploy to the organization. Enable automatic deployment.
- **D.** Create stacks in the management account with service-managed permissions. Deploy to the organization. Use drift detection.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C because AWS StackSets with service-managed permissions in the management account allow deploying configurations across all member accounts in an organization. Enabling automatic deployment ensures new accounts receive the Config rule. ✨
  
</details>

---

## ❓ Question 39

A company is planning to migrate its on-premises Linux and Windows workloads to AWS. The company's infrastructure includes bare-metal servers and virtual machines hosting a variety of applications. The company needs to capture system configurations, performance metrics, active processes, and network connections of its on-premises workloads. Additionally, the company must organize its applications into migration groups and obtain Amazon EC2 instance recommendations to ensure cost-effective operation on AWS.

Which combination of steps should a solutions architect take to meet these requirements? (Choose three.)

- **A.** Assess the on-premises workloads by deploying AWS Application Discovery Agent on the bare-metal servers and virtual machines.
- **B.** Assess the on-premises workloads by deploying AWS Systems Manager Agent on the bare-metal servers and virtual machines.
- **C.** Organize servers into migration groups by using AWS Systems Manager Application Manager.
- **D.** Organize servers into migration groups by using AWS Migration Hub.
- **E.** Generate suggested EC2 instance types and associated pricing by using AWS Migration Hub.
- **F.** Import server sizing data into AWS Trusted Advisor and implement its cost-optimization recommendations.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: ADE**
  
  > Short Explanation: The correct answers are A, D, and E. AWS Application Discovery Agent captures system configurations and metrics for migration planning. AWS Migration Hub organizes servers into migration groups and provides EC2 instance recommendations. Other options use incorrect services (e.g., Systems Manager, Trusted Advisor) for the stated requirements. ✨
  
</details>

---

## ❓ Question 40

A company operates a data analytics platform on AWS within a VPC spanning two Availability Zones. Each AZ has a public and a private subnet. The platform uses EC2 instances in the private subnets, fronted by an Application Load Balancer in the public subnets. The instances require internet access for software updates, handled by NAT gateways. They also process around 2 TB of data daily stored in an S3 bucket. The company emphasizes security and wants to cut costs without increasing operational overhead or security risks. Which solution meets these requirements?

- **A.** Replace NAT gateways with NAT instances, updating route tables to direct traffic from the private subnets to the NAT instances.
- **B.** Move the EC2 instances to the public subnets and eliminate the NAT gateways entirely.
- **C.** Create an S3 gateway VPC endpoint within the VPC and attach an endpoint policy permitting required S3 bucket actions.
- **D.** Migrate the data from Amazon S3 to an Amazon Elastic File System (EFS) volume mounted on the EC2 instances.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: Creating an S3 VPC gateway endpoint allows EC2 instances to securely access S3 without using NAT gateways, reducing costs and enhancing security without operational overhead. ✨
  
</details>

---

## ❓ Question 41

A company deployed an application on AWS using Amazon DynamoDB. The application experiences a weekly peak load lasting 5 hours, which is three times the average load. The rest of the week, the load remains near average. The access pattern involves significantly more writes than reads. A solutions architect must minimize the cost of the table while ensuring performance during peak periods.

Which solution meets these requirements?

- **A.** Use AWS Application Auto Scaling to adjust capacity during peak periods. Purchase reserved RCUs and WCUs to match the average load.
- **B.** Configure the table to use on-demand capacity mode.
- **C.** Use DynamoDB Auto Scaling with scheduled actions to increase capacity during peak periods. Purchase reserved RCUs and WCUs for the peak load.
- **D.** Enable DynamoDB Accelerator (DAX) and reduce provisioned write capacity to match the average load.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: Option A minimizes costs by using reserved capacity for the average load (lower cost) and auto-scaling during peaks. Other options either under-provision writes (D), use more expensive on-demand (B), or waste reserved capacity (C). ✨
  
</details>

---

## ❓ Question 42

A solutions architect needs to migrate an on-premises video rendering application to AWS. Users upload video files through a web interface, which are stored on a shared file system. The rendering process, which can take up to 2 hours per file, is triggered via a message queue. The workload fluctuates significantly, with high demand during business hours and low demand otherwise. What is the MOST cost-effective migration strategy?

- **A.** Use Amazon SQS for the queue. Configure the web server to publish messages to SQS. Invoke an AWS Lambda function to process each message, render the video, and store the output in an Amazon S3 bucket.
- **B.** Use Amazon MQ for the queue. Configure the web server to publish messages to the queue. Launch Amazon EC2 instances on demand to process messages, store rendered files in Amazon EFS, and terminate instances when idle.
- **C.** Use Amazon SQS for the queue. Configure the web server to publish messages to SQS. Use an EC2 Auto Scaling group to process messages, scaling instances based on the SQS queue length. Store rendered files in an Amazon S3 bucket.
- **D.** Use Amazon MQ for the queue. Configure the web server to publish messages to the queue. Invoke an AWS Lambda function to process each message, render the video, and store the output in Amazon EFS.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer is C. It uses EC2 Auto Scaling with SQS queue length metrics to handle fluctuating workloads cost-effectively, while leveraging S3 for storage. Other options use Lambda (unsuitable for 2-hour tasks) or less cost-efficient services (EFS/Amazon MQ). ✨
  
</details>

---

## ❓ Question 43

A company is using Amazon OpenSearch Service to store and analyze application logs. The company ingests logs into an OpenSearch Service cluster with 12 data nodes from an Amazon S3 bucket that uses S3 Standard-Infrequent Access (S3 Standard-IA). The logs remain in the cluster for 6 months for analysis, after which the company deletes the indexes. Compliance regulations require the company to retain all logs for 5 years. The company wants to minimize costs while meeting compliance requirements.

Which solution will meet these requirements MOST cost-effectively?

- **A.** Replace all data nodes with UltraWarm nodes to handle the logging workload. Transition the input logs from S3 Standard-IA to S3 Glacier Deep Archive immediately upon ingestion into the cluster.
- **B.** Reduce the number of data nodes in the cluster to 3. Add UltraWarm nodes to handle the logging workload. Configure indexes to transition to UltraWarm during ingestion. Apply an S3 Lifecycle policy to transition the input logs to S3 Glacier Deep Archive 6 months after ingestion.
- **C.** Reduce the number of data nodes in the cluster to 3. Use instance-backed storage for the remaining data nodes. Transition the input logs from S3 Standard-IA to S3 Glacier Deep Archive immediately upon ingestion into the cluster.
- **D.** Reduce the number of data nodes in the cluster to 3. Add UltraWarm nodes and cold storage nodes to the cluster. Configure indexes to transition from UltraWarm to cold storage after 6 months. Delete the input logs from S3 using an S3 Lifecycle policy after 6 months.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer reduces costs by minimizing data nodes, uses UltraWarm for storage, and transitions logs to S3 Glacier Deep Archive after 6 months via lifecycle policy, ensuring compliance and cost-effectiveness. ✨
  
</details>

---

## ❓ Question 44

A company has 10 accounts that are part of an organization in AWS Organizations. AWS Config is enabled in each account. All accounts belong to either the Prod OU or the NonProd OU. The company has configured an Amazon EventBridge rule in each account to notify an Amazon SNS topic when an S3 bucket policy is modified to allow public access (e.g., a policy granting '*' as the principal). The security team is subscribed to the SNS topic. For all accounts in the NonProd OU, the security team needs to prevent the creation of S3 bucket policies that allow public access. Which solution meets this requirement with the LEAST operational overhead?

- **A.** Modify the EventBridge rule to invoke an AWS Lambda function to revert the bucket policy change and publish to the SNS topic. Deploy the updated rule to the NonProd OU.
- **B.** Add the s3-bucket-public-read-prohibited AWS Config managed rule to the NonProd OU.
- **C.** Configure an SCP to allow the s3:PutBucketPolicy action when the value of the aws:Principal condition key does not include '*'. Apply the SCP to the NonProd OU.
- **D.** Configure an SCP to deny the s3:PutBucketPolicy action when the value of the aws:Principal condition key includes '*'. Apply the SCP to the NonProd OU.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. Using an SCP to deny s3:PutBucketPolicy when the condition is met ensures proactive prevention of public S3 bucket policies in NonProd OUs with minimal overhead. ✨
  
</details>

---

## ❓ Question 45

A company hosts a Git repository on-premises and uses webhooks to invoke AWS Cloud functions. The current solution runs on EC2 instances in an Auto Scaling group behind an Application Load Balancer (ALB). The company wants to transition to a serverless architecture with the LEAST operational overhead. Which solution meets these requirements?

- **A.** For each webhook, configure an AWS Lambda function with a function URL. Update the Git server to invoke these URLs directly.
- **B.** Create an Amazon API Gateway HTTP API, integrating each webhook's logic into separate Lambda functions. Update the Git server to send requests to the API Gateway endpoint.
- **C.** Deploy the webhook logic using AWS App Runner. Set up an ALB to route traffic to the App Runner service and update the Git server to target the ALB.
- **D.** Containerize the webhook application and deploy it using AWS Fargate. Create an API Gateway REST API to route requests to the Fargate service, then update the Git server to use the API Gateway endpoint.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: The correct answer is B. API Gateway HTTP API with Lambda integration provides a serverless solution with minimal operational overhead, enabling scalable webhook handling without managing infrastructure. ✨
  
</details>

---

## ❓ Question 46

A company is migrating 500 on-premises VMware servers to AWS. The servers require collection of metrics such as CPU utilization, disk I/O performance, installed software details, and network configurations. The company aims to analyze this data post-migration to optimize resource allocation. Which solution will meet these requirements?

- **A.** Deploy the AWS Agentless Discovery Connector on-premises. Configure Data Exploration in AWS Migration Hub. Use AWS Glue to transform the data. Query the data using Amazon S3 Select.
- **B.** Export VM performance and configuration data manually from the on-premises hosts. Import the data directly into AWS Migration Hub, supplementing missing fields. Query the data using Amazon QuickSight.
- **C.** Develop a custom script to collect server metrics. Use the AWS CLI to upload the data to AWS Migration Hub via the put-resource-attributes command. Query the data directly in the Migration Hub console.
- **D.** Install the AWS Application Discovery Agent on each on-premises server. Enable Data Exploration in AWS Migration Hub. Use Amazon Athena to query the data stored in Amazon S3.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: D**
  
  > Short Explanation: The correct answer is D. Installing AWS Application Discovery Agents on each server collects required metrics, and enabling Data Exploration in AWS Migration Hub stores data in Amazon S3. Amazon Athena is then used to query the data, meeting all requirements. ✨
  
</details>

---

## ❓ Question 47

A company is developing a serverless application hosted on AWS Lambda within a VPC. The application must communicate with an external API that mandates all requests originate from a single static public IPv4 address. The company needs to ensure the Lambda functions can securely access the API while adhering to this requirement.

Which solution will enable the application to meet the external provider's condition?

- **A.** Deploy a NAT gateway in a public subnet. Assign an Elastic IP address to the NAT gateway. Update the VPC route tables to direct outbound traffic from the Lambda function's subnet to the NAT gateway.
- **B.** Create an egress-only internet gateway. Attach an Elastic IP address to the gateway. Modify the Lambda function's security group to route traffic through the egress-only internet gateway.
- **C.** Configure an internet gateway with an Elastic IP address. Update the Lambda function's elastic network interface to associate with the internet gateway's Elastic IP address.
- **D.** Attach an internet gateway to the VPC. Assign an Elastic IP address to the internet gateway. Configure the main route table in the VPC to route all outbound traffic through the internet gateway.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: A**
  
  > Short Explanation: The correct answer is A. A NAT gateway with an Elastic IP (EIP) allows Lambda functions in a VPC to access the internet via a static public IP. Route tables direct outbound traffic through the NAT gateway, meeting the external API's requirement. ✨
  
</details>

---

## ❓ Question 48

A solutions architect has developed a web application that uses an Amazon API Gateway Regional endpoint and an AWS Lambda function. The consumers of the web application are all located near the AWS Region where the application is deployed. The Lambda function exclusively reads from an Amazon Aurora PostgreSQL database configured with three read replicas. During performance testing, the application experiences degraded performance due to a surge in database connections under high load. The solutions architect must optimize the application's efficiency.

Which two actions should the solutions architect take to address this issue? (Choose two.)

- **A.** Use the writer endpoint of the Aurora database.
- **B.** Use RDS Proxy to manage a connection pool for the reader endpoint.
- **C.** Change the API Gateway endpoint to an edge-optimized endpoint.
- **D.** Move the database connection initialization code outside the Lambda event handler.
- **E.** Enable Lambda Provisioned Concurrency.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: BD**
  
  > Short Explanation: The correct answers are B and D. Using RDS Proxy (B) manages database connections efficiently via pooling, reducing connection surges. Moving connection initialization outside the Lambda handler (D) leverages execution context reuse to minimize new connections per invocation. These address the root cause of degraded performance: excessive database connections under load. ✨
  
</details>

---

## ❓ Question 49

A company is deploying a web application on AWS and needs to ensure encrypted traffic between clients and the backend servers. They want to use AWS Certificate Manager (ACM) for managing SSL certificates wherever possible. Which setup meets these requirements?

- **A.** Use an Application Load Balancer (ALB) with an ACM certificate, forwarding traffic to instances on port 80. Install a third-party SSL certificate on each instance.
- **B.** Configure an ALB with an ACM certificate, terminating SSL at the ALB. Set up an HTTPS listener on the ALB forwarding to port 443 on instances, which have a third-party certificate installed.
- **C.** Deploy a Network Load Balancer (NLB) with an ACM certificate, forwarding traffic to instances using TLS on port 443. Install the same ACM certificate on each instance.
- **D.** Use CloudFront with an ACM certificate, pointing to an ALB with an HTTP listener. Install a third-party certificate on the ALB.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: B**
  
  > Short Explanation: Option B uses an ALB with ACM for SSL termination, ensuring encrypted client-to-ALB traffic. The ALB forwards HTTPS traffic to backend instances (port 443) with a third-party certificate, maintaining encryption end-to-end while maximizing ACM usage. ✨
  
</details>

---

## ❓ Question 50

A company is migrating its data processing system from on-premises to AWS. The system includes two applications: one ingests real-time user activity data into a PostgreSQL database, and the other generates dashboards. When dashboard generation runs, some data ingestion jobs fail. The company needs to resolve the ingestion issues and ensure a seamless migration without customer impact.

What should a solutions architect do to meet these requirements?

- **A.** Set up an Amazon Aurora PostgreSQL database as a replication target for the on-premises database. Create an Aurora Replica for the Aurora PostgreSQL database, and migrate the dashboard application to query the Aurora Replica. Deploy the ingestion endpoints as AWS Lambda functions behind a Network Load Balancer (NLB), and use Amazon RDS Proxy to write to the Aurora PostgreSQL database. After synchronization, disable replication and promote the Aurora Replica as the primary instance. Update the ingestion DNS record to point to the NLB.
- **B.** Set up an Amazon Aurora PostgreSQL database. Use AWS Database Migration Service (AWS DMS) for continuous replication from the on-premises database to Aurora. Migrate the dashboard application to query the Aurora database directly. Deploy the ingestion endpoints as Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer (ALB). After synchronization, update the DNS record to point to the ALB and disable the AWS DMS task post-cutover.
- **C.** Set up an Amazon Aurora PostgreSQL database. Use AWS Database Migration Service (AWS DMS) for continuous replication from the on-premises database to Aurora. Create an Aurora Replica for the Aurora PostgreSQL database, and migrate the dashboard application to query the Aurora Replica. Deploy the ingestion endpoints as AWS Lambda functions behind an Application Load Balancer (ALB), and use Amazon RDS Proxy to write to the Aurora PostgreSQL database. After synchronization, update the DNS record to point to the ALB and disable the AWS DMS task post-cutover.
- **D.** Set up an Amazon Aurora PostgreSQL database. Create an Aurora Replica for the Aurora PostgreSQL database, and migrate the dashboard application to query the replica. Deploy the ingestion endpoints as an Amazon Kinesis Data Stream, using Kinesis Data Firehose to load data into Aurora. After synchronization, promote the Aurora Replica as the primary instance and update the DNS record to point to the Kinesis stream.

<details>
  <summary>View Answer 👀</summary>
  
  **Correct Answer: C**
  
  > Short Explanation: The correct answer uses AWS DMS for continuous replication, separates read/write workloads via Aurora Replica, and leverages RDS Proxy to manage Lambda connections, ensuring seamless migration and resolving ingestion failures caused by dashboard queries. ✨
  
</details>