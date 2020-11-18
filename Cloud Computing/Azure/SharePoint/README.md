# Security and Complinace in SharePoint

Microsoft has adopted the Zero Trust Security Model as a holistic approach for the basis of its security and compliance infrastructure and its security posture and policies. The Microsoft 365 Compliance Center can centrally define, manage, deploy, and monitor security policies for services like SharePoint, OneDrive, Teams, Outlook, and Office 365 applications.

#### For more information See

* [Security and compliance in SharePoint and OneDrive](https://www.youtube.com/watch?v=uCDOtPgP7Gs)
* [Security and Compliance controls in SharePoint, OneDrive, and Teams](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/security-and-compliance-controls-in-sharepoint-onedrive-and/ba-p/1698280)

## Zero Trust Security Model

The basis of the Zero Trust security Model is: "never trust, always verify". Zero Trust is a security model centered around the principle that the organizations should not automatically trust anything inside or outside its security perimeters and instead must verify anything and everything trying to connect to its systems before granting access. This security model manages and grants access based on the continual verification of identities, devices, and services.

The followings are the basic controls for implementation of the Zero Trust Security Model;

*	Users authorization;
  *	Strong Authentication mainly Mutil-factor Authentication
  *	Internal Vs. External
  *	Sharing Policies, what asset is shared with who
*	Devices Management and validation of the devices that can access the data
  *	Device Management, including mobile devices.
  *	Fine-grained conditional Access
  *	Session Time out.
  *	Automatic expiration of external access to devices.
*	Location
  *	IP based Access control (White-listing access control)
  *	Encryption Certification, both at rest and inflight encryption
*	Asset Or Document Protection 
  *	using least-privilege user rights as part of user access and authorization. 
  *	Document Sensitivity Lable
  *	Auto Classification for Sensitivity Lable
  *	Lable Analytics, various analytical information regarding label distribution and utilization
  *	Auditing.


#### For more information See

* [How Zero Trust improves security and the user experience](https://www.youtube.com/watch?v=-Why_ZjJUhg)

## How Zero Trust Security Model is implemented by MicroSoft

The security and compliance are centrally managed and monitored using the Microsoft 365 Compliance Center. The Microsoft 365 Compliance Center can centrally define and deploy security policies for services like SharePoint, OneDrive, Teams, Outlook, and Office 365 applications. 

The following highlights some of the primary functions that are offered by the Microsoft 365 Compliance Center.
*	Document Sensitivity Labeling
*	Auto Classification 
*	Lable Analytics
*	Auditing

## Document Sensitivity Labeling

documents can be labeled with the sensitivity label, these labels allow the followings; 

*	Encryption policies
*	Internal or external access
*	Device Management (External devices access, Web Access, or none)
*	Content Marking (WaterMark or Header labels)

## Auto Classification and Labeling

The Sensitivity labels can be assigned manually or by the Auto Classification feature. The Auto Classification can be configured by utilizing various rules. These rules are applied to each document, and a label is assigned to the document based on the document contents. As an example when a document contains PII or PFI, a specific label is automatically assigned to such document and consequently a specific predefined security policy is enforced. As discussed before each label can enforce, access control, encryption level, service to apply such policy to (e.g. Sharepoint OneDrive, etc.), and content marking. 
Auto Classification can be run in a simulation model to preview how various labels are assigned to individual documents and if acceptable then the classification can be published. There are more than 100 rules that can be associated with each user-defined label.

## Lable Analytics
Lable Analytics provides various analytical reporting capabilities about the types of information detected (e.g. PII, PFI, etc.) in the documents and their distribution classified by their labels. 


 
#### For more information See

* [Security and compliance in SharePoint and OneDrive](https://www.youtube.com/watch?v=uCDOtPgP7Gs)
* [Microsoft 365 Security & Compliance Center](https://www.youtube.com/watch?v=Q8uZGGqOB3g)

