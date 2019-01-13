# Enterprise Resource Planning (ERP)

Enterprise resource planning (ERP) is a method of efficiently utilizing people, hardware and software to increase productivity and profit, thus simplifying a company’s business processes. ERP may include many software applications or a single (but more complex) software package that smoothly disseminates data required by two or more unique business departments.

The need for enterprise resource planning (ERP) software grew with big business’ mandate for a centralized solution to manage all information system requirements. An ERP may consist of many different business modules, including:

- Manufacturing
- Human Resources/Payroll
- Sales
- Inventory
- Supply Chain/Partners
- Finance and Accounting
- CRM

In short, an ERP solution allows each department or business domain to be managed centrally while operating independently. Advantages include interoperability of data, increased communication and increased data reliability through the use of a single database.

ERP also enhances the quality of enterprise-wide decision making. For example, a customized order may move from the sales department to inventory control, then on to invoicing to finance and manufacturing. By using an ERP, this type of process is an efficient and continuous series of events that allows for easy individual order tracking.

# Enterprise Application Integration (EAI)

Enterprise application integration (EAI) is the use of technologies and services across an enterprise to enable the integration of software applications and hardware systems. Many proprietary and open projects provide EAI solution support.

EAI is related to middleware technologies. Other developing EAI technologies involve Web service integration, service-oriented architecture, content integration and business processes.

Intercommunication between enterprise applications (EA), such as customer relations management (CRM), supply chain management (SCM) and business intelligence is not automated. Thus, EAs do not share common data or business rules. EAI links EA applications to simplify and automate business processes without applying excessive application or data structure changes.

However, EAI is challenged by different operating systems, database architectures and/or computer languages, as well as other situations where legacy systems are no longer supported by the original manufacturers.

EAI meets these challenges by fulfilling three purposes, as follows:

- Data Integration: Ensures consistent information across different systems.
- Vendor Independence: Business policies or rules regarding specific business applications do not have to be re-implemented when replaced with different brand applications.
- Common Facade: Users are not required to learn new or different applications because a consistent software application access interface is provided.

The advantages of EAI are clear:

- Real-time information access
- Streamlining processes
- Accessing information more efficiently
- Transferring data and information across multiple platforms
- Easy development and maintenance.

## Patterns

This section describes common design patterns for implementing EAI, including integration, access and lifetime patterns. These are abstract patterns and can be implemented in many different ways. There are many other patterns commonly used in the industry, ranging from high-level abstract design patterns to highly specific implementation patterns.

### Integration patterns

There are two patterns that EAI systems implement:


- **Mediation (intra-communication)**
Here, the EAI system acts as the go-between or broker between multiple applications. Whenever an interesting event occurs in an application (for instance, new information is created or a new transaction completed) an integration module in the EAI system is notified. The module then propagates the changes to other relevant applications.


- **Federation (inter-communication)**
In this case, the EAI system acts as the overarching facade across multiple applications. All event calls from the 'outside world' to any of the applications are front-ended by the EAI system. The EAI system is configured to expose only the relevant information and interfaces of the underlying applications to the outside world, and performs all interactions with the underlying applications on behalf of the requester.

Both patterns are often used concurrently. The same EAI system could be keeping multiple applications in sync (mediation), while servicing requests from external users against these applications (federation).

### Access patterns
EAI supports both asynchronous (fire and forget) and synchronous access patterns, the former being typical in the mediation case and the latter in the federation case.[citation needed]

### Lifetime patterns
An integration operation could be short-lived (e.g. keeping data in sync across two applications could be completed within a second) or long-lived (e.g. one of the steps could involve the EAI system interacting with a human work flow application for approval of a loan that takes hours or days to complete).


# Enterprise Content Management (ECM)

Enterprise Content Management (ECM) is an organizational process methodology designed for complete content life cycle management. ECM content includes documents, graphics, email and video.

ECM is derived from electronic document management systems (EDMS) used during the late 1980s to early 1990s for smaller scale imaging and work flow. Today, ECM solutions employ a single software package that encompasses multiple enterprise divisions, including accounting, customer service and human resources (HR).

ECM encompasses multiple management types, including Web content/document/digital asset and work flow management. ECM also provides data discovery and manipulation capabilities through search, collaboration, capture and scanning. 

Originally geared toward business-to-employee (B2E) systems, ECM now provides solutions to business-to-business (B2B), business-to-government (B2G), government-to-business (G2B) and other market segments.

The Association for Information and Image Management (AIIM) defines five ECM components, as follows:
 
- Capture
- Manage
- Store
- Preserve
- Deliver

The three software application sources of ECM are as follows:
 
- Locally installed software available through a local area network (LAN)
- Software as a Service (SaaS)
- Hybrid of locally installed SaaS and other software solutions

Key ECM benefits include:

- More efficient and cost-effective document management and control to drive enterprise adoption
- Ensured integrated compliance with government and industry regulations
- Security functions that filter sensitive data masked with redaction features, facilitating document sharing without compromising individual identities or other sensitive data
- Reduced costs through decreased storage space, supply resources and postal requirements
- Reduced IT resources via SaaS solutions	

# Business-to-Business (B2B)

Business-to-business (B2B) is an Internet business model that involves businesses that perform services or provide products for other businesses. Business information may also be shared. B2B is a form of e-commerce and it can involve businesses that manufacture a product, service or merchandise component that that is sold to another business, which then advertises or markets the product on its website for sale to consumers.

B2B is sometimes referred to as business or industrial marketing.

B2B may include outsourcing, which occurs when a business hires a contractor with knowledge and experience in that business's industry. The term B2B, however, is better known within the commercial trading realm, where wholesalers sell products to retailers, or a commercial original equipment manufacturer sells its products to wholesalers. Contained within a common supply chain execution are various business transactions. For instance, a home manufacturer will make purchases from lumber yards, window manufacturers, concrete businesses, etc. Each one of these transactions is considered to be a form of B2B.

# Business-to-Business Gateway

A Business-to-Business (B2B) Gateway is a part of a business IT architecture that connects internal resources to external ones. In general, a B2B Gateway links up in-house software processes to e-commerce platforms, or platforms featuring collaboration with partners or vendors.

In many cases, a B2B Gateway is deployed at that point where company data enters the cloud. For example, it can connect an intranet managed in-house to various software as a service (SaaS) platforms delivered by vendors. B2B Gateways may utilize standard languages such as extensible markup language (XML), or "commerce XML" to integrate them into a greater service-oriented architecture, which helps to deal with inventory, business partnerships, supply chains and more.

# Identity and Access Management (IAM)

Identity and access management (IAM) is the process used in businesses and organizations to grant or deny employees and others authorization to secure systems. IAM is an integration of work flow systems that involves organizational think tanks who analyze and make security systems work effectively. Policies, procedures, protocols and processes are all linked to IAM. Identity and security applications are also important considerations.

IAM verifies user access requests and either grants or denies permission to protected company materials. It also deals with various administrative functions including password problems, and helps oversees employee identity management. Standards and applications of IAM include the maintenance of user life cycles, various application accesses and singular logons.

There are several advantages of IAM including business value and security enhancements, increased work productivity and a reduction in the IT staff's workload. Businesses use IAM in order to comply with best practice standards, whether in healthcare, finance or other sectors. Best practice standards throughout several organizational arenas require record protection, which becomes increasingly important as more organizations adopt interoperability in confidential records systems.	