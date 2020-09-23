# AWS IAM Componenets

* `Users:` A user can be created in IAM and given the necessary permissions to access AWS resources.
* `Groups:` Users can be added to groups. Permissions can now be given to groups instead of individual users. 
This is a recommended best practice.
* `Policies:` Policies are JSON documents that define the permissions for users or groups.
* `Roles:` Roles are generally used for giving users temporary permissions to access an AWS service. For example, we can attach a role with S3 permissions to an EC2 service.


# Basic Concetps
* `Authentication` is the process of verifying a user's identity with a username and password, or credentials such as the access key and the secret access key.
There are primarily two types of access credentials in AWS for authenticating users:
	* `Access key ID and secret access key:` This is used for programmatic access, and is used with AWS APIs, CLI, SDK, and any development tools.
	* `Username and password:` For managing console access. 

* `Authorization` is the process of checking whether a user has the right permissions to perform an action and is usually defined using the permission's policies.
* `Confidentiality` is done to make sure the data that's sent from the source is not read by anyone in between. This can be made possible using cryptography. 
* `Data integrity` is done to make sure the data has come from the right person and has not been tampered in between. This is also generally made possible using cryptography. 
* `Availability` makes sure the service can be used when it is needed. 
* `Accounting` helps us identify the responsible parties in case of a security event.
* `Non-repudiation` prevents a user from denying an activity. Cryptography comes to our aid here.
* `The AWS shared responsibility model` defines the responsibilities of AWS and its customers in securing our solutions on the AWS cloud. In summary, it states that the security of the cloud, for example, securing the global infrastructure, hardware, networking, and so on is AWS's responsibility; while security in the cloud, for example, updates and security patches for the servers we provision, protecting credentials and keys, and so on is the customer's responsibility. 
* `AWS IAM supports Payment Card Industry Data Security Standard (PCI-DSS) compliance:`s This is an information security standard required for organizations that handle credit cards.


## For more information See:

* [The AWS shared responsibility model](https://aws.amazon.com/compliance/shared-responsibility-model/)
* [AWS Cloud Security](https://aws.amazon.com/security/)
* [Security, Identity, and Compliance on AWS](https://aws.amazon.com/products/security/?nc=sn&loc=2)