# Simple Storage Service (S3) #

* Object Based (Files only) v.s. Block based (file system).
* S3 is a global Service and it is managed globally not on region level 
* Any amount of Data from anywhere on the web
* Safe place place to store files
* Unlimited Storage but you pay by Gigs.
* Files can be 0 bytes to 5 TB 
* Files are stored in Buckets (folder)
* Bucket names must be universal unique name. They can be access by URL, hence the name has to be unique.
* URL looks like https://s3-eu-west-1.amazonaws.com/<bucketname> or https://S3<region>.amazonaws.com/bucketname>
* you always receive 200 when upload is successful.
* Buckets can be tagged and Files withing each bucket can have their own tags.
* Buckets can be configures to make User's pay for access
* Access to bucket can be managed by both ACL and plicies.
* ARN is Amazon Resource Name
* All files and Buckets by default are private, permissions must be granted.
* You can add multifactor option to delete a file on S3 or following operations;
	* Changing a Version 
	* Permanatly Deleteing
* Cross Region Replication
	* This is done on Bucket level only
	* you need versioning on both side
	* you need to add rules 
		* Entire bucket
		* Specific File
	* Only New objects are replicated
	* You can use Amazon CLI to copy the existing files to the replicated sit
	* When replicated the files permissions are replicated
	* Delete Markers are replicated but When file deleted the delete marker remains even if the original is changed. Similarly for individual versions.  

## Availability Model 

* 99.99% (four 9) availability for platform
* 99.9% (three 9) availability for Amazon
* Eleven-9 durability for the S3 File.
 
## S3 Tiered Storage

* **S3** Storage Store redundantly across multiple facilities and it can withstand lose of 2 facilities concurrently. 
* **S3-IA** : Infrequently Access Charge for each access Cheaper than S3, it used multiple AZs.
* **S3 One Zone IA** : Lower Cost, Infrequently Accessed, stored in a single AZ.  
* **Glacier** Data Archiving, Government records, stored in more than 3 zones, retrival fees  
	* Expedited few minutes retrieval, higher fees.
	* Standard retrieval takes 3-5 hours
	* Bulk retrieval takes 5-12 hours

## Charges

* Storage
* request
* Storage Management 
* Data Transfer across Zones
* Transfer Accelerations
	* Uses CloudFront and Edge-Locations

## Access Log

## Lifecycle Rules

* you can move file from S3 to other cheaper storage or completely delete the object
* Glacier is not available for all regions
* Use the Management tab to create lifecycle
* you can move objects to any lower level 
	* the latest version or all version
* you can use lifecycle to delete the file permanetly
* 
 


 
## Versioning

* Once you enable versioning you can only suspend it. 
* you will still pay for each version, as each is considered as a single file. 
* Great tool for backup

## Encryption

Server side encryption

* None
* AES-256 (SSE-S3)
* AWS-KMS (SSE-KMS)
* SSE-C (Customer provided Key encryption)

Files also can be encrypted on client side before upload. 

## Bucket Policies
you can access public access

## Access Control List   


## Data Consistancy

* Read After Write for PUTS of a new Object; first time upload the read can be done imminently. 
* Eventual Consistency for Overwrite PUTS and Deletes (Delay to propagate); eventually file will be updated when file is changed, otherwise the old file is read. Eventually the file is consistent. 

S3 us based on the Key value

1. Object Name
1. Value is the content
1. Version ID
2. Metadata
3. Subreource 
	1. Access Control List
	2. Torrent (Peer-to-peer access)  