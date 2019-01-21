# Elastic Compute Cloud (EC2)

* Virtual Machine in Cloud
* Scale capacity up and down
* Pay for what you use as you use it

# Pricing Options

* **on Demand** by hour / or by seconds no commitments
* **Reserved** 1-3 years length significant discount, some money upfront, good for apps with predictable usage
	* **Standard**
	* **Convertiable**
	* **Scheduled RI** 
* **Spot** instances bid on capacity
	* if AWS terminate you are not charged for partial Hr, if you terminate you are charged
* **Dedicated Hosts** dedicated hosts when you have licenses software,regulatory hosts. 

# EC2 Types

Letters are important numbers are just versions

* F1
* I3 Storage intensive
* G3 Graphic 
* H1
* T2 Genral porpuse
* D2 dense storage
* R4 Memory intensive (RAM)
* P3 Graphic intesive
* X1 Huge memory intensive 

# Elastric Block Storage

Virtual Disks, it is a block device. It is spread across availability zones. 

each EC2 can have a
 
* root device volume 
* other volumes

# EC2 Windows Password

* there is a process to get Admin password, 

# EBS Types 

* SSD type
	* General Purpose SSD (GP2) **boot volume**
		* good price for performance
		* 3 IOPS per gigs with upto 10,000 IOPS
		* Burst 3000 IOPS for extended time for volumesn at 3334 GB and above
	* Provisioned IOPS SSD (IO1) **boot volume**
		* IO intensive apps or RDBMS or NOSQL DB
		* good for apps with 10,000 IOPS
		* Can be provisioned upto 20,000 IOPS per volume
* HDD (Magnetic Storage)
	* Throughput Optimized HDD (ST1) **Can not be a boot volume**
		* Bigdata, Data warehours, log processing
	* Colud HDD (SC1) Cheapest **Can not be a boot volume**
		* Infrequent Access workloads
		* Files Server
	* Magnetic (Standard) **boot volume**
		* Cheapest per per GB which is bootable
		* Slowest 

# Create an Instance

* Make sure you chose your region
* T2 is the cheapest instance
* To lunch and instance
	* Select the Amazon Machine Images (AMI)
	* HVM / Para-Virtual (PV)
	* Use Amazon Linux AMI (Has more tools)
	* Select the type T2 Micro
	* Pricing 
		* Spot 
		* Tanenecy (Shared)
	* Select Virtual Private Cloud (VPC) or create one Default VPC is create for each region is created
	* A Subnet define for each AZ. Subnets can not go across AZ's 
	* Public IP Address
	* Role
	* Shutdown Behavior (stopped or Terminated)
	* Termination Protection (Can not delete instance) it is off by default at creation
	* Monitoring every 5 minutes (CPU, Disk IO, Network) free every 1 minute = detailed monitoring (extra charge)
		* Default Metircs
	* Bootstrap (Shell script to run at the creation time)
	* Add Volume Type (Root and others) (delete on Termination is checked, means when instance is terminated the volume is deleted)
	* Tags = Administrator description/ categorization it help to control costs. 
	* Security Group (Virtual Firewall) assign name, 
		* SSH 0.0.0.0 CID=0 means from anywhere you can select specific IP set CID = 32
		* HTTP and HTTP 
	* Create or Add a Key pair for connection when created you download the Key
	* Find the public IP address so can SSH to EC2
	* run `chmod 400 keypair` and run `SSH user@ip -i Keypair.pem`
	* run `yum update` run `yum install -y apache` run `service start httpd` and `chkconfig  
	* you have private DNS Name Private IP address to connect internally
	* you have public DNS Name Private IP address to connect externally
	* No Elastic IP address is assigned
	* you can stop, reboot, and terminate (delete the instance)
	* Types of Status Check
		* System Status (reachable, network packet can be sent) this is for infrustructure
		* Instance Status (the operating system check)
	* You can have encrypted Volumes, 
		* for Boot Volume there are more steps involved
	* Make sure when creating EBS it is not delete-able at termination, this is not same as EC2 flag  

# Terminate the instance

Just terminate

# Reserved Instance

from dashboard -> menu -> purchase

# Putty
 
* need keygen to convert pem file to ppk file
* Download putty and puttygen from the site 
	* convert the key to ppk
	* Upload the key into putty

# Security Groups

* It is a virtual security group
* It has inbound and outbound section
	* they are stateful, if you have inbound it will automatically outbound as well
	* You can set all out bound allowed
	* For inbound all port as denied you define what is allowed
	* For inbound the default security group allow all instance server(127.0.0.1) for all ports
* Any change to security group is in effect immediately 
* you can have multiple security group associated with any EC2

# Network Access Control List

* Security group is stateful
* ACL is stateless 

# EBS

* All EBS must be in a same AZ as EC2 instance
* you can change the EBS size at anytime except the **Standard EBS (Normal Magnetic Storage)**
* Snapshot is a diskcopy
	* Snapshots are saved on S3 
		* Snapshots are incremental (only changes are saved after the first snapshot)
		* you can create snapshot while Instance is running
		* You can change size and type of Volume while instance is running.
		* Snapshots can be encrypted
		* you can share unecrypted snapshots with other accounts
	* you can create another volume 
		* you can change AZ 
		* you can change Type
		* you can create a volume in diff region or AZ
		* you can create an encrypted volume
		* you can create AMI snapshot if its the boot disk or you can create AMI directly from EC2 instance
* If you terminate the instance only Boot volume is deleted if flagged so.     
* To move a volume to a new AZ or region you need to create snapshot 

# Redundant Array of independent Disks (RAID)
* String is a technicque like Hadoop, 
	* break file into blocks
* Parity is the information to restore data 
* Bunch of disk act as one Disk array
	* good for redundancies 
	* good for performance
* Raid Type
	* **Raid Zero** Striped, No redundancies, Good Performance, Maximum Capacity (Among RAID)
		* Minimum of 2 disks
		* No fault tolloreance
		* Not good for High Availbility
		* Any disk failure result in total loss of data
	* **Raid One** Reduced Performance, %50 of total disks capacity (both disks must be same size)
		* Maximum of Min of 2 disks
		* data is mirrored into both disks at same time
		* Better availabilty 
		* Fault tolorent  
	* **Raid five** Striping with Parity, with Parity
		* to repair you need to add new disk
			* you can only lose only one Disk
			* No substitude for backup
		* Capacilty is less 
	* **Raid 10** Combination of RAID-1 RAID-0 good performance, Striped & Mirrored.
		* This is can be used to improve the IOPS for databases, with redundancies.  

RAID is used when you need Maximum IOPS, use RAID-0 or RAID-10
RAID 5 is not a good technology.

# Taking Snapshot of RAID array;

1. stop application and flush the cache (Shutdown EC2 instance)
2. Take snapshot 
2. restart the EC2

# Encrypt the Root Volume

1. stop the instance
2. take snapshot
3. Copy a snapshot into an encrypted snapshot
4. Create AMI from the encrypted AMI

# AMI 

* AMI's are not encrypted at rest. 

## EBS vs. Instance Store

* AMI can be instance Store (ephemeral Storage) just as root device, 
	* you can not stop this instance, 
	* you can only terminate or reboot only.
	* by default you lose the Instance Store at termination 
* AMI can be EBS backed, 
	* By default you will lose the EBS at termination if the flag is on, you can unset the flag




