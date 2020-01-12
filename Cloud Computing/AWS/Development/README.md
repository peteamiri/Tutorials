# AWS Development

# Regions and Availability Zones 

# IAM

* IAM is global/universal and it is independend of region and AZ independent

* root account is the super user that was created when account is created. 

* Identity and access management it allows the followings:  
	* define the user access and the level of access
	* it allows centrilized control of AWS account
	* Shared access to account
	* Granular permissions Differenct levels of access to various resouorces. 
	* Identify Federation (Active Directory, Facebook, Linkedin, others)
	* It allows Multi-factor authantications
	* Temporary access to users and devices
	* Aloows password rotation ploices
	* Integrates with many AWS services
	* PCI DSS compliance (payment)

* Important Terms: 
	* Users
	* Groups copllection of users
	* Roles Defines a set of permissions assumed by users or systems
	* Policies defiends sets of permissions that can be associated with users, groups, or roles. 

* A user, group, or Role may have more than one policies attached to them. 

* IAM Characteristics
	* IAM allows life-cycle management of users, groups, and policies,
	* IAM provides template policies to ease the process
	* IAM allows password policies (what and when)
	* New Users by default have no access to any resource, they access has to be granted
	* Always Create a MultiFactor Authantication on the root account, it is very important  	

* Policies are composed of series of key value pairs as shown below:
	* Version
	* Statements (Array) 
		* Effect    : "Allow"
		* Action    : "* means all"
		* Resources : Resource types

* IAM Dashboard allows you to create the followings;
	* Groups : (discussed before)
	* Users : (discussed before)
	* Roles : (discussed before)
	* Policies : (discussed before)
	* Identity providers: (need to get more details)
	* Account Settings : (need to get more details)
	* Credential reports : (need to get more details)
 
 * Roles are controlled by Policies
 * Roles are prefered over Access Keys
 * Changes to Role's policies are immediate
 * Roles allow you to avoid using Access keys for resources. 

# EC2 

* it is withing an Region and AZ
* it is a virtual server

* Scaling can be horizontal or vertical.
	* Hotizontal means increas the number of servers
	* Vertical means use a more powerful servers

* EC2 4 Options
	* On Deman allows a fixed rate by hour(Window Servers) or seconds(linux Servers) with no commitments.
	* Reserved is a contract that allows you reserve servers at a significant discunt for 1 year or 3 years terms. you can pay all the fees upfront or some of the fee upfront. 
		* `Standard Reserves instances RI` They can be upto %75 discount 
		* `Convertiable Resever instances RI` Up to %45 discount this allows you to sacel vertically as long as your instance is equal or greater value
		* `scheduled Resevers Instances RI` : this provides a time windows for reocurring schedules (fraction of days, weeks or months)
	* `Spot` you can bid for a price depends on the availability of servers. This is good got applications with flexible starts and ends.
		* If spot instance is terminated by AWS you will not be charged for the hour when you used a partial hour. 
		* If you terminate the Spot instance you will be charged for the hour when you used a partial hour.  
	* `Dedicated hosts`, these are dedicated servers (phyasical EC2 server bearmetal) on them. This is usually due to regulatory or licence requirements. Some regulatory or licencing requirements many prvent the use of multi-tenant virtualization. 
		* it can be purchaded On demand or as reservation with upto %70 descount. 


* EC2 Types
	* many variations (F,I,G,H,T,D,R,M,C,P,X) Fight Dr Mc PX
	* T2 is the lowest cost one

* At the Creation of EC2 you define:
	* AMI
	* Machine Type 
	* Number of instances
	* Purchage Option : Allows selecting spot, on demand, etc. instance. 
	* Netwrok / VPC : select custom VPC or default VPC detailed information is provided in subsequent sections in this document 
	* Subnet : detailed information is provided in subsequent sections in this document 
	* Auto Assign public IP : `Need this if you connect to this instance externally`. 
	* IAM Role, this is important to avoid adding user id and password to connect to other devices 
	* Shutdown behavior: Stop (you can restart), Terminate you delete the Instance
	* Terminatio protection: forces acknowldegment to terminat the EC2
	* Monitoring: allows cloudwatch detailed monitoring (montor every minute charged assocaiated); Regular monitoring is every 5 minutes no charge
	* Tanancy: Single / Multi-tenancy Virtual machine
	* T2 Unlimited: 
	* Addvanced Data: is the boot strap scripts, allowing you to install software when instance is created. 
	* Add Storage allows you select the Volumes to be mounted to the EC2 for roto volume you can chose `CP2, IO1, magnetic`.
	* Add Tages, they will be very usefule in later stages of system administration
	* Add Security Groups : they are virtual firewalls
		* you define Type, Protocols, Port, Source (IP or other Security Groups). Description
		* the Source can be a Cyder notation, 0.0.0.0/0 IP4 or ::/0 for IP6 means any source. When using IP6 you can skip the continious 0000's by using :: 
		* SSH for linux TCP,22
		* RDP for windows
		* HTTP for web port 80
		* HTTPS for secure web 443
	* you need an existing or new keypair This is combination of public and private keys. for SSH to connect to instance
		* download the new keypair. 
		* you can connect from another Linux instance using SSH
		* you can use Putty to connect from the Windows to Linux or use cygwin. addtional steps are required to convert the keypair for Putty.
		* Chmod 400 on keypair,  `ssh ec2-users@ip -i keypair.pem` and follow the instruction
			* use `PuttyGen` to convert the .pem to .ppk  then import the .ppk file as OAuth in putty.   

* `ec2-user` is the default user and it not the root / super user you need to use `sudo su` to have root privilages for any EC2

* run the followings
	* sudo su to have super user access
	* yum update -y 
	* yum install package-name -y 
	* add packeg to service `chkconfig packagename on` or your can remove it from service using off
	* Start package  as a service `service packagename start` you can also check status and stop the service. 
	* you can do the above commands as a boot strap at EC2 creation


* When assigning a Role to a device, group, or user always use the least privilage approach. 

* The EC2 properties can be change by using action on EC2 Console menu drop down select instance setting you will be able to;
	* Add or delete tags
	* Move EC2 to AutoScaling Group
	* Attach/Replace IAM Role
	* Change instance type
	* Chnage termination Protection
	* View or change User Data
	* Change Shutdown behaviou
	* Get System Log
	* Get instance Screen shuts
	* Modify Instance Placement

* The access keys have precedence over roles, when using the aws CLI. you need to remvoe all the access keys to allow Roles to work. 

* You can remove the Access keys from instance
	* in ec2-user home directory For windows OS the it is in $UserProfile\\.aws
	* cd .aws
	* two directories `configuration` and `credential` remove both directories. 

* you can change Roles on EC2 without shutting down the instance. 

# AMI Amazon Machin Images

* It is a template for EC2 that identifes the Operating system and possibly applications that are installed on them 
* Amazon AMI is the one used for all the classes
* you can creat your own custum AMI, this is specially good when using AutoScaling
* there are Alo
	* Market place : AMI for Sale
	* Community AMI : free AMI

# EBS Elastic Block Storage 

* It is a virtual disk
* It is region dependent
* Create storage volumes to be attached to EC2. 
* EBS must be in same AZ as the EC2 that is attached to
* They are replicated across AZ's to prevent single point of failure (SPF) 

* EBS Usage:  
	* Root device (Operating system is installed)
	* Other volums for storage

* EBS Types: 
	* `General Purpose SSD (GP2)` : it is an SSD Drive and it is most popular type, balances of price and performance. 
		* 3 IOPs per GB upto 10,000 IOPS and ability to burst up to 3000 IOPS for extended time for Volumes at 3334 GiB and more 
	* `Provision IOPS SSD (IO1)` : It is a SSD Drive. Used for IO intensive use. for use with more than 10,000 IOPS. It can be provisioned for upto 20,000 IOPs per volume. 
	* `thoughput Optimized HDD  (ST1)` : it is a magnetic disc. `NOT a Boot/Boot volume` Good for BigData, Data warehouses Log Processing.
	* `Cold HDD (SC1)` : Lowest cost storage for infrequently accessed data. `Canot be a Root Volume` 
	* `Magnetic (Standard)` : Lowest cost per GB that can be use as a Boot/Root Drive. Old generation and possibly it will phase out. good for infrequent accessed data. 

* EBS can be encrypted to clear text. Special steps required when trying to encrypt the Root Volume

# Security Groups

* Security Groups are virtual Firewalls 

# Elastic Load balancers 

* Elastic Load balancer routes and balances the load across various servers, by routing the payload using various algorithem. 

* types of Elastic load blancers
	* `Application Load balancer` : Operates at OSI lvevel 7 (application layer), this will impact the performance. it inspect the packet and can route the payload accordingly (need more information)
	* `Networ Load balancer` : Operate at layer 4 it is high performance. Most expensive, and if performnace is a requirment.  Can route millions of payload per second with low latency. It is mostly for TCP protocols. 
	* `Classic Load Balancer` : Original AWS Load balancer, may be phaed out. They do allow Stick Session and X-Forwarded to identify the actual source IP rather than load balancer IP. It is a TCP protocol. It is both layer 4 and layer 7 but not as intelligent as `Application load balancer`. 

* Load balancer may responde with `HTTP 504 Error` gateway time out. This is when Load blancer times out and can not get response from underlaying infrustructure. The followings may be some of the cases that can cuase this error; 
	* If the servers is down,
	* If the server is not accissble,
	* It application on the server is down,
	* it the load is too high. 

* `X-Forwareded-For` will contain the actual senders IP address. This is good when and EC2 is trying to see the original Senders IP instead of the internal routers IP address in the payload. This is used in Classic load blancer. This is only IPV4.

* To create a load balancer 
	* Select the load blancer type (As discussed before)
		* Application Load balancer (Operated at HTTP/HTTPS level layer 7)
		* Network Load balancer (Operates at TCP layer 4)
		* Classic load balancer (Operatess at both HTTP/HTTPS layer 7 and TCP layer 4)

* To create application Load blancer
	* Name : 
	* Schema (internet facing or internal) : 
	* IP Address type : IPV4/ IPV6 
	* Listeners: What port Load Blancer will be listening on
		* Load Blanacer Protocol: protocol and port
	* Avaliability Zone 
		* VPC
		* list of AZ that load balancer is hosted to provide redundancies. 
	* Security Groups: 
		* Assign or create security groups
	* configure Routing
		* Target Group : grouping of the target
		* Name : Target Names
		* Protocol : HTTP 
		* Port : 80
		* Target Type : instance / or IP 
	* Health Checks 
		* Protocol : What protocl to use for health checks
		* Path :  path for health check index.htm 
	* Advanced health Check setting: 
		* Values to be assigned how often to check for health check, how many time for bad server and how long to check again


# Route 53 

* it is a globla or universal service and it is independent of Region
* It is the DNS Server for applications associated with your AWS account
* it provides tha follwoing services;
	* DNS management
	* Traffic management 
	* Availabilty Monitoring
	* Domain Registration

* It allows to map domain name to:
	* EC2 instances
	* Load blancer
	* S3 Buckets
	* cloudFront
	* Elastic Beanstalk 

* `Naked domain name`: is a domain name that as it is registered with out www or any other prefix. generally the A and AAAA record contains
	* "naked domain name"
	* www."naked domain name"

* `Naked Domain name` is also refered to as a `Apex Zone Record` 

* AWS provides Domain registration services (TLD) 

* DNS Record Type supported by AWS:  
	* `A     - Alias Record Type` : is an alias record for IPV4 it routes the IP address to a server, load blancer or S3.
	* `AAAA  - Alias Record Type` :  for IPV6 it routes the IP address to a server, load blancer or S3. 
	* `NS    - Name Server Record type` :
	* `SOA   - Start of Header Record type` :
	* `CNAME - Canonical Name Record type`: 
	* `MX    - Mail Exchange Record type`: 
	* `TXT   - Text Record type`: 
	* `PTR   - Pointer Rerord type` : 
	* `SRV   - Service Locator Record type` : 
	* `SPF   - Sender Policy Pointer Record type`: 
	* `NAPTR - Name Authority Pointer Record type`: 
	* `CAA   - Certification Authority Authorization Record type`: 
	
* When create Route 53 you need to have
	* Name: it can be domain name, alias, server name, cloudfront, Elastic Beanstalk, or etc. 
	* Type is the record type as identified above
	* Alias: must be selected for Apex Zone Record Type or Named Domain name
	* Alias Target: you can select S3, EC2 or load blanacer, cloud front drop down. 
	* routing Policies
	* Evaluate target Health (Yes / No)

# VPC

* upto 5 VPC per Region
* VPC can  be peered as long as the CIDR is not overlaps
* VPC can not be cross region
* VPC can not be peered cross region


# Relational Database Service RDS

* Relational Database key Terms;
	* `Database` : 
	* `Table` : 
	* `Row` : 
	* `Fields or Columns` :  

* There are Six (6) AWS Relational Database Types;
	* `MicroSoft SQL Server` : 
	* `Oracle Database` : 
	* `MySQL` : 
	* `PostgreSQL` : 
	* `Amazon Aurora` :  AWS Flagship database. Fully Compatible with MySQL. It is not avialble for Free Tier. 
	* `MAriaDB` :   

* IN relational databases the schema or structure of the table must be predefiend. 

* When creating database you can use templates
	* Production
	* Dev/Test
	* Free Tier
* You will define the followings;
	* Instance name
	* Admin user
	* Admin password
	* Instance Size
		* Standard Classes
		* Memory Optimized
		* Burstable Classes (Cheapest)
	* Storage Size
	* Storage AutoScaling 
	* Maximum Storage 
	* Multi-AZ - Standby
	* VPC 
	* Additional Connectivity Configuration
		* Subnet Groups
		* Publicly Accessible 
		* VPC Security Group (Chose existing one or Create New one)
		* Availability ZOne 
		* Database Ports  
	* Additional Configuration 
		* Initial Database name (need this to creaet the database)
		* DB parameter group 
		* IAM DB Authantication 
		* Backup
		* Monitoring
		* Log Exports
			* Error Logs
			* General Logs
			* Slow Query Logs
			* Audit Logs
		* Maintenance
			* Enable Auto Miror upgrade 
			* maintenance window 
			* Deletion protection
	* Estimared montly Cost

#### For more information See

* [AWS Documents](https://docs.aws.amazon.com/)

# AWS None Relational Database NOSQL 

* Key Terms;
	* Database
	* Collection = A single Table
	* Document = Row
	* Keyvalue Pairs = Fields 

* NOSQL database do not require predefined Structure (Schema), you can always add addtional keyvalue pair to a Document. 

Following is a sample document

```

{
    "Count": 1, 
    "Items": [
        {
            "AlbumTitle": {
                "S": "Somewhat Famous"
            }, 
            "Awards": {
                "N": "1"
            }, 
            "SongTitle": {
                "S": "Call Me Today"
            }, 
            "Artist": {
                "S": "No One You Know"
            }
        }
    ], 
    "ScannedCount": 1, 
    "ConsumedCapacity": null
} 

```

##### For more information See 

* [AWS DynamoDB Document](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)

# AWS Data Warehousing 

* AWS Data Warehousing engine is `RedShit` 

* Data warehousing is used for business intelligence. 
	* Deals with very large and compex data sets, 
	* Used by mamanget to creat summary reports. 

* General Data warehousing Tools;
	* Cognos
	* Jaspersoft
	* SQL server Reporting Services
	* Oracle Hyperion
	* SAP NetWeaver

* Online Analytical Processing (OLAP) Vs. Online transaction Processin (OLTP)
	* OLTP Deals with CRUD and it is mostly realtime

* OLAP uses different type of architecture and schema than OLTP

#### For more information See

* [AWS Documents](https://docs.aws.amazon.com/)

# ElastiCache

* ElastiCache is an in-memeory Cache. it improves perfromance.  

* There are 2 Types of AWS ElastiCache Engines
	* Memcachedd
	* Redis   
#### For more information See

* [AWS Documents](https://docs.aws.amazon.com/)
* [AWS ElastiCache](https://docs.aws.amazon.com/elasticache)
* [ElastiCache for Redis User Guide](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/WhatIs.html)
* [ElastiCache for Memcached User Guide](https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/WhatIs.html)

# API Gateway 

# Serverless 

# Security

* Always role over authantication
* You should always give users the least privilage  
* Always great groups for specific group of users and assign individual users to that group
* every single user must have his/her own userID (no sharing)
* users automatically inherit the group privilages
* privilages are assigned to groups using policy documents. 
* secret access keys are only once at generation time, if needed again it must be regenerated again and delete the original one. 
* Key pair in this context is 
	* Access Key ID : public key
	* Secret Access Key : private key
* Each user must have his/her own access keys, Never share the access keys. 
	* if the employee is terminated all other users are effected.   

* Always assign roles to resources like EC2. This prevents the developer to embed the Access keys in the servers, or as part of the code
	* hackers scan the githubs for aws access keys ID and secret access keys

# AWS Console, API, SDK, and  CLI

## Console

## CLI

* CLI or command line interface, provides ability to interact with various services using command line. 
	* you can access the AWS resources enternally (to AWS) or internally (within AWS). 
		* for external access you must always user CLI Configure and access keys. Roles will never work. 

* All CLI must start with AWS followed by the services name for example: 
	* `aws s3 ls` list all the buckets in S3
	* `aws s3 ls s3://bucketname` displayes the content of the given bucket
	* `aws s3 mb s3://bucketname`: creates a bucket in S3 
	* `aws s3 cp filename s3://bucketname/subbucket/` copies the file to s3 

* to start CLI you must configure credentials using the following command.
	* `aws configure`, it will promopt you for the followings;
		* AWS Access Key ID: public key of a user with programatic access. This user must have aproper plocy for target resource. 
		* AWS Secret Access Code : private key for same user
		* default Region : Blank is N. Virginia
		* output format : leave blank

* instead of configuring the aws CLI you can assign a Role to the server;

#### For more information about AWS CLI 

* [Download AWS CLI](https://aws.amazon.com/cli/)
* [AWS CLI Documents](https://docs.aws.amazon.com/cli/index.html)
* [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)
* [AWS CLI Reference Guide](https://docs.aws.amazon.com/cli/latest/reference/)

## SDK

#### For more information about AWS SDK
* [Starting point](https://aws.amazon.com/tools/)

## API


#### For more information about AWS API

* [Starting point for AWS API](https://aws.amazon.com/api-gateway/)  
* [AWS Step-by-Step tutorial](https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started.html)
* [AWS API Features](https://aws.amazon.com/api-gateway/features/)

