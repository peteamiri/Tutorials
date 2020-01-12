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

* Policies are composed of series of key value pairs as shown below:
	* Version
	* Statements (Array) 
		* Effect    : "Allow"
		* Action    : "* means all"
		* Resources : Resource types
 
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

# Route 53 

* it is a globla or universal service and it is independent of Region
* It is the DNS Server for applications associated with your AWS account 

# VPC 

# RDS 

# API Gateway 

# Serverless 

# DunamoDB

# Security

* Always role over authantication 

# AWS API, SDK, and  CLI 