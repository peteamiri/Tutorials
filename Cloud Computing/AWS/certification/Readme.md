## Resources

* [AWS certification information](https://aws.amazon.com/certification/)
* [Summary of Services](https://www.youtube.com/watch?v=TkT4iFRkaZk)
* [AWS Certification](https://www.youtube.com/watch?v=ye7hgGZwSsY&list=PLJIqXVV4K5LXEGBDPy1mxigzNVMAzkOHv)

* [AWS Quickstart Sourcecodes](https://github.com/aws-quickstart)

## IAAS, PAAS, SAAS

* [Good Picture](https://azure.microsoft.com/en-us/overview/what-is-iaas/)

## Region ##

AWS regions are geographic locations in the world that AWS has a group of data centers. The data centers are commonly knows as Availability zones or AZ for short. Each Region may contain at least 2 data centers. Location like Northern Virginia has as many as six Availability Zone. These AZ's are located such to increase availability in case of any disaster.

* These AZ with in each Region are connected with high speed network.

## Availability Zones ##

As stated previously, currently, there are 35 Availability Zone's (AZ). These zones are consist of **independent "Data Centers"** (for DR reason).

They have low latency Network Infrastructure within a region across the AZ's

Generally; each Region has at least 2 or more Availability Zones

> Note: It is important to Always validate your region, otherwise you may create resources in different regions and you may not know what region they are in.

As default your data is always stays in same region that you store it

you can do cross-region copy, etc.


## Edge Location ##

* CDN (End Point for CloudFront) CDN = Conntent Delivery Networks
* Edge locations are not Availability zones
* CDN is content caching
* CDN caches the static data on S3 to provide low latency access to the data on varius Regions
* CDN also can be used for faster file upload (using CloudFront/Edgelocation for file upload)
* 66 Edge Location

## Network and CDN ##

* Upto 5 VPC per Region
* VPC can  be peered as log as the CIDR is not overlaps
* VPC can not be cross region
* VPC can not be peered cross region

## Route53 ##

* Register Domain Name
* There is a soft 50 domin name limit, this limit can be changed by AWS Support
* 53 is the DNS Port

## CloudFront ##

* Is the interface to CDN

## Direct Connect

* Dedicated line to AWS (Reliable private network, Security)
* Hardeware VPN
* it is a fullly managed and highly available service
* End-point on AWS is "Virtual Private Gateway"
* End-point on Customer Site "Customer Gateway"
* create 2 tunnels (resiliance) each tunnel is terminated in Different AZ's
* Standard IP-Sec Tunnels, Supports AES-256, SHA-2 encryption
* Charges $0.05 / hr / VPN Connections (For the two tunnels)

## AWS DirectConnect

* [Reinvent](https://www.youtube.com/watch?v=DXFooR95BYc)

## Security & Identity Management (IAM)

- Centrilized control of your AWS account
- IAM is not bound to a region, it is universal
- IAM is fully intergated with many of AWS services
- Two methood of connection to AWS
- 	User Id and password
- 	Console requirs user ID and password
- 	you can not use your Access Key ID and secret access key to access the console
- 	Allows loging to the console
- 	you can not use User Id and password for API, ssh login or CLI
- 	Access Key ID and Secret Access Key
- 	Allows programitical access
- 	API,SDK, CLI require access keys (Access Key Id and Secret Access Key)
- 		you can not use this for console login
- 	Multi Factor Authantication is Something you know and something you have
- 		you know the password and user id and code from the token, you need to have one of the followings;
- 		1Virtual/Soft Token (software on your device)
- 		2Physical/Hardware Token (Token generator) Order from AWS
- 	IAM is universal (not depend on a region), and not bound to a region (users are per account and not region)
- 	Power User Policy vs. Admin User, Admin user has same power as AWS root User, Power User can do anything but create users and accounts
- 	Enables to control who can do what with your AWS Account
- 	Shared Access to your AWS account, create various users
- 	Granular Permissions /Fine Grained
- 	Identify Federation (Active Directory, Facebook, Linkedin, Gmail) SSO
- 	Multifactor Authentication
- 	Temprorary security credentials: Allows temprotary and short term access for various users or devices
- 	Password Rotation Policy
- 		Select password change period
- 		How many previous password can not be used
- 		Lenght of password
- 		Mixture of letters
- 	PCI/DSS Support (Credit Card Processing)
- 	Two types of user credential,
- 		1Console Users Password Authentication
- 		2CLI, API, SDK need access key ID and secret Key
- 		need to create groups (optional) and attach policies to either groupp or users.
- 		if you loose these credential you need to delete the user and then add it again
- 	Credential Report provides list of active users, when they used their credentials, when they retated their credentials.
- 		Console-->IAM --> Credential Report
- 	Password Policies:
- 		Console-->IAM--> Account Setting
- 	Secured by default:
- 		as default users/resources can not access anything
- 	There are two kind of plicies:
- 		1Inline Policies
- 		2Attached Policies
- 	As best practices:
- 		Grant least privilage, easier to add more
- 		Each user must have his/her own credential (Do not share)
- 		Credential rotation policy
- 			Create strong password policy
- 		Use groups vs. users for permission settings
- 		Enable CloudTrail
- 		Retate Credentials
- 			rotate access keys often
- 		Use MFA for privilaged access
- 		Do NOT USE AWS ROOT
- terms:
-  User: apply policy
-  Group (group of users to apply a policy to)
-  Roles (allow a resource access to other resources)
- Policies JSON document, it is a Key value pair

## Inspector

## Certificate Manager

## Directory Service

### Resouorces

* [Reinvent](https://www.youtube.com/watch?v=dyspfGRF9Bw)
* [Reinvent](https://www.youtube.com/watch?v=lOT3c-FDKqo)

## WAF (Web Application Firewall)
	protects the application against the commonn exploits
	Stop SQL Injection, cross site scripting and other types Attacks
Artifacts
	Certification of compliances for various Security Compliance Certifications

## Management Tools ##

* Cloud Watch
* Cloud Formation
* OpsWorks
* Config
	Monitors your environement configuration, you can set alerts for when a configuration is changed against the policies you have set to send notifications

* Trusted Advisor
	scans your environement for and provides a series of advises to improve you environement (security, performance, connectivity, cost optimization, etc.)

* Service Catalog
	Allows to create and manage a catalog of services that are approved for use within your company greared toward the governance and compliance

## Application Services ##

* Step Functions
	Visualizing what is going on your application (debuger I assume)
* SWF (Simple Workflow Services) Workflow system
	cordinating tasks
* API Gateway
	API to access backend data, like lambda.
* AppStream
	Stream Desktop Applications to users
* Elastic Transcoders
	Changes video formates

## Developer Tools

* Code Commite
	it is GitHub
* Code Build
	Compile the code Pay by minutes
* Code CDeploy
	Deployment services
* Code Pipeline
	Deploy code to varios environements

## Mobile Services

* Mobile Hub
	Content Delivery for mobile apps, user authentication database access, etc. It is the console for Mobile Apps
* Cognito
	Sing-In utility	(oauth2) signup and signin
* Device Farm
	testing environement for mobile apps, farms of varous devicces
* Mobile Analytics
	collect and use app-usage data
* PinPoint
	similar google Analytics (user behaviour) for mobile (where they are, what they do, etc.)

## Business Productivity

WorkDocs
	Securitly stores the documents
WorkMail
	send and recieve eamils and calandar services

## Internet of Things

IoT

## Desktop and App Streaming

WorkSpaces
	Virtual Desktop
AppStream 2.0
	AppStream 1.0 is retired

Artificial Intelligence

(Ilan Musk SuperIntelligence)
Alexa (Voice Service in Cloud)
	Lex
Polly
	Most Advanced TTS 24 languages, 47 voices, generate Mp3 file
Machine Learning
	give data set and outcomes, and you predict the outcome based on the given case.
Rekognition
	reads images and recognizes various Objects (object name with % of recogintion)
	Facial Recognitions

## Messaging

SQS
	Simple Queue Services, decoupling components
SNS
	Simple Notification Services (email, text, etc.)
SES
	Simple Email Services

### EC2

EC2 is a virtual server. It standss for elastic Compute Cloud (EC2). The instance is charged per hour with different rates depending on the type of the virtual server. These EC2 types are optimized based on the business needs.


EBS availability is garanteed %99.95
AWS recommends to use Roles on EC2 to connect to other resources
Roles can be only assingned at the creation time
Roles can not be assigned to an instance after it is created
	you can change the policies that are attached to the roles (workaround)
When Creating an EC2 you have the following Options:
	1- Create a new KeyPairs
	2- Use and existing Keypair
	3- Proceed without the Keypair
Stop (stops the operating system it can be restarted) Vs. Terminate (Terminates and deletes the Virtual Machine it can not be restarted)
	you have terminate protection (check box) when creating instance
you can not stop an instance with the Instance Store only reboot/terminate.
	when you reboot you wil lose all the data on ephameral storage
You can not change the roles after it is assigned
	You can change the permissions on the role that is currently assigned to the EC2
To Create Key Pair
	Console --> EC2 --> Key Pair --> Create Key Pair need the followings:
	1- Name
		it will display the public key , the private key is downloaded to your computer.
		AWS does not maintain the private keys, if lost you need to create a new key pairs.
	from dropdown you have the following choices:
		1- Choose an existng key pair
		2- Create a new Key pair
		3- Proceed without a key Pair
Cloud Watch resources for EC2 to monitor:
	CPU
	Network
	Storage
	NOT THE RAM
Steps to create EC2 Instance
	if you have windows instance you can get windows password by using the Key Pair
		Instance--> Action --> get windows password
			cut and paste the private key in the window
			1- User Name = Administrator
			2- Password
	Console --> EC2 --> Lunch and Instance there are 6 Steps;
		1- Chose AMI (Linux/Windows/etc) you can even create RDS AMI on EC2 and manage it yourself
			MarketPlace vs. Community AMI
			AMI Type types of VM:
				1- HVM Hardware virtual machine (Better option)
				2- PV Para Virtualized
		2- Chose Instance Types :
			DR MC GIFT PX
		3- Configure Instance
			Number of instance / AutoScaling Group
			Request Spot Instance
			VPC
			Subnet
				Subnet is always within one AZ, Subnet CAN NOT span over AZ
			Auto-Assign Public IP (Yes)
			IAM Role
			Shutddown Behavioor
			Enable Terminate Protection: Protect Accidental termination
				This will not allow you to terminate the instance only to stop the instance
		4- Add Storage
			Root is there /dev/xvda or /dev/sdf Volume type (Delete on Termination) Encrypted ?
			you can add EBS:
				it is persistant
				Types of EBS:
					1- General Purpose SSD(GP2) default
						%99.999(5 nine) Availability
						3 IOPS/Gb and  short burst of 3000 IOPS good for Max 10,000 IOPS
						1GB to 16 TB
					2- Provisioned IOPS SSD(io1)
						IO Intensive Applications
						good for 10,000 IOPS or more, if less use GP2 20,000
						4 GB to 16 TB
					3- Throughput Optimized HDD (st1)
						Large amount of sequential data
						Big Data, Log processing, Data Warehourse
						Can not be used as boot volume
						500 IOPS
						500 GB to 16 TB
					4- Cold HDD (sc1)
						Big Archive
						lowest cost EBS
						Not boot volume
						250 IOPS
						500 GB to 16 TB
					5- Magnetic Volumes (Stanndard)
						Lowest cost bootable volume
						great for infrequent accessed data
						500 IOPS
						500 GB to 16 TB
					if you want to change the type later you can create snapshot and create a new EBS
				Create Sanpshot of EBS into S3
		5- Tag Instance
			Allows to create name, and other information that help in billing and classifing the instances (more useful in larg server farms)
		6- Configure Security Group
			Create a Security Group or use and existing Security Group
			for New Security Group need the following Information:
				1- Name
				2- Description
				Rules for both inbound and outbounds (this  is stateful)
		7- Review and Lunch
		8- Chose the Key Pair (Existing or a New)
		the default user is "ec2-user"
		for windows instance need to RDP (not SSH)
			console-->Instances-->instance-->Action-->get Windows Password
			you upload the private key (the pem file) and you will get the user id and password, user= Administrator
		SnapShots are incremental, the first snapshot contains image of entire volume, the subsequent snapshots contains the changes to the Volume
		To take snapshot from a volume you must One of the followings
			1- Freese the filesystem (or)
			2- Unmount the RAID Array (or)
			3- Shutddown the associated EC2 instance
		this will force all the buffered files to be synced into the disk
		Snapshot of the encrypted volume is encrypted automatically
		Volumes created from the encrypted snapshots is encrypted autommatically
		you can share snapshots, only if they are NOT encrypted (Encrypteion key is tied to your account)
			they can be shared with other accounts or become public and possibly sold (As AMI)
		To encrypt the Root Volume
			1- Stop the Instance
			2- Take a snapshot of the root volume
			3- you can copy the snapshot (you can use this also to creat snapshots across regions)
				make sure you encrypt the copied snapshot (Option in copy screen)
			4- Create a Volumen from the encyrpted snapshot
			5- Use the new vloume for the New instance
Instance purchasing Options:
	1- On-Demand
		get more as you need them with no long term commitments. Charged by hours till instance is stopped or terminated.
		Partial hours is chagred as full hour (stopped/terminated)
		two types of reboot, instance reboot (done through console) Operating System Reboot (from the instance itself)
		When rebooting the instace it remains the same instance (DNS names.IP's) the Instance Stored data is also maintained.
		No Charge for rebooting, or charge for partial hours
	2- Reseved Instances
		determind the avarage use over the year and pay long term commitment (discount upto %70 off compare to On-Demand)
		One Year or 3 year terms, payment can be upfront, partial upfront, No Upfront, Any
	3- Dedicated Host
		most expensive option dedicated Hardwares , you can also reserve the dedicated instacne for discount upto %70 off
	5- Spot instances
		bet on leftover compute capabilities,you get 2 minutes warning beffore shutdown. You pay for hours used AWS pays for fraction hour
		if you terminate before AWS then you pay for the fraction/partial hour otherwise the partial hour is free
		you make bid, you pay market price upto what you bid one when market surpass the bid price you get 2 minute warning

Accessing Metadata
	curl http://169.254.169.254/latest/meta-data

### For EC2 to connect to Internet you must have the followings:
	1- VPC must have Internet Gateway attached to VPC
	2- The Subnet with EC2 must be point to the Internate Gateway via the router
	3- the Instance must have public IP or Elastic IP
	4- The ACL and security Group must allow trafic to and from Inernet

### 5 ways to manage resources

- AWS CLI
- AWS Tools for Windows PowerShell
- AWS Consol
- AWS API
- AWS SDK

to login to the EC2 using SSH use "ec2-user" as the user name
System Status Check Vs. Instance Status Check Under the Status Check Tab for EC2
	System Status indicates that the Hypervisor and the infrustrucutre is working properly
	Instance Status check indicates that the VM and Operation system is working properly
You can have multiple Security Group associated with an Instance
You can have only One ACL on each subnet
For every EC2 --> one or many security group
For every security group --> one ot many EC2 instances
All Changes to Security Groups are immediate
Security Groups are stateful ACL are stateless
with the Security Group You can only allow trafic in/out. You can not deny anything. Deny is always implicit
with ACL you can deny or allow, they are executed by rule number, and it is stateless

### Resources

* [Reinvent](https://www.youtube.com/watch?v=of0BECWQfxE)
* [Reinvent](https://www.youtube.com/watch?v=97Wi7V1wLYA)

## EC2 Container Services (ECS)

* it uses the Docker

## S3

- it is object based, it is an internet storage
- Static objects, or web-based file storage
- You can enable MFA for delete at bucket level and object level on S3
- By default all buckets and objects are private
- you can use Multi-Part for lager files to upload
	you can resume the upload on errors
Bucket Name unique Globally, name must be all lowercase, alphanumeric, with dash
	with Unlimited Storage and objects, objects from 1-5TB size
You can enable the following capabilities at the bucket level
	1- Versioning;
		Once the versioniing is turned on, it can not be off, only suspended
		you will be charged for storage for each version. best practice: setup object lifecycle management with versioning
		if you deleted a version you can not restore it, if you delete the object when versioning is on, you can restore the object
		by deletiing the delete marker
	2- Static Web-Site Hosting
	3- Logging
	4- Tagging
	5- Cross Region Replication optinal
	6- Events (notificcation when specfic event occures)
	7- Lifecycle Management
		Allow you to manage the files lifecycle.
		you can move the file to S3-IA storage (128 Kb min size & 30 after creation), and then to glacier(30 days after S3-IA) and then delete the file
		you can move the version of the file to the S3-IA and then to glacier and then delete the version (if versioning is enabled)
		you can remove the failed multipart upload files
	8- Permission (by default everything is not accessible/or private)
		for read/write (select one or both) for both object and for Changing ACL
		1- Owner
		2- Evryone
		3- AWS users
		4- Log Delivery
	9- analytics
	1- Management
You can perform the following at the object level;
	1- Storage type
	2- Encrytion AES-256
	3- MetaData
	4- Tags
S3 Permissions can be done on Bucket Level or Object Level you can also manage permissions on Versions of the objects
	for read/write (select one or both) for both object and for Changing ACL
	1- Owner
	2- Everyone
	3- AWS users
	4- Log Delivery
	you can also setup a MFA for Object/Bucket deletions, that allows the object/bucket to be delete only if MFA is validated
S3 Charges:
	Amount of Storage
	Number of Requests
	Storage Managemment (Tag the data, and you are charged for tags)
	Data Transfer (incomming free out going is charged)
	Transfer Acceleration: uses Colud Front (incomming)
		Secure
		Fast and easy
1 Byte to 5TB
Bucket Security
	Bucket Policy
	ACL
	you can also enable MFA for delete on either bucket and objects
you can have Access logs to another bucket or another AWS account
Storage Tier
	S3:
		%99.99 Availability and 11-9 Durability (depends on storage type)
	S3-IA: infrequent accessed (Lower fee but charged for retrivals)
		%99.99 Availability and 11-9 Durability (depends on storage type)
	RRS: Reduced Redundancy Storage 4-9 durability and 4-9 availability
		%99.99 Availability RRS is only %99.99 durability
	Glacier: for archival only. 3-5 hours for retrival of the object
		Not all region has glacier
LifeCycle Management
Versioning
Encryptions
	in transit
		SSL/TLS
	At rest
		Server side
			S3 Managed Keys SSE-S3 (AS-256 encryption) fully managed, the keys are encrypted with another key and that key is rotated regularly,
				This is fully managed process.
	 		S3 Key Managged SSE-KMS Manages Keys (default or your own keys), KMS also provides log of who access the keys for autditing
			S3 Customer provided S3 SSE-C Customer manages the keys
		Client Side
			you encrypt the file and then upload the file
Secure the objects:
	1- ACL
	2- Bucket Policies
	3- IAM Access Control Policy
Bucket, Objects and folders
Bucket Names are universally Unique (Accros all Regions)
Objects within S3 always remain in same region
When Upload the file, you will get http 200 code if operation was scccessful
AWS account have upto 100 Buckets Unlimited Objects in a single Bucket
You can not creat a bucket within a bucket, you can create Folders within a Bucket
Bucket Name can  be between 3-63 characters all lowercase and  alpanumerical
URL are as follow:
	https://s3-Region-Name.amazonaws.com/acloudguru
		S3-Region       Amazon        BucketName
No limits to the S3 Storage Size (you can have unlimited number of Objects)
Highly Scalebale and Durable
Encrypption Available
	At Rest
		SSE-S3 : Server Side Encryption, Amazon handles key management and key protection.
				each object is encryppted with unque key, keys are encrypted by a master key. Master Keys are rotated monthly
				Keys are stored on seperate host.
		SSE-C : Server Side Encryption, Customer nmanage key (Send the key)
		SSE-KMS : Server Side Encryption use KMS to manage your own keys
		Customer: encrypt the data before uploading
	In Flight
		SSL/HTTPS
Object contains the followings:
	1- Key
	2- The Data (or the objects itself)
	3- Version
	4- Metadata (e.g data of creation, etc.)
	5- Source Resources
		Access Control List
		Torrent
you can use tags to sub-categorize objects, Tags are key-value pairs associated with each object. You can have upto 10 tags.
	You can use Tags with IAM Policies. There are charges for tags.
Data Consistency Model for S3:
	1- Read after write consistancy for PUT of new Objects (first write is after all copies are created)
	2- Eventual Consistancy for overwrite PUTS and Deletes (a few secons latancy of update)
		you will either get old data or new data, never partially updated data
		if you read right after update you may get older version of object
S3 Buket Names are unique across the region for all accounts
to Create a Bucket
	Console-->S3-->Create Bucket
		1- Provide Unique Name (across the region for all accounts)
Objects remain in same region as they are created
	you can configure multi-region copies A.K.A cross-region-replication
Object Level Permisions
Objects can be 1Byte to 5TB
Object Meta data
buckets
	Folder
	Objects
Versioning
Object Lifecycle Management
Security
	IAM Policy
	ACL
	Bucket Policy
Encryption
	in-flight / in-transition encryption
	At-rest encryption
Methods to  get Data into S3
	AWS Direct Connect
	AWS Snowball
	AWS Snowball Edge
		Device for PetaByte storage to send to AWS with limited compute power
	AWS Snowmobile
		Very Very Large amout of data,
	ISV Connector
	AWS Kenesis Firehouse
	S3 Transfer Acceleration
		Use of CloudFront (Edgelocation) as means to upload the data
	AWS Storage Gateway
		op-premise data connection with AWS cloud
S3 Analytics
	Visual tool that shows your data usage patterns, and help you set data lifecycle plicies to move data to
		S3 --> S3 IA --> Glacier--> Expire/Delete to save costs
	you can also expoert this to Excel and other applications for more inddept analysis
to impprove performance have randomnes in first few charactire of file name, this will move the data in differenct partitions
	less cloide and faster access
you can use CloudTrail to create Audits for objects(new for objects) and bucketsi, logs are saved on S3, charge of $0.10 for every 100,000 events as well as the storage.
Cross Region Replication, you must have versioning enabled for this
you can run CloudWatch to monitor and set alarms to get notifications, by buckets or tags.

### Resources

* [Reinvent](https://www.youtube.com/watch?v=9_vScxbIQLY)

## Glacier

- Data Archiviing
- Write-Once read-never
- 3-5 hours to retrive
- very cheap


## EFS

Elastic File Service
	NFS or shared volume across multiple EC2's
Similar to EBS, not bootable
It uses NFS V4

Local Instance Storage:

temporary block-level storage for Instances. These storage are physically connected to the instances. Greate for temporary storage (Cache, Buffers, temp)
Emphemeral = transient this information is not saved when the instance is (instance can not be stopped) terminnated.
	Also the data is lost with disk drive failes.

## EBS

- Elastic Block Storage
- Volume = Virtual Disk in CLoud
- when terminating the instance by default the EBS is deleted, unless the Delete On Termination is checked off (as default it is checked to allow termination you must uncheck it)
- You can Check, Delete on Termination box when Adding EBS Storage to EC2 instance, this will delets the EBS when EC2 is terminated.
	default is teminate when EC2 is termindated
Root Volumen = /dev/xvda
Other Volumen = /dev/sdb
by default the EBS root volume is not encrypted (EAS 265) and you have option to encrypt the other volumes at cration time
	you can encrypt the root volume using third party tools,
		you can create a new AMI and make the root device encrypted on the new AMI
TO Create EBS make sure it is in a same AZ as the EC2 otherrwise you can not attach it to the EC2
	Console-->EC2-->Volume-->Create Volume you need the following Information:
		1- Volume Type Dropdown;
			1- General Purpose SSD(gp2) default
				upto 10,000 IOPS
			2- Provisioned IOPS SSD(io1)
				10,000 to 20,000 IOPS
			3- Throughput Optimized HDD (st1)
				not for boot ebs
			4- Cold HDD (sc1)
				not for boot ebs
				Big Archive
			5- Magnetic Storage
				for boot but slow and cheap
			if you want to change the type later you can create snapshot and create a new EBS
		2- Size
			1GB to 16TB
		3- IOPS
		4- Througputs
		5- AZ
		6- SnapShot ID
		7- Encryption: Encrypt this volume
	Need to attche the Volume to an Instance
		Select the volume --> Action--> Attache
			Select the instance in that AZ from the dropdown
			Device /dev/sdf
		You need to format and mount the volume
To create snapshot of Volume, select the volumen-->action-->creat snapshot provide the following information:
		1- Name (Snapshot)
		2- Description
		3- Encrypted (No/Yes) no option to change it

- you can create volume from snapshot,
- you can create snapshot from volume
- you can modify/change volume type when creating volume from snapshot

### Resources

*[Reinvent](https://www.youtube.com/watch?v=AnLCr99kFcY)

## Storage Gateway

* Means to connect on-premise to AWS/S3 it is a virtual machine image running on VM on-premise
* the VM is VMwaure ESXi or Microsoft HyperV
can connect via dirct connect or AWS VPC (VPN) EC2 (need more inforramtion)
* It is a virtual appliance and it replicate the data from your datacenter into S3 and possibly Galcier
* it  can be downloaded and it runs on VMWare ESXi or MicroSoft Hyper-V

### four types of Storage Gateways:
	1- File Gateway (it uses NFS) Flat files in S3
		you can use bucket polices after the upload
		connections across the sites can be provided by
		Direct Connect or VPN
	2- Volume Gateway (iSCSI) block based storage like Virtual Hard-drive
		this is like raw device data
		Like Virtual Hard Disk saved as AWS EBS Snapshots
		like a point-in-time snapshot(Similar to EBS snapshots) and written Asynchronously
		All snapshots are incremental and they are compressed to reduce the storage utilization
			only blocks that are changed are stored in subsequent snapshots
		two types:
		1- Stored Volumes
			entire/complete data set locally and asynchronously copied/backedup to AWS S3
			1GB to 16TB size as AWS EBS Snapeshots
		2- Cached Volumes
			S3 as the primary storage you keep the sub-set on the premises
			1GB to 32TB
	3- Tape Gateways (VTL) virtual tapes
		uses existng tape cartdges. Comppatible with NetBackup, Backup Execm Veam, etc.
## AMI

- AMI are regional
- If you want to creat a AMI in another region you must manually copy the AMI
- There are two types of AMI
	1- EBS Backed : you can terminate/reboot/stop the instance, you can detach and attache the volume, you can encrypt the volumne, more selction of AMI
		The AMI is created from EBS SnapShot
		Faster instance Creation
		The EBS generally is independent of the instance, it instance fails you have the data
			if you have terminate EBS when instance s terminnated checked you will loose the EBS, not the snapshots
	2- Instance Backed (instance Store / EPHEMERAL Storage ): You can only Reboot/Terminate you can not stop the instance, you can not encrypt the volume
		Attache and detach is not an option, the AMI types are very limited
		The AMI is created from a Template (Not a Snapshot)
		Slower instance Creation
		If instance failes you loose all the data
		you will not loose data on reboot
		The Storage is deleted when instance is terminated (No Options)

To Create AMI two steps,
	1- Create Snapshot of root device
	2- Create Image/AMI from snapshot
	3- Change Image Permision from private to public (optional)
	4- You can share image with other accounts without making AMI public
To Create AMI
	Select the instance-->action-->Image-->Create Image Provide the following Information:
		Image Name:
		Description
		No Reboot (Check Mark) Prevent the instance to reboot while creating AMI
	This will reboot the instance : Best practice is to run against instances that are not running
to See the Create AMI
		Console-->EC2-->AMI list of existing AMI
			you can creat new instance from this AMI
three types:
	Amazone  Maintained
		created and maintained by AWS in each regin (Free)
	Community Maintained
		created by other users, and maintained by MarketPlace (not free)
	your Machine Images
		you create them, It can be private or share with other accounts
Back-In Vs. Configure Dynamicly
	Create static in AMI and more dynamic in user data at instanciation (application code)
	best practicce use the combination of two

CloudFront

Content Delivery Network, number of servers cache the contents to deliver,based on the locations, Edge Locations
there are aboout 50 edge locations in the world
Objects are cached for the given TTL before they are upated again
	if you clear cached objects prior to TTL you may be charged
they are not limited to read-only. You can use Edge locations for faster uploads/write also
three parts to CloudFront
	Edge Location: locations that that contents are cached, Totally independent of the AZ and regions.
	Distribution
		Collection of the Edge Locations
	Origin
		S3, EC2 Web Server, ELB, Route53, Custom Origin or none AWS origin servers.
You can lockdown the Origin in S3 to CloudFront Only (no one but CloudFront has access to the Object)
To Create Distribution
	Console-->CloudFront-->Create Distribution-->RTM/Web
		RTMP is for Adobe Flash
		Web is for Static Objects
		provide the following information:
			Distribution (drop Down, source or Orgin) S3 Bucket
				Origin Domain Name: drop down with all bucket names
				Origin Path: directories within the bucket
				Orign ID is a given name and not necessary the bucket name
			Restic Bucket Access Yes/No
				Yes --> Only CloudFront can access the bucket
					Create a new IAM Identity/Existing IAM Identity
					Grant Read Option Policy (Yes/No)
			Path Pattern
			you can have http / HTTPS
			you can limit the access to Distributionn using Signed URL or Signed Cookies
			you can have compression of object while in flight (Browser capability)
			you can enable the WAF and Web ACL
			Set TTL (Max, Min, Default) in seconds
			Object Caching (Define TTL or get TTL from Obect Header)
			Price Class : what Geographic Location to distribute the object
			SSL Certificate Default/Your Own
			Logging Yes/No if Yes specify log bucket and file
			you can blacklist/whitelist access to certain countries
Fully Managed Service
Supports HTTP and HTTPS
Sources of CloudFront
Realtime reporting
URL for objects are randonename.cloudfront.net/bucketname
Characteristics:
	1- Highly Secure
	2- Highly Available
	3- Scaleable
	4- Performant / Low Latency
	5- Cost Effective
	6- Easy to use

## EBS

* Reduce Redundancy Storage
* Standard
* Provsioned IOPS
* RRS
* RAID
* SnapShots
* RAID
* RAID is reddundant array of disks
	* RAID 0 -Striped, No Redundancy, Good Performance (Gaming)
	* RAID 1 Mirrored, Redundancy
	* RAID 5 3 Disk or more Good reads, bad writes, AWS does not recommend it
	* RAID 10Combination of RAID 1 and RAID 0, Striped & Mirrored, Good Reedundancy, Good Performance
* Reommended RAID 0, 10 Avoid RAID 5

## RDS

- While taking backup your Database IO my be suspended
- When delete the database the backups will be removed
- The snapshot remains even after removing the RDS
- You do not have SSH or Root Access to the instances, databases are fully managed bu AWS
- Not all Engines support data encrypption at rest
- You can not encrypt an existing instance, you must create a new instance
- you can copy the snapshots to different regions.
- When Encrypt RDS data at rest, all the followings are encrypted also:
	automated backups,
	read replicas,
	Snapshots
* Data Encryption at rest is only suppported for, MySQL, Oracle, SQL Server, PostSQL and MariaDB
	the Key is stored in KMS,
Point-in-time recovery, is ability to recover a database from the backup and transaction logs to a given second within a "retention period"
Retention Period can be between 1-35 days.
Automatic logs take snapshot of the database and maintain the transaction logs.
Automated backup is enable by default, the backup is stored in S3, and you get free storage equal to the size of database
While backup is being performed, storage I/O is suspended, and it may result in an increased latency
Snapshot is a done manually and they are not backup, Snapshots are not removed when database is deleted, but backups are deleted.
When you restore the backup or snapshots, they are restored in a new database instance.
fully managed
	backup, patch, maintenace, and availability is responsibility of AWS
	you do not have any access or control over server No RDP, SSH to server
	you can have access to database and control it at application side not physical side
	you can have multiple AZ option, and you can select the AZ's within a single Region
Relational DB
	MariaDB, MySQL, PostSQL, Oracle, SQL Server, AruraDB
For Oracle and SQL Server you have two type of licence;
	Licence is Included
	Bring your own Licence
For SQL Server you can not resize the DB and you can creat the engine but not the Database (like Sybase)
Max Backup retention is 35 days (take backup every 35 days)
backup windows (define when to take backup)
maintenance windows:
Some Database instances you can not increse the size/Resize (SQL Server) you may have to perfrom Capcity planning

#### Resources

* [Reinvent](https://www.youtube.com/watch?v=TJxC-B9Q9tQ)

## Aurora:
- is a relational DB, upto 5 times faster than MYSQL,
- 	mySQL compatible
- 	starts at 10GB and increases in 10GB increments.
- 	Max 32 vCPU, and 244 GB Memory
- 	2 copies per AZ, with minimum of 3 AZ's (6 copies of your data)
- 	Self-Healing: Data blocks are validated in background and fixed constantly
- 	Always use the Cluster Connection String to connect, this allows the transparent switch over when primary(write) instance is down)
- 	Not available on all Machine Sizes (No T2.macro)
- 	you can have 2 types of replica
		Aurora (up to 15)
		MySQL (upto 5)
Pricing:
	Starts at 10Gb and increament in 10GB upto 64Tb
Availability:
	2 copies are kept in EACH AZ with minimum of 3 AZ---> 6 Copies of data you can read from any of the nodes
	it handles upto 2 copies of data lose without affecting the write availability and 3 copies without affecting the read
	Self Healing, all bloocks are scaned for errors and fixed
Scale up to 32 virtual CPU and 244 GB RAM
Multi-AZ is available for SQL Server, Oracle, MySQL, PostgresSQL MariaDB (Elastic Map Reduce)
Multi-AZ RDS is for DR only, not for performance, to improve performance you can use read Replicas.
	when primary failes, the database is switched to the second db automatically (no manual intervention) and no connection string changes
Multi-AZ is done synchroneously replication
read replica are asynchronous
you can not have multi-az read replica, only the primary can be multi-az
you can have upto 5 read-replica databases, only for MySQL, PostgreSQL and MariaDB
Read Replica is fro scaling and not DR
You must have autoomatic backup setup in order to have read-replica
You can promote the read-replica to be its own database, but this will break the replication (no more replication)
Read Replica is asynchroneouse replication of data into new instances that are read-only (e.g. reporting)
	you can have read-replica of read-replica (there could be a latency), and you can have upto 5 copies of the database
	read-replica is supported only for the followings:
	1- MySQL
	2- PostGreSQL
	3- MariaDB
	4- AroraDB
You can have cross region read-replica (ony for MySQL and MariaDB, Not for PostGreSQL)
Scaling is much easier with DynamoDB it is more manual in RDS
NOSQL Engines
you can scale the dynamoDB on fly, wwithout any downtime (automatic scaling)
RDS scaling is more manual
SimpleDB
	highly available NOSQL DB
	Fully Managed
	Multi-AZ
	Data is automatically Indexed
	Flexible/Simple

#### Resources

* [Reinvent](https://www.youtube.com/watch?v=DAJhvRMniqo)

## NOSQL Database vs. RDBSM

The Nosql db has the following advantages;

1- Leanear scaling
2- No relationship / Siingle table
3- No fixed Schema
4- More agaile in creation (No schema)

# DynamoDB
	Preddictable Performance
	Massively Scalable
	Highly Available %99.99, Highly Durable
	Fully Managed
	Low Cost
	It is always stored on Solid State Drive (SSD) only
	is a Document Bases NoSQL engine
	It is always spread over 3 distinct data Centers (possibly AZ's)
	Eventuall Consistancy by Default but can be configured to be Stronglly Consistent Read
		when replicated there could be delay in data changes across 3 data Centers (One Second)
	You are charged for read, write and storage

## DynamoDB vs. SimpleDB
	SimpleDB is not as scalable as DynamoDB, more complex
	SimpleDB is simple/Flexible DynamoDB is scalble and Fast with predictable performance
	DynamoDB can be considered as Successor of SimpleDB
Access Pattern
	Relational DB are optimized for Storage, NoSQL optimized for Computing.
Difference between DynameDB and MongoDB is you can not nested Key-Value Pairs in DynameDB
RDS can Scaleup, NOSQL ScaleOut
Replicated across 3 AZ's
DynameDB (unlike MongoDB) does not allow embeded data structure (key  value pair inside the record)
DynamoDB is only installed on SSD, with three AZ's
two options in Replication:
	1- Eventual Consistent Reads (Default)
		when reading the data you may not get the latest data, you have to wait for the data replicated, Best performance lowest latency
	2- Strong Consistent Reads
		may have higher latency, but you always get the latest data. (may wait till all data is replicated across all AZ's)
Pricing of DynamoDB:
	1- Provisioned Throughputs
		allocate number of read
		Allocate number of write
		and storage ($0.25/GB)

### Resources

* [Reinvent](https://www.youtube.com/watch?v=HaEPXoXVf2k)

## Analytics:
### RedShift
	Data Warehousing
### Athena
	Allows to run SQL against the S3, turn flat files to Database
	usecase: csv files, json files
### EMR (Elastic Map Reduce)
	Hadoop, Apach Spark, Apach HBase, Presto, Flunk
### CloudSearch
	Fully Managed search engine
### Elastic Search
	Open Source Search Engine
### Kinesis
	Streaming and analysing realtime data, capture and store TB of data
	Data Pipeline
	Allows you to move data from S3(and other resources) to Datastorage (and other resources)
### Quick Sight
	Business Analytics tool provides visual dashboard.

### RedShift
Data Warehousing / OLAP
It is fully managed, Single AZ installation, Redundancies are manual using spanshots
Claimed to be 10 faster than other Dataware housing Engines
data is compressed to optimize storage utilization
It uses only columns and no tables
No Indexing, No views,
Advanced Comppressions for a specific data types
Provides Encyrption for data in Transit
1-128 Nodes you are not charged for leader node only for compute nodes
Two Components:
	Leader Node : mamange the Client conntection and queries and results (160GB)
	Compute Nodes: performe all the calcullations and queries
Charges:
	Compute node / hours
	Backup
	Data Transfer (within the VPC)
	you pay for Computer nodes only
Security:
	Encryppted in transit
	Encrypted at rest using AES-256
		redshift manages all the keys
		you can also manage keys using HSM or AWS KMS
Availabilit
	1 AZ only if you loose that AZ, you can restore in another AZ, this is a manual process
	RedShit can not cross AZ's
	Reporting services does not require high availability
two parts:
	1- Leader Node
		Manage Client connections and recieves the queries
	2- Compute Nodes
		perform all the work
Uses MPP (Massively Paralell processing)

## Route53

you are charged for CNAME, but ARecords are free
There are max 50 Domain Name , this limit can  be increased by AWS support
Global Service not by AZ's or region (configuration is not limited to the a region)
Public Hosted Zone Vs. Private Hosted Zone
allow you create private hosted zone, this is to allow you assign arbitrarry TLD without registering the TLD (Good within the VPC)
	this is good only within the AWS
Zone Apex record (AKA naked domain name) is the TLD without the WWW
it is a managed service, across all region, global.
After creating Hosted Zone, it may take 48 hours to take effect (DNS Cached)
%100 Avaiablity, use over 50 locations
It strickty deals with IPV4 (2017 supports IPV6) some resources support IPV6 but it is not fully implemented yet
Access Route53
	SDK,CLI, API, AWS tools, Console, Third Party Tools
Create DNS Entries:
	1- Create Domain Name
		if you use AWS to buy the domain this is done for you,
		otherwise:
		Console-->Route53-->HostedZone-->Create Hosted Zone and provide the followings:
			1- Domain Name
			2- Comments
			3- type (drop down) select public hosted Zone
		are created for you are: NS(Name Servers), SOA records
	2- Create Hosted Zone
	3- Create records in Hosted Zone
	4- Deligate to Route53 (Update the Registrar with Server IP) if you buy the Name from amazone this part is done for you
	you can have wild card *.example.com (anything else)
	Create Record;
		domain,
		Record Type
		TTL
		IP / Alias
		Ruting Policy

Record Types
	CNAME: does not have Ip but it is a DNS Name (www.example.com) this is also refered to aliasing
	CNAME stands for  Canonical Name
	There are charges for resolution to CNAME, the A Record is free
	A Record is Address Record, in AWS it is refered to Alias Record
	You can not use CNAME for apax/naket domain name translation to another domain name
	A Record in DNS = Address Record, in AWS it also referes to Alais Record, it is only for IPV4
	AAA Record is same is ARecord with for IPV6
	TTL (Time to Live) for DNS is always in Seconds, time to cache this record
	A (Alias Record) this record is for Root Domain and Sub-Domain , you can provide the Alias name (use public host name instead of IP)
		this can be:
			ELB, Elastic BeanStalk, CloudFront,S3
	NS Name Servers (pass to the Register to like the tld to AWS servers)
	SOA : start of authority (Start of the Zone)
	TXT record for email validation
	MX email host
Routing Policies:
	Simple : default routing policy, used when you have a single reource to map to (Single EC2/Load Balancer/etc). No intellignece is buit into it.
	GeoLocation: users are routed based on their geological locations, to the certain location/region as defined by the configuration
	Failover: if device is failed to pass healthcheck, then route the traffic to the secondary resources (Active And Passive Site)
	Weighted: split the trafic based on a static / predeined allocation (%10 to one server %90 to another)
	Latency: route the record to resources with the minimum latancies. The DNS automatically sends the user request to a given region defined in the DNS Record.


ElasticCache
Managed service
two diffferent engines:
	1- Radis
		Master Slave replications and Multiple AZ deployment
		Key Value
	2- MemCached

CloudWatch
allows various monitoring capabilites. It shows the utilization of Disc, RAM, CPU and other resources.
1- Basic monitoring (Free) is done every 5 minutes and stored for two weeks The followings are default matrics
	CPU
	Disk I/O (Various Opertaions Read, Write,etc )
	Network I/O (Various Operations)
	Status Check
2- Detailed Monitoring ($0.015/hr), 1 minute intervals

you can integrate Cloud watch to Console
you can use SNS for CloudWatch
you can integrate with AutScaling


### CloudTrail

Provides loging and auditing.

### CloudFormation
	Allows you to create a Template
Templates
	Description
	Prameters
	Resources
		Type
		Properties

### Elstic BeanStock
Provision underlaying resources for application
BeanStock is a Free, but you pay for the resources that you create (EC2, S3, EBS, etc)

### Lambda
- ServerLess
- Upload to code and it is triggered by an event
- It is fully managed, just run the code
- Fully scaleable
- it runs the code in response to an event. It manages all the resources
- Supports Four langugaes: Java, Nodejs (I assume this means JavaScript), Python, and C#
- it is 99.99% availablity (4 nines)
- Chargess are per requests (first 1 Million are free), $0.20 / Million Requests there after
	Also duration of execution(rounded up to 100Ms), and memory utilization GB used per seconds after frist 400,000 GB/Seconds
you can run the code using
	AWS SDK
	AWS Gateway API
	Invoked by an Event (need to findout more)
#### Resoourcs

* [Reinvent](https://www.youtube.com/watch?v=WbHw14hF7lU)
* [Reinvent](https://www.youtube.com/watch?v=Xi_WrinvTnM)
* [Reinvent](https://www.youtube.com/watch?v=QdzV04T_kec)
* [Lambda with Example](https://www.youtube.com/watch?v=xyHi1hR-UzA)
* [Lambda](https://www.youtube.com/watch?v=fSUEk6iMW88&list=PLzvRQMJ9HDiSQMe68cti8cupI0mzLk1Gc)


### Lightsail
Web Application Servers:
	Wordpress
	Jumla
Messaging
### SNS
	Messaging services
### SQS
	Message Queue system, means to decouple application
### SES
	Simple Email Service

Mobile Hub
Console	for Mobile applications
Cognito
Device Farm
Mobile Analytics
App usage data
Pinpoint
gathers information regarding the user behaviours
WorkDoc
Documentation storage
WorkMail
send and recieve email
IoT
Internet of Thiings
WorkSpace
Virtual Desktop

SES
SWF
Simple Workflow Similar to BPM
Deciders
Activity Workers
OpsWork
provides admiinnistrative task using Chef.
Config
monitoes and generate warnings when a specific task are performed. allows monitoring the changes of resources.
CloudSearch
AWS Trusted Advisor
automated process that provides advices
Security
Shared Security Model
----------------------------------
VPC
Similar to your Data Center Network, AKA Virtual DataCenter
When you creat a custom VPC the AWS created following automatically:
	1- Route Table
	2- Security Group
	3- ACL
Every VPC has a default Route Table, as best practice do not delete the default route table
When you allocate Subnets the following addresses are revereved:
	1- X.X.X.0
	2- X.X.X.1
	3- X.X.X.2
	4- X.X.X.3
	5- X.X.X.255 Brodcast address
	Results in 251 addresses available for resources
Do not Delete Default VPC, you can not re-create it, you must call support to re-create it
Default VPC vs. Custome VPC
	you can have custome IP's address range, Route Tables, Custom Subnets , and Gateways
VPC is within a Regsion and not across region
VPC can span over multiple AZ's
VPC Subnet Mask or CIDR must be between /16 and /28
VPC Restrictions:
	1 and only one Internet Gateway
	5 Elastic IP / VPC
	5 Internet Gateway / region
	5 VPC / Region
	100 Security Groups / VPC
	50 Rules / Security Group
	50 VPN Connection Per Region
	50 Customer Gateway Per Region
	200 Route Table Per Region
VPC Components:
	ENI Elastic Network Interface
	Subnet
	ACL Network access control list
	Route Table
	Internet Gateway
	Virtual Private Gateway
	Customer Gateway
	Route 53 private/public hosted zone
To Create VPC: console-->VPC (Either use wizard or Create VPC Option) you need the following:
	1-Name
	2-CIDR
	3-Tenancy
To Create Internet Gateway and attach it to the custom VPC:
	Console-->VPC-Internet Gateway-->Create Internet Gateway Provide the followings:
		1- Name
		then you need to attach it to a VPC by clickiing on Attach (select from option of all VPC's without any Internate Getways)
To Create a Custome Route Table console-->VPC-->Route Table-->	Create Route Table you need the provide the following Information:
	1- Name
	2- VPC
	need to all rules by clicking on the Route
		the local trafic is there add another,
	destination = 0.0.0.0/0 Target=Internet Gateway (drop down)
	Associate route table to Subnet
		Subnet Associate (Tab) to Route Table; click on Edit and select the subnet

VPC Tenancy 2 Options
	Default: this means all your resources in that vpc are sharing Hardware with other customers
	Dedicated: means dedicate Hardware, selection this option will result in all resources in VPC to be on a dedicated Hardware (Much more expesive)
		much better pefromance and possibly more secure
When VPC is created
	you can not change CIDR
	You can not change the Size (e.g. /16)
you can have max 200 subnet in a single VPC
min size of subnet is /28 and max can not be larger than VPC
AWS reserve the first 4 IP and last 1 Ip within is subnet (example 172.1.1.1-4 and 172.1.1.255)
Public IP remains with Instance lifetime (terminated state), the private IP can change at anytime
CIDR max is /28 for VPC and /16 for subnet
When Creating VPC you can enable assign public IP address (provision public IP address for each resource(EC2) in the VPC)
4 Steps to create VPC
	1- Chose IP Address
	2- Setup subnets in AZ's
		public subnet
		private subnet
	3- Create Routes, to Internet
	4- Authorize traffic to and From VPC
CIDR
	XXX.XXX.XXX.XXXX/XX (Slach indicates Number of High bits to remain constant)
	16 = 64,000 (254x254) Addresses
	Can not change VPC Address and CIDR so make sure you aviod oerlappping with your on-premises netwrok addresses
	RFC 1918 (Addressing sceam for private network)
Subnet
	lives inside a SINGLE AZ can not expand across AZ's
	subnet can have only one ACL, but many subnet can share same ACL
	Every Subnet must have one and only one Route Table
	Multiple subnet can have same route table
	to create console-->VPC-->Subnets-->Create Subnet need the followings:
		1- Name
		2- VPC
		3- AZ
		4- CIDR

	Subnets get subrange of addresses from VPC (CIDR user 24 after slash)
		251 IP addresses for sub-resources
	Subnets can  be
		Public
			Internet facing / Internet Connected
		private
			No Access to Intenet / Internal
			NAT (Network Address Translation) get access to internet to update software etc.
			NAT Gateway fully managed by AWS
			Bastian Host
			Put a NAT in a public Subnet (with Internet Gateway) route 0.0.0.0/0 to the NAT instance in the public subnet
				Search for vpc-nat for the NAT instance
NAT Gatway:
	Prefered over NAT Instance,
	NAT Gateway is fully managed
	High Availablity
	high capacity
NAT Device/Instance:
	you manage the instance
	you need to manage the availability
	capacity depends on the instance size
	you can allow an instance in private subnet to conntect to Internet, without allowing the Internet to initiate any connections (Oneway)
		Egress-only Internet Gateway
	The Nat instance will be placed in public subnet and route is create from private subnet to the NAT device
	The NAT translates the instance to NAT IP when message is going out, and It will translate the NAT IP to instance IP when it is returing.
		In the Route table in the private subnet a new rule is added 0.0.0.0/0 will point to NAT Device in the private subnet (route table)
	Two types:
		1- NAT Gatewat
			Fully managed,higher availability and higher bandwidth
			Need Elastic IP
		2- NAT Instance
			an instance that must be managed by you
	To create NAT Gateway, console-->VPC--> NAT Gateway --> Create new Nat Gateway provide the following Information:
		1- Subnet
		2- Elastic IP Address (Create Before, or create a new one)
Public IP address
	use for instances to communicate across VPC's, they are reassinged only when the instance is in Terminated state
Private IP Address
	use for instances to communicate within same VPC, they may reassinged at anytime
external Hostname
	is resolved to External IP when it is used outside the VPC, and Internal IP when it is used inside the VPC
internal Hostname
	Similar to Private IP addresses they can be resolved within the same VPC, and they only resolve to Internal IP.
Elastic IP Assress
	Static IP that is assigne to account and you can map it to resources. They outlast the life of resource. there is a charge for Elastic IP that is not
		mapped to any instance.
	to create: colsole-->VPC-->Elastic IP-->action -->Allocate new Address
Default VPC
	gets 172.31.0.0/16 CIDR
	default subnets get 172.31.0.0/20 CIDR
	do not delete default VPC, only AWS support can re-create it
Custom VPC
	allow you to customize you IP addresses
	Allows you to have more secure VPC (no Internet Gateway, etc.)
VPC allows:
	VPC subnet routing
	VPC Peering
		All VPC's must be in a same region
		It can be cross multiple AWS Accounts
		It uses private IP addresses
		must not have any Overalaping IP addresses otherwise you can not peer the VPC's
		it is Not a VPN or Gateway
		it does not create bandwidth blocking or Single Point  of failure
		There are no transitive connection/Peering (A->B B->C does not means A -> C)
		When VPC's are peered the resources can communicate via private IP's
		No transitive Connection A<-->B and A<-->C does not allow C<-->B unless they are directly paired
		Allows private connectivity (no need to go to Internet)
		IP Addresses must not overlaps, otherwise they can not be paired
		usecase: developement/production, Admin monitoring (loging, etc), Business units
		both side must agree to it
			init peering request / other must accept the request
			creat rout to the new VPC
				they must go to PCX (Peering connections) and use private IP (CIDR) addresses
			can be in one AWS account or seperate accounts
	VPC connection to on-premises
		both provide secure connection
		for high availability you can use both VPN and Direct Connect combined
		VPN
			can be established in minutes Direct Connect you need to configure devices
				VPC has lower bandwiddth than Direct Connect
			Customer Gateway (on your dataCenter) must be in appproved list
			Virtual Gateway (on AWS Side) AKA Virtual Private Gateway (VGW)
			This will give you a pair of IP-Sec tunnels (for redundancies and availabilites) over the Inernet
			need a route rule on your routing table to Virtual Gateway
		Direct Connect
			uses Enternet VLAN trunking (802.1Q)
			Dedicated lines private network connection from on-premisses to AWS It does not use Internet
				It reduce costs
				Increase reliability
				Increase the bandwith
				More secure than VPN
			Very similar to VPN but it is a dedicate line
			It comes in either connections:
				1- 10 GB / Second
				2- 1 GB / Second
				3- you can get sub 1 GB throught third parties/AWS Partners
			higher bandwidth and throughput (more data and faster)
	VPC Address Resolution
		DNS resolution : allows AWS to do the DNS at the VPC level (allows the private and public DNS name resolution)
			the private hostname is only valid inside the VPC
			the public hostname is visible from inside and outside the VPC
				it resolves to public IP when outside and Private IP when inside the VPC
		DNS hostname: when lunch instance in the VPC , AWS assign public and private hostname that the above DNS capability is performed

RouteTable
	the default allows all components in the vpc can talk to each others and package stays local
	Default Route Table
	All routeTables have rules
	each rule has destination, target(local or your Internet Gateway), status (active)
	local in route table means it stays within the subnet
	0.0.0.0/0 means everything
	On ACL you can Allow/Deny packages on Security Group you can only Allow
	All entries on ACL are stateleass and on Security Groups they are stateful
	Route # with are applied in the order they are specified
	Rules are applied from more specific to more generic
		(e.g. 0.0.0.0/0 is excuted the last)
Internaet Gateway
	it is a resource and it is attached to VPC to allow trafic outside the VPC
you can control the incomming trafics with two diff resources:
	1- ACL (NACL)
		Similar to Stateless firewall rules, the responses to a request are subject to the inbound rules.(unlike security Groups)
		Apply to Ingreass (incomming) and EGress(outgoing) traffic
		it contains Rule#, Protocols, Ports, Sources, and Allow/Deny
		excuted by the order of Rule Number
		applied to subnets
		ACL matching the rules starting with the lowest, best is to inncreament the number by factor of 50 or 100.
		if massage does not match any of the rules the * rule is executed.

	2- Security Groups
		Security Group = Virtual Firewall
		As default All inbound trafic is blocked , all inbound trafics are allowed
		you can have multiple Security Group associated with an instance
		You can explicitly only allow trafic in or out, all other trafics are implicitly denied
		Seccurity Group rules is allows permisions, means you always allow access (Never deny access)
		if(all outbound rules are deleted) a request that comes in will still get the response
		YOU CAN NOT DENY ANY Trafic, only explictly allow trafic in
		By Default all outbound trafics are allowed and no inboound trafic is allowed.
		you can reference other security groups from given security group
		Similar to Statefull Firewall Rules (if you send a request, the respnse is allowed in regardless of the rule)
		Rules are applied immediatly after modification
		Apply to Ingreass (incomming) and Egress(outgoing) traffic
		it contains Rule#, Protocols, Ports, Sources (CIDR Or other Security Groups), and Allow/Deny
		best practice use reference to other security group instead of CIDR when possible
		To create security group: console--> VPC-->Security Group-->Create Security
		Alternative way to create security group: console--> EC2 -->Security Group-->Create Security Group and provide the following Informaiton:
			1- Name: (can be same as Group name)
			2- Group Name
			3- description
			4- VPC
			Add inbound and outbound(all are allowed) rules.

Security Groups
ACL/NACL
Routing Tables
For debuging the VPC use VPC Flow Log (Similar to tcpdump) send the log to CloudWatch
New feature VPC and route to S3 now without Internet Gateway
	you can set policy at S3 to allow / disallow functionalities at VPC level

AutoScaling
Work across AZ's as evenly as possible and Subnets
Advantages:
	1- Elasticity: Match capacity and demands
	2- Availablity and reliability
		perform health checks, unhealthy instances are replaced
If Entire AZ failes the Desired # of instances are created in the other AZ
	AutoScaling will keep try lunch instances to see if AZ is backup
	As soon as AZ is back to life the # instances are balanced across AZ's
You can have autoscaling of max 1 instance across 2 AZ, this will ensure on instance in case of AZ or instance faliur
AutoScaling groups
	Group Name
	Min instances
	Max Instances
	desired # instances
1- Lunch Configurations
	The Entire process must be automated it requires the following Information:
		EC2 Instance type & Size
		AMI (Gloden Image)
		Security Groups, SSH Keys, IAM Instance Profile
		User Data (BootStrap)
		YOU DO NOT provide AZ's or Subnet information in the Lunch Configuration
2- Termination Policies:
	What instance to be terminated first: (3 Options)
		1- longest running
		2- Oldest Lucnch Configuration (if lunch Configuration has changed) To use to recycle the Lunch Policies
		3- Closest to full billing hour (optimize th costs)
		But balancing the capacitly across AZ has precedence
3- Scaling Plan:
	When to lunch more or terminate instances AKA Scale in/out
	Default Scaling Plan:
		if no scaling plan is defined.
		ensures the current capcity of health instances remains (if one is unhealthy creates a new one)
	Manual Scaling Plan:
		Use external Monitoring or Event to triger add / remove instances:
	Schedule Scaling Plan:
		use time / calandar to add / remove instances
	Dynamic Scaling Plan:
		use CloudWatch
What Goes in AMI vs. User Data
	More Static setup in AMI, dynamic setup in BootStrap
	Less timesensitve, like operation system software with Golden Image.
	Software Version use Bootstrap since it is timesensitive
	Other Options use Chef/Puppet/Ansible or AWS Code Deploy in the AMI
AutoScaling integrate with ELB
	Can work with one or multiple Load Balancers (e.g. same servers different ports for diff applications)
	automatically register and unregister instances as it slaces in or out
	use healthcheck
Health Check
	EC2 instance--> "running" or "Impared"
	ELB HealthCheck --> "OutOfService"
	Manual --> Mark instance as "Unhealthy" (use with external monitoriing)
Scaling Policies:
	when to change capacity:
		1- How many instances you want.
	Scaling Schedule :
		1- Cron like syntax
		2- Event syntax (e.g evry monday) you can schedul upto 35 days
			Available only on CLI / SDK not on Console
	Dynamic Scaling
		Triger scale in/out base on Demand
		response to change in Metrics (CloudWatch)
Step Scaling Policies Vs. Simple caling Policies
	Step Scaling Plocies provides a plociy based on the magnitude of the breach, (if CPU is %70 or if CPU is %90,etc)
	Simple Scaling trigers when no scaling is being performed (while saling in/out on additional instance is created)
	Instance lifecycle:
		1- Pending
			Pending Wait --> you can either Continue or Abandon (Terminate the instance)
		2- InService
			Terminating Wait (time for cleanup) only state is terminate
		3- Standby State
			you can go either to InService / Terminated
		4- Terminated
		you can attach hooks to these lifecycles
AutoScaling Service
it has 3 compoenents:
	1- Lunch Configuration (what to lunch)
	2- AutoScaling Group (where to lunch)
	3- Scaling Policy (when to lunch)
		Scale out
		Scale in

Security Group
Gateway
NAT Server
Elastic IP
Eastic Load Balancing
Internal VS. External Load Balancer (it is Internet facing)
	so you will be using Internal IP(of the EC2's) for Internal Loadbalancer / External IP for external or Internet facing LB
to Create Load Balancer following Steps:
	1- define Load Balancer:
		Name,
		VPS
		Define the list of Protocols:
			into the loadbalancer and going to device (e.g. HTTPS-->HTTP)
	2- Configure Health Check
		a file to get
		protcol
		port
		file
		Response timeout: if no response stop the socket
		Interval: time to check
		Unhealthy Threshold : Number concecetive of failed pings before mark device as dead
		Health Threshold: Number of consective successful pings to make device Alive after it was dead
	3- Assign Security Group:
		Assing the security group for the loadbalancer
	4- Add EC2 instances
		Assign the EC2's to the load balancer
		check or uncheck cross AZ for Loadbalancer (remain in one AZ)
	5- Add tags (optional)
Security
ACL
Routers
MFA
two types:
	Virtual MFA
		install apps on your device
	Hardware MFA
		AWS provides the token generator hardware
Region
Availabiility Zone
Edge Locations
Content Delivery Network
BootStraping
CIDR
Bastian HOST

## Snowball
* A storage appliance to move large amount of data to AWS.
	* Import to S3
	* Export from S3

you can restore from Galcier to S3 and then export from S3 to Snowball appliance
replacement for Import/Export

* three types:

1- Snowball
		Only Storage no compute capability
		Peta-byte data transport secure appliance 1/5 of cost
		50TB is starting and 80 TB max-size 256-AES encrypption
		After trransfer is complete the data is deleted

2- SnowEdge
		100 TB, onboard storage and compute capability
		They can be clustered

3- Snowmobile
		Peta-byte/Exa-Byte of data capacity mobile/Truck
		Secure/fast / cost efective

## Import/Export

External Hard disk that copied the data into it and AWS coopied it to S3
this is a lagacy, Snowball is replacing this
DMS
Data Migration Services, allowing to move and switch database engine
This is a managed service
Manages the data Transformation
Parrallel Processing for faster transformation
Data Compression
Manages Changes to the database during the migration
Schema COnversion tool: converts schema for majority of the database engines
	includes: views, stored procedure, functions
Server Migration Service (SMS)
Allows the migration of Virtual Machine to AWS.
Inspector
examines and reports any issues with the various configurations of resources that may have any security vlanaribilities.
Certification Manager
provides free certification.
Directory Service
WAF (Web Application Firewalls)
protects the application from various attack vectors.
Artifacts
Displays various certifications like ISO 9001, PCI Attestation Certification, and mny others.
Step Functions
provides a visual resource utilization when applications are performed.
API Gateway
provides access to your external(External to AWS) data.
AppStream
AppStream 2.0
Stream desktop to users
Elastic Transcoder
Elastic Search
Cloud Search
CodeCommit
GitHub for WAS,
CodeBuild
Pay by minutes,
CodeDeploy
Deploy Code to EC2's
CodePipleline
traks various versions in various environements.
AI
Artificial Intelligence
Alexa
	AWS Voice Services (Lambda). Lex is the program
Polly
	Most advances Text to Speech
Machine Learning
Rekognition
	similar to openCV, facial recognition, Object recognition

Placement Groups
anables the EC2's to participate in low-latency/High Throughput 10 GBps networks.
Placement groups only deals with EC2's
no charge for Placenment Groups
Name must be unique with your account
Certain types of instances can be in Placement Groups
Single AZ, it CAN NOT span over AZ's
It can span peered VPC's
Not all instances can be lunched into Placement Groups
As best practice use same instance type to put in a Placement Group
you can not marge placement groups
you can not move existing instances into a placement groups, Create a new ones
to Create Placement Groups:
	first create placmenet group, then add EC2's to it
	best practice lunch the EC2's in a single request, use same instance type.
	if you add diff instance or add EC2's later you may get innsufficient capacity error.
	if you stop and start and instance in a placement group, it will remain in there

Billing Alarms
Set alarm to notify the user when the bill goes over certain amount (Send email)
Console--> my billing dashboard	--> enable billing --> reccieve billing Alert (once enabled it will nt be disabled)-->Cloudwatch --> billing --> exceeds amount --> email address --> enable alarm

### AWS Storage: ###
Amazon EFS (File)
	Share across multile instance
Amazon EBS (Block)
	EBS
		Mount on a single Instance
	EC2 Instance Store
		Phemeral/Instance Store (Used for root file system, it is temporart you loose data on Stop/Terminate but not reboot)
		EBS Elastic Block Store (mount to only one instance)
		EFS Elastic File System (multipe instance mount AKA NFS)
		S3
Amazon S3 (Object)
	S3 andd Glacier
Security
Shared Responsibility Model
Roles are global, when you create a role it can be used across all regions
Access Credentials
	Access Key and Secrete key use to access AWS reources using API
KeyPairs
	public and private keys to access EC2's
Login and Password
	use to access console

### Best practice use roles instead of passing Access Credentials for an instance

- when usng the AWS CLI from an EC2 you can use either Access Credential or Create a Role for that EC2
- if you use the Access Credential, it is saved in ~/.aws/credentials file, if anyone acess such information they can
- control your entire network.
- if is best to assign a role to the EC2
- this can be done by assigiing the role at the creation of instance, that allows the access to other components.
- Roles can not be assigned to an instance after it is created
- You can not change the roles after it is assigned
- You can change the permissions on the role

### General Best practices: ###

* Always user DNS Names instead of IP, this can be intetnal or External IP or DNS Names.
* this is applicable to EC2's, Loadbalancers

### Transfer Acceleration: ###

* Using the Cloudfront edge locations to upload the file and then to the S3 Buckets
* to accelerate the upload process
* you will get a distinct URL:
	* bucketName.s3-accelerate.amazonaws.com
* it cost more than the S3 upload by in some cases it is faster (not all cases)

## Port Scanning:

- you must apply in advance and get permissions to scan ports, otherwise you are in violation of Acceptable Use Policy.
- Corporate Network is totally segregated from the AWS reources
- AWS physically destroy the disks at the end of their life to ensure security of data,

## Health Check:

* Supported protocols are (default is HTTP)
	* TCP/SSL
	* HTTP/HTTPS

## CIDR Notation:

* Indicates the High Bytes to remain unchange on IP address assignment

## SQS:

- Pull system,
- Distributed, with high availability
- Decouple the systems
- Throtle the systems, or buffer across system's components
- Messages can be upto 256 chunks KB  1 to 10
- SQS garantees deliver of each message at least once
- SQS supports multiple reader and writer at once
- SQS does not garantee first-in first-out, the message ordering ccan be done manually by adding sequence number
- Pricing:
	* First 1 Million free / month
	* $0.50 for each additional Million queue / month
	* Message size is 64Kb

## Terms:

- PIOPS is same as IOPS
- PIOPS = provisioned IO Per Seconds
- IOPS= IO per Seconds

## Consolidated Billing Account:
- An account that has no authoricty over the other AWS account by it is provide a means to pay mulitple accounts to
- 	get a single bill and trackall charges in a single bill
- you can link upto 20 AWS accounts to a Single Consilidated Billing Account
- provide a volume discount accross all account
- Billing Alert:
- Alerts that are activated when the bill exceeds certain amount
- TAGS:
- Key Value Pair
- Meta Data
- Can be Inherited
- 	Autoscaling, cloudformation Elastic BeanStolk

## Resource Groups:

- Grouping of resources using/share tags
- Active Directory:
- Federated Identity
- SSO using ADFS and SAML
- you login into AD and authenticated at AD and then get SAML

## Support

* AWS offers Enterprise, Business and Developers support

## Elastic Loadbalancer

* [Reinvent](https://www.youtube.com/watch?v=9TwkMMogojY)

### Well Architecture Framework

there are 4 pillars:
1- Security
2- Reliability (See Service Limits)
3- Performance Efficiency
4- Cost Optimization
5- Optimizing Over Time

### Termination Policy

Is a configuration of AutoScaling which instance to be removed first

### Elastic Load Balancer (ELB)

they do not have public Ip address only DNS Name

## Question

1- Eastic Beanstalk vs. CloudFormation

2- Difference between NAT Instance and Bastian Server

3- Main diffrence of EBS and S3

4- S3 is Object Based EBS is bock based

5- S3 is an Web Based Object Store

6- What is ENI, Elastic Network Interface

* [More details](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)
