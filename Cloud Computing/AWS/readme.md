# Amazon Web Services (AWS)

Amazon Web Services (AWS), is a cloud computing platform that provides access, management, and development of applications and services via globally-distributed data centers. AWS has multiple capabilities such as software as a service (SaaS), platform as a service (PaaS) and infrastructure as a service (IaaS) and supports many different programming languages, tools, and frameworks.

AWS is a subsidiary of Amazon, it provides on-demand cloud computing platforms and APIs to individuals, companies, and governments, on a metered, pay-as-you-go basis. Often times, clients will use this in combination with autoscaling (a process that allows a client to use more compute in times of high application usage, and then scale down to reduce costs when there is less traffic). These cloud computing web services provide various services related to networking, compute, storage, middleware, IOT and other processing capacity, as well as software tools via AWS server farms. This frees clients from managing, scaling, and patching hardware and operating systems. One of the foundational services is Amazon Elastic Compute Cloud (EC2), which allows users to have at their disposal a virtual cluster of computers, with extremely high availability, which can be interacted with over the internet via REST APIs, a CLI or the AWS console. AWS's virtual computers emulate most of the attributes of a real computer, including hardware central processing units (CPUs) and graphics processing units (GPUs) for processing; local/RAM memory; hard-disk/SSD storage; a choice of operating systems; networking; and pre-loaded application software such as web servers, databases, and customer relationship management (CRM).

AWS services are delivered to customers via a network of AWS server farms located throughout the world. Fees are based on a combination of usage (known as a "Pay-as-you-go" model), hardware, operating system, software, or networking features chosen by the subscriber required availability, redundancy, security, and service options. Subscribers can pay for a single virtual AWS computer, a dedicated physical computer, or clusters of either.[8] Amazon provides select portions of security for subscribers (e.g. physical security of the data centers) while other aspects of security are the responsibility of the subscriber (e.g. account management, vulnerability scanning, patching). AWS operates from many global geographical regions including seven in North America.[9]

Amazon markets AWS to subscribers as a way of obtaining large-scale computing capacity more quickly and cheaply than building an actual physical server farm.[10] All services are billed based on usage, but each service measures usage in varying ways. As of 2021 Q4, AWS has 33% market share for cloud infrastructure while the next two competitors Microsoft Azure and Google Cloud have 21%, and 10% respectively, according to Synergy Group.

AWS (Amazon Web Services) Cloud is a popular cloud computing platform offered by Amazon. It provides a wide range of services that enable businesses and individuals to deploy applications and services in the cloud, using the computing power, storage, and other resources provided by AWS.

Some of the key services offered by AWS include:

* Compute Services: AWS offers various compute services, including Elastic Compute Cloud (EC2), which provides virtual servers for running applications, and Elastic Kubernetes Service (EKS) for managing containers.

* Storage Services: AWS provides a range of storage services, including Simple Storage Service (S3), Elastic Block Store (EBS), and Glacier, which enable businesses to store, backup, and retrieve data easily.

* Database Services: AWS offers managed database services, including Amazon Relational Database Service (RDS) and Amazon DynamoDB, to help businesses deploy, operate, and scale databases in the cloud.

* Networking Services: AWS provides several networking services, such as Virtual Private Cloud (VPC), which enables businesses to launch AWS resources in a virtual network that they define, and Elastic Load Balancing (ELB), which distributes incoming traffic across multiple targets.

* Security Services: AWS offers various security services, such as AWS Identity and Access Management (IAM) and Amazon GuardDuty, to help businesses secure their cloud infrastructure and protect against potential threats.

AWS Cloud is widely used by businesses of all sizes, startups, and individuals for various purposes, including running applications, hosting websites, storing and analyzing data, and much more.

* Cerfitication
* Design

# AWS Services
AWS comprises over 200 products and services including computing, storage, networking, database, analytics, application services, deployment, management, machine learning, mobile, developer tools, RobOps and tools for the Internet of Things. The most popular include Amazon Elastic Compute Cloud (EC2), Amazon Simple Storage Service (Amazon S3), Amazon Connect, and AWS Lambda (a serverless function that can perform arbitrary code written in any language that can be configured to be triggered by hundreds of events, including http calls).

Services expose functionality through APIs for clients to use in their applications. These APIs are accessed over HTTP, using the REST architectural style and SOAP protocol for older APIs and exclusively JSON for newer ones. Clients can interact with these APIs in various ways, including from the AWS console (a website), by using SDKs written in various languages (such as Python, Java, and JavaScript), or by making direct REST calls.

## AWS Compute services

AWS (Amazon Web Services) provides several compute services that enable businesses to run applications and workloads in the cloud, using virtual servers, containers, and serverless computing. Here are some of the main AWS compute services:

* Amazon EC2: Elastic Compute Cloud (EC2) provides virtual servers (instances) that businesses can use to run their applications, databases, and other workloads in the cloud. EC2 offers a wide range of instance types, operating systems, and other configuration options to meet different needs.

* AWS Lambda: AWS Lambda is a serverless compute service that enables businesses to run code in response to events or requests, without managing any servers. Lambda automatically scales the computing resources based on the demand, and charges only for the actual usage.

* Amazon Elastic Container Service (ECS): Amazon ECS is a fully managed container orchestration service that enables businesses to run and manage Docker containers in the cloud. ECS provides features such as automatic scaling, load balancing, and integration with other AWS services.

* Amazon Elastic Kubernetes Service (EKS): Amazon EKS is a fully managed Kubernetes service that enables businesses to deploy, manage, and scale containerized applications using Kubernetes on AWS. EKS provides a highly available and secure Kubernetes control plane, and integrates with other AWS services.

* AWS Batch: AWS Batch is a managed batch computing service that enables businesses to run batch computing workloads on AWS. Batch automatically provisions the computing resources based on the workload demands, and optimizes the resource utilization and cost.

* AWS Fargate: AWS Fargate is a serverless compute engine for containers that enables businesses to run containers without managing the underlying infrastructure. Fargate provides on-demand, per-second billing, and automatically scales the resources based on the demand.

These compute services provide businesses with flexibility, scalability, and cost-effectiveness to run their applications and workloads in the cloud.


## AWS Storage Services


AWS (Amazon Web Services) offers a variety of storage services to help businesses store, backup, and retrieve data in the cloud. Here are some of the main AWS storage services:

* Amazon S3: Simple Storage Service (S3) is an object storage service that provides businesses with a scalable, durable, and highly available storage solution for data and files. S3 allows businesses to store and retrieve any amount of data from anywhere on the internet.
  - Amazon S3 Standard is the default. It is general purpose storage for frequently accessed data.  -
  - Amazon S3 Standard-Infrequent Access (Standard-IA) is designed for less frequently accessed da  - ta, such as backups and disaster recovery data.
  - Amazon S3 One Zone-Infrequent Access (One Zone-IA) performs like the Standard-IA, but stores data only in one availability zone.
  - Amazon S3 Intelligent-Tiering moves objects automatically to a more cost-efficient storage class.
  - Amazon S3 on Outposts brings storage to installations not hosted by Amazon.
  - Amazon S3 Glacier Instant Retrieval is a low-cost storage for rarely accessed data, but which still requires rapid retrieval.
  - Amazon S3 Glacier Flexible Retrieval is also a low-cost option for long-lived data; it offers 3 retrieval speeds, ranging from minutes to hours.
  - Amazon S3 Glacier Deep Archive is another low-cost option.[17][better source needed]

* Amazon EBS: Elastic Block Store (EBS) provides persistent block-level storage volumes for use with Amazon EC2 instances. EBS allows businesses to store data that requires frequent updates, such as databases or transactional workloads.

* Amazon EFS: Elastic File System (EFS) provides scalable, shared file storage for use with Amazon EC2 instances. EFS allows businesses to share data across multiple instances and applications, and provides a fully-managed file system that scales automatically.

* Amazon Glacier: Amazon Glacier provides low-cost, long-term storage for data archiving and backup. Glacier allows businesses to store large amounts of data that is infrequently accessed, and provides retrieval options that range from minutes to hours.

* AWS Storage Gateway: AWS Storage Gateway provides hybrid cloud storage solutions that enable businesses to seamlessly integrate on-premises applications and data with cloud storage. Storage Gateway supports file, volume, and tape gateway configurations, and provides a variety of data transfer and synchronization options.

* Amazon FSx: Amazon FSx provides fully-managed file systems that are optimized for Windows and Linux workloads. FSx allows businesses to run their applications and workloads that require file storage, and provides features such as backup and restore, automatic software updates, and integration with other AWS services.

These storage services offer businesses flexibility, scalability, and durability to store and manage their data in the cloud.

## AWS Database Services

AWS (Amazon Web Services) provides a variety of database services to help businesses deploy, operate, and scale databases in the cloud. Here are some of the main AWS database services:

* Amazon RDS: Amazon Relational Database Service (RDS) provides fully-managed relational databases, such as MySQL, PostgreSQL, Oracle, SQL Server, and MariaDB. RDS allows businesses to easily deploy and scale databases in the cloud, and provides features such as automated backups, patches, and monitoring.
  * MySQL,
  * PostgreSQL,
  * Oracle Database,
  * SQL Server,
  * MariaDB

* Amazon DynamoDB: Amazon DynamoDB provides a fully-managed NoSQL database service that can handle any amount of data and traffic. DynamoDB allows businesses to store and retrieve data using flexible data models, and provides features such as automatic scaling, backup and restore, and real-time data streams.

* Amazon Aurora: Amazon Aurora is a fully-managed MySQL and PostgreSQL-compatible relational database service that provides high performance, availability, and scalability. Aurora allows businesses to run mission-critical applications in the cloud with low latency and high throughput.

* Amazon DocumentDB: Amazon DocumentDB is a fully-managed document database service that is compatible with MongoDB. DocumentDB allows businesses to store, query, and index JSON data at scale, and provides features such as automatic scaling, backup and restore, and encryption.

* Amazon Neptune: Amazon Neptune is a fully-managed graph database service that is optimized for storing and querying graph data. Neptune allows businesses to build and run graph applications that require real-time querying of large datasets.

* Amazon ElastiCache: Amazon ElastiCache provides fully-managed in-memory caching engines, such as Redis and Memcached. ElastiCache allows businesses to improve the performance of their applications by caching frequently accessed data in memory.

These database services offer businesses flexibility, scalability, and reliability to manage their data in the cloud.


## AWS Networking Services

AWS (Amazon Web Services) provides a variety of networking services that help businesses build, manage, and optimize their network infrastructure in the cloud. Here are some of the main AWS networking services:

* Amazon VPC: Amazon Virtual Private Cloud (VPC) enables businesses to create a virtual network in the cloud, with complete control over network topology, IP addressing, and security. VPC allows businesses to launch AWS resources, such as EC2 instances, RDS databases, and Lambda functions, in a virtual network that is isolated from other networks.

* AWS Direct Connect: AWS Direct Connect provides a dedicated network connection between an on-premises data center and the AWS cloud. Direct Connect allows businesses to bypass the public internet and establish a private, high-bandwidth, and low-latency connection to AWS resources.

* Amazon Route 53: Amazon Route 53 is a highly available and scalable domain name system (DNS) service that enables businesses to route traffic to AWS resources, such as EC2 instances, S3 buckets, and Elastic Load Balancers. Route 53 provides features such as health checks, traffic policies, and DNSSEC.

* Elastic Load Balancing: Elastic Load Balancing (ELB) provides a managed load balancing service that distributes incoming traffic across multiple instances, containers, or IP addresses. ELB allows businesses to increase the availability and scalability of their applications by automatically routing traffic to healthy instances.

* AWS Global Accelerator: AWS Global Accelerator is a network service that improves the performance and availability of applications by using a global network of AWS edge locations. Global Accelerator allows businesses to direct traffic to optimal AWS endpoints based on geography, health, and routing policies.

* AWS Transit Gateway: AWS Transit Gateway provides a centralized hub that connects multiple VPCs, data centers, and remote offices. Transit Gateway allows businesses to simplify network connectivity, reduce operational costs, and improve security by using a single gateway to manage network traffic.

These networking services offer businesses the flexibility, scalability, and security to build and manage their network infrastructure in the cloud.

## AWS Security Services:

AWS (Amazon Web Services) provides a variety of security services to help businesses protect their applications, data, and infrastructure in the cloud. Here are some of the main AWS security services:

* AWS Identity and Access Management (IAM): AWS IAM enables businesses to manage access to AWS services and resources securely. IAM allows businesses to create and manage users, groups, and permissions to access resources in a granular and controlled way.

* AWS Key Management Service (KMS): AWS KMS provides a fully-managed service to create and control the encryption keys used to encrypt data stored in AWS services or on-premises. KMS allows businesses to encrypt data easily and manage access to the keys in a secure and compliant way.

* Amazon GuardDuty: Amazon GuardDuty is a threat detection service that uses machine learning and analytics to identify and respond to potential security threats in real-time. GuardDuty allows businesses to continuously monitor their AWS environment for unusual activity and potential security threats.

* AWS WAF: AWS WAF is a web application firewall that protects web applications from common web exploits, such as SQL injection and cross-site scripting (XSS). WAF allows businesses to create custom rules to block malicious traffic and protect their applications from attacks.

* AWS Shield: AWS Shield is a managed DDoS protection service that helps businesses protect their applications from DDoS attacks. Shield provides always-on detection and automatic inline mitigation to protect against network and application-layer attacks.

* Amazon Inspector: Amazon Inspector is an automated security assessment service that helps businesses improve the security and compliance of their applications deployed in AWS. Inspector identifies security vulnerabilities and compliance violations in applications and provides guidance on how to remediate them.

These security services offer businesses the tools and capabilities to build and manage a secure and compliant environment in the cloud.





















# AWS Introduction

* [Intoduction & Overview](https://www.javatpoint.com/aws-tutorial)
* [General Course](https://www.youtube.com/watch?v=k1RI5locZE4)
* [AWS Products](https://aws.amazon.com/products/#)
* [AWS Architecture](https://aws.amazon.com/architecture/)
* [AWS GitHub Repository](https://github.com/awsdocs)
* [AWS Products](https://aws.amazon.com/products/?pg=WIAWS-N&tile=learn_more)

# List of AWS Services

* [Amazon API Gateway](https://aws.amazon.com/api-gateway/)
* [AppStream 2.0](https://aws.amazon.com/appstream2/)
* [Amazon Athena](https://aws.amazon.com/athena/)
* [Amazon Cloud Directory](https://aws.amazon.com/cloud-directory/)
* [CloudFront](https://aws.amazon.com/cloudfront/)
* [CloudWatch](https://aws.amazon.com/cloudwatch/)
* [EventBridge](https://aws.amazon.com/eventbridge/)
* [Amazon Cognito](https://aws.amazon.com/cognito/)
* [Amazon Comprehend](https://aws.amazon.com/comprehend/)
* [Amazon Comprehend Medical](https://aws.amazon.com/comprehend/medical/)
* [Amazon Connect](https://aws.amazon.com/connect/)
* [DocumentDB (with MongoDB compatibility)](https://aws.amazon.com/documentdb/)
* [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)
* [Amazon Elastic Block Store (Amazon EBS)](https://aws.amazon.com/ebs/)
* [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/)
* [Amazon Elastic Container Registry (Amazon ECR)](https://aws.amazon.com/ecr/)
* [Amazon Elastic Container Service](https://aws.amazon.com/ecs/)
* [Amazon Elastic Container Service for Kubernetes (Amazon EKS)](https://aws.amazon.com/eks/)
* [Amazon Elastic File System (Amazon EFS)](https://aws.amazon.com/efs/)
* [ElastiCache Redis](https://aws.amazon.com/elasticache/redis/)
* [Elasticsearch Service](https://aws.amazon.com/elasticsearch-service/)
* [Amazon EMR](https://aws.amazon.com/emr/)
* [Amazon Forecast](https://aws.amazon.com/forecast/)
* [Amazon FreeRTOS](https://aws.amazon.com/freertos/)
* [Amazon FSx](https://aws.amazon.com/fsx/)
* [GuardDuty](https://aws.amazon.com/guardduty/) 
* [Amazon Inspector](https://aws.amazon.com/inspector/)
* [Amazon Kinesis Data Analytics](https://aws.amazon.com/kinesis/data-analytics/)
* [Amazon Kinesis Data Firehose](https://aws.amazon.com/kinesis/data-firehose/)
* [Amazon Kinesis Data Streams](https://aws.amazon.com/kinesis/streams/)
* [Amazon Kinesis Video Streams](https://aws.amazon.com/kinesis/video-streams/)
* [Amazon Lex](https://aws.amazon.com/lex/)
* [Amazon Macie](https://aws.amazon.com/macie/)
* [Amazon Managed Streaming for Kafka (Amazon MSK)](https://aws.amazon.com/msk/)
* [Amazon MQ](https://aws.amazon.com/amazon-mq/)
* [Amazon Neptune](https://aws.amazon.com/neptune/)
* [Amazon Personalize](https://aws.amazon.com/personalize/)
* [Amazon Pinpoint](https://aws.amazon.com/pinpoint/)
* [Amazon Polly](https://aws.amazon.com/polly/)
* [QuickSight](https://aws.amazon.com/quicksight/)
* [Amazon Redshift](https://aws.amazon.com/redshift/)
* [Rekognition](https://aws.amazon.com/rekognition/)
* [Amazon Relational Database Service (Amazon RDS) includes Amazon Aurora](https://aws.amazon.com/rds/) 
* [Amazon Route 53](https://aws.amazon.com/route53/)
* [Amazon S3 Glacier](https://aws.amazon.com/glacier/)
* [SageMaker](https://aws.amazon.com/sagemaker/)
* [Amazon SimpleDB](https://aws.amazon.com/simpledb/)
* [Amazon Simple Email Service (Amazon SES)](https://aws.amazon.com/ses/)
* [Amazon Simple Notification Service (Amazon SNS)](https://aws.amazon.com/sns/)
* [Amazon Simple Queue Service (Amazon SQS)](https://aws.amazon.com/sqs/)
* [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/)
* [Amazon Simple Workflow Service (Amazon SWF)](https://aws.amazon.com/swf/)
* [Amazon Transcribe](https://aws.amazon.com/transcribe/)
* [Amazon Translate](https://aws.amazon.com/translate/)
* [Amazon Virtual Private Cloud (Amazon VPC)](https://aws.amazon.com/vpc/)
* [Amazon WorkDocs](https://aws.amazon.com/workdocs/)
* [Amazon WorkLink](https://aws.amazon.com/worklink/)
* [Amazon WorkMail](https://aws.amazon.com/workmail/)
* [WorkSpaces](https://aws.amazon.com/workspaces/)
* [AWS Amplify Console](https://aws.amazon.com/amplify/console/)
* [AWS AppSync](https://aws.amazon.com/appsync/)
* [AWS Auto Scaling](https://aws.amazon.com/autoscaling/)
* [AWS Backup](https://aws.amazon.com/backup/)
* [AWS Batch](https://aws.amazon.com/batch/)  
* [AWS Certificate Manager (ACM)](https://aws.amazon.com/certificate-manager/)
* [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
* [AWS CloudHSM](https://aws.amazon.com/cloudhsm/)
* [AWS CloudTrail](https://aws.amazon.com/cloudtrail/)
* [AWS CodeBuild](https://aws.amazon.com/codebuild/)
* [AWS CodeCommit](https://aws.amazon.com/codecommit/)
* [AWS CodeDeploy](https://aws.amazon.com/codedeploy/)
* [AWS CodePipeline](https://aws.amazon.com/codepipeline/)
* [AWS Config](https://aws.amazon.com/config/)
* [AWS Control Tower](https://aws.amazon.com/controltower/)
* [AWS Database Migration Service (AWS DMS)](https://aws.amazon.com/dms/)
* [AWS DataSync](https://aws.amazon.com/datasync/)
* [AWS Direct Connect](https://aws.amazon.com/directconnect/)
* [AWS Directory Service](https://aws.amazon.com/directoryservice/)
* [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/)
* [AWS Elemental MediaConnect](https://aws.amazon.com/mediaconnect/)
* [AWS Firewall Manager](https://aws.amazon.com/firewall-manager/)
* [AWS Global Accelerator](https://aws.amazon.com/global-accelerator/)
* [AWS Glue](https://aws.amazon.com/glue/) AWS Lake Formation
* [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/)
* [AWS IoT Core](https://aws.amazon.com/iot-platform/)
* [AWS IoT Device Management](https://aws.amazon.com/iot-device-management/)
* [AWS IoT Events](https://aws.amazon.com/iot-events/)
* [AWS IoT Greengrass](https://aws.amazon.com/greengrass/)
* [AWS Key Management Service (AWS KMS)](https://aws.amazon.com/kms/)
* [AWS Lambda](https://aws.amazon.com/lambda/)
* [AWS License Manager](https://aws.amazon.com/license-manager/)
* [AWS Managed Services](https://aws.amazon.com/managed-services/)
* [AWS OpsWorks](https://aws.amazon.com/opsworks/)
* [AWS OpsWorks for Chef Automate](https://aws.amazon.com/opsworks/chefautomate/)
* [AWS OpsWorks for Puppet Enterprise](https://aws.amazon.com/opsworks/puppetenterprise/)
* [AWS Organizations](https://aws.amazon.com/organizations/)
* [AWS Resource Groups](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/welcome.html)
* [AWS RoboMaker](https://aws.amazon.com/robomaker/)
* [AWS Secrets Manager](https://aws.amazon.com/secrets-manager/)
* [AWS Security Hub](https://aws.amazon.com/security-hub/)
* [AWS Server Migration Service (AWS SMS)](https://aws.amazon.com/server-migration-service/)
* [AWS Serverless Application Repository](https://aws.amazon.com/serverless/serverlessrepo/)
* [AWS Service Catalog](https://aws.amazon.com/servicecatalog/)
* [AWS Shield](https://aws.amazon.com/shield/)
* [AWS Snowball](https://aws.amazon.com/snowball/)
* [AWS Snowball Edge](https://aws.amazon.com/snowball-edge/)
* [AWS Snowmobile](https://aws.amazon.com/snowmobile/)
* [AWS Step Functions](https://aws.amazon.com/step-functions/)
* [AWS Storage Gateway](https://aws.amazon.com/storagegateway/)
* [AWS Systems Manager](https://aws.amazon.com/systems-manager/)
* [AWS Transfer for SFTP](https://aws.amazon.com/sftp/)
* [AWS WAF](https://aws.amazon.com/waf/)
* [AWS X-Ray](https://aws.amazon.com/xray/)
* [Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/)
* [VM Import/Export](https://aws.amazon.com/ec2/vm-import/)
* [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)

### AWS Compute Services

Here, are Cloud Compute Services offered by Amazon:

1.  **EC2(Elastic Compute Cloud)** - EC2 is a virtual machine in the cloud on which you have OS level control. You can run this cloud server whenever you want.
2.  **LightSail **-This cloud computing tool automatically deploys and manages the computer, storage, and networking capabilities required to run your applications.
3.  **Elastic Beanstalk —** The tool offers automated deployment and provisioning of resources like a highly scalable production website.
4.  **EKS (Elastic Container Service for Kubernetes) — **The tool allows you toKubernetes on Amazon cloud environment without installation.
5.  **AWS Lambda — **ThisAWS service allows you to run functions in the cloud. The tool is a big cost saver for you as you to pay only when your functions execute.

### Migration

Migration services used to transfer data physically between your datacenter and AWS.

1.  **DMS (Database Migration Service)** -DMS service can be used to migrate on-site databases to AWS. It helps you to migrate from one type of database to another — for example, Oracle to MySQL.
2.  **SMS (Server Migration Service)** - SMS migration services allows you to migrate on-site servers to AWS easily and quickly.
3.  **Snowball** — Snowball is a small application which allows you to transfer terabytes of data inside and outside of AWS environment.

### Storage

1.  **Amazon Glacier-** It is an extremely low-cost storage service. It offers secure and fast storage for data archiving and backup.
2.  **Amazon Elastic Block Store (EBS)-** It provides block-level storage to use with Amazon EC2 instances. Amazon Elastic Block Store volumes are network-attached and remain independent from the life of an instance.
3. **Amazon Elasitc File System (EFS)-** provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources. It is built to scale on demand to petabytes without disrupting applications, growing and shrinking automatically as you add and remove files, eliminating the need to provision and manage capacity to accommodate growth.
4.  **AWS Storage Gateway-** This AWS service is connecting on-premises software applications with cloud-based storage. It offers secure integration between the company's on-premises and AWS's storage infrastructure.

### Security Services

1.  **IAM (Identity and Access Management)** —  IAM is a secure cloud security service which helps you to manage users, assign policies, form groups to manage multiple users.
2.  **Inspector** — It is an agent that you can install on your virtual machines, which reports any security vulnerabilities.
3.  **Certificate Manager** — The service offers free SSL certificates for your domains that are managed by Route53.
4.  **WAF (Web Application Firewall)** — WAF security service offers application-level protectionand allows you to block SQL injection and helps you to block cross-site scripting attacks.
5.  **Cloud Directory **— This service allows you to create flexible, cloud-native directories for managinghierarchies of data along multiple dimensions.
6.  **KMS (Key Management Service)** — It is a managed service. This security service helps you to create and control the encryption keyswhich allows you to encrypt your data.
7.  **Organizations** — You can create groups ofAWS accounts using this service to manages security and automation settings.
8.  **Shield** — Shield is managedDDoS (Distributed Denial of Service protection service). It offers safeguards against web applications running on AWS.
9.  **Macie** — It offers a data visibility security service which helps classify and protect your sensitive critical content.
10.  **GuardDuty** —It offers threat detectionto protect your AWS accounts and workloads.

### Database Services

1.  **Amazon RDS-** ThisDatabase AWS service is easy to set up, operate, and scale a relational database in the cloud.
2.  **Amazon DynamoDB-** It is a fast, fully managed NoSQL database service. It is a simple service which allow cost-effective storage and retrieval of data. It also allows you to serve any level of request traffic.
3.  **Amazon ElastiCache-** It is a web service which makes it easy to deploy, operate, and scale an in-memory cache in the cloud.
4.  **Neptune-** It is a fast, reliable and scalable **graph database** service.
5.  **Amazon RedShift - **It is Amazon's data warehousing solution which you can use to perform complex OLAP queries.

### Analytics

1.  **Athena** — This analytics service allows permSQL queries on your S3 bucket to find files.
2.  **CloudSearch** — You should use this AWS service to create a fully managed search engine for your website.
3.  **ElasticSearch** — It is similar to CloudSearch. However, it offers more features like application monitoring.
4.  **Kinesis** — This AWS analytics service helps you to stream and analyzing real-time data at massive scale.
5.  **QuickSight** —It is a business analytics tool. It helps you to create visualizations in a dashboard for data in Amazon Web Services. For example, S3, DynamoDB, etc.
6.  **EMR (Elastic Map Reduce) **—This AWS analytics service mainly used for big data processing like Spark, Splunk, Hadoop, etc.
7.  **Data Pipeline** — Allows you to move data from one place to another. For example from DynamoDB to S3\.

### Management Services

1.  **CloudWatch** — Cloud watch helps you to monitor AWS environments like EC2, RDS instances, and CPU utilization. It also triggers alarms depends on various metrics.
2.  **CloudFormation** — It is a way of turning infrastructure into the cloud. You can use templates for providing a whole production environment in minutes.
3.  **CloudTrail** — It offers an easy method of auditing AWS resources. It helps you to log all changes.
4.  **OpsWorks** — The service allows you to automated Chef/Puppet deployments on AWS environment.
5.  **Config** — This AWS service monitors your environment. The tool sends alerts about changes when you break certain defined configurations.
6.  **Service Catalog **— This service helps large enterprises to authorize which services user will be used and which won't.
7.  **AWS Auto Scaling** — The service allows you to automatically scale your resources up and down based on given CloudWatch metrics.
8.  **Systems Manager **— This AWS service allows you to group your resources. It allows you to identify issues and act on them.
9.  **Managed Services**—It offers management of your AWS infrastructure which allows you to focus on your applications.

### Internet of Things

1.  **IoT Core**— It is a managed cloud AWS service. The service allows connected devices like cars, light bulbs, sensor grids, to securely interact with cloud applications and other devices.
2.  **IoT Device Management **— It allows you to manage your IoT devices at any scale.
3.  **IoT Analytics** — This AWS IOT service is helpful to perform analysis on data collected by your IoT devices.
4.  **Amazon FreeRTOS** — This real-time operating system for microcontrollers helps you to connect IoT devices in the local server or into the cloud.

### Application Services

1.  **Step Functions** — It is a way of visualizing what's going inside your application and what different microservices it is using.
2.  **SWF (Simple Workflow Service)** — The service helps you to coordinate both automated tasks and human-led tasks.
3.  **SNS (Simple Notification Service)** — You can use this service to send you notifications in the form of email and SMS based on given AWS services.
4.  **SQS (Simple Queue Service)** — Use this AWS service to decouple your applications. It is a pull-based service.
5.  **Elastic Transcoder** — This AWS service tool helps you to changes a video's format and resolution to support various devices like tablets, smartphones, and laptops of different resolutions.

### Deployment and Management

1.  **AWS CloudTrail:** The services records AWS API calls and send backlog files to you.
2.  **Amazon CloudWatch:** The tools monitor AWS resources like Amazon EC2 and Amazon RDS DB Instances. It also allows you to monitor custom metrics created by user's applications and services.
3.  **AWS CloudHSM:** This AWS service helps you meet corporate, regulatory, and contractual, compliance requirements for maintaining data security by using the Hardware Security Module(HSM) appliances inside the AWS environment.

### Developer Tools

1.  **CodeStar** — Codestar is a cloud-based service for creating, managing, and working with various software development projects on AWS.
2.  **CodeCommit** —  It is AWS's version control servicewhich allows you tostore your code and other assets privately in the cloud.
3.  **CodeBuild** — This Amazon developer service help you to automates the process of building and compilingyour code.
4.  **CodeDeploy** — It is a way of deploying your code in EC2 instances automatically.
5.  **CodePipeline** — It helps you create a deployment pipeline like testing, building, testing, authentication, deployment on development and production environments.
6.  **Cloud9** —It is an Integrated Development Environment for writing, running, and debugging code in the cloud.

### Mobile Services

1.  **Mobile Hub **— Allows you to add, configure and design features for mobile apps.
2.  **Cognito** — Allows users to signup using his or her social identity.
3.  **Device Farm** — Device farm helps you to improve the quality of apps by quickly testing hundreds of mobile devices.
4.  **AWS AppSync** —It is a fully managed GraphQL service that offers real-time data synchronization and offline programming features.

### Business Productivity

1.  **Alexa for Business** — It empowers your organization with voice, using Alexa. It will help you to Allows you to build custom voice skills for your organization.
2.  **Chime** — Can be used for online meeting and video conferencing.
3.  **WorkDocs** — Helps to store documents in the cloud
4.  **WorkMail** — Allows you to send and receive business emails.

### Desktop & App Streaming

1.  **WorkSpaces** — Workspace is a VDI(Virtual Desktop Infrastructure). It allows you to use remote desktops in the cloud.
2.  **AppStream —** A way ofstreaming desktop applicationsto your users in the web browser. For example, using MS Word in Google Chrome.

### Artificial Intelligence

1.  **Lex** — Lex tool helps you to build chatbots **quickly.**
2.  **Polly** —  It is AWS's text-to-speech service allows you to create audio versions of your notes.
3.  **Rekognition**  — It is AWS's face recognition service. This AWS service helps you to recognize faces and object in images and videos.
4.  **SageMaker** — Sagemaker allows you to build, train, and deploy machine learning models at any scale.
5.  **Transcribe** —  It is AWS's speech-to-text service that offers high-quality and affordable transcriptions.
6.  **Translate** — It is a very similar tool to Google Translate which allows you to translate text in one language to another.

### AR & VR (Augmented Reality & Virtual Reality)

1.  **Sumerian** — Sumerian is a set of tool for offering high-quality virtual reality (VR) experiences on the web. The service allows you to create interactive 3D scenes and publish it as a website for users to access.

### Customer Engagement

1.  **Amazon Connect** — Amazon Connect allows you to create your customer care centerin the cloud.
2.  **Pinpoint** — Pinpoint helps you to understand your users and engage with them.
3.  **SES (Simple Email Service)** — Helps you to send bulkemails to your customers at a relatively cost-effective price.

### Game Development

1.  **GameLift**- It is a service which is managed by AWS. You can use this service to host dedicated game servers. It allows you to scale seamlessly without taking your game offline.
