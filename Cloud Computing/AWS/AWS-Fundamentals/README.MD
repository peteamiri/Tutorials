# Detailed Study Plan for AWS Cloud Computing

##  Overview
Utilizing Pareto's Principle, focus on key areas for comprehensive understanding of AWS cloud computing.

# Basic Concepts:
1. ** Managed Service**: Amazon RDS automates time-consuming administrative tasks, such as database setup, patching, backups, and software maintenance. This allows users to focus on their applications rather than managing the underlying infrastructure.

# Major Services in AWS Cloud (as a starting point)

1. **Amazon Computing**
2. **Amazon Storage**
3. **Amazon Data Storge**
4. **Amzon Network**
5. **Amazon Security**
6. **AWS Lambda**
7. **Amazon DynamoDB**
8. **AWS IAM (Identity and Access Management)**
9. **Amazon SQS (Simple Queue Service)**
10. **Amazon Route 53**
11. **Amazon Loadbalancers**
12. **Amazon Elastic Cache**

## AWS Storag Devices
Amazon offers various physical storage types across its services. Here are some examples:

1. **Amazon EBS Volumes**: Amazon Elastic Block Store (EBS) provides durable block-level storage volumes that can be attached to Amazon EC2 instances. These volumes function like physical hard drives and can be used as primary storage for instances or for storage in database applications.

2. **Instance Store**: Amazon EC2 instances also provide temporary block-level storage known as instance store. This storage is physically attached to the host computer and is ideal for temporary storage of frequently changing data, such as buffers, caches, and scratch data.

## AWS Data Storage

Amazon Web Services (AWS) provides various database storage types across its services. Here are some of the database storage types available in AWS:

1. **Object Storage**: Amazon S3 (Simple Storage Service) provides object storage for storing and retrieving any amount of data from anywhere on the web. It is suitable for storing unstructured data such as photos, videos, backups, and web content.

   1. **Amazon RDS Storage Types**: Amazon RDS (Relational Database Service) offers different storage types for its supported database engines, such as
   1. Amazon Aurora,
   2. MySQL,
   3. PostgreSQL,
   4. Oracle,
   5. SQL Server.

1. **Data Warehouse**: AWS Redshift is a fully managed data warehousing service. It provides columnar storage for large-scale data analytics and reporting.

1. **NO SQL Database**: AWS DocumentDB is a fully managed NoSQL document database service compatible with MongoDB. It provides scalable and highly available storage for JSON-like documents. DocumentDB uses SSD storage to deliver low-latency performance.

1. **Graph Database**: AWS Neptune is a fully managed graph database service. It provides storage for highly connected data, such as social networks, recommendation engines, and fraud detection. Neptune uses SSD storage to deliver fast and reliable graph queries.

1. **Amazon ElastiCache**: ElastiCache is a fully managed in-memory data store service. It provides storage for caching frequently accessed data, such as session data, metadata, and results of expensive database queries. ElastiCache supports two storage engines: Redis and Memcached.

These are just a few examples of the database storage types available in AWS. Each storage type is optimized for specific use cases and provides different performance characteristics, scalability options, and pricing structures.


## Amazon Network

AWS offers various network components that help in building and managing network infrastructure. Here are some of the network components available in AWS:

1. **Amazon VPC (Virtual Private Cloud)**: VPC allows you to create a virtual network in the AWS cloud, providing control over network settings, IP addressing, subnets, and routing. It allows you to launch AWS resources, such as EC2 instances, within a virtual network that you define.

2. **AWS Direct Connect**: Direct Connect provides a dedicated network connection between your on-premises data center and AWS. It offers a private and secure connection with higher bandwidth and lower latency compared to internet-based connections.

3. **Amazon Route 53**: Route 53 is a scalable domain name system (DNS) web service that translates domain names into IP addresses. It provides highly reliable and cost-effective domain registration, routing, and health checking of resources.

4. **Amazon CloudFront**: CloudFront is a content delivery network (CDN) service that delivers content, such as web pages, videos, and images, to users with low latency and high transfer speeds. It caches content at edge locations worldwide for faster delivery.

5. **AWS Global Accelerator**: Global Accelerator improves the availability and performance of your applications by directing traffic through the AWS global network infrastructure. It automatically routes traffic to the nearest AWS edge location, reducing latency and improving user experience.

6. **AWS Transit Gateway**: Transit Gateway simplifies network connectivity by acting as a hub for connecting multiple VPCs, on-premises networks, and VPN connections. It provides centralized management and simplifies routing between networks.

7. **AWS VPN**: VPN (Virtual Private Network) enables secure communication between your on-premises network and your VPCs in AWS. It encrypts traffic and provides a secure connection over the internet.

8. **AWS PrivateLink**: PrivateLink allows you to securely access AWS services privately from your VPC, without using public IPs or traversing the internet. It provides private connectivity to services like S3, DynamoDB, and others.


### AWS VPC

The components for AWS VPC (Virtual Private Cloud) include:

1. **Subnets**: Subnets are subdivisions of a VPC's IP address range. They allow for further segmentation and organization of resources within a VPC. Each subnet is associated with a specific availability zone.

2. **Route Tables**: Route tables control the traffic flow between subnets within a VPC. They determine how traffic is routed within the VPC and to external networks.

3. **Internet Gateway**: An internet gateway enables communication between instances within a VPC and the internet. It acts as a bridge between the VPC and the public internet.

4. **NAT Gateway**: A NAT (Network Address Translation) gateway allows instances within private subnets to access the internet while preventing direct inbound access from the internet. It provides a way for private instances to communicate with the internet using a public IP address.

5. **VPC Peering**: VPC peering allows the connection of two VPCs, enabling communication between them as if they were on the same network. It allows resources in different VPCs to communicate securely.

6. **Security Groups**: Security groups act as virtual firewalls for instances within a VPC. They control inbound and outbound traffic by allowing or denying specific network connections based on rules defined by the user.

7. **Network Access Control Lists (ACLs)**: ACLs are stateless firewalls that control traffic at the subnet level. They provide an additional layer of security by allowing or denying traffic based on rules defined by the user.

8. **VPC Endpoints**: VPC endpoints enable private connectivity between a VPC and other AWS services without the need for internet gateways, NAT gateways, or VPN connections. They allow secure and direct access to AWS services from within the VPC.

9. **VPC Flow Logs**: VPC Flow Logs capture information about the IP traffic going to and from network interfaces within a VPC. They provide visibility into network traffic patterns, helping with troubleshooting, security analysis, and compliance.

1. **Transit Gateway**: Transit Gateway acts as a central hub for routing traffic between VPCs, VPN connections, and AWS Direct Connect connections. It simplifies network architecture and enables efficient and scalable connectivity between multiple VPCs and on-premises networks.


## Amazon Security

AWS offers a range of security and monitoring services to help protect and monitor your resources in the cloud. Here are some of the key services:

1. **Amazon GuardDuty**: GuardDuty is a threat detection service that continuously monitors your AWS accounts and workloads for malicious activity and unauthorized behavior. It combines machine learning and integrated threat intelligence to provide detailed security findings for visibility and remediation.

2. **AWS Security Hub**: Security Hub provides a comprehensive view of your high-priority security alerts and compliance status across your AWS accounts. It aggregates and prioritizes security findings from various AWS services and third-party tools, making it easier to manage and respond to security issues.

3. **AWS CloudTrail**: CloudTrail records API calls and events for your AWS account, providing visibility into user activity, resource changes, and system events. It helps with security analysis, resource change tracking, and compliance auditing.

4. **AWS Config**: Config continuously monitors and records the configuration changes of your AWS resources. It provides a detailed inventory of your resources, tracks changes over time, and enables you to assess resource configurations for compliance and security purposes.

5. **Amazon Inspector**: Inspector helps you assess the security and compliance of your applications by automatically analyzing their behavior and identifying potential vulnerabilities or deviations from best practices. It provides detailed findings and recommendations for remediation.

6. **Amazon Macie**: Macie is a data security service that uses machine learning to automatically discover, classify, and protect sensitive data, such as personally identifiable information (PII), in your AWS environment. It helps you understand and protect your data at scale.

7. **Amazon Detective**: Detective helps you investigate potential security issues and conduct forensic analysis by analyzing log data from various AWS services. It automatically generates visualizations and insights to simplify the process of identifying the root cause of security incidents.

These are just a few examples of the security and monitoring services available in AWS. Each service offers specific capabilities to enhance the security and monitoring of your AWS resources. For more detailed information about each service and their use cases, you can refer to the official AWS documentation and resources provided by AWS.

## Amazon Computing

AWS offers a variety of computing services to meet different needs and use cases. Some of the key AWS computing services include:

1. **Amazon EC2 (Elastic Compute Cloud)**: EC2 provides resizable compute capacity in the cloud. It allows you to launch virtual servers (EC2 instances) with different configurations, such as CPU, memory, storage, and networking. EC2 offers flexibility, scalability, and control over your computing resources.

2. **Amazon ECS (Elastic Container Service)**: ECS is a fully managed container orchestration service. It allows you to run and scale containerized applications using Docker containers. ECS simplifies the deployment and management of containers, making it easier to build scalable and highly available applications.

3. **Amazon EKS (Elastic Kubernetes Service)**: EKS is a fully managed Kubernetes service. It simplifies the deployment, management, and scaling of containerized applications using Kubernetes. EKS provides a highly available and secure environment for running Kubernetes workloads.

4. **AWS Lambda**: Lambda is a serverless computing service that allows you to run code without provisioning or managing servers. It enables you to build and run applications in response to events, such as changes to data in an S3 bucket or updates to a DynamoDB table. Lambda automatically scales your applications based on incoming requests, and you only pay for the compute time consumed.

5. **Amazon Lightsail**: Lightsail provides a simplified way to launch and manage virtual private servers (VPS) with pre-configured compute, storage, and networking options. It is designed for developers, small businesses, and individuals who need a simple and cost-effective solution for hosting websites or applications.

6. **AWS Batch**: Batch enables you to run batch computing workloads on AWS. It allows you to define and manage batch jobs, specify resource requirements, and automatically scale resources based on workload demands. Batch is suitable for running large-scale parallel and high-performance computing (HPC) workloads.


## **Amazon EC2 (Elastic Compute Cloud)**

AWS EC2 (Amazon Elastic Compute Cloud) is a web service provided by Amazon Web Services (AWS) that allows users to rent virtual servers, known as instances, in the cloud. EC2 provides scalable computing capacity, allowing users to quickly scale up or down based on their needs.

**Key Features of AWS EC2**:

1. Instances: EC2 allows users to create and manage virtual instances, which are essentially virtual servers running in the cloud. Users can choose from a wide range of instance types based on their requirements, such as CPU, memory, storage, and networking capabilities.

2. Elastic IP Addresses (EIP): EC2 provides the option to assign static public IP addresses, known as Elastic IP addresses, to instances. This allows users to maintain a consistent IP address even if the instance is stopped or restarted.

3. Security Groups: EC2 uses security groups to control inbound and outbound traffic to instances. Users can define rules to allow or deny specific types of traffic based on protocols, ports, and IP addresses.

4. Storage Options: EC2 offers various storage options, including
   1. Amazon Elastic Block Store (EBS) for persistent block-level storage,
   2. Amazon Elastic File System (EFS) for scalable file storage,
   3. instance store volumes for temporary storage.

5. Auto Scaling: EC2 Auto Scaling enables users to automatically adjust the number of instances based on demand. It helps maintain application availability and optimize costs by scaling up or down based on predefined policies.

6. Load Balancing: EC2 Load Balancers distribute incoming traffic across multiple instances to improve application availability and fault tolerance. Users can choose between based on their specific needs:
   1. Application Load Balancer (ALB)
   2. Network Load Balancer (NLB) .

7. Virtual Private Cloud (VPC) Integration: EC2 instances can be launched within a Virtual Private Cloud (VPC), providing users with control over their virtual network environment. Users can define
   1. subnets,
   2. configure routing tables,
   3. apply network access control lists (ACLs) to secure their instances.

8. Integration with Other AWS Services: EC2 seamlessly integrates with other AWS services, such as
   1. Amazon S3 for object storage,
   2. Amazon RDS for managed databases,
   3. AWS Lambda for serverless computing.


## **Amazon RDS (Relational Database Service)**

Amazon Relational Database Service (Amazon RDS) is a managed database service provided by Amazon Web Services (AWS). It simplifies the process of setting up, operating, and scaling a relational database in the cloud. With Amazon RDS, users can choose from various popular database engines, including:
* Amazon Aurora,
* PostgreSQL,
* MySQL,
* MariaDB,
* SQL Server,
* Oracle,
* Db2.

**Key Features**:
1. Managed Service: Amazon RDS automates time-consuming administrative tasks, such as database setup, patching, backups, and software maintenance. This allows users to focus on their applications rather than managing the underlying infrastructure.

2. Scalability and Flexibility: Amazon RDS allows users to easily scale their database instances up or down based on demand. It provides options for both vertical scaling (increasing or decreasing the instance size) and horizontal scaling (replicating data across multiple instances).

3. High Availability and Durability: Amazon RDS offers built-in features for high availability, such as automated backups, automated software patching, and Multi-AZ deployments. Multi-AZ deployments provide synchronous replication and automatic failover to ensure database availability in the event of a failure.

4. Security: Amazon RDS provides several security features, including network isolation using Amazon Virtual Private Cloud (VPC), encryption at rest using AWS Key Management Service (KMS), and encryption in transit using SSL/TLS.

5. Monitoring and Metrics: Amazon RDS integrates with AWS CloudWatch to provide monitoring and metrics for database instances. Users can monitor performance metrics, set up alarms, and gain insights into database performance.

6. Automated Backups and Point-in-Time Recovery: Amazon RDS automatically performs regular backups of the database and allows users to restore to any point within the retention period. This helps protect against data loss and provides the ability to recover to a specific point in time.

7. Database Engine Compatibility: Amazon RDS supports a wide range of database engines, allowing users to choose the engine that best suits their application requirements. It provides compatibility with existing applications and tools, making it easy to migrate existing databases to Amazon RDS.

Amazon RDS simplifies the process of managing and scaling relational databases in the cloud, providing users with a reliable and scalable solution for their database needs. It offers a range of features and benefits that help reduce administrative overhead and improve application performance.


## **Amazon S3 (Simple Storage Service)**

Amazon S3 (Simple Storage Service) is a highly scalable and durable cloud storage service provided by Amazon Web Services (AWS). It is designed to store and retrieve any amount of data from anywhere on the web. Here are some key features and functionalities of Amazon S3:

1. **Scalability and Durability**: Amazon S3 is built to provide high scalability and durability. It is designed to store data across multiple devices and multiple facilities within a region, ensuring high availability and data durability. It offers 99.999999999% (11 nines) data durability, making it highly reliable for storing critical data.

2. **Object Storage**: Amazon S3 is an object storage service, which means it stores data as objects rather than in a traditional file hierarchy. Each object consists of data, metadata, and a unique identifier. Objects can be up to 5 terabytes in size and are stored in buckets.

3. **Buckets**: Amazon S3 uses buckets to organize and store objects. A bucket is a container for objects and is globally unique across all AWS accounts. Users can create multiple buckets and define access controls and policies for each bucket.

4. **Data Management**: Amazon S3 provides various features for managing data, including versioning, lifecycle policies, cross-region replication, and event notifications. Versioning allows users to keep multiple versions of an object, providing protection against accidental deletion or overwrites. Lifecycle policies enable automatic transitioning of objects between different storage classes based on predefined rules. Cross-region replication allows users to replicate objects across different AWS regions for data redundancy and disaster recovery. Event notifications can be set up to trigger actions or workflows when specific events occur in the S3 bucket.

5. **Security and Access Control**: Amazon S3 offers several security features to protect data. It supports server-side encryption to encrypt data at rest using AWS Key Management Service (KMS) or customer-provided keys. Access control can be managed using bucket policies, access control lists (ACLs), and AWS Identity and Access Management (IAM) policies. Fine-grained access control can be achieved using pre-signed URLs or temporary security credentials.

6. **Integration and Ecosystem**: Amazon S3 integrates seamlessly with other AWS services, such as AWS Lambda, Amazon CloudFront, Amazon Athena, and Amazon Redshift. It also has a rich ecosystem of third-party tools and services that provide additional functionalities and capabilities for data management, backup, and analytics.

Amazon S3 is widely used for various use cases, including backup and restore, data archiving, content distribution, data lakes, and application hosting. Its scalability, durability, and flexibility make it a popular choice for storing and managing data in the cloud.


Amazon S3 (Simple Storage Service) offers different types of storage classes to cater to various data storage needs. Here are some of the types of storage classes available in Amazon S3:

1. **S3 Standard**: This is the default storage class and is designed for frequently accessed data. It provides high durability, availability, and low latency. S3 Standard is suitable for a wide range of use cases, including websites, mobile applications, and content distribution.

2. **S3 Intelligent-Tiering**: This storage class is designed to optimize costs by automatically moving data between two access tiers: frequent access and infrequent access. It uses machine learning to analyze access patterns and automatically moves data to the appropriate tier. This helps optimize costs for data with changing access patterns.

3. **S3 Standard-IA (Infrequent Access)**: This storage class is designed for data that is accessed less frequently but requires rapid access when needed. It offers lower storage costs compared to S3 Standard, but with a slightly higher retrieval cost. S3 Standard-IA is suitable for backups, disaster recovery, and long-term storage.

4. **S3 One Zone-IA (Infrequent Access)**: This storage class is similar to S3 Standard-IA but stores data in a single Availability Zone instead of multiple Availability Zones. While it offers lower storage costs compared to S3 Standard-IA, it does not provide the same level of durability. It is suitable for data that can be easily reproduced or is non-critical.

5. **S3 Glacier and S3 Glacier Deep Archive**: These storage classes are designed for long-term data archival. They offer very low storage costs but with longer retrieval times. S3 Glacier is suitable for data that may need to be retrieved within minutes to hours, while S3 Glacier Deep Archive is designed for data that may need to be retrieved within hours to days.

Each storage class has its own pricing structure and characteristics, allowing users to choose the most suitable option based on their specific requirements for durability, availability, performance, and cost.

It's important to note that the availability of specific storage classes may vary by AWS Region. For the most up-to-date information and details on each storage class, you can refer to the official AWS documentation on Amazon S3 storage classes.

## **Amazon VPC (Virtual Private Cloud)**
## **AWS Lambda**
## **Amazon CloudFront**
## **Amazon DynamoDB**
## **AWS IAM (Identity and Access Management)**
## **Amazon SQS (Simple Queue Service)**
## **Amazon Route 53**
