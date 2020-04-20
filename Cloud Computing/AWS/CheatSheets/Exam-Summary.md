# Exam Summary

I recently cleared the AWS Certified Advanced Networking – Speciality (ANS-C00), which was my first, enroute my path to the AWS Speciality certifications. Frankly, I feel the time I gave for preparation was still not enough, but I just about managed to get through. So a word of caution, this exam is inline or more tough than the professional exam especially for the reason that the Networking concepts it covers are not something you can get your hands dirty with easily.

AWS Certified Advanced Networking – Speciality (ANS-C00) exam is the focusing on the AWS Networking concepts. It basically validates

*   Design, develop, and deploy cloud-based solutions using AWS
    Implement core AWS services according to basic architecture best practices
*   Design and maintain network architecture for all AWS services
*   Leverage tools to automate AWS networking tasks

Refer to [AWS Certified Advanced Networking – Speciality Exam Guide](https://d1.awsstatic.com/training-and-certification/eligibilityupdates/AWS%20Certified%20Advanced%20Networking%20-%20Speciality_Exam_Guide_v1.2_FINAL.pdf)


### AWS Certified Advanced Networking – Speciality (ANS-C00) Exam Summary

*   AWS Certified Advanced Networking – Speciality exam covers a lot of Networking concepts like VPC, VPN, Direct Connect, Route 53, ALB, NLB.
*   One of the key tactic I followed when solving the DevOps Engineer questions was to read the question and use paper and pencil to draw a rough architecture and focus on the areas that you need to improve. Trust me, you will be able eliminate 2 answers for sure and then need to focus on only the other two. Read the other 2 answers to check the difference area and that would help you reach to the right answer or atleast have a 50% chance of getting it right.
*   Be sure to cover the following topics
    *   **Networking & Content Delivery**
        *   You should know everything in Networking.
        *   Understand VPC in depth
            *   Understand [VPC](//jayendrapatil.com/aws-virtual-private-cloud-vpc/), Subnets
            *   Know that [AWS allows you to extend your VPC by adding a secondary VPC](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html#vpc-resize) (_hint: focus on the IP limitations that you can assign to a created VPC_)
            *   Understand [Security Groups, NACLs](//jayendrapatil.com/aws-vpc-security-group-vs-nacls/) (_Hint : know NACLs are stateless and how it is reflected in_ [_VPC Flow Logs_](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html#flow-log-records))
            *   Understand [DHCP Option Sets](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_DHCP_Options.html) esp. how to resolve DNS from both on-premises data center and AWS.
            *   Understand [VPC Peering](//jayendrapatil.com/aws-vpc-peering/), configuration and its limitations (_Hint: try it yourself esp. cross account ones to know whats needed_)
            *   Understand [Placement Groups](//jayendrapatil.com/aws-ec2-placement-groups/), [Enhanced Networking](//jayendrapatil.com/aws-ec2-enhanced-networking/)
            *   Understand [VPC Endpoints](//jayendrapatil.com/aws-vpc-endpoints/) esp. services supported by Gateway and Interface Endpoints. Interface Endpoints are also called Private Links.
            *   Know [Transit VPC](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/transit-vpc.html) and its use case
            *   Know [CloudHub](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-vpn-cloudhub-network-to-amazon.html) and its use case
        *   [Virtual Private Network](//jayendrapatil.com/aws-vpc-vpn-cloudhub/) to establish connectivity between on-premises data center and AWS VPC
        *   [Direct Connect](//jayendrapatil.com/aws-direct-connect-dx/) to establish connectivity between on-premises data center and AWS VPC and Public Services
            *   Make sure you understand Direct Connect in detail, without this you cannot clear the exam
            *   Understand Direct Connect connections – Dedicated and Hosted connections
            *   Understand how to [create a Direct Connect connection](https://docs.aws.amazon.com/directconnect/latest/UserGuide/WorkingWithConnections.html) (_hint: LOA-CFA provides the details for partner to connect to AWS_ _Direct Connect location_)
            *   Understand [virtual interfaces](https://docs.aws.amazon.com/directconnect/latest/UserGuide/WorkingWithVirtualInterfaces.html) options – Private Virtual Interface for VPC resources and Public Virtual Interface for Public resources
            *   Understand [setup Private and Public VIF](https://docs.aws.amazon.com/directconnect/latest/UserGuide/create-vif.html)
            *   Understand Route Propagation, [propagation priority](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPNRoutingTypes.html), BGP connectivity
            *   Understand High Availability options based on cost and time i.e. Second Direct Connect connection OR VPN connection
            *   Understand Direct Connect Gateway – it provides a way to connect to multiple VPCs from on-premises data center using the same Direct Connect connection
        *   Route 53
            *   Understand [Route 53](//jayendrapatil.com/aws-route-53/) and [Routing Policies](//jayendrapatil.com/aws-route-53-routing-policy/) and their use cases Focus on Weighted, Latency routing policies
            *   Understand Route 53 [Split View DNS](https://aws.amazon.com/premiumsupport/knowledge-center/internal-version-website/) to have the same DNS to access a site externally and internally
        *   Understand [CloudFront](//jayendrapatil.com/aws-cloudfront/) and use cases
        *   Load Balancer
            *   Understand [ELB](//jayendrapatil.com/aws-elb-network-load-balancer/), [ALB](//jayendrapatil.com/aws-elb-application-load-balancer/) and [NLB](//jayendrapatil.com/aws-elb-network-load-balancer/) 
            *   Understand the difference ELB, ALB and NLB _esp. ALB provides Content, Host and Path based Routing while NLB provides the ability to have static IP address_
            *   Know how to design VPC CIDR block with NLB (_Hint – minimum number of IPs required are 8_)
            *   Know how to pass original Client IP to the backend instances (_Hint – X-Forwarded-for and Proxy Protocol_)
        *   Know [WorkSpaces](//jayendrapatil.com/aws-workspace/) requirements and setup
    *   **Security**
        *   Know [AWS GuardDuty](https://aws.amazon.com/guardduty/faqs/) as managed threat detection service
        *   Know [AWS Shield](https://aws.amazon.com/shield/faqs/) esp. the Shield Advanced option and the features it provides
        *   Know [WAF](//jayendrapatil.com/aws-waf/) as Web Traffic Firewall – _(Hint – WAF can be attached to your CloudFront, Application Load Balancer, API Gateway to dynamically detect and prevent attacks)_
    *   **Monitoring & Management Tools**
        *   Understand AWS [CloudFormation](//jayendrapatil.com/aws-cloudformation/) esp. in terms of Network creation. (_Hint – Know Custom resources can be used to handle activities not supported by AWS_)
        *   Understand [CloudTrail](//jayendrapatil.com/aws-cloudtrail/) for audit and governance
        *   Understand [AWS Config](//jayendrapatil.com/aws-config/) and its use case
    *   **Integration Tools**
        *   Know how CloudWatch integration with [SNS](//jayendrapatil.com/aws-sns-simple-notification-service/) and [Lambda](//jayendrapatil.com/aws-lambda/) can help in notification (Topics are not required to be in detail)
    *   Whitepapers and articles
        *   [AWS Network Connectivity Options](//jayendrapatil.com/aws-network-connectivity-options/)
        *   [AWS Certification – Networking Services – Cheat Sheet](//jayendrapatil.com/aws-certification-networking-services-cheat-sheet/)
        *   [AWS Certification – Security & Identity Services – Cheat Sheet](//jayendrapatil.com/aws-certification-security-identity-services-cheat-sheet/)
        *   [AWS VPC Connectivity Options](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/introduction.html)
        *   [AWS Single Region Multi VPC Connectivity](https://aws.amazon.com/answers/networking/aws-single-region-multi-vpc-connectivity/)
        *   [AWS Multiple VPC VPN Connection Sharing](https://aws.amazon.com/answers/networking/aws-multiple-vpc-vpn-connection-sharing/)
        *   [DNS Resolution between On-premises and AWS](https://aws.amazon.com/blogs/security/how-to-set-up-dns-resolution-between-on-premises-networks-and-aws-by-using-unbound/)

## AWS Certified Advanced Networking – Speciality (ANS-C00) Exam Resources

*   Online Courses
    *   Zeal Vora – [AWS Certified Advanced Networking – Specialty 2020](https://www.udemy.com/course/aws-certified-advanced-networking-specialty/?couponCode=AWSJROCKS-MAR-2020)
    *   Linux Academy – [AWS Certified Advanced Networking – Speciality](https://linuxacademy.com/amazon-web-services/training/course/name/aws-advanced-networking-specialty) [**Recommended**] Although it does not cover all the topics
*   Practice tests
    *   Braincert [AWS Certified Advanced Networking – Speciality Practice Exams](https://www.braincert.com/course/13936-AWS-Certified-Advanced-Networking-Specialty-Practice-Exams) [**Recommended**]


# [AWS DynamoDB Throughput Capacity](https://jayendrapatil.com/aws-dynamodb-throughput-capacity/)


# AWS DynamoDB Throughput Capacity

AWS DynamoDB throughput capacity depends on the read/write capacity modes for processing reads and writes on the tables.

There are two types of read/write capacity modes:

*   On-demand
*   Provisioned

**NOTE – Provisioned mode is covered in the AWS Certified Developer – Associate exam (DVA-C01) esp. the calculations. On-demand capacity mode is latest enhancement and does not yet feature in the exams.**

## Provisioned Mode

*   Provisioned mode requires you to specify the number of reads and writes per second as required by the application
*   Provisioned throughput is the maximum amount of capacity that an application can consume from a table or index
*   If the provisioned throughput capacity on a table or index is exceeded, it is subject to request throttling
*   Provisioned mode is a good for applications  
    *   predictable application traffic
    *   consistent traffic 
    *   ability to forecast capacity requirements to control costs
*   Provisioned mode provides the following capacity units 
    *   Read Capacity Units (RCU)
        *   Total number of read capacity units required depends on the item size, and the consistent read model (eventually or strongly)
        *   one RCU represents
            *   **one strongly consistent read per second for an item up to 4 KB in size**
            *   **two eventually consistent reads per second, for an item up to 4 KB in size i.e. 8 KB**
        *   Transactional read requests require two read capacity units to perform one read per second for items up to 4 KB.
        *   DynamoDB must consume additional read capacity units for items greater than 4 KB _for e.g. for an 8 KB item size, 2 read capacity units to sustain one strongly consistent read per second, 1 read capacity unit if you choose eventually consistent reads, or 4 read capacity units for a transactional read request would be required_
        *   Item size is rounded off to 4 KB equivalents _for e.g. a 6 KB or a 8 KB item in size would require the same RCU_
    *   Write Capacity Units (WCU)
        *   Total number of write capacity units required depends on the item size only
        *   **one write per second for an item up to 1 KB in size**
        *   Transactional write requests require 2 write capacity units to perform one write per second for items up to 1 KB.
        *   DynamoDB must consume additional read capacity units for items greater than 1 KB _for an 2 KB item size,  2 write capacity units would be required to sustain one write request per second or 4 write capacity units for a transactional write request_
        *   Item size is rounded off to 1 KB equivalents _for e.g. a 0.5 KB or a 1 KB item would need the same WCU_

## On-demand Mode

*   On-demand mode provides flexible billing option capable of serving thousands of requests per second without capacity planning
*   There is no need to specify the expected read and write throughput
*   Charged for only the reads and writes that the application performs on the tables in terms of read request units and write request units.
*   Offers pay-per-request pricing for read and write requests so that you pay only for what you use
*   DynamoDB adapts rapidly to accommodate the changing load
*   Read & Write Capacity Units performance remains the same as provisioned mode


## AWS Certification Exam Practice Questions

1.  You need to migrate 10 million records in one hour into DynamoDB. All records are 1.5KB in size. The data is evenly distributed across the partition key. How many write capacity units should you provision during this batch load?
    1.  6667
    2.  4166
    3.  **5556** ( 2 write units (1 for each 1KB) * 10 million/3600 secs)
    4.  2778
2.  A meteorological system monitors 600 temperature gauges, obtaining temperature samples every minute and saving each sample to a DynamoDB table. Each sample involves writing 1K of data and the writes are evenly distributed over time. How much write throughput is required for the target table?
    1.  1 write capacity unit
    2.  **10 write capacity units** ( 1 write unit for 1K * 600 gauges/60 secs)
    3.  60 write capacity units
    4.  600 write capacity units
    5.  3600 write capacity units
3.  A company is building a system to collect sensor data from its 36000 trucks, which is stored in DynamoDB. The trucks emit 1KB of data once every hour. How much write throughput is required for the target table. Choose an answer from the options below

    1.  **10**
    2.  60
    3.  600
    4.  150
4.  A company is using DynamoDB to design storage for their IOT project to store sensor data. Which combination would give the highest throughput?
    1.  **5 Eventual Consistent reads capacity with Item Size of 4KB** (40KB/s)
    2.  15 Eventual Consistent reads capacity with Item Size of 1KB (30KB/s)
    3.  5 Strongly Consistent reads capacity with Item Size of 4KB (20KB/s)
    4.  15 Strongly Consistent reads capacity with Item Size of 1KB (15KB/s)
5.  If your table item’s size is 3KB and you want to have 90 strongly consistent reads per second, how many read capacity units will you need to provision on the table? Choose the correct answer from the options below
    1.  **90**
    2.  45
    3.  10
    4.  19

## References

*   [DynamoDB_Developer_Guide](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)


# [AWS Certified SysOps Administrator – Associate (SOA-C01) Exam Learning Path](https://jayendrapatil.com/aws-certified-sysops-administrator-associate-soa-c01-exam-learning-path/)


# AWS Certified SysOps Administrator – Associate (SOA-C01) Exam Learning Path

AWS Certified SysOps Administrator – Associate (SOA-C01) exam is the latest AWS exam and has already replaced the old SysOps Administrator – Associate exam from 24th Sept 2018\. It basically validates

*   Deploy, manage, and operate scalable, highly available, and fault tolerant systems on AWS
*   Implement and control the flow of data to and from AWS
*   Select the appropriate AWS service based on compute, data, or security requirements
*   Identify appropriate use of AWS operational best practices
*   Estimate AWS usage costs and identify operational cost control mechanisms
*   Migrate on-premises workloads to AWS

Refer [AWS Certified SysOps – Associate Exam Guide Sep 18](https://d1.awsstatic.com/training-and-certification/docs-sysops-associate/AWS%20Certified%20SysOps%20-%20Associate_Exam%20Guide_Sep18.pdf)


## AWS Certified SysOps Administrator – Associate (SOA-C01) Exam Summary

*   AWS Certified SysOps Administrator – Associate exam is quite different from the previous one with more focus on the error handling, deployment, monitoring.
*   AWS Certified SysOps Administrator – Associate exam covers a lot of latest AWS services like ALB, Lambda, AWS Config, AWS Inspector, AWS Shield while focusing majorly on other services like CloudWatch, Metrics from various services, CloudTrail.
*   Be sure to cover the following topics
    *   ** Monitoring & Management Tools**
        *   Understand [CloudWatch](https://jayendrapatil.com/aws-cloudwatch-overview/) monitoring to provide operational transparency
            *   Know which [EC2 metrics](https://jayendrapatil.com/aws-ec2-monitoring/) it can track (disk, network, CPU, status checks) and which would need custom metrics (memory, disk swap, disk storage etc.)
            *   Know [ELB monitoring](https://jayendrapatil.com/aws-elb-monitoring/)
                *   Classic Load Balancer metrics **SurgeQueueLength** and **SpilloverCount**
                *   Reasons for 4XX and 5XX errors
        *   Understand [CloudTrail](https://jayendrapatil.com/aws-cloudtrail/) for audit and governance
        *   Understand [AWS Config](https://jayendrapatil.com/aws-config/) and its use cases
        *   Understand [AWS Systems Manager](https://jayendrapatil.com/aws-systems-manager-certification/) and its various services like parameter store, patch manager
        *   Understand [AWS Trusted Advisor](https://jayendrapatil.com/aws-trusted-advisor-categories/) and what it provides
        *   Very important to understand AWS CloudWatch vs AWS CloudTrail vs AWS Config
        *   Very important to understand Trust Advisor vs Systems manager vs Inspector
        *   Know Personal Health Dashboard & Service Health Dashboard
        *   Deployment tools
            *   Know [AWS OpsWorks](https://jayendrapatil.com/aws-opsworks/) and its ability to support chef & puppet
            *   Know [Elastic Beanstalk](https://jayendrapatil.com/aws-elastic-beanstalk/) and its advantages
            *   Understand AWS [CloudFormation](https://jayendrapatil.com/aws-cloudformation/)
                *   Know stacks, templates, nested stacks
                *   Know how to wait for resources setup to be completed before proceeding esp. cfn-signal
                *   Know how to retain resources (RDS, S3), prevent rollback in case of a failure
    *   **Networking & Content Delivery**
        *   Understand [VPC](https://jayendrapatil.com/aws-virtual-private-cloud-vpc/) in depth
            *   Understand the difference between
                *   [Bastion host](https://jayendrapatil.com/aws-bastion-host/) – allow access to instances in private subnet
                *   NAT – route traffic from private subnets to internet
                *   [NAT instance vs NAT Gateway](https://jayendrapatil.com/aws-vpc-nat/)
                *   Internet Gateway – Access to internet
                *   [Virtual Private Gateway ](https://jayendrapatil.com/aws-vpc-vpn-cloudhub/)– Connectivity between on-premises and VPC
                *   Egress-Only Internet Gateway – relevant to IPv6 only to allow egress traffic from private subnet to internet, without allowing ingress traffic
            *   Understand
                *   Private Subnet vs Public Subnet
                *   how to configure Route Tables
                *   [Security Groups vs NACLs](https://jayendrapatil.com/aws-vpc-security-group-vs-nacls/)
            *   Understand how [VPC Peering](https://jayendrapatil.com/aws-vpc-peering/) works and limitations
            *   Understand [VPC Endpoints](https://jayendrapatil.com/aws-vpc-endpoints/) and supported services
            *   Ability to debug networking issues like EC2 not accessible, EC2 instances not reachable, Instances in subnets not able to communicate with others or Internet.
        *   Understand [Route 53](https://jayendrapatil.com/aws-route-53/) and [Routing Policies](https://jayendrapatil.com/aws-route-53-routing-policy/) and their use cases
            *   Focus on Weighted, Latency routing policies
        *   Understand [VPN](https://jayendrapatil.com/aws-vpc-vpn-cloudhub/) and [Direct Connect](https://jayendrapatil.com/aws-direct-connect-dx/) and their use cases
        *   Understand [CloudFront](https://jayendrapatil.com/aws-cloudfront/) and use cases
        *   Understand [ELB](https://jayendrapatil.com/aws-elb-network-load-balancer/), [ALB](https://jayendrapatil.com/aws-elb-application-load-balancer/) and [NLB](https://jayendrapatil.com/aws-elb-network-load-balancer/) and what features they provide like
            *   ALB provides content and path routing
            *   NLB provides ability to give static IPs to load balancer.
    *   **Compute**
        *   Understand [EC2](https://jayendrapatil.com/aws-ec2-overview/) in depth
            *   Understand [EC2 instance types](https://jayendrapatil.com/aws-ec2-instance-types/)
            *   Understand [EC2 purchase options](https://jayendrapatil.com/aws-ec2-instance-purchasing-option/) esp. spot instances and improved reserved instances options.
            *   Understand how IO Credits work and T2 burstable performance and T2 unlimited
            *   Understand [EC2 Metadata & Userdata](https://jayendrapatil.com/aws-ec2-instance-metadata-userdata/). Whats the use of each? How to look up instance data after it is launched.
            *   Understand [EC2 Security. ](https://jayendrapatil.com/aws-ec2-security/)
                *   How IAM Role work with EC2 instances
                *   IAM Role can now be attached to stopped and runnings instances
            *   Understand [AMIs](https://jayendrapatil.com/aws-ec2-ami/) and remember they are regional and how can they be shared with others.
            *   Troubleshoot issues with launching EC2 esp. RequestLimitExceeded, InstanceLimitExceeded etc.
            *   Troubleshoot connectivity, lost ssh keys issues
        *   Understand [Auto Scaling](https://jayendrapatil.com/aws-auto-scaling/)
        *   Understand [Lambda](https://jayendrapatil.com/aws-lambda/) and its use cases
        *   Understand Lambda with [API Gateway](https://jayendrapatil.com/aws-api-gateway/)
    *   **Storage**
        *   Understand [S3](https://jayendrapatil.com/aws-simple-storage-service-s3-overview/) and all its topics
            *   Understand S3 features like
                *   [storage classes](https://jayendrapatil.com/aws-s3-storage-classes/) with [lifecycle policies](https://jayendrapatil.com/aws-s3-object-lifecycle-management/),
                *   [S3 data protection](https://jayendrapatil.com/aws-s3-data-protection/)
                *   multi-part handling esp. how do you handle completions and aborts.
                *   static website hosting, CORS
                *   [Versioning](https://jayendrapatil.com/aws-s3-object-versioning/)
                *   Pre-Signed URLs for both upload and download
        *   Understand [Glacier](https://jayendrapatil.com/aws-glacier/) as archival storage
        *   Understand [EBS](https://jayendrapatil.com/aws-ec2-ebs-storage/) storage option
            *   [EBS vs Instance store volumes ](https://jayendrapatil.com/aws-ebs-vs-instance-store/)
            *   [EBS volume types](https://jayendrapatil.com/aws-ebs-volume-types/) and their use cases, limitations esp. IOPS
            *   RAID 0 and RAID 1 configurations and their use cases
        *   Understand [Storage Gateway](https://jayendrapatil.com/aws-storage-gateway/) and their use cases
            *   Know uses cases for VTL
        *   Know EFS as shared file system.
        *   Know Snowball for data migration
            *   Know Snowball vs Snowball Edge
    *   **Databases**
        *   Understand [RDS ](https://jayendrapatil.com/aws-relational-database-service-rds/)
            *   Understand RDS [Multi-AZ vs Read Replicas](https://jayendrapatil.com/aws-rds-replication-multi-az-read-replica/) and use cases
        *   Understand [DynamoDB](https://jayendrapatil.com/aws-dynamodb/)
        *   Understand [Aurora](https://jayendrapatil.com/aws-rds-aurora/)
        *   Know [ElastiCache](https://jayendrapatil.com/aws-elasticache-certification/) use cases, mainly for caching performance
            *   Understand ElastiCache Redis vs Memcached
    *   **Security**
        *   Understand [IAM](https://jayendrapatil.com/aws-iam-role/) as a whole
            *   Focus on [IAM role](https://jayendrapatil.com/aws-iam-role/) and its use case especially with EC2 instance
            *   Know how to test and validate IAM policies
            *   Understand [IAM identity providers and federation](https://jayendrapatil.com/iam-role-identity-providers-federation/) and use cases
            *   Understand MFA and How would implement two factor authentication for your application
            *   Focus on [S3 with SSE, SSE-C, SSE-KMS](https://jayendrapatil.com/aws-s3-data-protection/). How they work and differ?
        *   Understand [KMS](https://jayendrapatil.com/aws-key-management-service-kms/) for key management and envelope encryption
        *   Understand [CloudHSM](https://jayendrapatil.com/aws-cloudhsm/) and KMS vs CloudHSM esp. support for symmetric and asymmetric keys
        *   Know AWS Inspector and its use cases
        *   Know AWS GuardDuty as managed threat detection service. Will help eliminate as the option
        *   Know AWS Shield esp. the Shield Advanced option and the features it provides
        *   Know WAF as Web Traffic Firewall
        *   Know AWS Artifact as on-demand access to compliance reports
    *   **Integration Tools**
        *   Understand [SQS](https://jayendrapatil.com/aws-sqs-simple-queue-service/) as message queuing service and SNS as pub/sub notification service
            *   Focus on SQS as a decoupling service
            *   Understand [SQS FIFO](https://jayendrapatil.com/aws-sqs-fifo-queue/), make sure you know the [differences](https://jayendrapatil.com/aws-sqs-standard-vs-fifo-queue/) between standard and FIFO
        *   Understand CloudWatch integration with [SNS](https://jayendrapatil.com/aws-sns-simple-notification-service/) for notification
    *   **Cost management**
        *   Know AWS [Organizations](https://jayendrapatil.com/aws-organizations/) and [Consolidated billing](https://jayendrapatil.com/aws-consolidated-billing/)
        *   Understand how to setup Billing Alerts using CloudWatch

## AWS Certified SysOps Administrator – Associate (SOA-C01) Exam Resources

*   Online Courses
    *   Udemy [AWS Certified Solutions Architect Associate Exam Mastery 2018](https://www.udemy.com/aws-certified-solutions-architect-associate-exam/?couponCode=J-PATIL-N) – can be a good start to other services
    *   Stephane Maarek – [Ultimate AWS Certified SysOps Administrator Associate 2019](https://links.datacumulus.com/aws-certified-sysops-coupon-jayendra) – **Highest Rated**
    *   A Cloud Guru – [AWS Certified SysOps Administrator – Associate 2019](https://click.linksynergy.com/link?id=l7C703x9gqw&offerid=323058.422702&type=2&murl=https%3A%2F%2Fwww.udemy.com%2Faws-certified-sysops-administrator-associate%2F)![](https://ad.linksynergy.com/fs-bin/show?id=l7C703x9gqw&bids=323058.422702&type=2&subid=0)
    *   Linux Academy – [AWS Certified SysOps Administrator – Associate (2018)](https://click.linksynergy.com/link?id=l7C703x9gqw&offerid=323058.1905402&type=2&murl=https%3A%2F%2Fwww.udemy.com%2Flinux-academy-aws-certified-sysops-administrator-associate-2018%2F)
*   Practice tests
    *   Braincert [AWS Certified SysOps Administrator – Associate SOA-C01 Practice Exams](https://www.braincert.com/course/15716-AWS-Certified-SysOps-Administrator-Associate-SOA-C01-Practice-Exams), which provide extensive scenario based questions and are inline with the actual exams
*   Signed up with AWS for the [Free Tier](https://aws.amazon.com/free/) account which provides a lot of the Services to be tried for free with certain limits which are more then enough to get things going. Be sure to decommission anything, if you using any thing beyond the free limits, preventing any surprises 🙂
*   Also, use [QwikLabs](https://qwiklabs.com/) for introductory courses which are free
*   Read the [FAQs](https://aws.amazon.com/faqs/) atleast for the important topics, as they cover important points and are good for quick review

## AWS Cloud Computing Whitepapers

*   [Architecting for the AWS Cloud: Best Practices](https://jayendrapatil.com/aws-architecting-for-the-cloud-best-practices-whitepaper/)
*   [AWS Well-Architected Framework whitepaper](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf) (This is theoretical paper, with loads of theory and is tiresome. If you cover the above topics, you can skip this one)
*   [AWS Security Best Practices whitepaper](https://d0.awsstatic.com/whitepapers/Security/AWS_Security_Best_Practices.pdf), August 2016
*   [Amazon Web Services: Overview of Security Processes](http://d0.awsstatic.com/whitepapers/Security/AWS%20Security%20Whitepaper.pdf)
*   [Development and Test on AWS](https://media.amazonwebservices.com/AWS_Development_Test_Environments.pdf)
*   [Backup and Recovery Approaches Using AWS](https://d0.awsstatic.com/whitepapers/Backup_Archive_and_Restore_Approaches_Using_AWS.pdf)
*   [Amazon Virtual Private Cloud Connectivity Options](https://media.amazonwebservices.com/AWS_Amazon_VPC_Connectivity_Options.pdf)
*   [How AWS Pricing Works](http://d0.awsstatic.com/whitepapers/aws_pricing_overview.pdf)

## AWS Certified SysOps Administrator – Associate (SOA-C01) Exam Contents

### **Domain 1: Monitoring and Reporting**

1.  Create and maintain metrics and alarms utilizing AWS monitoring services

1.  Recognize and differentiate performance and availability metrics
2.  Perform the steps necessary to remediate based on performance and availability metrics

### **Domain 2: High Availability**

1.  Implement scalability and elasticity based on use case
2.  Recognize and differentiate highly available and resilient environments on AWS

### **Domain 3: Deployment and Provisioning**

1.  Identify and execute steps required to provision cloud resources
2.  Identify and remediate deployment issues

### **Domain 4: Storage and Data Management**

1.  Create and manage data retention
2.  Identify and implement data protection, encryption, and capacity planning needs

### **Domain 5: Security and Compliance**

1.  Implement and manage security policies on AWS

1.  Implement access controls when using AWS
2.  Differentiate between the roles and responsibility within the shared responsibility model

### **Domain 6: Networking**

1.  Apply AWS networking features

1.  Implement connectivity services of AWS
2.  Gather and interpret relevant information for network troubleshooting

### Domain 7: Automation and Optimization

1.  Use AWS services and features to manage and assess resource utilization
2.  Employ cost-optimization strategies for efficient resource utilization
3.  Automate manual or repeatable process to minimize management overhead

# [AWS Certified Developer – Associate DVA-C01 Exam Learning Path](https://jayendrapatil.com/aws-certified-developer-associate-june-2018-exam-learning-path/)


# AWS Certified Developer – Associate DVA-C01 Exam Learning Path

AWS Certified Developer – Associate DVA-C01 exam is the latest AWS exam and would replace the old Developer – Associate exam. It basically validates

*   Demonstrate an understanding of core AWS services, uses, and basic AWS architecture best practices.
*   Demonstrate proficiency in developing, deploying, and debugging cloud-based applications using AWS.

Refer [AWS Certified Developer – Associate (Released June 2018) Exam Blue Print](https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS_Certified_Developer_Associate_Updated_June_2018_Exam_Guide_v1.3.pdf)

<figure class="wp-block-image">![AWS Certified Developer - Associate June 2018 Domains](https://secureservercdn.net/160.153.138.177/3d9.249.myftpupload.com/wp-content/uploads/2018/07/AWS-Certified-Developer-Associate-June-2018-Domains.png)</figure>

## AWS Certified Developer – Associate DVA-C01 Summary

*   AWS Certified Developer – Associate DVA-C01 exam is quite different from the previous one with more focus on the hands-on development and deployment concepts rather then just the architectural concepts
*   AWS Certified Developer – Associate DVA-C01 exam covers a lot of latest AWS services like Lambda, X-Ray while focusing majorly on other services like DynamoDB, Elastic Beanstalk, S3, EC2
*   Be sure to cover the following topics
    *   **Compute**
        *   Understand what AWS services you can use to build a serverless architecture?
        *   **Make sure you know and understand [Lambda](https://jayendrapatil.com/aws-lambda/) and serverless architecture, its features and use cases.**
        *   Know Lambda limits _for e.g. execution time, deployable zipped and unzipped package limit_
        *   **Be sure to know how to deploy, package using Lambda.**
        *   Understand tracing of Lambda functions using [X-Ray](https://jayendrapatil.com/aws-x-ray/)
        *   Understand integration of Lambda with [CloudWatch](https://jayendrapatil.com/aws-cloudwatch-overview/).
        *   Understand how to handle multiple releases using Alias
        *   Know AWS Step Functions to manage Lambda functions flow
        *   Understand Lambda with [API Gateway](https://jayendrapatil.com/aws-api-gateway/)
        *   Understand API Gateway stages, ability to cater to different environments _for e.g. dev, test, prod_
        *   Understand [EC2](https://jayendrapatil.com/aws-ec2-overview/) as a whole
        *   Understand [EC2 Metadata & Userdata](https://jayendrapatil.com/aws-ec2-instance-metadata-userdata/). Whats the use of each? How to look up instance data after it is launched.
        *   Understand [EC2 Security. ](https://jayendrapatil.com/aws-ec2-security/)How IAM Role work with EC2 instances.
        *   Understand how does EC2 evaluates the order of credentials, when multiple are provided. Remember the order – _Environment variables -> Java system properties -> Default credential profiles file -> ECS container credentials -> Instance Profile credentials_
        *   Know [Elastic Beanstalk](https://jayendrapatil.com/aws-elastic-beanstalk/) at a high level, what it provides and its ability to get an application running quickly
        *   Understand Elastic Beanstalk configurations and [deployment types](https://jayendrapatil.com/aws-elastic-beanstalk-deployment-strategies/) with their advantages and disadvantages
    *   **Databases**
        *   Understand relational and NoSQLs data storage options which include [RDS](https://jayendrapatil.com/aws-relational-database-service-rds/), [DynamoDB](https://jayendrapatil.com/aws-dynamodb/) and their use cases
        *   Understand [DynamoDB Secondary Indexes](https://jayendrapatil.com/aws-dynamodb-secondary-indexes/)
        *   **Make sure you understand [DynamoDB](https://jayendrapatil.com/aws-dynamodb-secondary-indexes/) provisioned throughput for Read/Writes and its calculations**
        *   Make sure you understand DynamoDB Consistency Model – difference between Strongly Consistent and Eventual Consistency
        *   Understand DynamoDB with its low latency performance, DAX
        *   Know how to configure fine grained security for DynamoDB table, items, attributes
        *   Understand DynamoDB Best Practices regarding
            *   table design
            *   provisioned throughput
            *   Query vs Scan operations
            *   improving Scan operation performance
        *   Understand RDS features – [Read Replicas for scalability, Multi-AZ for High Availability](https://jayendrapatil.com/aws-rds-replication-multi-az-read-replica/)
        *   Know [ElastiCache](https://jayendrapatil.com/aws-elasticache-certification/) use cases, mainly for caching performance
        *   Understand ElastiCache Redis vs Memcached
    *   **Storage**
        *   Understand [S3](https://jayendrapatil.com/aws-simple-storage-service-s3-overview/) storage option
        *   Understand [S3 Best Practices](https://jayendrapatil.com/aws-s3-best-practices/) to improve performance for GET/PUT requests
        *   Understand S3 features like different [storage classes](https://jayendrapatil.com/aws-s3-storage-classes/) with [lifecycle policies](https://jayendrapatil.com/aws-s3-object-lifecycle-management/), static website hosting, versioning, Pre-Signed URLs for both upload and download, CORS
    *   **Security**
        *   Understand [IAM](https://jayendrapatil.com/aws-iam-role/) as a whole
        *   Focus on [IAM role](https://jayendrapatil.com/aws-iam-role/) and its use case especially with EC2 instance
        *   Know how to test and validate IAM policies
        *   Understand [IAM identity providers and federation](https://jayendrapatil.com/iam-role-identity-providers-federation/) and use cases
        *   Understand how AWS Cognito works and what features it provides
        *   Understand MFA and How would implement two factor authentication for your application
        *   Understand [KMS](https://jayendrapatil.com/aws-key-management-service-kms/) for key management and envelope encryption
        *   Know what services support KMS
            *   Remember SQS, Kinesis now provides SSE support
        *   Focus on [S3 with SSE, SSE-C, SSE-KMS](https://jayendrapatil.com/aws-s3-data-protection/). How they work and differ?
        *   Know how can you enforce only buckets to only accept encrypted objects
        *   Know various KMS encryption options encrypt, reencrypt, generateEncryptedDataKey etc
        *   Know how KMS impacts performance of the services
    *   **Management Tools**
        *   Understand [CloudWatch](https://jayendrapatil.com/aws-cloudwatch-overview/) monitoring to provide operational transparency
        *   Know which [EC2 metrics](https://jayendrapatil.com/aws-ec2-monitoring/) it can track.
        *   Understand CloudWatch is extendable with custom metrics
        *   Understand [CloudTrail](https://jayendrapatil.com/aws-cloudtrail/) for Audit
    *   **Integration Tools**
        *   Understand [SQS](https://jayendrapatil.com/aws-sqs-simple-queue-service/) as message queuing service and SNS as pub/sub notification service
        *   Understand SQS features like visibility, long poll vs short poll
        *   Focus on SQS as a decoupling service
        *   AWS has released [SQS FIFO](https://jayendrapatil.com/aws-sqs-fifo-queue/), make sure you know the [differences](https://jayendrapatil.com/aws-sqs-standard-vs-fifo-queue/) between standard and FIFO
        *   Know the different development and deployment tools like CodeCommit, CodeBuild, CodeDeploy, CodePipeline
    *   **Networking**
        *   Does not cover much on networking or designing of networks, but be sure you understand VPC, Subnets, Routes, Security Groups etc.

## AWS Certified Developer – Associate DVA-C01 Exam Resources

*   None of the courses actually cover the topics completely and are in the process of being updated. You need to make sure you cover the latest services in details esp. Lambda, API Gateway, X-Ray
*   Online courses
    *   Udemy [AWS Certified Solutions Architect Associate Exam Mastery 2018](https://www.udemy.com/aws-certified-solutions-architect-associate-exam/?couponCode=J-PATIL-N) – can be a good start to other services
    *   Stephane Maarek – [Ultimate AWS Certified Developer Associate 2019 – NEW!](https://links.datacumulus.com/aws-certified-dev-coupon-jayendra) – **Best Seller**
    *   A Cloud Guru – [AWS Certified Developer – Associate 2018](https://click.linksynergy.com/link?id=l7C703x9gqw&offerid=323058.393306&type=2&murl=https%3A%2F%2Fwww.udemy.com%2Faws-certified-developer-associate%2F)![](https://ad.linksynergy.com/fs-bin/show?id=l7C703x9gqw&bids=323058.393306&type=2&subid=0)
    *   Linux Academy – [AWS Certified Developer – Associate (2018)](https://click.linksynergy.com/link?id=l7C703x9gqw&offerid=323058.1824298&type=2&murl=https%3A%2F%2Fwww.udemy.com%2Flinux-academy-aws-certified-developer-associate%2F)
*   Practice tests
    *   Braincert [AWS Certified Developer – Associate DVA-C01 Practice Exams](https://www.braincert.com/course/14950-AWS-Certified-Developer-Associate-June-2018-Practice-Exams), which provide extensive scenario based questions and are inline with the actual exams
    *   [Udemy AWS Certified Developer – Associate DVA-C01 Practice Exams](https://www.udemy.com/aws-certified-developer-associate-june-2018-practice-exams/?couponCode=JAYENDRA)
*   Signed up with AWS for the [Free Tier](https://aws.amazon.com/free/) account which provides a lot of the Services to be tried for free with certain limits which are more then enough to get things going. Be sure to decommission anything, if you using any thing beyond the free limits, preventing any surprises 🙂
*   Also, use [QwikLabs](https://qwiklabs.com/) for introductory courses which are free
*   Read the [FAQs](https://aws.amazon.com/faqs/) atleast for the important topics, as they cover important points and are good for quick review

## AWS Cloud Computing Whitepapers

*   [Architecting for the AWS Cloud: Best Practices](https://jayendrapatil.com/aws-architecting-for-the-cloud-best-practices-whitepaper/)
*   [AWS Well-Architected Framework whitepaper](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf) (This is theoretical paper, with loads of theory and is tiresome. If you cover the above topics, you can skip this one)
*   [AWS Security Best Practices whitepaper](https://d0.awsstatic.com/whitepapers/Security/AWS_Security_Best_Practices.pdf), August 2016
*   [Practicing Continuous Integration and Continuous Delivery on AWS Accelerating Software Delivery with DevOps whitepaper](https://d1.awsstatic.com/whitepapers/DevOps/practicing-continuous-integration-continuous-delivery-on-AWS.pdf?), June 2017
*   [Microservices on AWS whitepaper](https://d1.awsstatic.com/whitepapers/microservices-on-aws.pdf?), September 2017
*   [Serverless Architectures with AWS Lambda whitepaper](https://d1.awsstatic.com/whitepapers/serverless-architectures-with-aws-lambda.pdf?)<span class="s3">,</span> November 2017
*   [Optimizing Enterprise Economics with Serverless Architectures whitepaper](https://d1.awsstatic.com/whitepapers/optimizing-enterprise-economics-serverless-architectures.pdf?)<span class="s3">,</span> October 2017
*   [Running Containerized Microservices on AWS whitepaper](https://d1.awsstatic.com/whitepapers/DevOps/running-containerized-microservices-on-aws.pdf?)<span class="s3">,</span> November 2017
*   [Blue/Green Deployments on AWS whitepaper](https://jayendrapatil.com/aws-blue-green-deployment/), August 2016

## AWS Certified Developer – Associate DVA-C01 Exam Contents

### **Domain 1: Deployment**

1.  Deploy written code in AWS using existing CI/CD pipelines, processes, and patterns.

1.  Deploy applications using Elastic Beanstalk.

1.  Prepare the application deployment package to be deployed to AWS.
2.  Deploy serverless applications.

### **Domain 2: Security**

1.  Make authenticated calls to AWS services.

1.  Implement encryption using AWS services.
2.  Implement application authentication and authorization.

### **Domain 3: Development with AWS Services**

1.  Write code for serverless applications.

1.  Translate functional requirements into application design.

1.  Implement application design into application code.
2.  Write code that interacts with AWS services by using APIs, SDKs, and AWS CLI.

### **Domain 4: Refactoring**

1.  Optimize application to best use AWS services and features.
2.  Migrate existing application code to run on AWS.

### **Domain 5: Monitoring and Troubleshooting**

1.  Write code that can be monitored.
2.  Perform root cause analysis on faults found in testing or production.

</div>

</article>

<article id="post-10374" class="post-10374 post type-post status-publish format-standard hentry category-aurora category-aws tag-aurora tag-aws tag-certification tag-exam tag-practice-questions tag-sample-questions">

<header class="entry-header">

# [AWS RDS Aurora – Certification](https://jayendrapatil.com/aws-rds-aurora/)

</header>

<div class="entry-meta"><span class="posted-on">[<time class="entry-date published" datetime="2018-07-04T17:52:42+05:30">July 4, 2018</time> ~ Last updated on : <time class="updated" datetime="2018-07-04T18:27:22+05:30">July 4, 2018</time>](https://jayendrapatil.com/aws-rds-aurora/)</span><span class="byline"> <span class="sep">~</span> <span class="author vcard">[jayendrapatil](https://jayendrapatil.com/author/jayendrapatil/)</span></span> <span class="sep">~</span> <span class="comments-link">[3 Comments](https://jayendrapatil.com/aws-rds-aurora/#comments)</span></div>

<div class="entry-content">

# AWS Aurora

*   AWS Aurora is a relational database engine that combines the speed and reliability of high-end commercial databases with the simplicity and cost-effectiveness of open source databases.
*   Amazon Aurora (Aurora) is a fully managed, MySQL- and PostgreSQL-compatible, relational database engine i.e. applications developed with MySQL can switch to Aurora with little or no changes
*   Aurora delivers up to 5x performance of MySQL without requiring any changes to most MySQL applications
*   Aurora PostgreSQL delivers up to 3x performance of PostgreSQL.
*   RDS manages the Aurora databases, handling time-consuming tasks such as provisioning, patching, backup, recovery, failure detection and repair.
*   Based on the database usage, Aurora storage will automatically grow, from **10GB to 64TB** in 10GB increments with no impact to database performance

**<span style="color: #ff0000;">NOTE</span> – AWS Aurora is covered in the latest Solution Architect – Associate Feb 2018 extensively, so be sure to cover the same.**

![AWS Aurora Architecture](https://secureservercdn.net/160.153.138.177/3d9.249.myftpupload.com/wp-content/uploads/2018/07/AWS-Aurora-Architecture.png)

## High Availability and Replication

*   Aurora provides data durability and reliability by replicating the database volume six ways **across three Availability Zones in a single region**
    *   Aurora automatically divides the database volume into 10GB segments spread across many disks.
    *   Each 10GB chunk of your database volume is replicated six ways, across three Availability Zones
*   RDS databases _for e.g. MySQL, Oracle etc._ have the data in a single AZ
*   Aurora is designed to transparently handle the loss of up to two copies of data without affecting database write availability and up to three copies without affecting read availability.
*   Aurora storage is also self-healing. Data blocks and disks are continuously scanned for errors and repaired automatically.
*   Aurora Replicas share the same underlying volume as the primary instance. Updates made by the primary are visible to all Aurora Replicas
*   As Aurora Replicas share the same data volume as the primary instance, there is virtually no replication lag
*   Any Aurora Replica can be promoted to become primary without any data loss and therefore can be used for enhancing fault tolerance in the event of a primary DB Instance failure.
*   To increase database availability, 1 to 15 replicas can be created in any of 3 AZs, and RDS will automatically include them in failover primary selection in the event of a database outage.

## Security

*   Aurora uses SSL (AES-256) to secure the connection between the database instance and the application
*   Aurora allows database encryption using keys managed through AWS Key Management Service (KMS).
*   Encryption and decryption are handled seamlessly.
*   With Aurora encryption, data stored at rest in the underlying storage is encrypted, as are its automated backups, snapshots, and replicas in the same cluster.
*   Encryption of existing unencrypted Aurora instance is not supported. Create a new encrypted Aurora instance and migrate the data

## Backup and Restore

*   Automated backups are always enabled on Aurora DB Instances.
*   Backups do not impact database performance.
*   Aurora also allows creation of manual snapshots
*   Aurora automatically maintains 6 copies of your data across 3 AZs and will automatically attempt to recover your database in a healthy AZ with no data loss.
*   If in any case the data is unavailable within Aurora storage,
    *   DB Snapshot can be restored or
    *   point-in-time restore operation can be performed to a new instance. Latest restorable time for a point-in-time restore operation can be up to 5 minutes in the past.
*   Restoring a snapshot creates a new Aurora DB instance
*   Deleting Aurora database deletes all the automated backups (with an option to create a final snapshot), but would not remove the manual snapshots.
*   Snapshots (including encrypted ones) can be shared with another AWS accounts

## AWS Certification Exam Practice Questions

> *   <span style="color: #ff0000;">Questions are collected from Internet and the answers are marked as per my knowledge and understanding (which might differ with yours).</span>
> *   <span style="color: #ff0000;">AWS services are updated everyday and both the answers and questions might be outdated soon, so research accordingly.</span>
> *   <span style="color: #ff0000;">AWS exam questions are not updated to keep up the pace with AWS updates, so even if the underlying feature has changed the question might not be updated</span>
> *   <span style="color: #ff0000;">Open to further feedback, discussion and correction.</span>

1.  Company wants to use MySQL compatible relational database with greater performance. Which AWS service can be used?
    1.  **Aurora**
    2.  RDS
    3.  SimpleDB
    4.  DynamoDB
2.  An application requires a highly available relational database with an initial storage capacity of 8 TB. The database will grow by 8 GB every day. To support expected traffic, at least eight read replicas will be required to handle database reads. Which option will meet these requirements?
    1.  DynamoDB
    2.  Amazon S3
    3.  **Amazon Aurora**
    4.  Amazon Redshift
3.  A company is migrating their on-premise 10TB MySQL database to AWS. As a compliance requirement, the company wants to have the data replicated across three availability zones. Which Amazon RDS engine meets the above business requirement?
    1.  Use Multi-AZ RDS
    2.  Use RDS
    3.  **Use Aurora**
    4.  Use DynamoDB

</div>

</article>

<article id="post-10369" class="post-10369 post type-post status-publish format-standard hentry category-aws category-x-ray tag-aws tag-certification tag-exam tag-practice-questions tag-sample-questions tag-x-ray">

<header class="entry-header">

# [AWS X-Ray – Certification](https://jayendrapatil.com/aws-x-ray/)

</header>

<div class="entry-meta"><span class="posted-on">[<time class="entry-date published" datetime="2018-07-04T14:12:16+05:30">July 4, 2018</time> ~ Last updated on : <time class="updated" datetime="2018-07-04T15:12:55+05:30">July 4, 2018</time>](https://jayendrapatil.com/aws-x-ray/)</span><span class="byline"> <span class="sep">~</span> <span class="author vcard">[jayendrapatil](https://jayendrapatil.com/author/jayendrapatil/)</span></span> <span class="sep">~</span> <span class="comments-link">[Leave a comment](https://jayendrapatil.com/aws-x-ray/#respond)</span></div>

<div class="entry-content">

# AWS X-Ray

*   AWS X-Ray helps developers analyze and debug production, **distributed applications** _for e.g. built using a microservices lambda architecture_
*   X-Ray provides an end-to-end view of requests as they travel through the application, and shows a map of the application’s underlying components.
*   X-Ray helps to understand how the application and its underlying services are performing to identify and troubleshoot the root cause of performance issues and errors.
*   X-Ray to analyze both applications in development and in production, from simple three-tier applications to complex microservices applications consisting of thousands of services.
*   X-Ray can be used with distributed applications of any size to trace and debug both synchronous requests and asynchronous events.
*   X-Ray can be used to track requests flowing through applications or services across multiple regions. X-Ray data is stored locally to the processed region and customers can build a solution over it to combined the data
*   Trace data sent to X-Ray is generally available for retrieval and filtering within 30 seconds of it being received by the service.
*   X-Ray stores trace data for the last 30 days. This enables you to query trace data going back 30 days.
*   Integration
    *   X-Ray integrates with applications running on EC2, ECS, Lambda, and Elastic Beanstalk.
    *   X-Ray SDK automatically captures metadata for API calls made to AWS services using the AWS SDK
    *   X-Ray SDK provides add-ons for MySQL and PostgreSQL drivers.
    *   For Elastic Beanstalk, include the language-specific X-Ray libraries in your application code.
    *   Applications running on other AWS services, such as EC2 or ECS, install the X-Ray agent and instrument the application code

## X-Ray Core Concepts

*   **Trace**
    *   An X-Ray trace is a set of data points that share the same trace ID.
    *   Trace helps track the request, which is assigned a unique trace id, while it navigates through services
    *   Piece of information relayed by each service in the application to X-Ray is a segment, and a **trace is a collection of segments**.
*   **Segment**
    *   An X-Ray segment encapsulates all the data points for a single component of the distributed application _for e.g. authorization component_
    *   Segments include system-defined and user-defined data in **the form of annotations** and are composed of one or more sub-segments that represent remote calls made from the service.  _for e.g. database call and its result within the overall request/response_
*   **Annotation**
    *   An X-Ray annotation is system-defined or user-defined data
    *   Annotation is associated with a segment and a segment can contain multiple annotations.
    *   System-defined annotations include data added to the segment by AWS services
    *   User-defined annotations are metadata added to a segment by a developer
*   **Errors**
    *   X-Ray errors are system annotations associated with a segment for a call that results in an error response.
    *   Error includes the error message, stack trace, and any additional information _for e.g, version_ to associate the error with a source file.
*   **Sampling**
    *   X-Ray collects data for significant number of requests, instead of each request sent to an application, for performant and cost-effectiveness
    *   X-Ray should not be used as an audit or compliance tool because it does not guarantee data completeness.
*   **X-Ray agent**
    *   X-Ray agent helps collect data from log files and sends them to the X-Ray service for aggregation, analysis, and storage.
    *   Agent makes it easier for you to send data to the X-Ray service, instead of using the APIs directly, and is
    *   Agent is available for Amazon Linux AMI, Red Hat Enterprise Linux (RHEL), and Windows Server 2012 R2 or later operating systems.

## AWS Certification Exam Practice Questions

> *   <span style="color: #ff0000;">Questions are collected from Internet and the answers are marked as per my knowledge and understanding (which might differ with yours).</span>
> *   <span style="color: #ff0000;">AWS services are updated everyday and both the answers and questions might be outdated soon, so research accordingly.</span>
> *   <span style="color: #ff0000;">AWS exam questions are not updated to keep up the pace with AWS updates, so even if the underlying feature has changed the question might not be updated</span>
> *   <span style="color: #ff0000;">Open to further feedback, discussion and correction.</span>

1.  A company is facing performance issues with their microservices architecture deployed on AWS. Which service can help them debug and analyze the issue? [CCP]
    1.  AWS Inspector
    2.  CodeDeploy
    3.  **X-Ray**
    4.  AWS Config

</div>

</article>

<article id="post-10352" class="post-10352 post type-post status-publish format-standard hentry category-aws category-dynamodb tag-aws tag-certification tag-dynamodb tag-exam tag-practice-questions tag-sample-questions">

<header class="entry-header">

# [AWS DynamoDB Advanced – Certification](https://jayendrapatil.com/aws-dynamodb-advanced/)

</header>

<div class="entry-meta"><span class="posted-on">[<time class="entry-date published" datetime="2018-07-03T07:48:19+05:30">July 3, 2018</time> ~ Last updated on : <time class="updated" datetime="2018-07-04T12:52:54+05:30">July 4, 2018</time>](https://jayendrapatil.com/aws-dynamodb-advanced/)</span><span class="byline"> <span class="sep">~</span> <span class="author vcard">[jayendrapatil](https://jayendrapatil.com/author/jayendrapatil/)</span></span> <span class="sep">~</span> <span class="comments-link">[2 Comments](https://jayendrapatil.com/aws-dynamodb-advanced/#comments)</span></div>

<div class="entry-content">

# AWS DynamoDB Advanced Features

This post covers DynamoDB advanced features

## DynamoDB Secondary Indexes

DynamoDB supports Local and Global Secondary Indexes.

Refer to My Blog Post about [AWS DynamoDB Secondary Indexes](https://jayendrapatil.com/aws-dynamodb-secondary-indexes/)

## DynamoDB Cross-region Replication

*   DynamoDB cross-region replication allows identical copies (called replicas) of a DynamoDB table (called master table) to be maintained in one or more AWS regions
*   Writes to the table will be automatically propagated to all replicas
*   Cross-region replication currently supports **single master mode**. A single master has one master table and one or more replica tables
*   Read replicas are updated **asynchronously** as DynamoDB acknowledges a write operation as successful once it has been accepted by the master table. The write will then be propagated to each replica with a slight delay.
*   Cross-region replication can be helpful in scenarios
    *   **Efficient disaster recovery,** in case a data center failure occurs.
    *   **Faster reads**, for customers in multiple regions by delivering data faster by reading a DynamoDB table from the closest AWS data center.
    *   **Easier traffic management,** to distribute the read workload across tables and thereby consume less read capacity in the master table.
    *   **Easy regional migration**, by promoting a read replica to master
    *   **Live data migration**, to replicate data and when the tables are in sync, switch the application to write to the destination region
*   Cross-region replication costing depends on
    *   Provisioned throughput (Writes and Reads)
    *   Storage for the replica tables.
    *   Data Transfer across regions
    *   Reading data from DynamoDB Streams to keep the tables in sync.
    *   Cost of EC2 instances provisioned, depending upon the instance types and region, to host the replication process.
*   **NOTE** : Cross Region replication on DynamoDB was performed defining AWS Data Pipeline job which used EMR internally to transfer data before the DynamoDB streams and out of box cross region replication support

## DynamoDB Global Tables

*   DynamoDB Global Tables is a new **multi-master, cross-region replication** capability of DynamoDB to support data access locality and regional fault tolerance for database workloads.
*   Applications can now perform reads and writes to DynamoDB in AWS regions around the world, with changes in any region propagated to every region where a table is replicated.
*   Global Tables help in building applications to advantage of data locality to reduce overall latency.
*   Global Tables ensures eventual consistency
*   Global Tables replicates data among regions within a single AWS account, and currently does not support cross account access

## DynamoDB Streams

*   DynamoDB Streams provides a **time-ordered sequence of item-level changes** made to data in a table in the last 24 hours, after which they are erased
*   DynamoDB Streams maintains ordered sequence of the events per item however across item are not maintained
*   _Example_
    *   _For e.g., suppose that you have a DynamoDB table tracking high scores for a game and that each item in the table represents an individual player. If you make the following three updates in this order:_
        *   _Update 1: Change Player 1’s high score to 100 points_
        *   _Update 2: Change Player 2’s high score to 50 points_
        *   _Update 3: Change Player 1’s high score to 125 points_
    *   _DynamoDB Streams will maintain the order for Player 1 score events. However, it would not maintain the order across the players. So Player 2 score event is not guaranteed between the 2 Player 1 events_
*   DynamoDB streams can be used for multi-region replication to keep other data stores up-to-date with the latest changes to DynamoDB or to take actions based on the changes made to the table
*   DynamoDB Streams APIs helps developers consume updates and receive the item-level data before and after items are changed
*   DynamoDB Streams allows read at up to twice the rate of the provisioned write capacity of the DynamoDB table
*   DynamoDB Streams have to be enabled on a per-table basis
*   DynamoDB Streams is designed so that every update made to the table will be represented exactly once in the stream
*   DynamoDB Streams is designed so that every update made to the table will be represented exactly once in the stream. No Duplicates

## DynamoDB Triggers

*   DynamoDB Triggers (just like database triggers) is a feature which allows execution of custom actions based on item-level updates on a table
*   DynamoDB triggers can be used in scenarios like sending notifications, updating an aggregate table, and connecting DynamoDB tables to other data sources
*   DynamoDB Trigger flow
    *   Custom logic for a DynamoDB trigger is stored in an AWS Lambda function as code.
    *   A trigger for a given table can be created by associating an AWS Lambda function to the stream (via DynamoDB Streams) on a table.
    *   When the table is updated, the updates are published to DynamoDB Streams.
    *   In turn, AWS Lambda reads the updates from the associated stream and executes the code in the function.

## DynamoDB Accelerator DAX

*   DynamoDB Accelerator (DAX) is a fully managed, highly available, in-memory cache for DynamoDB that delivers up to a 10x performance improvement – from milliseconds to microseconds – even at millions of requests per second.
*   DAX does all the heavy lifting required to add in-memory acceleration to the tables, without requiring developers to manage cache invalidation, data population, or cluster management.
*   DAX is fault-tolerant and scalable.
*   DAX cluster has a primary node and zero or more read-replica nodes. Upon a failure for a primary node, DAX will automatically fail over and elect a new primary. For scaling, add or remove read replicas

## VPC Endpoints

*   VPC endpoints for DynamoDB improve privacy and security, especially those dealing with sensitive workloads with compliance and audit requirements, by enabling private access to DynamoDB from within a VPC without the need for an internet gateway or NAT gateway.
*   VPC endpoints for DynamoDB support IAM policies to simplify DynamoDB access control, where access can be restricted to a specific VPC endpoint.
*   VPC endpoints can be created only for Amazon DynamoDB tables in the same AWS Region as the VPC
*   DynamoDB Streams cannot be access using VPC endpoints for DynamoDB

## AWS Certification Exam Practice Questions

> *   <span style="color: #ff0000;">Questions are collected from Internet and the answers are marked as per my knowledge and understanding (which might differ with yours).</span>
> *   <span style="color: #ff0000;">AWS services are updated everyday and both the answers and questions might be outdated soon, so research accordingly.</span>
> *   <span style="color: #ff0000;">AWS exam questions are not updated to keep up the pace with AWS updates, so even if the underlying feature has changed the question might not be updated</span>
> *   <span style="color: #ff0000;">Open to further feedback, discussion and correction.</span>

1.  What are the services supported by VPC endpoints, using Gateway endpoint type? Choose 2 answers
    1.  **Amazon S3**
    2.  Amazon EFS
    3.  **Amazon DynamoDB**
    4.  Amazon Glacier
    5.  Amazon SQS
2.  A company has setup an application in AWS that interacts with DynamoDB. DynamoDB is currently responding in milliseconds, but the application response guidelines require it to respond within microseconds. How can the performance of DynamoDB be further improved? [SAA-C01]
    1.  Use ElastiCache in front of DynamoDB
    2.  Use DynamoDB inbuilt caching
    3.  **Use DynamoDB Accelerator**
    4.  Use RDS with ElastiCache instead

</div>

</article>

<article id="post-10158" class="post-10158 post type-post status-publish format-standard hentry category-aws tag-certification tag-exam tag-saa-c01 tag-solutions-architect">

<header class="entry-header">

# [AWS Certified Solutions Architect – Associate SAA-C01 Exam Learning Path](https://jayendrapatil.com/aws-solutions-architect-associate-feb-2018-exam-learning-path/)

</header>

<div class="entry-meta"><span class="posted-on">[<time class="entry-date published" datetime="2018-06-28T08:03:30+05:30">June 28, 2018</time> ~ Last updated on : <time class="updated" datetime="2020-04-10T08:46:43+05:30">April 10, 2020</time>](https://jayendrapatil.com/aws-solutions-architect-associate-feb-2018-exam-learning-path/)</span><span class="byline"> <span class="sep">~</span> <span class="author vcard">[jayendrapatil](https://jayendrapatil.com/author/jayendrapatil/)</span></span> <span class="sep">~</span> <span class="comments-link">[250 Comments](https://jayendrapatil.com/aws-solutions-architect-associate-feb-2018-exam-learning-path/#comments)</span></div>

<div class="entry-content">

# AWS Certified Solutions Architect – Associate SAA-C01 Exam Learning Path

AWS Solutions Architect – Associate SAA-C01 exam is the latest AWS exam and would replace the old CSA-Associate exam. It basically validates the ability to effectively demonstrate knowledge of how to architect and deploy secure and robust applications on AWS technologies

*   Define a solution using architectural design principles based on customer requirements.
*   Provide implementation guidance based on best practices to the organization throughout the life cycle of the project.

Refer [AWS_Solution_Architect_-_Associate_SAA-C01_Exam_Blue_Print](https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS_Certified_Solutions_Architect_Associate_Feb_2018_%20Exam_Guide_v1.5.2.pdf)


## AWS Solutions Architect – Associate SAA-C01 Exam Summary

*   AWS has updated the exam concepts from the focus being on individual services to more building of scalable, highly available, cost-effective, performant, resilient and operational effective architecture
*   Although, most of the services covered by the the old exam are the same. There are few new additions like API Gateway, Lambda, ECS, Aurora
*   Exam surely covers the architecture aspects in deep, so you must be able to visualize the architecture, even draw them out in the exam just to understand how it would work and how different services relate.
*   Be sure to cover the following topics
    *   **Networking**
        *   Be sure to create VPC from scratch. **This is mandatory**.
            *   Create [VPC](//jayendrapatil.com/aws-virtual-private-cloud-vpc/) and understand whats an CIDR.
            *   Create public and private subnets, configure proper routes, security groups, NACLs.
            *   Create [Bastion](//jayendrapatil.com/aws-bastion-host/) for communication with instances
            *   Create [NAT Gateway or Instances](//jayendrapatil.com/aws-vpc-nat/) for instances in private subnets to interact with internet
            *   Create two tier architecture with application in public and database in private subnets
            *   Create three tier architecture with web servers in public, application and database servers in private.
            *   Make sure to understand how the communication happens between Internet, Public subnets, Private subnets, NAT, Bastion etc.
        *   Understand [VPC endpoints](//jayendrapatil.com/aws-vpc-endpoints/) and what services it can help interact
        *   Understand difference between NAT Gateway and NAT Instance
        *   Understand how NAT high availability can be achieved
        *   Understand [CloudFront](//jayendrapatil.com/aws-cloudfront/) as CDN and the static and dynamic caching it provides, what can be its origin (it can point to on-premises sources)
        *   Understand [Route 53](//jayendrapatil.com/aws-route-53/) for routing, health checks and various [routing policies](//jayendrapatil.com/aws-route-53-routing-policy/) it provides and their use cases mainly for high availability
        *   Be sure to cover [ELB](//jayendrapatil.com/aws-elb-application-load-balancer/) in deep. AWS has introduced [ALB](//jayendrapatil.com/aws-elb-application-load-balancer/) and [NLB](//jayendrapatil.com/aws-elb-network-load-balancer/) and there are lot of questions on ALB
        *   Understand [ALB](//jayendrapatil.com/aws-classic-load-balancer-vs-application-load-balancer/) features with its ability for content based and URL based routing with support for dynamic port mapping with ECS
    *   **Storage**
        *   Understand various storage options [S3](//jayendrapatil.com/aws-simple-storage-service-s3-overview/), [EBS](//jayendrapatil.com/aws-ec2-ebs-storage/), [Instance store](//jayendrapatil.com/aws-ec2-instance-store-storage/), EFS, [Glacier](//jayendrapatil.com/aws-glacier/) and what are the use cases and anti patterns for each
        *   Would recommend referring [Storage Options](//jayendrapatil.com/aws-storage-options-whitepaper/) whitepaper, although a bit dated 90% still holds right
        *   Understand various [EBS volume types](//jayendrapatil.com/aws-ebs-volume-types/) and their use cases in terms of IOPS and throughput. SSD for IOPS and HDD for throughput
        *   Understand Burst performance and I/O credits to handle occasional peaks
        *   Understand S3 features like different [storage classes](//jayendrapatil.com/aws-s3-storage-classes/) with [lifecycle policies](//jayendrapatil.com/aws-s3-object-lifecycle-management/), static website hosting, versioning, Pre-Signed URLs for both upload and download, CORS
        *   Understand Glacier as an archival storage with various retrieval patterns
        *   Glacier Expedited retrieval now allows object retrieval within mins
        *   Understand [Storage gateway](//jayendrapatil.com/aws-storage-gateway/) and its different types
    *   **Compute**
        *   Understand [EC2](//jayendrapatil.com/aws-ec2-overview/) as a whole
        *   Understand [Auto Scaling](//jayendrapatil.com/aws-auto-scaling/) and [ELB](//jayendrapatil.com/aws-elastic-load-balancing/), how they [work together](//jayendrapatil.com/aws-auto-scaling-elb/) to provide High Available and Scalable solution
        *   Understand [EC2 various purchase types](//jayendrapatil.com/aws-ec2-instance-purchasing-option/) – Reserved, On-demand and Spot and their use cases
        *   Understand Reserved purchase types with the introduction of Scheduled and Convertible types
        *   Understand [Lambda](//jayendrapatil.com/aws-lambda/) and serverless architecture, its features and use cases. How do you benefit from Lambda?
        *   Understand [ECS](//jayendrapatil.com/aws-ec2-container-service-ecs/) with its ability to deploy containers and micro services architecture
        *   Know [Elastic Beanstalk](//jayendrapatil.com/aws-elastic-beanstalk/) at a high level, what it provides and its ability to get an application running quickly
    *   **Databases**
        *   Understand relational and NoSQLs data storage options which include [RDS](//jayendrapatil.com/aws-relational-database-service-rds/), [DynamoDB](//jayendrapatil.com/aws-dynamodb/), [Aurora](//jayendrapatil.com/aws-rds-aurora/) and their use cases
        *   Aurora has been added to the exam and most of time the questions refer to Aurora given its abilities for multiple read replicas and replication of data across AZs
        *   Understand S3 is not a storage option for database
        *   Understand RDS features – [Read Replicas for scalability, Multi-AZ for High Availability](//jayendrapatil.com/aws-rds-replication-multi-az-read-replica/), Automated Backups, underlying volume types
        *   Understand DynamoDB with its low latency performance, DAX
        *   Understand [DynamoDB](//jayendrapatil.com/aws-dynamodb-secondary-indexes/) provisioned throughput for Read/Writes
        *   Know [ElastiCache](//jayendrapatil.com/aws-elasticache-certification/) use cases, mainly for caching performance
    *   **Analytics**
        *   Not much in deep, but understand what the services are and what they can do
        *   Understand [Redshift](//jayendrapatil.com/aws-redshift/) as a business intelligence tool
        *   Know [Kinesis](//jayendrapatil.com/aws-kinesis/) for real time data capture and analytics
        *   Atleast know what AWS Glue does, so you can eliminate the answer
    *   **Security**
        *   Understand [IAM](//jayendrapatil.com/aws-iam-role/) as a whole
        *   Focus on [IAM role](//jayendrapatil.com/aws-iam-role/) and its use case especially with EC2 instance
        *   Understand [IAM identity providers and federation](//jayendrapatil.com/iam-role-identity-providers-federation/) and use cases
        *   Understand MFA and How would implement two factor authentication for your application
        *   Understand encryption services
            *   [KMS](//jayendrapatil.com/aws-key-management-service-kms/) for key management and envelope encryption
            *   Focus on [S3 with SSE, SSE-C, SSE-KMS](//jayendrapatil.com/aws-s3-data-protection/)
            *   Know SQS now provides SSE support 
        *   Refer [Disaster Recovery](//jayendrapatil.com/aws-disaster-recovery-whitepaper/) whitepaper, be sure you know the different recovery types with impact on RTO/RPO.
    *   **Management Tools**
        *   Understand [CloudWatch](//jayendrapatil.com/aws-cloudwatch-overview/) monitoring to provide operational transparency
        *   Know which [EC2 metrics](//jayendrapatil.com/aws-ec2-monitoring/) it can track. Remember, it cannot track memory and disk space/swap utilization
        *   Understand CloudWatch is extendable with custom metrics
        *   Understand [CloudTrail](//jayendrapatil.com/aws-cloudtrail/) for Audit
        *   Have a basic understanding of CloudFormation, OpsWorks
    *   **Integration Tools**
        *   Understand [SQS](//jayendrapatil.com/aws-sqs-simple-queue-service/) as message queuing service and SNS as pub/sub notification service
        *   Understand SQS features like visibility, long poll vs short poll
        *   Focus on SQS as a decoupling service
        *   AWS has released [SQS FIFO](//jayendrapatil.com/aws-sqs-fifo-queue/), make sure you know the [differences](//jayendrapatil.com/aws-sqs-standard-vs-fifo-queue/) between standard and FIFO

<span style="color: #ff0000;">**NOTE**</span>: I have just marked the topics inline with the AWS Exam Blue Print. So be sure to check the same, as it is updated regularly and go through Whitepapers, FAQs and Re-Invent videos.

## AWS Solutions Architect – Associate SAA-C01 Exam Resources

<figure>[![](https://secureservercdn.net/160.153.138.177/3d9.249.myftpupload.com/wp-content/uploads/2018/12/DolfinEd-CSA-Associate-656-x-81.jpg)](https://www.udemy.com/course/aws-certified-solutions-architect-associate-exam/?couponCode=JCSAAAPR)</figure>

*   Online Courses
    *   DolfinEd Udemy [AWS Certified Solutions Architect Associate Exam Mastery](https://www.udemy.com/course/aws-certified-solutions-architect-associate-exam/?couponCode=JCSAAAPR) – **[Highest rated]** AWS course which covers the exam topics in detail, is extensive, scenario based practice questions and visual aids.
    *   Stephane Maarek – [Ultimate AWS Certified Solutions Architect Associate 2019](https://links.datacumulus.com/aws-certified-sa-associate-coupon-jayendra) **[Highest Rated]**
    *   A Cloud Guru – [AWS Certified Solutions Architect – Associate 2018](https://click.linksynergy.com/link?id=l7C703x9gqw&offerid=323058.362328&type=2&murl=https%3A%2F%2Fwww.udemy.com%2Faws-certified-solutions-architect-associate%2F)
    *   Linux Academy –  [AWS Certified Solutions Architect – Associate 2018](https://click.linksynergy.com/link?id=l7C703x9gqw&offerid=323058.1845824&type=2&murl=https%3A%2F%2Fwww.udemy.com%2Flinux-academy-aws-certified-solutions-architect-associate%2F)![](https://ad.linksynergy.com/fs-bin/show?id=l7C703x9gqw&bids=323058.1845824&type=2&subid=0)
    *   Zeal Vora – [AWS Certified Solutions Architect – Associate 2020](https://www.udemy.com/course/aws-certified-solutions-architect-associate-2018/?couponCode=AWSJROCKS-MAR-2020) course
*   Practice tests
    *   Braincert [AWS Solutions Architect – Associate SAA-C01 Practice Exams](https://www.braincert.com/course/14804-AWS-Solutions-Architect-%E2%80%93-Associate-Feb-2018), which provide extensive scenario based questions
    *   Udemy [AWS Solutions Architect – Associate SAA-C01 Practice Exams](https://www.udemy.com/aws-solutions-architect-associate-feb-2018-practice-exams/?couponCode=JAYENDRA)
*   Signed up with AWS for the [Free Tier](https://aws.amazon.com/free/) account which provides a lot of the Services to be tried for free with certain limits which are more than enough to get things going. Be sure to decommission services beyond the free limits, preventing any surprises 🙂
*   Also, use [QwikLabs](https://qwiklabs.com/) for introductory courses which are free
*   Read the [FAQs](https://aws.amazon.com/faqs/) atleast for the important topics, as they cover important points and are good for quick review

## AWS Cloud Computing Whitepapers

*   [Architecting for the AWS Cloud: Best Practices](//jayendrapatil.com/aws-architecting-for-the-cloud-best-practices-whitepaper/)
*   [AWS Well-Architected Framework whitepaper](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf) (This is theoretical paper, with loads of theory and is tiresome. If you cover the above topics, you can skip this one)

## AWS Solutions Architect – Associate Exam Contents

### Domain 1: Design Resilient Architectures

1.  Choose reliable/resilient storage.
2.  Determine how to design decoupling mechanisms using AWS services.
3.  Determine how to design a multi-tier architecture solution.
4.  Determine how to design high availability and/or fault tolerant architectures.

### Domain 2: Define Performant Architectures

1.  Choose performant storage and databases.
2.  Apply caching to improve performance.
3.  Design solutions for elasticity and scalability.

### Domain 3: Specify Secure Applications and Architectures

1.  Determine how to secure application tiers.
2.  Determine how to secure data.
3.  Define the networking infrastructure for a single VPC application.

### Domain 4: Design Cost-Optimized Architectures

1.  Determine how to design cost-optimized storage.
2.  Determine how to design cost-optimized compute.

### Domain 5: Define Operationally-Excellent Architectures

1.  Choose design features in solutions that enable operational excellence.


# [AWS ELB Network Load Balancer – Certification](https://jayendrapatil.com/aws-elb-network-load-balancer/)

# AWS ELB Network Load Balancer

*   Network Load Balancer operates at the connection level (Layer 4), routing connections to targets – EC2 instances, containers and IP addresses based on IP protocol data.
*   Network Load Balancer is suited for load balancing of TCP traffic
*   Network Load Balancer is capable of handling millions of requests per second while maintaining ultra-low latencies.
*   Network Load Balancer is optimized to handle sudden and volatile traffic patterns while using a single static IP address per Availability Zone.
*   NLB is integrated with other AWS services such as Auto Scaling, EC2 Container Service (ECS), and CloudFormation.

## Network Load Balancer Features

### **Connection-based Load Balancing**

*   Allows load balancing of  TCP traffic, routing connections to targets – EC2 instances, microservices and containers, and IP addresses.

### **High Availability**

*   is highly available.
*   accepts incoming traffic from clients and distributes this traffic across the targets within the same Availability Zone.
*   monitors the health of its registered targets and routes the traffic only to healthy targets
*   if a health check fails and an unhealthy target is detected, it stops routing traffic to that target and reroutes traffic to remaining healthy targets.
*   if configured with multiple AZs and if all the targets in a single AZ fail, it routes traffic to healthy targets in the other AZs

### **High Throughput**

*   is designed to handle traffic as it grows and can load balance millions of requests/sec.
*   can also handle sudden volatile traffic patterns.

### **Low Latency**

*   offers extremely low latencies for latency-sensitive applications.

### **Preserve source IP address**

*   preserves client side source IP allowing the back-end to see client IP address

### **Static IP support**

*   automatically provides a static IP per Availability Zone (subnet) that can be used by applications as the front-end IP of the load balancer.

### **Elastic IP support**

*   an Elastic IP per Availability Zone (subnet) can also be assigned, optionally, thereby providing a fixed IP.

### **Health Checks**

*   supports both network and application target health checks.
*   Network-level health check
    *   is based on the overall response of the underlying target (instance or a container) to normal traffic.
    *   target is marked unavailable if it is slow or unable to respond to new connection requests
*   Application-level health check
    *   is based on a specific URL on a given target to test the application health deeper

### **DNS Fail-over**

*   integrates with Route 53
*   Route 53 will direct traffic to load balancer nodes in other AZs, if there are no healthy targets with NLB or if the NLB itself is unhealthy
*   if NLB is unresponsive, Route 53 will remove the unavailable load balancer IP address from service and direct traffic to an alternate Network Load Balancer in another region.

### **Integration with AWS Services**

*   is integrated with other AWS services such as Auto Scaling, EC2 Container Service (ECS), CloudFormation, CodeDeploy, and AWS Config.

**Long-lived TCP Connections**

*   supports long-lived TCP connections ideal for WebSocket type of applications

**Central API Support**

*   uses the same API as Application Load Balancer.
*   enables you to work with target groups, health checks, and load balance across multiple ports on the same EC2 instance to support containerized applications.

**Robust Monitoring and Auditing**

*   integrated with CloudWatch to report Network Load Balancer metrics.
*   CloudWatch provides metrics such as Active Flow count, Healthy Host Count, New Flow Count, Processed bytes, and more.
*   integrated with CloudTrail to track API calls to the NLB

### **Enhanced Logging**

*   use the Flow Logs feature to record all requests sent to the load balancer.
*   Flow Logs capture information about the IP traffic going to and from network interfaces in the VPC
*   Flow log data is stored using CloudWatch Logs

**Zonal Isolation**

*   is designed for application architectures in a single zone.
*   can be enabled in a single AZ to support architectures that require zonal isolation
*   automatically fails-over to other healthy AZs, if something fails in a AZ
*   its recommended to configure the load balancer and targets in multiple AZs for achieving high availability

**Load Balancing using IP addresses as Targets**

*   allows load balancing of any application hosted in AWS or **on-premises** using IP addresses of the application backends as targets.
*   allows load balancing to an application backend hosted on any IP address and any interface on an instance.
*   ability to load balance across AWS and on-premises resources helps migrate-to-cloud, burst-to-cloud or failover-to-cloud
*   applications hosted in on-premises locations can be used as targets over a Direct Connect connection and EC2-Classic (using ClassicLink).

## Advantages over Classic Load Balancer

*   Ability to handle volatile workloads and scale to millions of requests per second, without the need of pre-warming
*   Support for static IP/Elastic IP addresses for the load balancer
*   Support for registering targets by IP address, including targets outside the VPC (on-premises) for the load balancer.
*   Support for routing requests to multiple applications on a single EC2 instance. Single instance or IP address can be registered with the same target group using multiple ports.
*   Support for containerized applications. Using Dynamic port mapping, ECS can select an unused port when scheduling a task and register the task with a target group using this port.
*   Support for monitoring the health of each service independently, as health checks are defined at the target group level and many CloudWatch metrics are reported at the target group level. Attaching a target group to an Auto Scaling group enables scaling each service dynamically based on demand


## AWS Certification Exam Practice Questions

* Questions are collected from Internet and the answers are marked as per my knowledge and understanding (which might differ with yours).
* AWS services are updated everyday and both the answers and questions might be outdated soon, so research accordingly.
* AWS exam questions are not updated to keep up the pace with AWS updates, so even if the underlying feature has changed the question might not be updated
* Open to further feedback, discussion and correction.

## References

[ELB_Network_Load_Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)


# [AWS Organizations – Certification](https://jayendrapatil.com/aws-organizations/)


# AWS Organizations

*   AWS Organizations is an account management service that enables consolidating multiple AWS accounts into an _organization_ that can be created and centrally managed.
*   AWS Organizations includes [consolidated billing](https://jayendrapatil.com/aws-consolidated-billing/) and account management capabilities that enable one to better meet the budgetary, security, and compliance needs of your business.
*   As an administrator of an organization, new accounts can be created in an organization and invite existing accounts to join the organization.
*   AWS Organizations enables you to
    *   Centrally manage policies across multiple AWS accounts
    *   Control access to AWS services
    *   Automate AWS account creation and management
    *   Consolidate billing across multiple AWS accounts

## AWS Organizations

## AWS Organization Features

### Centralized management of all of your AWS accounts

*   Combine existing accounts into or create new ones within an organization that enables them to be managed centrally
*   Policies can be attached to accounts that affect some or all of the accounts

### Consolidated billing for all member accounts

*   [Consolidated billing](https://jayendrapatil.com/aws-consolidated-billing/) is a feature of AWS Organizations.
*   Master account of the organization can be used to consolidate and pay for all member accounts.

### Hierarchical grouping of accounts to meet budgetary, security, or compliance needs

*   Accounts can be grouped into organizational units (OUs) and each OU can be attached different access policies.
*   OUs can also be nested to a depth of five levels, providing flexibility in how you structure your account groups.

### Control over AWS services and API actions that each account can access

*   As an administrator of the master account of an organization, access to users and roles in each member account can be restricted to which AWS services and individual API actions
*   **Organization permissions overrule account permissions.**
*   This restriction even overrides the administrators of member accounts in the organization.
*   When AWS Organizations blocks access to a service or API action for a member account, a user or role in that account can’t access any prohibited service or API action, even if an administrator of a member account explicitly grants such permissions in an IAM policy.

### Integration and support for AWS IAM

*   IAM provides granular control over users and roles in individual accounts.
*   AWS Organizations expands that control to account level by giving control over what users and roles in an account or a group of accounts can do
*   User can access only what is allowed by both the AWS Organizations policies and IAM policies.
*   Resulting permissions are the logical intersection of what is allowed by AWS Organizations at the account level, and what permissions are explicitly granted by IAM at the user or role level within that account.
*   If either blocks an operation, the user can’t access that operation.

### Integration with other AWS services

*   Select AWS services can be enabled to access accounts in the organization and perform actions on the resources in the accounts.
*   When another service is configured and authorized to access with the organization, AWS Organizations creates an **IAM service-linked role** for that service in each member account.
*   Service-linked role has predefined IAM permissions that allow the other AWS service to perform specific tasks in the organization and its accounts
*   All accounts in an organization automatically have a service-linked role created, which enables the AWS Organizations service to create the service-linked roles required by AWS services for which you enable trusted access
*   These additional service-linked roles come with policies that enable the specified service to perform only those required tasks

### Data replication that is eventually consistent

*   AWS Organizations is **eventually consistent**.
*   AWS Organizations achieves high availability by replicating data across multiple servers in AWS data centers within its region.
*   If a request to change some data is successful, the change is committed and safely stored.
*   However, the change must then be replicated across the multiple servers.

## AWS Organizations Terminology and Concepts

![AWS Organizations Concepts](https://secureservercdn.net/160.153.138.177/3d9.249.myftpupload.com/wp-content/uploads/2018/06/AWS-Organizations-Concepts.png)

### Organization

*   An entity created to consolidate AWS accounts.
*   An organization has one master account along with zero or more member accounts.
*   An organization has the functionality that is determined by the feature set that you enable i.e. All features or Consolidated Billing only

### Root

*   Parent container for all the accounts for the organization.
*   Policy applied to the root is applied to all the organizational units (OUs) and accounts in the organization.
*   There can be only one root currently and AWS Organization automatically creates it when an organization is created

### Organization unit (OU)

*   A container for accounts within a root.
*   An OU also can contain other OUs, enabling hierarchy creation that resembles an upside-down tree, with a root at the top and branches of OUs that reach down, ending in accounts that are the leaves of the tree.
*   A policy attached to one of the nodes in the hierarchy, flows down and affects all branches (OUs) and leaves (accounts) beneath it
*   An OU can have exactly one parent, and currently each account can be a member of exactly one OU.

### Account

*   A standard AWS account that contains AWS resources.
*   Each account can be directly in the root, or placed in one of the OUs in the hierarchy.
*   Policy can be attached to an account to apply controls to only that one account.
*   Accounts can be organized in a hierarchical, tree-like structure with a root at the top and organizational units nested under the root.
*   Master account
    *   Primary account which creates the organization
    *   can create new accounts in the organization, invite existing accounts, remove accounts, manage invitations, apply policies to entities within the organization.
    *   has the responsibilities of a payer account and is responsible for paying all charges that are accrued by the member accounts.
*   Member account
    *   Rest of the accounts within the organization are member accounts.
    *   An account can be a member of only one organization at a time.

### Invitation

*   Process of asking another account to join an organization.
*   An invitation can be issued only by the organization’s master account and is extended to either the account ID or the email address that is associated with the invited account.
*   Invited account becomes a member account in the organization, after it accepts the invitation.
*   Invitations can be sent to existing member accounts as well, to approve the change from supporting only consolidated billing feature to supporting all features
*   Invitations work by accounts exchanging handshakes.

### Handshake

*   A multi-step process of exchanging information between two parties
*   Primary use in AWS Organizations is to serve as the underlying implementation for invitations.
*   Handshake messages are passed between and responded to by the handshake initiator (master account) and the recipient (member account) in such a way that it ensures that both parties always know what the current status is.

### Available feature sets

#### Consolidated billing

*   provides shared billing functionality

#### All features

*   includes all the functionality of consolidated billing,
*   includes advanced features that gives more control over accounts in the organization.
*   allows master account to have full control over what member accounts can do
*   master account can apply SCPs to restrict the services and actions that users (including the root user) and roles in an account can access, and it can prevent member accounts from leaving the organization.

### Service control policy (SCP)

*   Service control policy specifies the services and actions that users and roles can use in the accounts that the SCP affects.
*   SCPs are similar to IAM permission policies except that they don’t grant any permissions.
*   SCPs are filters that allow only the specified services and actions to be used in affected accounts.
*   SCPs override IAM permission policy. So even if a user is granted full administrator permissions with an IAM permission policy, any access that is not explicitly allowed or that is explicitly denied by the SCPs affecting that account is blocked.
*   _For e.g., if you assign an SCP that allows only database service access to your “database” account, then any user, group, or role in that account is denied access to any other service’s operations._
*   SCP can be attached to
    *   A root, which affects all accounts in the organization
    *   An OU, which affects all accounts in that OU and all accounts in any OUs in that OU subtree
    *   An individual account
*   Master account of the organization is not affected by any SCPs that are attached either to it or to any root or OU the master account might be in.

### Whitelisting vs. blacklisting

Whitelisting and blacklisting are complementary techniques used to apply SCPs to filter the permissions available to accounts.

#### Whitelisting

*   Explicitly specify the access that is allowed.
*   All other access is implicitly blocked.
*   By default, all permissions are whitelisted.
*   AWS Organizations attaches an AWS managed policy called FullAWSAccess to all roots, OUs, and accounts, which ensures building of the organizations.
*   For restricting permissions, replace the FullAWSAccess policy with one that allows only the more limited, desired set of permissions.
*   Users and roles in the affected accounts can then exercise only that level of access, even if their IAM policies allow all actions.
*   If you replace the default policy on the root, all accounts in the organization are affected by the restrictions.
*   You can’t add them back at a lower level in the hierarchy because an SCP never grants permissions; it only filters them.

#### Blacklisting

*   Default behavior of AWS Organizations.
*   Explicitly specify the access that is not allowed.
*   Explicit deny of a service action overrides any allow of that action.
*   All other permissions are allowed unless explicitly blocked
*   By default, AWS Organizations attaches an AWS managed policy called FullAWSAccess to all roots, OUs, and accounts. This allows any account to access any service or operation with no AWS Organizations–imposed restrictions.
*   With blacklisting, additional policies are attached that explicitly deny access to the unwanted services and actions

Refer Blog Post [AWS Organizations – Service Control Policies](https://jayendrapatil.com/aws-organizations-service-control-policies-certification/)


## **AWS Certification Exam Practice Questions**

*   <span style="color: #ff0000;">Questions are collected from Internet and the answers are marked as per my knowledge and understanding (which might differ with yours).</span>
*   <span style="color: #ff0000;">AWS services are updated everyday and both the answers and questions might be outdated soon, so research accordingly.</span>
*   <span style="color: #ff0000;">AWS exam questions are not updated to keep up the pace with AWS updates, so even if the underlying feature has changed the question might not be updated</span>
*   <span style="color: #ff0000;">Open to further feedback, discussion and correction.</span>

1.  An organization that is currently using consolidated billing has recently acquired another company that already has a number of AWS accounts. How could an Administrator ensure that all AWS accounts, from both the existing company and the acquired company, are billed to a single account?
    1.  Merge the two companies, AWS accounts by going to the AWS console and selecting the “Merge accounts” option.
    2.  **Invite the acquired company’s AWS account to join the existing company’s organization using AWS Organizations.**
    3.  Migrate all AWS resources from the acquired company’s AWS account to the master payer account of the existing company.
    4.  Create a new AWS account and set it up as the master payer. Move the AWS resources from both the existing and acquired companies’ AWS accounts to the new account.
2.  Which of the following are the benefits of AWS Organizations? Choose the 2 correct answers:
    1.  **Centrally manage access polices across multiple AWS accounts.**
    2.  **Automate AWS account creation and management.**
    3.  Analyze cost across all multiple AWS accounts.
    4.  Provide technical help (by AWS) for issues in your AWS account.
3.  A company has several departments with separate AWS accounts. Which feature would allow the company to enable consolidate billing?
    1.  AWS Inspector
    2.  AWS Shield
    3.  **AWS Organizations**
    4.  AWS Lightsail

## References

*   [AWS_Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html)
