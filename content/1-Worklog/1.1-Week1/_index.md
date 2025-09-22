---
title: "Week 1 Worklog"
date: "2025-09-09T14:41:44+07:00"
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---


### Week 1 Objectives:

* Connect and get acquainted with members of First Cloud Journey.
* Understand basic AWS services, how to use the console & CLI.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2 | - Get acquainted with FCJ members, mentors, and supervisors. Learned about each member's role and responsibilities in the project team. <br> - Read and summarized internship unit rules and regulations including working hours, attendance policy, communication channels, task reporting, and security guidelines. <br> - Understood expectations for weekly progress reports and deliverables. | 06/09/2025 | 13/09/2025 | |
| 3 | - Learned about **AWS Global Infrastructure** (Regions, Availability Zones, Edge Locations). <br> - Studied key **AWS Service Categories**: <br>&emsp; + **Compute:** EC2, Lambda, Elastic Beanstalk, Auto Scaling. <br>&emsp; + **Storage:** S3 (standard, IA, Glacier), EBS, EFS. <br>&emsp; + **Networking:** VPC, Subnets, Internet Gateway, NAT Gateway, Route 53. <br>&emsp; + **Database:** RDS (MySQL, PostgreSQL), DynamoDB, Aurora. <br>&emsp; + **Security & Identity:** IAM (Users, Groups, Roles, Policies), KMS. <br>&emsp; + **Monitoring & Management:** CloudWatch (metrics & alarms), CloudTrail (logs), Trusted Advisor. <br> - Took detailed notes of use cases, pricing considerations, and real-world examples. | 06/09/2025 | 13/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Successfully created **AWS Free Tier** account, enabled **MFA** for root user for better security. <br> - Configured **Billing Alerts** in CloudWatch to monitor cost usage. <br> - Learned navigation of **AWS Management Console**, explored service categories, search bar, and pinned favorite services. <br> - Installed and configured **AWS CLI** locally: <br>&emsp; + Generated **Access Key & Secret Key** from IAM. <br>&emsp; + Set **Default Region** and **Output Format** using `aws configure`. <br>&emsp; + Verified configuration with `aws sts get-caller-identity`. <br> - **Practice:** Ran commands like `aws s3 ls`, `aws ec2 describe-regions`, `aws ec2 describe-instances` to confirm CLI works correctly. | 06/09/2025 | 13/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Learned about **Amazon EC2** core concepts: <br>&emsp; + **Instance Types:** General Purpose, Compute Optimized, Memory Optimized, Storage Optimized. <br>&emsp; + **AMI:** Choosing right image (Amazon Linux 2, Ubuntu, Windows Server). <br>&emsp; + **EBS:** gp3, io2, sc1, and their performance characteristics. <br>&emsp; + **Key Pairs:** Importance for SSH authentication. <br>&emsp; + **Security Groups:** Inbound and Outbound rule configuration. <br> - Studied **Elastic IP** concept for static public IPs. <br> - Learned different ways to connect to EC2: <br>&emsp; + SSH from local terminal. <br>&emsp; + Session Manager (browser-based). <br>&emsp; + EC2 Instance Connect. | 06/09/2025 | 13/09/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - **Hands-on Practice:** <br>&emsp; + Launched a **t2.micro** EC2 instance under Free Tier in a chosen region. <br>&emsp; + Generated key pair, downloaded `.pem` file, and updated permissions (`chmod 400 key.pem`). <br>&emsp; + Successfully connected to EC2 via SSH using terminal command `ssh -i key.pem ec2-user@<public-ip>`. <br>&emsp; + Created new EBS volume, attached it to instance, formatted and mounted it (`mkfs -t xfs /dev/xvdf`). <br>&emsp; + Verified data persistence after instance reboot. <br>&emsp; + Took screenshots for documentation and future reference. <br> - Learned how to stop, start, and terminate EC2 instances and the difference between them. | 06/09/2025 | 13/09/2025 | <https://cloudjourney.awsstudygroup.com/> |


### Week 1 Achievements:

* Gained a solid understanding of **AWS Cloud Computing** concepts and mastered the basic service groups:  
  * **Compute** – EC2 (virtual servers), Lambda (serverless), Auto Scaling, Elastic Beanstalk.  
  * **Storage** – S3 (object storage), EBS (block storage), EFS (file storage), lifecycle management policies.  
  * **Networking** – VPC, Subnets, Internet Gateway, NAT Gateway, Route Tables, Security Groups, Route 53.  
  * **Database** – RDS (MySQL, PostgreSQL), DynamoDB (NoSQL), Aurora, database backup & restore strategies.  
  * **Monitoring & Security** – IAM (users, groups, roles), CloudWatch (metrics & alarms), CloudTrail (logs).  

* Successfully created and configured an **AWS Free Tier account**, including:  
  * Enabled **MFA** on the root account for added security.  
  * Configured **Billing Alerts** to avoid unexpected charges.  
  * Set up a personal IAM user with administrator access for safer daily operations.  

* Became familiar with the **AWS Management Console**:  
  * Navigated through service categories and pinned frequently used services.  
  * Explored EC2, S3, VPC, and IAM dashboards.  
  * Learned to locate documentation and pricing calculators from the console.  

* Installed and configured **AWS CLI** on the computer, including:  
  * Generated **Access Key** & **Secret Key** from IAM.  
  * Configured **Default Region** and **Output Format** with `aws configure`.  
  * Verified identity using `aws sts get-caller-identity`.  
  * Stored credentials securely and learned how to rotate keys if needed.  

* Used AWS CLI to perform essential operations such as:  
  * Retrieve account information and CLI configuration.  
  * List available AWS regions (`aws ec2 describe-regions`).  
  * View EC2 instances, AMIs, and security groups.  
  * Create and manage key pairs for SSH access.  
  * Check running services and their states.  

* Acquired the ability to **combine AWS Management Console and CLI**:  
  * Launched resources from the Console and monitored/managed them with CLI.  
  * Practiced stopping/starting EC2 instances from CLI and verifying status in Console.  
  * Understood advantages of automation and scripting for repeatable tasks.  

* Documented each step with **screenshots and notes** for easy reference and reproducibility.  

* Learned about **cost optimization and security best practices** as part of AWS Well-Architected Framework.  

* Gained confidence to explore more advanced AWS services in the future such as S3 static website hosting, VPC design, and load balancing.
