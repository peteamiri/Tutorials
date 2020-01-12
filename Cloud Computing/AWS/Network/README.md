# AWS Network

* [AWS Network](https://www.youtube.com/watch?v=hiKPPy584Mg)
* [AWS VPC](https://www.youtube.com/watch?v=LX5lHYGFcnA)

# AWS Global Infrastructure
AWS operates a global infrastructure. This network is operated by one company, Amazon, and it spans the continents where AWS has a presence. This infrastructure enables traffic to flow between AWS Regions, Availability Zones, edge locations, and customer cross-connect facilities. Traffic between nodes on this network uses the AWS global infrastructure, with the exception of AWS GovCloud (US) and China. A representation of the global infrastructure

# Regions
A region is a geographic area in the world where AWS operates cloud services (for example,Amazon Elastic Compute Cloud, also known as Amazon EC2). AWS Regions are designed to be completely independent from other regions. This approach provides fault isolation, fault tolerance, and stability.

Most AWS Cloud services operate within a region. Since these regions are separated, you only see the resources tied to the region that you have specified. This design also means that customer content that you put into a region stays in that region unless you take an explicit action to move it.

# Availability Zones
Each region is composed of two or more Availability Zones. Each Availability Zone contains one or more data centers. The zones are engineered such that they have different risk profiles. That is, AWS considers factors like power distribution, floodplains, and tectonics when placing Availability Zones within a region. The zones are connected to one another by low-latency, high-bandwidth fiber optics. Availability Zones are typically less than 2 milliseconds apart.

Amazon operates state-of-the-art, highly-available data centers. Although rare, failures can occur that affect the availability of resources that are in the same location. If you host all of your Amazon EC2 instances in a single location that is affected by such a failure, for example, none of your instances would be available. When you launch an Amazon EC2 instance, you can select an Availability Zone or let AWS choose one for you. If you distribute your instances across multiple Availability Zones and then one instance fails, you can design your application so that an instance in another zone can handle requests.

# Edge Locations
To deliver content to end users with low latency, AWS provides a global network of edge locations. This content distribution network is called Amazon CloudFront. As end users make requests, the AWS Domain Name System (DNS), Amazon Route 53, routes requests to the Amazon CloudFront edge location that can best serve the user’s request, typically the nearest edge location in terms of latency.

In the edge location, Amazon CloudFront checks its cache for the requested content. If the data is locally cached, Amazon CloudFront returns the content to the user. If the data is not in the cache, Amazon CloudFront forwards the request for the files to the applicable gorigin server for the corresponding file type. The origin servers then send the files back to
the Amazon CloudFront edge location.

-------------------------------------------------------------------------------
# Exam Objectives

The AWS Certifi ed Advanced Networking – Specialty Exam is intended for people who have experience designing and implementing scalable network infrastructures. Exam concepts that you should understand for this exam include the following:

* Designing, developing, and deploying cloud-based solutions using AWS
* Implementing core AWS services according to basic architectural best practices
* Designing and maintaining network architecture for all AWS services
* Leveraging tools to automate AWS networking tasks

## In general, certification candidates should understand the following:
* AWS networking nuances and how they relate to the integration of AWS services
* Advanced networking architectures and interconnectivity options (for example, IP VPN, and MPLS/VPLS)
* Networking technologies within the OSI model and how they affect implementation decisions
* Development of automation scripts and tools
* Design, implementation, and optimization of the following:
  - Routing architectures
  - Multi-region solutions for a global enterprise
  - Highly-available connectivity solutions
* CIDR and subnetting (IPv4 and IPv6)
* IPv6 transition challenges
* Generic solutions for network security features, including WAF, IDS, IPS, DDoS protection, and Economic Denial of Service/Sustainability (EDoS)
* Professional experience using AWS technology
* Experience implementing AWS security best practices
* Knowledge of AWS storage options and their underlying consistency models

The exam covers six different domains, with each domain broken down into objectives
and subobjectives.
