# Azure fundamentals

Azure, often referred to as Microsoft Azure, is a cloud computing platform and service offered by Microsoft. It provides a wide range of cloud-based services, including computing, storage, databases, networking, analytics, machine learning, and more. Azure is one of the major players in the cloud computing industry, alongside Amazon Web Services (AWS) and Google Cloud Platform (GCP).

Here are some key components and services offered by Azure:

1. **Virtual Machines (VMs)**: Azure allows you to create and manage virtual machines in the cloud. These VMs can run Windows or Linux and can be used for various purposes, such as hosting web applications, running databases, or performing data analysis.

1. **Azure App Service**: This platform-as-a-service (PaaS) offering enables you to build, deploy, and scale web applications and APIs quickly.

1. **Azure Blob Storage**: It provides scalable object storage for unstructured data, such as images, videos, and documents.

1. **Azure SQL Database**: A fully managed relational database service that is compatible with SQL Server. It's suitable for hosting applications that require a relational database.

1. **Azure Kubernetes Service (AKS)**: A managed Kubernetes container orchestration service for deploying, managing, and scaling containerized applications.

1. **Azure Functions**: A serverless compute service that allows you to run code in response to events without having to manage infrastructure.

1. **Azure Active Directory**: A cloud-based identity and access management service that helps you manage user identities and secure access to resources.

1. **Azure DevOps**: A set of development tools and services for software development, including version control, build automation, and release management.

1. **Azure AI and Machine Learning**: Azure provides various services for building, training, and deploying machine learning models and AI applications.

1. **Azure Networking**: This includes services like Virtual Network (VNet), Azure Load Balancer, and Azure VPN Gateway, which help you create and manage network infrastructure in the cloud.

1. **Azure Security Center**: A unified security management system that helps you protect your Azure resources.

1. **Azure IoT (Internet of Things)**: Provides tools and services for building and managing IoT applications and devices.

1. **Azure Synapse Analytics**: A big data and data warehousing service that enables data integration and analytics at scale.

1. **Azure Cosmos DB**: A globally distributed, multi-model database service designed for high availability and low latency.

1. **Azure Functions**: A serverless compute service that allows you to run code in response to events without having to manage infrastructure.

These are just a few examples of the many services and solutions available on the Azure cloud platform. Azure is known for its flexibility, scalability, and integration with Microsoft products, making it a popular choice for businesses of all sizes looking to leverage cloud computing to meet their IT needs.


azure cloud

Azure Cloud, also known as Microsoft Azure, is a comprehensive cloud computing platform provided by Microsoft. It offers a wide array of cloud services, tools, and solutions for building, deploying, and managing various types of applications and services. Azure is used by organizations and developers for a variety of purposes, including hosting websites and web applications, running virtual machines, storing and analyzing data, and much more.

Here are some key aspects of Azure Cloud:

Infrastructure as a Service (IaaS): Azure provides virtual machines (VMs) that you can use to run your own software, giving you control over the underlying infrastructure.

Platform as a Service (PaaS): Azure offers platforms and services for developers to build, deploy, and scale applications without worrying about the underlying infrastructure. This includes services like Azure App Service and Azure Functions.

Containers and Orchestration: Azure supports containerization technologies like Docker and Kubernetes, making it easier to manage and deploy containerized applications at scale with services like Azure Kubernetes Service (AKS).

Serverless Computing: Azure Functions allows you to run code in a serverless environment, where you pay only for the resources used during execution.

Storage: Azure provides various storage options, including Azure Blob Storage for object storage, Azure Files for file shares, and Azure SQL Database for relational data storage.

Databases: You can use Azure for various database solutions, such as Azure SQL Database for relational databases, Azure Cosmos DB for NoSQL databases, and Azure Database for PostgreSQL, MySQL, and more.

Networking: Azure offers a range of networking services, including Azure Virtual Network for creating isolated network environments, Azure Load Balancer for distributing traffic, and Azure VPN Gateway for secure connections.

Security and Identity: Azure offers robust security features and identity management through services like Azure Active Directory and Azure Security Center.

AI and Machine Learning: Azure provides tools and services for building, training, and deploying machine learning models and AI applications.

IoT (Internet of Things): Azure IoT services enable you to connect, monitor, and manage IoT devices and collect data from them.

Analytics and Big Data: Azure offers services like Azure Data Lake Storage and Azure Synapse Analytics for processing and analyzing large datasets.

DevOps and Dev/Test Environments: Azure DevOps and Azure DevTest Labs help streamline the development and testing of applications.

Hybrid Solutions: Azure supports hybrid cloud scenarios, allowing you to integrate on-premises infrastructure with the Azure cloud.

Global Reach: Azure has data centers located around the world, providing a global presence for your applications and services.

Cost Management: Azure provides tools and features for managing and optimizing your cloud spending.

Microsoft Azure is a popular choice for organizations of all sizes due to its scalability, flexibility, and integration with Microsoft products. It caters to a wide range of industries and use cases, making it a versatile cloud platform for various business needs.

# Azure Shared Responsibility Model

The **Azure Shared Responsibility Model** is a concept in cloud computing that outlines the division of security and compliance responsibilities between the cloud service provider (Microsoft Azure) and the customer. Understanding this model is essential for ensuring the security and compliance of your applications and data in the Azure cloud environment.

## Microsoft's Responsibility (Cloud Service Provider)

- **Physical Infrastructure:** Microsoft is responsible for securing and maintaining the physical data centers, servers, networking equipment, and other hardware components.

- **Hypervisor Security:** Microsoft manages the virtualization infrastructure and ensures the security of the hypervisor used for creating and managing virtual machines.

- **Network Infrastructure:** Microsoft is responsible for the security and maintenance of the network infrastructure connecting data centers.

- **Azure Platform Security:** Microsoft ensures the security, availability, scalability, and integrity of Azure services.

- **Azure Compliance Certifications:** Microsoft obtains various compliance certifications and conducts audits to ensure Azure complies with industry standards and regulations.

## Customer's Responsibility

- **Data and Application Security:** Customers are responsible for securing their own data, applications, and workloads hosted on Azure. This includes configuring firewalls, access controls, and encryption.

- **Identity and Access Management (IAM):** Customers must manage user access to Azure resources, including setting up role-based access control (RBAC) and implementing strong authentication mechanisms.

- **Operating System and Software Patching:** Customers are responsible for keeping operating systems, applications, and software on Azure virtual machines up-to-date with security patches.

- **Data Encryption:** Customers must encrypt data at rest and in transit using Azure-provided encryption tools and best practices.

- **Security Monitoring and Logging:** Implementing security monitoring and logging solutions to detect and respond to security threats and incidents within the Azure environment is the customer's responsibility.

- **Compliance:** Customers are responsible for ensuring that their applications and data comply with industry-specific regulations and standards. Microsoft provides tools and services to assist with compliance, but customers must configure and monitor these controls.

- **Backup and Disaster Recovery:** Customers should implement backup and disaster recovery solutions to protect against data loss and ensure business continuity.

The specific division of responsibilities may vary depending on the Azure services used and the deployment model (IaaS, PaaS, or SaaS). It's crucial for organizations using Azure to understand and fulfill their responsibilities within this shared responsibility model.


## Cloud Service Models

Cloud computing offers various service models that define how cloud resources are provisioned and managed. The three primary cloud service models are **Infrastructure as a Service (IaaS)**, **Platform as a Service (PaaS)**, and **Software as a Service (SaaS)**. Each model offers a different level of control and management for users and organizations.

#### Infrastructure as a Service (IaaS)

IaaS provides the fundamental building blocks of cloud infrastructure, allowing users to provision virtualized computing resources over the internet. In an IaaS model:

- Users have control over virtual machines, storage, and networking components.
- They are responsible for managing the operating system, applications, and data hosted on virtual machines.
- IaaS is suitable for users who require full control and flexibility to configure and manage their infrastructure.

Common IaaS providers include Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

#### Platform as a Service (PaaS)

PaaS abstracts the underlying infrastructure and provides a platform for developers to build, deploy, and manage applications without worrying about hardware or operating system management. In a PaaS model:

- Users focus on writing and deploying code, while the cloud provider handles infrastructure and runtime environment management.
- PaaS is ideal for developers looking to streamline the development and deployment process without infrastructure management complexities.

Popular PaaS offerings include Azure App Service, Google App Engine, and Heroku.

#### Software as a Service (SaaS)

SaaS delivers software applications over the internet, enabling users to access and use software without the need for installation or maintenance. In a SaaS model:

- Users can access applications through web browsers or dedicated clients.
- The cloud provider manages all aspects of the application, including infrastructure, maintenance, and updates.
- SaaS is suitable for end-users and organizations looking for ready-to-use software solutions.

Examples of SaaS applications include Microsoft 365, Salesforce, and Dropbox.

#### Hybrid and Multi-Cloud Deployments

Many organizations adopt hybrid cloud or multi-cloud strategies, combining different service models and cloud providers to meet their specific needs. Hybrid cloud involves integrating on-premises infrastructure with cloud services, while multi-cloud leverages multiple cloud providers to avoid vendor lock-in and enhance redundancy.

Understanding these cloud service models helps organizations choose the right approach to meet their requirements, whether it's full control over infrastructure (IaaS), streamlined development (PaaS), or ready-to-use software (SaaS).

## Cloud Deployment Models

Cloud computing offers various deployment models that define how cloud resources are hosted, managed, and accessed. These deployment models cater to different needs, ranging from full cloud adoption to on-premises infrastructure integration. The primary cloud deployment models are **Public Cloud**, **Private Cloud**, **Hybrid Cloud**, and **Multi-Cloud**.

#### Public Cloud

In a **Public Cloud** deployment:

- Cloud resources and services are owned and operated by a third-party cloud service provider, such as Amazon Web Services (AWS), Microsoft Azure, or Google Cloud Platform (GCP).
- These resources are made available to the public over the internet, and multiple customers share the same infrastructure.
- Users pay for the services they consume on a pay-as-you-go basis, avoiding upfront capital expenses.
- Public clouds offer scalability, flexibility, and rapid provisioning of resources.
- They are suitable for organizations seeking cost-effective, easily scalable, and globally accessible cloud services.

#### Private Cloud

In a **Private Cloud** deployment:

- Cloud resources are dedicated to a single organization or entity, either on-premises or hosted by a third-party provider.
- The organization has full control over the infrastructure, security, and management of the private cloud environment.
- Private clouds provide greater customization, security, and compliance options.
- They are ideal for organizations with specific regulatory or security requirements, or those needing complete control over their cloud infrastructure.

#### Hybrid Cloud

A **Hybrid Cloud** deployment combines elements of both public and private clouds:

- Organizations maintain a combination of on-premises infrastructure (private cloud) and public cloud services.
- Data and applications can be moved between the two environments, providing flexibility and scalability.
- Hybrid clouds enable organizations to take advantage of public cloud resources while retaining control over critical data and applications.
- They are suitable for businesses with fluctuating workloads, data sensitivity, or legacy systems.

#### Multi-Cloud

A **Multi-Cloud** deployment involves using services from multiple cloud providers:

- Organizations use different cloud service providers for various applications, workloads, or geographic regions.
- Multi-cloud strategies reduce vendor lock-in and enhance redundancy and resilience.
- They offer flexibility in choosing the best-fit services for specific needs.
- Multi-cloud can involve both public and private cloud providers.
- Organizations must manage and integrate resources across multiple providers effectively.

Choosing the right cloud deployment model depends on an organization's goals, requirements, and existing infrastructure. Some organizations may even combine multiple deployment models to create a customized cloud strategy that meets their unique needs.

## Multi-Tenant Environment

A **multi-tenant environment** is a computing or software architecture in which a single instance of an application or system serves multiple independent users or organizations, known as tenants. In this shared model, each tenant has its own isolated and secure space within the same application or infrastructure. Multi-tenancy is a common approach in cloud computing and software-as-a-service (SaaS) platforms.

### Key Characteristics of Multi-Tenancy

1. **Shared Resources:** Multiple tenants share the same underlying resources, such as servers, databases, and infrastructure components. These resources are partitioned and isolated to ensure data privacy and security.

2. **Isolation:** Tenants are logically isolated from one another, meaning that one tenant's data and operations are kept separate from those of other tenants. This isolation prevents one tenant from accessing or affecting the data of another.

3. **Customization:** Multi-tenant systems often allow tenants to customize certain aspects of their environment, such as branding, configuration, and user settings. However, customization is typically limited to maintain system integrity.

4. **Economies of Scale:** Multi-tenancy allows providers to achieve economies of scale, as they can serve multiple tenants from a single shared infrastructure, reducing operational costs for both providers and tenants.

5. **Resource Efficiency:** Resources are allocated dynamically based on the needs of each tenant. This ensures efficient resource utilization and scalability as tenants can use more resources as their requirements grow.

6. **Security and Compliance:** Robust security measures are in place to protect tenant data and ensure compliance with data privacy regulations. Access controls and encryption are commonly used to enhance security.

7. **Maintenance and Updates:** Providers are responsible for system maintenance, updates, and ensuring high availability. Tenants benefit from automatic updates without the burden of managing infrastructure.

### Use Cases for Multi-Tenancy

Multi-tenancy is prevalent in various industries and applications:

- **SaaS Applications:** Many software-as-a-service providers use multi-tenancy to serve multiple customers with a single instance of their software, reducing operational costs and simplifying software management.

- **Cloud Computing:** Public cloud providers offer multi-tenant infrastructure where multiple customers can provision virtual machines, storage, and other resources on shared hardware.

- **Enterprise IT:** Large organizations often implement multi-tenant architectures for their internal applications and services to optimize resource utilization and reduce costs.

- **Managed Hosting:** Hosting providers may use multi-tenancy to offer shared hosting services to multiple website owners, each with their own isolated web space.

Multi-tenant environments offer cost-efficiency, scalability, and streamlined management, making them a popular choice for cloud services and SaaS applications. However, ensuring proper data isolation, security, and compliance is crucial in these environments to maintain the trust of tenants and protect their data.

# Advantages of Multi-Tenancy in Cloud Computing

Multi-tenancy is a key architectural approach in cloud computing that offers several advantages for both cloud providers and tenants (users or organizations). This shared model, where a single instance of an application or system serves multiple independent tenants, brings forth numerous benefits:

## 1. Cost Efficiency

- **Resource Sharing:** Multi-tenancy allows multiple tenants to share the same underlying infrastructure and resources, leading to more efficient resource utilization. This shared approach reduces overall infrastructure and operational costs.

- **Economies of Scale:** Cloud providers can leverage economies of scale, as they serve numerous tenants from a single infrastructure. This enables them to offer services at a lower cost per tenant.

## 2. Scalability

- **Dynamic Resource Allocation:** Multi-tenant systems can dynamically allocate resources based on the needs of each tenant. Tenants can easily scale their resource usage up or down as their requirements change, ensuring optimal performance without overprovisioning.

## 3. Simplified Management

- **Centralized Maintenance:** Cloud providers are responsible for system maintenance, updates, and ensuring high availability. This relieves tenants of the burden of managing infrastructure, allowing them to focus on their core business functions.

## 4. Rapid Deployment

- **Quick Onboarding:** Tenants can quickly onboard and start using cloud services without the need for extensive setup or configuration. This speeds up the time-to-market for applications and services.

## 5. Resource Efficiency

- **Efficient Use of Resources:** Resources are allocated dynamically, and unused resources can be repurposed for other tenants as needed. This results in optimal resource utilization and reduces waste.

## 6. Customization and Flexibility

- **Tenant Customization:** Multi-tenant systems often allow tenants to customize certain aspects of their environment, such as branding and configuration. This provides a degree of flexibility while maintaining system integrity.

## 7. Collaboration and Sharing

- **Collaboration Tools:** Multi-tenancy is conducive to collaboration among tenants. It allows multiple organizations or users to work together on shared projects and data securely.

## 8. High Availability

- **Redundancy:** Multi-tenant systems are designed with redundancy and failover mechanisms to ensure high availability. Tenants benefit from reliable access to their services and data.

## 9. Security and Compliance

- **Security Measures:** Multi-tenant environments implement robust security measures, such as access controls and encryption, to protect tenant data and ensure compliance with data privacy regulations.

## 10. Global Reach

- **Global Accessibility:** Multi-tenant cloud services are accessible from anywhere with an internet connection. This global reach is valuable for organizations with distributed teams or a global customer base.

In summary, multi-tenancy in cloud computing offers numerous advantages, including cost efficiency, scalability, simplified management, rapid deployment, resource efficiency, customization, collaboration opportunities, high availability, security, and global accessibility. These benefits make multi-tenancy a compelling choice for both cloud providers and tenants looking to optimize their cloud computing experience.

# Disadvantages of Multi-Tenancy in Cloud Computing

While multi-tenancy offers numerous benefits, it also comes with some disadvantages and challenges that organizations need to consider when adopting this model:

## 1. Security and Data Privacy

- **Data Isolation:** Ensuring complete data isolation between tenants can be challenging. A security breach or misconfiguration could potentially expose one tenant's data to others.

- **Compliance Concerns:** Different tenants may have varying compliance requirements, making it complex to maintain compliance standards across the entire multi-tenant environment.

## 2. Performance Variability

- **Noisy Neighbor Effect:** In a multi-tenant environment, the performance of one tenant's applications or workloads can impact the performance of others. If one tenant consumes excessive resources, it can lead to performance degradation for neighboring tenants.

## 3. Customization Limitations

- **Limited Customization:** While multi-tenant systems often allow for some level of customization, they may have limitations in terms of the extent to which tenants can modify the environment to suit their specific needs.

## 4. Vendor Lock-In

- **Dependency on the Provider:** Tenants may become dependent on the cloud provider's ecosystem and services, making it challenging to migrate to a different provider or back to on-premises infrastructure.

## 5. Upgrade and Maintenance Synchronization

- **Forced Upgrades:** Tenants may be forced to accept system upgrades and maintenance schedules determined by the cloud provider, potentially causing disruptions to their operations.

## 6. Limited Control

- **Reduced Control:** Tenants have less control over the underlying infrastructure, making it challenging to implement highly customized or specialized configurations.

## 7. Incompatibility with Legacy Systems

- **Integration Challenges:** Integrating legacy systems with a multi-tenant cloud environment can be complex and may require substantial modifications to existing systems.

## 8. Resource Allocation

- **Resource Allocation:** Balancing resource allocation among tenants can be difficult. Overprovisioning or underprovisioning resources for specific tenants can result in inefficiencies.

## 9. Complexity of Multi-Cloud and Hybrid Scenarios

- **Complex Management:** In multi-cloud and hybrid cloud scenarios where tenants use multiple cloud providers or combine on-premises and cloud resources, managing and orchestrating resources across different environments can be complex.

## 10. Service Provider Dependency

- **Service Provider Reliability:** Tenants rely on the reliability and uptime of the cloud service provider. Downtime or service interruptions on the provider's end can affect tenants' operations.

In conclusion, while multi-tenancy offers significant advantages in terms of cost efficiency, scalability, and resource optimization, organizations must carefully consider these disadvantages and challenges, particularly in areas such as security, performance, customization, and dependency on the service provider, when planning their cloud adoption strategy.

# Cloud Consumption-Based Cost Model

The **cloud consumption-based cost model** is a billing and pricing approach used by cloud service providers, such as Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP), to charge customers for their usage of cloud resources.

This model is also commonly referred to as **pay-as-you-go** or **pay-per-use** pricing.

## Key Characteristics

1. **Usage-Based Billing:** In a consumption-based cost model, customers are billed based on the actual usage of cloud resources. They pay for the compute, storage, network, and other resources they consume, typically on an hourly or per-minute basis.

2. **No Upfront Costs:** Unlike traditional IT infrastructure, which often requires substantial upfront capital expenditures, consumption-based pricing eliminates the need for significant upfront investments. Customers only pay for what they use.

3. **Scalability:** The consumption-based model allows customers to scale their resources up or down as needed. They can provision additional resources during peak usage and de-provision them during periods of lower demand.

4. **Resource Flexibility:** Customers have the flexibility to choose from a wide range of cloud services and resource types, such as virtual machines, databases, storage, and more. They can select the resources that best meet their specific requirements.

5. **Cost Transparency:** Cloud providers typically offer tools and dashboards that provide real-time visibility into resource usage and associated costs. This transparency enables customers to monitor and optimize their spending.

6. **Automatic Scaling:** Many cloud services can automatically scale resources based on demand, helping customers maintain performance while minimizing costs. This is often referred to as auto-scaling.

7. **Geographic Reach:** Consumption-based pricing is available globally, allowing customers to deploy resources in data centers around the world and pay for resources in the regions where they are used.

## Benefits

- **Cost Efficiency:** Organizations can optimize costs by paying only for the resources they use, avoiding overprovisioning and underutilization of infrastructure.

- **Flexibility:** Customers have the flexibility to experiment with different services and configurations without committing to long-term contracts.

- **Elasticity:** Businesses can quickly respond to changing workloads by scaling resources up or down as needed, ensuring consistent performance.

- **Cost Transparency:** Real-time cost tracking and management tools help organizations understand and control their cloud spending.

- **Lower Entry Barrier:** Small businesses and startups benefit from reduced upfront costs, enabling them to access enterprise-level infrastructure without a significant financial burden.

## Considerations

- **Cost Monitoring:** Organizations must actively monitor their resource usage and costs to avoid unexpected bills. Effective cost management practices are essential.

- **Resource Optimization:** Continuous optimization of resources is necessary to ensure cost-effectiveness, as cloud bills can increase if resources are not used efficiently.

- **Budgeting:** Budgeting and forecasting cloud costs are crucial for managing expenses effectively and avoiding budget overruns.

- **Data Transfer Costs:** Data transfer between regions or over the internet may incur additional charges, and organizations should be aware of these costs.

In summary, the cloud consumption-based cost model offers organizations the advantages of cost efficiency, scalability, flexibility, and cost transparency. However, effective cost monitoring and optimization practices are essential to fully realize the benefits of this pricing model.

# Benefits of Microsoft Azure Cloud

Microsoft Azure is a leading cloud computing platform that offers a wide range of services and solutions to help organizations meet their IT and business needs. Here are some key benefits of using Microsoft Azure:

## 1. Scalability and Flexibility

- **Elasticity:** Azure allows you to quickly scale up or down based on your workload requirements. This flexibility ensures that you have the right amount of resources when you need them, optimizing cost and performance.

- **Wide Range of Services:** Azure provides a comprehensive set of services, including virtual machines, databases, AI and machine learning tools, IoT services, and more, enabling you to build and scale applications of varying complexity.

## 2. Global Reach

- **Global Data Center Presence:** Azure has data centers located in regions around the world. This global reach allows you to deploy your applications and services closer to your users for reduced latency and improved performance.

- **Availability Zones:** Azure offers availability zones and paired regions to ensure high availability and disaster recovery capabilities for your critical workloads.

## 3. Security and Compliance

- **Advanced Security:** Azure provides robust security features, including identity and access management (Azure Active Directory), threat detection (Azure Security Center), and encryption at rest and in transit.

- **Compliance Certifications:** Azure complies with numerous industry standards and regulations, making it suitable for organizations with strict compliance requirements.

## 4. Integration with Microsoft Products

- **Seamless Integration:** Azure integrates seamlessly with other Microsoft products and services, such as Windows Server, SQL Server, and Microsoft 365, making it an attractive choice for organizations already using Microsoft technologies.

- **Azure DevOps:** Azure offers a suite of DevOps tools and services for building, testing, and deploying applications, enhancing collaboration between development and IT operations teams.

## 5. Cost Management

- **Pay-as-You-Go Pricing:** Azure follows a consumption-based pricing model, allowing you to pay only for the resources and services you use. This can lead to cost savings compared to traditional IT infrastructure.

- **Cost Management Tools:** Azure provides cost management and optimization tools to help you monitor and control your cloud spending effectively.

## 6. Innovation and AI

- **AI and Machine Learning:** Azure offers a wide range of AI and machine learning services, enabling organizations to build intelligent applications and make data-driven decisions.

- **Innovation:** Azure continually introduces new features and services to keep pace with technological advancements, allowing you to leverage the latest innovations in cloud computing.

## 7. Hybrid Capabilities

- **Hybrid Cloud:** Azure supports hybrid cloud scenarios, allowing you to seamlessly integrate on-premises infrastructure with Azure cloud services. This enables hybrid cloud flexibility and migration options.

- **Azure Arc:** Azure Arc extends Azure's management and governance capabilities to on-premises and multi-cloud environments, providing a unified management experience.

## 8. Developer-Friendly

- **Developer Tools:** Azure provides a rich set of development tools and services, including Azure DevOps, Visual Studio integration, and support for various programming languages, making it developer-friendly.

These benefits make Microsoft Azure a powerful and versatile cloud platform for organizations of all sizes, helping them innovate, scale, and meet their business goals efficiently and securely.
