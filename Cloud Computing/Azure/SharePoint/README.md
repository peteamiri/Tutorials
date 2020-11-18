# Security and Complinace in SharePoint

The Misrosoft has adopted the Zero Trust Security Model as a holistic approach for security and compliance for, SharePoint, OneDrive, Teams, outlook, and Office 365 applications.

#### For more information See

* [Security and compliance in SharePoint and OneDrive](https://www.youtube.com/watch?v=uCDOtPgP7Gs)
* [Security and Compliance controls in SharePoint, OneDrive, and Teams](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/security-and-compliance-controls-in-sharepoint-onedrive-and/ba-p/1698280)

## Zero Trust Security Model

The basis of the Zero Trust security Model is: "never trust, always verify". Zero Trust is a security model centered around 
the organizations should not automatically trust anything inside or outside its perimeters and instead must verify 
anything and everything trying to connect to its systems before granting access. This security model manages and grant access 
based on the continual verification of identities, devices and services.

The followings are the basic principlas of the Model 

* Strong user identity authentication. This may include Multi-factor Autnatication (MFA).
* User device management and validation.
  * Least-privilege user rights as part of user access and authorization. 
* Services and Corporate resources identification and availability. 

Controls for implementation of Zero Trust Security Model;

* Users authorization;
  * Strong Authantication mainly Mutil-factor Authantication
  * Internal Vs. External
  * Sharing Policies, what asset is shared with who
* Devices
  * Device Mamagement, includiing mobile devices. 
  * Fine grained conditional Access
  * Session Time out.
  * Automatic expiration of the external access.  
* Location
 * IP based Access control (White List access control)
 * Encryption Certification, both at rest and inflight encryption
* Asset Protection
 * Document Sessitivity Lable
 * Auto Calssification
 * Lable Analytics, 
  * Auditing, who viewed the document. 
  * what service contains how many item classified with each label.  
 

#### For more information See

* [How Zero Trust improves security and the user experience](https://www.youtube.com/watch?v=-Why_ZjJUhg)

## How Zero Trust Security Model is implemented by MicroSoft

This Zero Trust Model is implemented using the "Microsoft 365 Compliance Center".

### Microsoft 365 compliance center

This section highlights some of the primary functionality that Microsoft 365 Compliance Center provides. 

* Document Labling
* Auto Classification
* Lable Anaytics
* Data Loss Prevention (DLP)   


documents can be  labeled with sesitivity label, these lables allows

  * Encryption plocies
  * Internal or external access
  * Device Management (External devices access, Web Access, or none)
  * Content Marking (WaterMark or Header lables) 

The Sesitivity lables and be assigned manually or by Auto Classification feature. Also, the Auto Classification can be run in a simulation mode to preview how various lables assigned to documents. 
There are more that 100 polices that can be associated with each user defined lable. 

As an example, there are policies, that if document contains Personal Ideintifiable Information (PII), a centrain lable must be applied to such documents. As discussed before each lable can control, access, encryption, application (Sharepoint OneDrive, etc.) and content marking.
When the policy run in a simulation mode, and pass the user requirments, it can be published. 
   
Lable Analytics: provides various analytical information about the types of documents and their contents using various visual reporting capability. These reports provide view of what type information is detected within the repository, this includes, PII, PFI, etc. 
 
Data Loss Prevension (DLP):
 
#### For more information See

* [Security and compliance in SharePoint and OneDrive](https://www.youtube.com/watch?v=uCDOtPgP7Gs)
* [Microsoft 365 Security & Compliance Center](https://www.youtube.com/watch?v=Q8uZGGqOB3g)

