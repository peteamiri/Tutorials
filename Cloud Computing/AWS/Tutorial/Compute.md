# AWS Cloud Computing

# Summary of Services

here's a table describing the AWS cloud compute services:

| Service Name          | Description                                                                                                                                                  |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amazon Elastic Compute Cloud (EC2) | Amazon EC2 is a web service that provides resizable compute capacity in the cloud. It offers a wide selection of instance types, allowing users to choose the optimal configuration for their applications. EC2 instances can be launched, stopped, and terminated as needed, providing flexibility and scalability. |
| AWS Lambda            | AWS Lambda is a serverless computing service that allows users to run code in response to events without provisioning or managing servers. It automatically scales and manages compute resources, charging only for the compute time consumed by the code. Lambda supports multiple programming languages and integrates with other AWS services. |
| Amazon Elastic Container Service (ECS) | Amazon ECS is a fully managed container orchestration service that allows users to run, manage, and scale Docker containers on AWS. It provides features for deploying, scheduling, and monitoring containerized applications, making it easier to build and operate microservices architectures. ECS integrates with other AWS services such as Elastic Load Balancing and IAM for enhanced functionality. |
| Amazon Elastic Kubernetes Service (EKS) | Amazon EKS is a managed Kubernetes service that allows users to run Kubernetes clusters on AWS without managing the underlying infrastructure. It provides features for deploying, scaling, and managing containerized applications using Kubernetes, an open-source container orchestration platform. EKS integrates with other AWS services such as IAM, VPC, and CloudFormation for seamless integration and enhanced security. |
| AWS Batch             | AWS Batch is a fully managed batch processing service that enables users to run batch computing workloads on AWS. It automatically provisions and scales compute resources based on workload demand, allowing users to focus on building and running batch jobs without managing infrastructure. Batch supports containerized and non-containerized workloads, providing flexibility for different types of batch processing tasks. |
| Amazon Lightsail      | Amazon Lightsail is a simplified virtual private server (VPS) service that allows users to launch and manage virtual private servers in the cloud with ease. It provides pre-configured server templates, networking features, and management tools for building and deploying web applications, websites, and development environments. Lightsail offers predictable pricing and a user-friendly interface, making it ideal for small-scale projects and developers getting started with cloud computing. |
| AWS Outposts          | AWS Outposts is a fully managed service that extends AWS infrastructure and services to customer premises. It allows users to run AWS compute, storage, and database services locally, providing a consistent hybrid cloud experience across on-premises and cloud environments. Outposts supports a wide range of compute instances, storage options, and AWS services, enabling customers to modernize their applications and workflows while maintaining data residency and low-latency requirements. |

These compute services offer a range of capabilities for running applications and workloads in the cloud, catering to different use cases, requirements, and preferences.

AWS offers a variety of compute services that cater to different use cases, ranging from traditional virtual servers to serverless computing. Here's a detailed description of each AWS cloud compute service:

1. **Amazon Elastic Compute Cloud (EC2)**:
   - **Description**: Amazon EC2 is a web service that provides resizable compute capacity in the cloud. It allows users to launch virtual servers, known as instances, with customizable configurations, including CPU, memory, storage, and networking capacity. EC2 instances run on physical servers in AWS data centers and can be easily scaled up or down to meet changing demand. Users have full control over their instances, including the choice of operating system, instance type, and security settings.
   - **Use Cases**: EC2 is suitable for a wide range of use cases, including web hosting, application development, testing, high-performance computing (HPC), and enterprise applications.

2. **Amazon Elastic Container Service (ECS)**:
   - **Description**: Amazon ECS is a fully managed container orchestration service that allows users to run Docker containers on a scalable cluster of EC2 instances. It provides features for deploying, managing, and scaling containerized applications using familiar Docker tools and APIs. ECS supports both Fargate, which is a serverless compute engine for containers, and EC2 launch types, giving users flexibility in how they deploy and manage containers.
   - **Use Cases**: ECS is suitable for deploying and managing microservices architectures, containerized applications, and batch processing workloads.

3. **Amazon Elastic Kubernetes Service (EKS)**:
   - **Description**: Amazon EKS is a managed Kubernetes service that allows users to run Kubernetes clusters on AWS without the need to install, operate, and manage the Kubernetes control plane. It provides features for deploying, managing, and scaling Kubernetes applications using standard Kubernetes APIs and tooling. EKS integrates with other AWS services such as EC2, IAM, and VPC for seamless integration with existing AWS environments.
   - **Use Cases**: EKS is suitable for running containerized applications with Kubernetes orchestration, deploying microservices architectures, and building cloud-native applications.

4. **AWS Lambda**:
   - **Description**: AWS Lambda is a serverless compute service that allows users to run code without provisioning or managing servers. It supports a wide range of programming languages, including Node.js, Python, Java, and .NET, and allows users to upload code and define triggers that automatically execute the code in response to events. Lambda automatically scales the execution environment based on incoming requests and charges users only for the compute time consumed.
   - **Use Cases**: Lambda is suitable for event-driven applications, data processing tasks, real-time stream processing, and building serverless architectures.

5. **AWS Batch**:
   - **Description**: AWS Batch is a fully managed batch processing service that allows users to run batch computing workloads at any scale. It provides features for provisioning compute resources, scheduling jobs, and monitoring job execution, enabling users to efficiently run batch processing jobs without managing infrastructure. Batch integrates with other AWS services such as S3, DynamoDB, and CloudWatch for data storage, job coordination, and monitoring.
   - **Use Cases**: AWS Batch is suitable for running batch processing workloads such as data transformation, ETL (extract, transform, load), scientific simulations, and rendering.

6. **AWS Outposts**:
   - **Description**: AWS Outposts is a fully managed service that extends AWS infrastructure, services, and APIs to customer premises. It allows users to run compute and storage workloads on-premises using the same AWS tools and APIs they use in the cloud. Outposts provides a consistent hybrid cloud experience and enables users to seamlessly integrate on-premises environments with the AWS cloud.
   - **Use Cases**: AWS Outposts is suitable for workloads that require low-latency access to on-premises data or applications, compliance requirements, or data residency regulations.

These AWS cloud compute services offer a range of options for deploying and managing compute resources in the cloud, providing flexibility, scalability, and ease of use for various application workloads and use cases.

## Amazon Elastic Compute Cloud (Amazon EC2)

Amazon Elastic Compute Cloud (EC2) is a web service provided by Amazon Web Services (AWS) that compute capacity in the cloud. It enables users to launch and manage virtual servers, known as instances, to run applications and workloads. EC2 instances are available in a variety of configurations, allowing users to choose the instance type, CPU, memory, storage, and networking capacity that best suits their needs.

Here's a more detailed description of AWS Cloud EC2:

1. **Instance Types**: EC2 offers a wide range of instance types optimized for different use cases, such as general-purpose computing, memory-intensive workloads, compute-optimized applications, storage-optimized tasks, and GPU-accelerated computing.

1. **Operating System Support**: EC2 supports various operating systems, including Amazon Linux, Ubuntu, Windows Server, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and others. Users can choose the desired operating system and customize the instance accordingly.

1. **Pricing Options**: EC2 offers flexible pricing options, including On-Demand Instances, which allow users to pay for compute capacity by the hour with no long-term commitments, Reserved Instances, which offer significant discounts for a one- or three-year commitment, and Spot Instances, which enable users to bid for spare AWS capacity and obtain instances at lower costs.

1. **Security**: EC2 provides features for securing instances, such as security groups, which act as virtual firewalls to control inbound and outbound traffic, and key pairs, which allow users to securely connect to instances using SSH (Secure Shell) for Linux or RDP (Remote Desktop Protocol) for Windows.

1. **Integration with Other AWS Services**: EC2 seamlessly integrates with other AWS services, such as Amazon Elastic Block Store (EBS) for persistent block storage, Amazon Simple Storage Service (S3) for object storage, AWS Identity and Access Management (IAM) for access control, and Amazon Virtual Private Cloud (VPC) for networking.

Overall, AWS Cloud EC2 provides users with the flexibility, scalability, and control they need to deploy and manage virtual servers in the cloud efficiently.

### How to use EC2

Using AWS Cloud EC2 (Elastic Compute Cloud) involves several steps to provision, configure, and manage virtual servers in the cloud. Here's a detailed guide on how to use AWS EC2:

1. **Sign in to the AWS Management Console**:
   - Open your web browser and navigate to the AWS Management Console at https://console.aws.amazon.com/.
   - Sign in with your AWS account credentials.

2. **Navigate to the EC2 Dashboard**:
   - Once logged in, navigate to the EC2 service by either typing "EC2" in the search bar or selecting it from the list of services under "Compute".

3. **Launch an EC2 Instance**:
   - Click on the "Instances" link in the EC2 dashboard to view your existing instances or click on the "Launch Instance" button to launch a new instance.
   - Choose an Amazon Machine Image (AMI) that best suits your requirements. AWS provides various pre-configured AMIs, including popular operating systems like Amazon Linux, Ubuntu, and Windows Server.
   - Select an instance type based on your workload requirements, such as CPU, memory, and storage capacity.
   - Configure instance details, including network settings (VPC, subnet), security groups, and IAM roles.
   - Add storage volumes as needed. You can attach additional EBS (Elastic Block Store) volumes for persistent storage.
   - Configure any additional options, such as instance monitoring, user data scripts, and tags.
   - Review your instance configuration and click "Launch".

4. **Access and Manage Your Instance**:
   - Once the instance is launched, you can view its status and details in the EC2 dashboard under "Instances".
   - To access the instance, you can use SSH (for Linux instances) or Remote Desktop Protocol (RDP) (for Windows instances). Make sure to configure security groups to allow inbound traffic on the necessary ports (e.g., port 22 for SSH, port 3389 for RDP).
   - Connect to your instance using the appropriate credentials (e.g., SSH private key, username/password for RDP).
   - Once connected, you can configure the instance, install software, and deploy applications as needed.
   - Monitor your instance's performance, status, and resource utilization using AWS CloudWatch metrics and logs.

5. **Manage Your Instances**:
   - In the EC2 dashboard, you can perform various management tasks on your instances, such as starting, stopping, rebooting, terminating, and resizing.
   - You can also create AMIs from your instances to capture their configurations and create snapshots of EBS volumes for backup and disaster recovery purposes.

6. **Terminate Instances**:
   - When you no longer need an instance, remember to terminate it to avoid incurring unnecessary costs. You can do this by selecting the instance in the EC2 dashboard and choosing "Instance State" > "Terminate".

7. **Explore Advanced Features**:
   - AWS EC2 offers many advanced features and capabilities, such as auto-scaling groups, load balancers, spot instances, and reserved instances. Explore these features to optimize performance, availability, and cost-efficiency for your workloads.

By following these steps, you can effectively use AWS Cloud EC2 to provision, configure, and manage virtual servers in the cloud to meet your computing needs.

### What is AWS AMI (Amazon Machine Image)

An AWS AMI (Amazon Machine Image) is a template used to create virtual servers, known as EC2 instances, within the Amazon Elastic Compute Cloud (EC2) service. It essentially serves as the foundation for launching instances in the AWS cloud. AMIs contain the operating system, application server, applications, and associated configurations needed to launch an EC2 instance.

Here's a detailed breakdown of AWS AMIs:

1. **Operating System**: The AMI includes the base operating system (OS) that will run on the EC2 instance. This can be a variety of operating systems, such as Amazon Linux, Ubuntu, Windows Server, Red Hat Enterprise Linux, CentOS, Debian, and more. AWS provides a selection of pre-built AMIs for different operating systems, and users can also create custom AMIs based on their specific requirements.

2. **Application Server and Software Stack**: Depending on the use case, the AMI may include additional software components, such as web servers (e.g., Apache, Nginx), application servers (e.g., Tomcat, JBoss), databases (e.g., MySQL, PostgreSQL, SQL Server), development frameworks (e.g., Node.js, Django), and other middleware or runtime environments. These components are pre-installed and pre-configured within the AMI to streamline the deployment process.

3. **Configuration Settings**: AMIs often include default configuration settings for the operating system and installed software. These settings may include network configurations, security settings, user permissions, and other parameters that define the behavior of the EC2 instance. Users can customize these settings during instance launch or by creating custom AMIs with specific configurations.

4. **Security Updates and Patches**: AWS regularly updates and maintains the AMIs to include the latest security updates, patches, and bug fixes for the underlying operating system and software components. This helps ensure that instances launched from AMIs are secure and up-to-date with the latest security patches.

5. **Customization and Versioning**: Users can create custom AMIs by starting with a pre-built AMI and modifying it to suit their specific requirements. This allows users to install additional software, apply custom configurations, and make other changes as needed. AWS also supports versioning of AMIs, allowing users to track and manage multiple versions of their custom AMIs over time.

6. **Public and Private AMIs**: AWS provides a marketplace where users can find and purchase public AMIs created by AWS and third-party vendors. Additionally, users can create private AMIs for their own use or share them with specific AWS accounts or IAM users within their organization.

Overall, AWS AMIs provide a convenient and efficient way to launch EC2 instances with predefined configurations and software stacks, enabling users to deploy applications quickly and consistently in the AWS cloud. They serve as the building blocks for creating virtual servers and play a crucial role in the infrastructure-as-code paradigm, enabling users to define their infrastructure configurations programmatically.

### EC2 Instance Type

AWS offers a wide range of EC2 instance types, each optimized for specific use cases and workloads. These instance types vary in terms of compute power, memory, storage, and networking capabilities. Here's a detailed breakdown of AWS EC2 instance types:

1. **General Purpose Instances**:
   - **Use Case**: General-purpose instances offer a balance of compute, memory, and networking resources and are suitable for a variety of workloads, including web servers, development environments, and small to medium-sized databases.
   - **Instance Types**: Examples include `t2`, `t3`, `m4`, `m5`, `m6g`, and `m6gd` families.

2. **Compute-Optimized Instances**:
   - **Use Case**: Compute-optimized instances provide high-performance computing capabilities and are optimized for CPU-intensive workloads such as batch processing, data analytics, and scientific computing.
   - **Instance Types**: Examples include `c4`, `c5`, `c6g`, and `c6gd` families.

3. **Memory-Optimized Instances**:
   - **Use Case**: Memory-optimized instances are designed to handle memory-intensive workloads such as in-memory databases, caching, and real-time analytics.
   - **Instance Types**: Examples include `r4`, `r5`, `r6g`, and `r6gd` families.

4. **Storage-Optimized Instances**:
   - **Use Case**: Storage-optimized instances are optimized for high-throughput, low-latency storage performance and are suitable for data-intensive applications such as data warehousing, data processing, and distributed file systems.
   - **Instance Types**: Examples include `i3`, `i3en`, `d2`, and `h1` families.

5. **Accelerated Computing Instances**:
   - **Use Case**: Accelerated computing instances feature specialized hardware accelerators such as GPUs (Graphics Processing Units) or FPGAs (Field-Programmable Gate Arrays) and are optimized for compute-intensive tasks such as machine learning, deep learning, graphics rendering, and video encoding.
   - **Instance Types**: Examples include `p3`, `p4`, `g4`, `f1`, and `inf1` families.

6. **Burstable Instances**:
   - **Use Case**: Burstable instances provide a baseline level of performance with the ability to burst above the baseline when needed. They are suitable for workloads with variable CPU utilization patterns and periodic bursts of activity.
   - **Instance Types**: Examples include `t2` and `t3` families.

7. **Graviton Instances**:
   - **Use Case**: Graviton instances are powered by AWS-designed Arm-based processors (AWS Graviton) and offer a cost-effective alternative to traditional x86-based instances. They are suitable for a variety of workloads, including web servers, containerized applications, and microservices.
   - **Instance Types**: Examples include `a1`, `m6g`, `c6g`, `r6g`, and `t4g` families.

Each EC2 instance type comes in different sizes (e.g., small, medium, large) with varying combinations of vCPUs, memory, storage, and network performance. Users can choose the instance type and size that best matches their workload requirements and budget constraints. Additionally, AWS regularly introduces new instance types and sizes to meet evolving customer needs and technological advancements.

### EC2 Pricing Options

AWS EC2 offers several pricing options to accommodate different usage patterns and budgetary considerations. Here are the main EC2 pricing options in detail:

1. **On-Demand Instances**:
   - **Description**: On-Demand Instances allow users to pay for compute capacity by the hour or by the second with no long-term commitments. Users can launch instances when needed and terminate them when they're finished, paying only for the compute time used.
   - **Use Cases**: On-Demand Instances are suitable for applications with short-term, unpredictable workloads, development and testing environments, and applications that require flexibility and scalability.

2. **Reserved Instances (RI)**:
   - **Description**: Reserved Instances provide users with a significant discount (compared to On-Demand pricing) in exchange for a one- or three-year commitment. Users can choose between Standard Reserved Instances, which offer a fixed capacity reservation, and Convertible Reserved Instances, which provide flexibility to change instance attributes such as instance type, operating system, or tenancy.
   - **Use Cases**: Reserved Instances are suitable for applications with steady-state workloads, production environments, and applications with predictable usage patterns. They offer cost savings for long-term commitments and provide capacity assurance.

3. **Spot Instances**:
   - **Description**: Spot Instances allow users to bid for unused AWS EC2 capacity, offering potentially significant cost savings compared to On-Demand pricing. Spot Instances are available at variable prices that fluctuate based on supply and demand dynamics in the AWS cloud. Instances are terminated if the current Spot price exceeds the user's bid price.
   - **Use Cases**: Spot Instances are suitable for fault-tolerant and flexible workloads, batch processing, data analysis, and applications that can tolerate interruptions. They offer the opportunity to access spare capacity at low costs but may not be suitable for mission-critical or time-sensitive workloads.

4. **Dedicated Hosts**:
   - **Description**: Dedicated Hosts allow users to have physical servers dedicated to their use, providing visibility and control over the underlying hardware. Dedicated Hosts offer a flat, hourly rate for hosting EC2 instances on dedicated hardware, with pricing based on the instance type and region.
   - **Use Cases**: Dedicated Hosts are suitable for applications with regulatory or compliance requirements, licensing restrictions, or security concerns. They offer isolation and compliance benefits but may incur higher costs compared to shared infrastructure options.

5. **Savings Plans**:
   - **Description**: Savings Plans offer flexible pricing options that provide significant savings on AWS usage in exchange for committing to a consistent amount of usage (measured in dollars per hour) over a one- or three-year term. Users can choose between Compute Savings Plans, which offer savings on EC2 usage, and EC2 Instance Savings Plans, which offer savings on specific instance families in exchange for a commitment to a consistent instance usage.
   - **Use Cases**: Savings Plans are suitable for users with predictable usage patterns who want to maximize cost savings on their AWS usage. They offer flexibility to adapt to changing workload requirements while providing cost-effective pricing options.

These pricing options provide users with flexibility and cost optimization opportunities, allowing them to choose the most appropriate pricing model based on their usage patterns, budget constraints, and business requirements.
