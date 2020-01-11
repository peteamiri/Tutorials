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

# EBS Elastic Block Storage 

* It is a virtual disk
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

# RDS 

# API Gateway 

# Serverless 

# DunamoDB

# Security

* Always role over authantication 

# AWS API, SDK, and  CLI 