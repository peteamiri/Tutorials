1) Explain what AWS is?

AWS stands for Amazon Web Service; it is a collection of remote computing services also known as a cloud computing platform.  This new realm of cloud computing is also known as IaaS or Infrastructure as a Service.
2) Mention what the key components of AWS are?

The key components of AWS are
Route 53:A DNS web service
Simple E-mail Service:It allows sending e-mail using RESTFUL API call or via regular SMTP
Identity and Access Management:It provides enhanced security and identity management for your AWS account
Simple Storage Device or (S3):It is a storage device and the most widely used AWS service
Elastic Compute Cloud (EC2): It provides on-demand computing resources for hosting applications. It is handy in case of unpredictable workloads
Elastic Block Store (EBS):It offers persistent storage volumes that attach to EC2 to allow you to persist data past the lifespan of a single Amazon EC2 instance
CloudWatch: To monitor AWS resources, It allows administrators to view and collect key Also, one can set a notification alarm in case of trouble.
3) Explain what S3 is?

S3 stands for Simple Storage Service. You can use S3 interface to store and retrieve any amount of data, at any time and from anywhere on the web.  For S3, the payment model is “pay as you go.”
4) What is AMI?

AMI stands for Amazon Machine Image.  It’s a template that provides the information (an operating system, an application server, and applications) required to launch an instance, which is a copy of the AMI running as a virtual server in the cloud.  You can launch instances from as many different AMIs as you need.
5) Mention what the relationship between an instance and AMI is?

From a single AMI, you can launch multiple types of instances.  An instance type defines the hardware of the host computer used for your instance. Each instance type provides different computer and memory capabilities.  Once you launch an instance, it looks like a traditional host, and we can interact with it as we would with any computer.


6) What does an AMI include?

An AMI includes the following things
A template for the root volume for the instance
Launch permissions decide which AWS accounts can avail the AMI to launch instances
A block device mapping that determines the volumes to attach to the instance when it is launched
7) How can you send a request to Amazon S3?

Amazon S3 is a REST service, and you can send a request by using the REST API or the AWS SDK wrapper libraries that wrap the underlying Amazon S3 REST API.
8) Mention what the difference between Amazon S3 and EC2 is?

The difference between EC2 and Amazon S3 is that
EC2	S3
It is a cloud web service used for hosting your application
It is a data storage system where any amount of data can be stored
It is like a huge computer machine which can run either Linux or Windows and can handle application like PHP, Python, Apache or any databases
It has a REST interface and uses secure HMAC-SHA1 authentication keys
9) How many buckets can you create in AWS by default?

By default, you can create up to 100 buckets in each of your AWS accounts.
10) Explain can you vertically scale an Amazon instance? How?

Yes, you can vertically scale on Amazon instance. For that
Spin up a new larger instance than the one you are currently running
Pause that instance and detach the root webs volume from the server and discard
Then stop your live instance and detach its root volume
Note the unique device ID and attach that root volume to your new server
And start it again
11) Explain what T2 instances is?

T2 instances are designed to provide moderate baseline performance and the capability to burst to higher performance as required by the workload.
12) In VPC with private and public subnets, database servers should ideally be launched into which subnet?

With private and public subnets in VPC, database servers should ideally launch into private subnets.
13) Mention what the security best practices for Amazon EC2 are?

For secure Amazon EC2 best practices, follow the following steps
Use AWS identity and access management to control access to your AWS resources
Restrict access by allowing only trusted hosts or networks to access ports on your instance
Review the rules in your security groups regularly
Only open up permissions that you require
Disable password-based login, for example, launched from your AMI
14) Explain how the buffer is used in Amazon web services?

The buffer is used to make the system more robust to manage traffic or load by synchronizing different component.  Usually, components receive and process the requests in an unbalanced way. With the help of buffer, the components will be balanced and will work at the same speed to provide faster services.
15) While connecting to your instance what are the possible connection issues one might face?

The possible connection errors one might encounter while connecting instances are
Connection timed out
User key not recognized by the server
Host key not found, permission denied
An unprotected private key file
Server refused our key or No supported authentication method available
Error using MindTerm on Safari Browser
Error using Mac OS X RDP Client
16) What are key-pairs in AWS?

Key-pairs are secure login information for your virtual machines. To connect to the instances, you can use key-pairs which contain a public-key and private-key.
17)  What are the different types of instances?

Following are the types of instances:
General purpose
Computer Optimized
Memory Optimized
Storage Optimized
Accelerated Computing
18) Is the property of broadcast or multicast supported by Amazon VPC?

No, currently Amazon VPI not provide support for broadcast or multicast.
19) How many Elastic IPs is allows you to create by AWS?

5 VPC Elastic IP addresses are allowed for each AWS account.
20) Explain default storage class in S3

The default storage class is a Standard frequently accessed.
21) What are the roles?

Roles are used to providing permissions to entities which you can trust within your AWS account. Roles are very similar to users. However,  with roles, you do not require to create any username and password to work with the resources.
22) What are the edge locations?

Edge location is the area where the contents will be cached. So, when a user is trying to accessing any content, the content will automatically be searched in the edge location.
23) What is VPC?

aws-logo
VPC stands for Virtual Private Cloud. It allows you to customize your networking configuration. It is a network which is logically isolated from another network in the cloud. It allows you to have your IP address range,  internet gateways, subnet and security groups.

24) Explain snowball

Snowball is a data transport option. It used source appliances to a large amount of data into and out of AWS. With the help of snowball, you can transfer a massive amount of data from one place to another. It helps you to reduce networking costs.
25) What is a redshift?

Redshift is a big data warehouse product. It is fast and powerful, fully managed data warehouse service in the cloud.
26) What are the advantages of auto-scaling?

Following are the advantages of autoscaling
Offers fault tolerance
Better availability
Better cost management
27) What is meant by subnet?

A large section of IP Address divided into chunks is known as subnets.
28) Can you establish a Peering connection to a VPC in a different region?

No, It’s only possible between VPCs in the same region.
29) What is SQL?

Simple Queues Services also known as SQL. It is distributed queuing service which acts as a mediator for two controllers.
30) How many subnets can you have per VPC?

You can have 200 subnets per VPC.
31) DNS  and Load Balancer service comes under which type of cloud service?

DNS and Load Balancer and DNS services come under IAAS-storage cloud service.
32) What is the role of AWS CloudTrail?

CloudTrail is a specially designed tool for logging and tracking API calls. It helps to audit all S3 bucket accesses.
33) When EC2 officially launched?

EC2 officially launched in the year 2006.
34) What is SimpleDB?

SimpleDB is a data repository of structure record which encourages data doubts and indexing both S3 and EC2are called SimpleDB.
35) Explain Amazon ElasticCache

Amazon Elasticcache is a web service which makes it easy to deploy, scale and store data in the cloud.
36) What is AWS Lambda?

Lambda is an Amazon compute service which allows you to run code in the  AWS Cloud without managing servers.
37) Name the types of AMI provided by AWS

The types of AMI provided by AWS are:
Instance store backed
EBS backed
38) Name the AWS service exists only to redundantly cache data and images?

AWS Edge locations are service which redundantly cache data and images.
39) Explain Geo Restriction in CloudFront

A Geo-restriction feature helps you to prevent users of specific geographic locations from accessing content which you’re distributing through a CloudFront web distribution.
40) What is Amazon EMR?

EMR is a survived cluster stage which helps you to interpret the working of data structures before the intimation.  Apache Hadoop and Apache Spark on the Amazon Web Services helps you to investigate a large amount of data. You can prepare data for the analytics goals and marketing intellect workloads using Apache Hive and using other relevant open source designs.
41) What is boot time taken for the instance stored backed AMI?

The boot time for an Amazon instance store-backend AMI is less than 5 minutes.
42) Do you need an internet gateway to use peering connections?

Yes, the Internet gateway is needed to use VPC (virtual private cloud peering) connections.
43) How to connect EBS volume to multiple instances?

We can’t be able to connect EBS volume to multiple instances.  Although, you can connect various EBS Volumes to a single instance.
44) List different types of cloud services

Various types of cloud services are:
Software as a Service (SaaS),
Data as a Service (DaaS)
Platform as a Service (PaaS)
Infrastructure as a Service (IaaS).
45) State the difference between An Instance  and AMI

AMI is a template consisting software configuration part. For example Operating systems, applications, application server if you start an instance, a duplicate of the AMI in a row as an attendant in the cloud.
46) What are the different types of Load Balancer in AWS services?

Two types of Load balancer are:
Application Load Balancer
Classic Load Balancer
47) In which situation you will select provisioned IOPS over standard RDS storage?

You should select provisioned IOPS storage over standard RDS storage if you want to perform batch-related workloads.
48) What are the important features of Amazon cloud search?

Important features of the Amazon cloud are:
Boolean searches
Prefix Searches
Range searches
Entire text search
AutoComplete advice
49) Can vertically scaling is allows in  Amazon Instance?

Yes, you can vertically estimate one Amazon instance.
50) What is the use of lifecycle hooks in Autoscaling?

Lifecycle hooks are used for autoscaling to put an additional wait time to a scale in or scale out event.
51) What are various layers of Cloud Architecture explained in AWS training?

Different layers of cloud architecture are:
Cloud controller
Cluster controller
Storage Controller
Node Controller
52) What are the storage class available in Amazon s3?

Storage classes available with Amazon s3 are:
Amazon S3 standard
Amazon S3 standard-infrequent Access
Amazon S3 Reduced Redundancy Storage
Amazon Glacier

53) Name some of the DB engines which can be used in AWS RDS

MS-SQL DB
MariaDB
MYSQL DB
OracleDB
PostgreDB
