# Simple Storage Service (S3)

## Encryption
* in transit
	* SSL / TLS (HTTPS)
* At rest there are 4 types of encryption;
	* **Service Side encryption**
		* **S3 Managed Keys - SSE-S3** each object has its own key and key is encrypted with Master Keys, ASE-256 and Master key is rotated often
		* **AWS Key Managment Service, Managed Keys - SSE-KMS** (Additional Charge) used envlop-key, provides audit trails (who and when)
		* **Customer provided Keys SSE-C** customer manages the keys
	* **Client Side encryption** you manage everything, file is encrypted by client and keys are managed by the clients.

# S3 transfer Acceleration

You can use CloudFront Edge Network to accelerate Uploads to S3. URL looks like

	<bucketName>.s3-accelerate.amazonaws.com

# Use of S3 for static website

## Resources

* [Static Website with S3](https://www.youtube.com/watch?v=g9NbuTcos18&list=PLzvRQMJ9HDiSaiCYWnEMdQvldmXrdUOmv)
