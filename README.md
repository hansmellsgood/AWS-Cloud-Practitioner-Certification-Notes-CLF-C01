# AWS Cloud Practitioner Certification Notes-CLF-C01
 A repository that I will use to store notes along the way of my studying for the certificate.<br>
 I have also added the exam guide and sample questions that are provided from AWS as of 19/07/2022.
 <br> Scheduling of exams can be done at: https://aws.amazon.com/certification/certified-cloud-practitioner/
# Goal
The AWS Certified Cloud Practitioner (CLF-C01) examination is intended for individuals who have the knowledge,
skills, and abilities to demonstrate basic knowledge of the AWS platform, including:
- Available services and their common use cases
- AWS Cloud architectural principles (at the conceptual level)
- Account security and compliance.

# Domain 1: Cloud Concepts
## 1.1 What is Cloud Computing?
The practice of using a network of remote servers hosed on the internet to store, manage and process data, rather than a local server or a personal computer.
## 1.2 Six advantages and benefits of Cloud computing
1. Trade capital expense for variable expense (No upfront cost, Pay on demand)
2. Benefit from massive economies of scale (Share cost with other customers)
3. Stop guessing capacity (Instead of paying for idle or underutilized servers, perform scaling)
4. Increase speed and agility (Within a few clicks in minutes)
5. Stop spending money on running and maintaining (Focus on your customers)
6. Go global in minutes (Deploy app in multiple regions around the world with a few clicks)
## 1.3 Types of Cloud Computing (26%)
### 1.3.1 Software as a service (SaaS)
A completed product that is run and managed by service provider. <br>
E.g Email,  Office365
### 1.3.2 Platform as a service (PaaS)
Removes the need for your organization to manage the underlying infrastructure. <br>
E.g Elastic Beanstalk, Heroku
### 1.3.3 Infrastructure as a service (IaaS)
The basic building blocks for cloud IT. Provides access to networking features, computers and data storage space.<br>
E.g AWS, GCP, Microsoft Azure
## 1.4 Cloud Computing Deployment Models
### 1.4.1 Cloud
Run all parts of the application in the cloud.
Migrate existing applications to the cloud.
Design and build new applications in the cloud.
- Well suited for startups, low cost
- SaaS offerings, nature of applications are not that complicated (Dropbox)
- New projects and companies, no red tape can design to be 100% on cloud.
### 1.4.2 Hybrid:
Connect cloud-based resources to on-premises infrastructure.
Integrate cloud-based resources with legacy IT applications.
In a hybrid deployment, cloud-based resources are connected to on-premises infrastructure.
- Banks
- Fintech, Investment management
- Large professional service providers (Deloitte)
### 1.4.3 On-Premise: 
Deploy resources by using virtualization and resource management tools.
Increase resource utilization by using application management and virtualization technologies. It is also known as a private cloud deployment.
- Public Sector (Government)
- Super sensitive data (Hospitals)
- Largest enterprise with heavy regulations (Insurance)
## 1.5 AWS Global Infrastructure
Serves over a million active customers in more than 190 countries <br>
Steadily expanding global infrastructure to help customers achieve lower latency and higher throughput
- 69 Available Zones
- 22 Geographic Regions
### 1.5.1 Regions
A geographically distinct location which have multiple datacenters (AZs).<br>
Every region is physically isolated from and independent of every other region in terms of location, power, water supply.
- AWS largest region is US-EAST.
- New services almost always become available first on US-EAST.
- Not all services are available in all regions.
- US-EAST-1 is the region to see billing information.
### 1.5.2 Availability Zones
An AZ is a datacenter owned and operated by AWS.<br>
- Each region has at least 2 AZS.
- AZs are represented by a Region code, followed by a letter identifier<br>
E.g US-EAST-1a <br>
- Multi-AZ Distributing your instances accross multiple AZs allows failover configuration for handling requests when one goes down.
- 10m latency between AZs.
### 1.5.3 Edge Locations
An edge location is a datacenter owned by a trusted partner of AWS which has a <b>direct connection</b> to the AWS network.<br>
- These location serve requests for CloudFront and Route53.<br>
Request going to either of these services will be routed to the nearest edge location automatically.<br>
- <b>S3 Transfer acceleration </b> traffic and API gateway endpoint traffic also use the AWS Edge Network.<br>
- <b> This allows for low latency</b> no matter where the  end user is geographically located.
### 1.5.4 GovCloud (US)
AWS GovCloud Region allow customers to host sensitive <b>Controlled Unclassified Information</b> and other types of regulated workloads.<br>
GovClout Regions are only operated by employees who are US citizens.<br>
They are only accessible to US entities and root account holders who pass a screening process.
# Domain 2:  Security and Compliance (25%)

# Domain 3: Technology (33%)
## 3.1 Amazon Elastic Compute Cloud (Amazon EC2)
Amazon Elastic Compute Cloud (Amazon EC2) provides secure, resizable compute capacity in the cloud as Amazon EC2 instances. <br>
Characteristics:
- You can provision and launch an Amazon EC2 instance within minutes.
- You can stop using it when you have finished running a workload.
- You pay only for the compute time you use when an instance is running, not when it is stopped or terminated.
- You can save costs by paying only for server capacity that you need or want.
### 3.1.1 Amazon EC2 instance types
- General purpose instances (Balances compute, memory, and networking resources)
- Compute optimized instances (Offers high-performance processors)
- Memory optimized instances (Ideal for high-performance databases)
- Accelerated computing instances (ideal graphics applications, game streaming, and application streaming.)
- Storage optimized instances (Suitable for data warehousing applications)
### 3.1.2 Amazon EC2 pricing
- On-Demand (ideal for short-term, irregular workloads that cannot be interrupted.)
- Amazon EC2 Savings Plans (reduce your compute costs by committing to a consistent amount of compute usage for a 1-year or 3-year term)
- Reserved Instances (billing discount applied to the use of On-Demand Instances)
- Spot Instances (use unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.)
- Dedicated Hosts (physical servers with Amazon EC2 instance capacity that is fully dedicated to individual use.)
### 3.1.3 Amazon EC2 Auto Scaling
Amazon EC2 Auto Scaling enables you to automatically add or remove Amazon EC2 instances in response to changing application demand.
- Dynamic scaling responds to changing demand. 
- Predictive scaling automatically schedules the right number of Amazon EC2 instances based on predicted demand.
#### Steps to configuring Auto Scaling Group:
1. Set the minimum number of Amazon EC2 instances. The minimum capacity is the number of Amazon EC2 instances that launch immediately after you have created the Auto Scaling group.
2. Set the desired capacity of Amazon EC2 instances
3. Set the maximum number of Amazon EC2 instances.
## 3.2 Elastic Load Balancing
Elastic Load Balancing is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.
- A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group.
- This means that as you add or remove Amazon EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first.
- Then, the requests spread across multiple resources that will handle them.

E.g. if you have multiple Amazon EC2 instances, Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it.
## 3.3 Messaging and Queuing
Monolithic application: Application with tightly coupled components.
- These components might include databases, servers, the user interface,
- If a single component fails, other components fail, and possibly the entire application fails.

Microservices approach: application components are loosely coupled.
- If a single component fails, the other components continue to work because they are communicating with each other.
- The loose coupling prevents the entire application from failing.
## 3.3.1 Amazon Simple Notification Service (Amazon SNS)
Amazon Simple Notification Service (Amazon SNS) is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers. In Amazon SNS, subscribers can be web servers, email addresses, AWS Lambda functions, or several other options. 
## 3.3.2 Amazon Simple Queue Service (Amazon SQS)
Amazon Simple Queue Service (Amazon SQS) is a message queuing service.
- Using Amazon SQS, you can send, store, and receive messages between software components, without losing messages or requiring other services to be available.
- In Amazon SQS, an application sends messages into a queue. A user or service retrieves a message from the queue, processes it, and then deletes it from the queue.
# Domain 4: Billing and Pricing (16%)


## Learning Resources:
https://www.youtube.com/watch?v=SOTamWNgDKc <br>
https://aws.amazon.com/training/digital/aws-cloud-practitioner-essentials/
