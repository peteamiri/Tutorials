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

1. **Resizable Compute Capacity**: EC2 allows users to scale compute capacity up or down based on demand. Users can launch one or thousands of instances simultaneously, and they can terminate instances when they are no longer needed.

2. **Instance Types**: EC2 offers a wide range of instance types optimized for different use cases, such as general-purpose computing, memory-intensive workloads, compute-optimized applications, storage-optimized tasks, and GPU-accelerated computing.

3. **Operating System Support**: EC2 supports various operating systems, including Amazon Linux, Ubuntu, Windows Server, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and others. Users can choose the desired operating system and customize the instance accordingly.

4. **Pricing Options**: EC2 offers flexible pricing options, including On-Demand Instances, which allow users to pay for compute capacity by the hour with no long-term commitments, Reserved Instances, which offer significant discounts for a one- or three-year commitment, and Spot Instances, which enable users to bid for spare AWS capacity and obtain instances at lower costs.

5. **Security**: EC2 provides features for securing instances, such as security groups, which act as virtual firewalls to control inbound and outbound traffic, and key pairs, which allow users to securely connect to instances using SSH (Secure Shell) for Linux or RDP (Remote Desktop Protocol) for Windows.

6. **Integration with Other AWS Services**: EC2 seamlessly integrates with other AWS services, such as Amazon Elastic Block Store (EBS) for persistent block storage, Amazon Simple Storage Service (S3) for object storage, AWS Identity and Access Management (IAM) for access control, and Amazon Virtual Private Cloud (VPC) for networking.

To use AWS Cloud EC2, users typically follow these steps:

1. **Sign Up for AWS**: Users need to sign up for an AWS account if they haven't already done so.

2. **Access the AWS Management Console**: Users can access the AWS Management Console, a web-based interface provided by AWS, to manage EC2 instances and other AWS services.

3. **Launch EC2 Instances**: In the EC2 dashboard, users can launch instances by selecting the desired instance type, AMI (Amazon Machine Image), and other configuration options. They can also choose the region and availability zone where they want to deploy the instances.

4. **Configure Security**: Users can configure security groups to control inbound and outbound traffic to their instances and manage key pairs for secure access.

5. **Connect to Instances**: Once the instances are running, users can connect to them using SSH or RDP and start using them to run applications, host websites, perform data processing tasks, or any other use case.

6. **Monitor and Manage Instances**: Users can monitor the performance and health of their instances using AWS CloudWatch, set up alarms for automated alerts, and manage instances using AWS APIs or command-line tools.

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
