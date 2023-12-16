# Detailed Study Plan for AWS Cloud Computing

##  Overview
Utilizing Pareto's Principle, focus on key areas for comprehensive understanding of AWS cloud computing.

# Basic Concepts:
1. ** Managed Service**: Amazon RDS automates time-consuming administrative tasks, such as database setup, patching, backups, and software maintenance. This allows users to focus on their applications rather than managing the underlying infrastructure.

# Major Services in AWS Cloud (as a starting point)

1. **Amazon EC2 (Elastic Compute Cloud)**
2. **Amazon RDS (Relational Database Service)**
3. **Amazon S3 (Simple Storage Service)**
4. **Amazon VPC (Virtual Private Cloud)**
5. **Amazon CloudFront**
6. **AWS Lambda**
7. **Amazon DynamoDB**
8. **AWS IAM (Identity and Access Management)**
9. **Amazon SQS (Simple Queue Service)**
10. **Amazon Route 53**


## **Amazon EC2 (Elastic Compute Cloud)**

AWS EC2 (Amazon Elastic Compute Cloud) is a web service provided by Amazon Web Services (AWS) that allows users to rent virtual servers, known as instances, in the cloud. EC2 provides scalable computing capacity, allowing users to quickly scale up or down based on their needs.

**Key Features of AWS EC2**:

1. Instances: EC2 allows users to create and manage virtual instances, which are essentially virtual servers running in the cloud. Users can choose from a wide range of instance types based on their requirements, such as CPU, memory, storage, and networking capabilities.

2. Elastic IP Addresses: EC2 provides the option to assign static public IP addresses, known as Elastic IP addresses, to instances. This allows users to maintain a consistent IP address even if the instance is stopped or restarted.

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

**Key Features of Amazon RDS**:
1. Managed Service: Amazon RDS automates time-consuming administrative tasks, such as database setup, patching, backups, and software maintenance. This allows users to focus on their applications rather than managing the underlying infrastructure.

2. Scalability and Flexibility: Amazon RDS allows users to easily scale their database instances up or down based on demand. It provides options for both vertical scaling (increasing or decreasing the instance size) and horizontal scaling (replicating data across multiple instances).

3. High Availability and Durability: Amazon RDS offers built-in features for high availability, such as automated backups, automated software patching, and Multi-AZ deployments. Multi-AZ deployments provide synchronous replication and automatic failover to ensure database availability in the event of a failure.

4. Security: Amazon RDS provides several security features, including network isolation using Amazon Virtual Private Cloud (VPC), encryption at rest using AWS Key Management Service (KMS), and encryption in transit using SSL/TLS.

5. Monitoring and Metrics: Amazon RDS integrates with AWS CloudWatch to provide monitoring and metrics for database instances. Users can monitor performance metrics, set up alarms, and gain insights into database performance.

6. Automated Backups and Point-in-Time Recovery: Amazon RDS automatically performs regular backups of the database and allows users to restore to any point within the retention period. This helps protect against data loss and provides the ability to recover to a specific point in time.

7. Database Engine Compatibility: Amazon RDS supports a wide range of database engines, allowing users to choose the engine that best suits their application requirements. It provides compatibility with existing applications and tools, making it easy to migrate existing databases to Amazon RDS.

Amazon RDS simplifies the process of managing and scaling relational databases in the cloud, providing users with a reliable and scalable solution for their database needs. It offers a range of features and benefits that help reduce administrative overhead and improve application performance.


## **Amazon S3 (Simple Storage Service)**
## **Amazon VPC (Virtual Private Cloud)**
## **AWS Lambda**
## **Amazon CloudFront**
## **Amazon DynamoDB**
## **AWS IAM (Identity and Access Management)**
## **Amazon SQS (Simple Queue Service)**
## **Amazon Route 53**
