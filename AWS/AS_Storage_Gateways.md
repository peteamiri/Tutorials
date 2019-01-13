# AWS Storage Gateway

is a service that provides a connection of clients (on-premises) data center with the cloud based storage. 

* Security 
* cost-effective
* scalable

This is a Virtual manchine downloadable and installed on client's data center and accosiate it with your AWS account.

* VMWare ESXi
* Microsoft Hyper-V

Four differnt Types;

* File Gateway (NFS); flat files stored directly in S3, all files are directly saved on the S3. 
* Vulume Getway (iSCSI) Block based, data written asynchronously, and stored as EBS snapshots. Snapshots are incrementals (Only Changes are written) the snapshots are compressed to minimize storage fees. 
	* Stored Volumes (All Data) Complete Copy of your Disk, all data is stored on-premise storage
	* Cached Volumes (most recent data) uses S3 as primary on S3, only latest data is cached on-premises.
* Tape Gateway (VTL) (old name is gateway Virtual Tape Library), uses your existing tape backups, it supports various backup programs. You create **Virtual Tape Backup**, with are uploaded in S3/Glacier in background. 


you can use Direct connect or Internet
you can also put the Storage Gatway on EC2's and connect to data Center

 