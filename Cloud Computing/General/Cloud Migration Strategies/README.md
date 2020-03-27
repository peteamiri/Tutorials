# Cloud Migration Strategies

#### Additional Information See:

* [AWS Blog](https://cloud.netapp.com/blog/aws-migration-strategy-the-6-rs-in-depth)
* [AWS Migration Challenges](https://cloud.netapp.com/blog/aws-migration-5-key-challenges-and-solutions)
* [Migration Checklist](https://cloud.netapp.com/blog/aws-migration-checklist)
* [Migration Guide](https://theappsolutions.com/blog/development/effective-cloud-migration-strategy-in-six-simple-steps/)

## Cloud Migration

Cloud migration is the process of moving digital business operations into the cloud. Cloud migration is sort of like a physical move, except it involves moving data, applications, and IT processes from some data centers to other data centers, instead of packing up and moving physical goods. Much like a move from a smaller office to a larger one, cloud migration requires quite a lot of preparation and advance work, but usually it ends up being worth the effort, resulting in cost savings and greater flexibility.

Most often, "cloud migration" describes the move from on-premises or legacy infrastructure to the cloud. However, the term can also apply to a migration from one cloud to another cloud.

## What is legacy infrastructure?
In computing, hardware or software is considered "legacy" if it is outdated but still in use. Legacy products and processes are usually not as efficient or secure as more up-to-date solutions. Businesses stuck running legacy systems are in danger of falling behind their competitors; they also face an increased risk of data breaches.

Legacy software or hardware may become unreliable, may run slowly, or may no longer be supported by the original vendor. Windows XP, for instance, is a legacy operating system: released in 2001, its capabilities have been exceeded by later releases of Windows, and Microsoft no longer supports the operating system by releasing patches or updates for it.

Infrastructure includes servers, networking equipment, applications, databases, and any other business-critical software or hardware. Legacy infrastructure, such as aging servers or physical firewall appliances, may slow down a company's business processes. It may also add more security risks as original vendors drop support for their products and stop releasing security patches.

Legacy infrastructure is typically hosted on-premises, meaning it is physically located in buildings or on property where the organization operates. For instance, many businesses host an on-premises data center in the same building where their employees work.

Companies that rely on on-premises legacy infrastructure are unable to experience the benefits of cloud computing. Because of this, most enterprises today have made at least a partial migration to the cloud.

## What are the main benefits of migrating to the cloud?
Scalability: Cloud computing can scale up to support larger workloads and greater numbers of users far more easily than on-premises infrastructure, which requires companies to purchase and set up additional physical servers, networking equipment, or software licenses.
* Cost: Companies that move to the cloud often vastly reduce the amount they spend on IT operations, since the cloud providers handle maintenance and upgrades. Instead of keeping things up and running, companies can focus more resources on their biggest business needs – developing new products or improving existing ones.
* Performance: For some businesses, moving to the cloud can enable them to improve performance and the overall user experience for their customers. If their application or website is hosted in cloud data centers instead of in various on-premises servers, then data will not have to travel as far to reach the users, reducing latency.
* Flexibility: Users, whether they're employees or customers, can access the cloud services and data they need from anywhere. This makes it easier for a business to expand into new territories, offer their services to international audiences, and let their employees work flexibly.

## What are the main challenges of migrating to the cloud?
Physical Cloud Migration
Migrating large databases: Often, databases will need to move to a different platform altogether in order to function in the cloud. Moving a database is difficult, especially if there are large amounts of data involved. Some cloud providers actually offer physical data transfer methods, such as loading data onto a hardware appliance and then shipping the appliance to the cloud provider, for massive databases that would take too long to transfer via the Internet. Data can also be transferred over the Internet. Regardless of the method, data migration often takes significant time.
Data integrity: After data is transferred, the next step is making sure data is intact and secure, and is not leaked during the process.

* Continued operation: A business needs to ensure that its current systems remain operational and available throughout the migration. They will need to have some overlap between on-premises and cloud to ensure continuous service; for instance, it's necessary to make a copy of all data in the cloud before shutting down an existing database. Businesses typically need to move a little bit at a time instead of all at once.

## How does an on-premises-to-cloud migration work?
Every business has different needs and will therefore follow a slightly different process for cloud migrations. Cloud providers can help businesses set up their migration process. Most cloud migrations will include these basic steps:

* Establish goals: What performance gains does a business hope to see? On what date will legacy infrastructure be deprecated? Establishing goals to measure against helps a business determine if the migration was successful or not.
Create a security strategy: Cloud cybersecurity requires a different approach compared to on-premises security. In the cloud, corporate assets are no longer behind a firewall, and the network perimeter essentially does not exist. Deploying a cloud firewall or a web application firewall may be necessary.
* Copy over data: Select a cloud provider, and replicate existing databases. This should be done continually throughout the migration process so that the cloud database remains up-to-date.
Move business intelligence: This could involve refactoring or rewriting code (see below). It can be done piecemeal or all at once.
* Switch production from on-premises to cloud: The cloud goes live. The migration is complete.
Some businesses turn off their on-premises infrastructure at the end of these steps, while others may keep legacy systems in place as backup or as part of a hybrid cloud deployment.


## 6 Application Migration Strategies: “The 6 R’s”
Gartner, a highly influential information technology research company, describes 5 options for organizations migrating to the cloud. These cloud migration strategies are commonly known as the "5 R's":

* Rehost - Rehosting can be thought of as "the same thing, but on cloud servers". Companies that choose this strategy will select an IaaS (Infrastructure-as-a-Service) provider and recreate their application architecture on that infrastructure.

* Refactor - Companies that choose to refactor will reuse already existing code and frameworks, but run their applications on a PaaS (Platform-as-a-Service) provider's platform – instead of on IaaS, as in rehosting.

* Revise - This strategy involves partially rewriting or expanding the code base, then deploying it by either rehosting or refactoring (see above).

* Rebuild - To "rebuild" means rewriting and re-architecting the application from the ground up on a PaaS provider's platform. This can be a labor intensive process, but it also enables developers to take advantage of modern features from PaaS vendors.

* Replace - Businesses can also opt to discard their old applications altogether and switch to already-built SaaS (Software-as-a-Service) applications from third-party vendors.

The last option is to retire that is not consider a pattern.

The 6 most common application migration strategies we see are:

### 1. Rehosting — Otherwise known as “lift-and-shift.”

We find that many early cloud projects gravitate toward net new development using cloud-native capabilities, but in a large legacy migration scenario where the organization is looking to scale its migration quickly to meet a business case, we find that the majority of applications are rehosted. GE Oil & Gas, for instance, found that, even without implementing any cloud optimizations, it could save roughly 30 percent of its costs by rehosting.
Most rehosting can be automated with tools (e.g. AWS VM Import/Export, Racemi), although some customers prefer to do this manually as they learn how to apply their legacy systems to the new cloud platform.
We’ve also found that applications are easier to optimize/re-architect once they’re already running in the cloud. Partly because your organization will have developed better skills to do so, and partly because the hard part — migrating the application, data, and traffic — has already been done.

Sometimes referred to as “lift and shift,” re-hosting simply entails redeploying applications to a cloud-based hardware environment and making the appropriate changes to the application’s host configuration. This type of migration can provide a quick and easy cloud migration solution. There are trade-offs to this strategy, as the IaaS-based benefits of elasticity and scalability are not available with a re-hosting deployment.

However, the solution is made even more appealing by the availability of automated tools such as Amazon Web Services VM Import/Export. Still, some customers prefer to “learn by doing,” and opt to deploy the re-hosting process manually. In either case, once you have applications actually running in the cloud they tend to be easier to optimize and re-architect.
Re-hosting is particularly effective in a large-scale enterprise migration. Some organizations have realized a cost savings of as much as 30 percent, without having to implement any cloud-specific optimizations.


### 2. Replatforming — I sometimes call this “lift-tinker-and-shift.”

Here you might make a few cloud (or other) optimizations in order to achieve some tangible benefit, but you aren’t otherwise changing the core architecture of the application. You may be looking to reduce the amount of time you spend managing database instances by migrating to a database-as-a-service platform like Amazon Relational Database Service (Amazon RDS), or migrating your application to a fully managed platform like Amazon Elastic Beanstalk.
A large media company we work with migrated hundreds of web servers it ran on-premises to AWS, and, in the process, it moved from WebLogic (a Java application container that requires an expensive license) to Apache Tomcat, an open-source equivalent. This media company saved millions in licensing costs on top of the savings and agility it gained by migrating to AWS.

This strategy entails running applications on the cloud provider’s infrastructure. You might make a few cloud-related optimizations to achieve some tangible benefit with relative ease, but you aren’t spending developer cycles to change an application’s core architecture.
Advantages of re-platforming include its “backward compatibility” that allows developers to reuse familiar resources, including legacy programming languages, development frameworks, and existing caches of an organization’s vital code.
An unfortunate downside to this strategy is the nascent state of the PaaS market, which doesn’t always provide some of the familiar capabilities offered to developers by existing platforms.


### 3. Repurchasing — Moving to a different product.
This solution most often means discarding a legacy application or application platform, and deploying commercially available software delivered as a service. The solution reduces the need for a development team when requirements for a business function change quickly. The repurchasing option often manifests as a move to an SaaS platform such as Salesforce.com or Drupal. Disadvantages can include inconsistent naming conventions, interoperability issues, and vendor lock-in.

Most commonly see repurchasing as a move to a SaaS platform.
* Moving a CRM to Salesforce.com,
* HR system to Workday,
* CMS to Drupal, and so on.

### 4. Refactoring / Re-architecting — Re-imagining how the application is architected and developed, typically using cloud-native features.

This is typically driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.
Are you looking to migrate from a monolithic architecture to a service-oriented (or server-less) architecture to boost agility or improve business continuity (I’ve heard stories of mainframe fan belts being ordered on e-bay)? This pattern tends to be the most expensive, but, if you have a good product-market fit, it can also be the most beneficial.

This solution involves re-imagining how an application is architected and developed, typically using the cloud-native features of PaaS. This is usually driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.
Unfortunately, this means the loss of legacy code and familiar development frameworks. On the flip side, it also means access to world-class developer’s tools available via the provider’s platform. Examples of productivity tools provided by PaaS providers include application templates and data models that can be customized, and developer communities that supply pre-built components.
The primary disadvantage to a PaaS arrangement is that the customer becomes extremely dependent on the provider. The fallout from a disengagement with the vendor over policies or pricing can be quite disruptive. A switch in vendors can mean abandoning most if not all, of a customer’s re-architected applications.

### 5. Retire — Get rid of.

Once you’ve discovered everything in your environment, you might ask each functional area who owns each application. We’ve found
that as much as 10% (I’ve seen 20%) of an enterprise IT portfolio is no longer useful, and can simply be turned off. These savings can boost the business case, direct your team’s scarce attention to the things that people use, and lessen the surface area you have to secure.

Typically, the initial step in the cloud migration process is the discovery of your entire IT portfolio. Often, this discovery process entails application metering to determine the actual usage of deployed applications. It’s not unusual to find that anywhere between 10 to 20 percent of an enterprise IT estate is no longer being used. Retiring these unused applications can have a positive impact on the company’s bottom line; not just with the cost savings realized by no longer maintaining the applications, but by allowing IT resources to be devoted elsewhere, and by minimizing security concerns for the obsolete applications.
Download our Cloud Migration Guide to learn more about approaches and security considerations for migrating your applications and data to the cloud.

### 6. Retain — Usually this means “revisit” or do nothing (for now).

Maybe you’re still riding out some depreciation, aren’t ready to prioritize an application that was recently upgraded, or are otherwise not inclined to migrate some applications. You should only migrate what makes sense for the business; and, as the gravity of your portfolio changes from on-premises to the cloud, you’ll probably have fewer reasons to retain.

## Phases for Migration

The cloud migration process, as described by Amazon, encompasses five stages:
* Phase 1: Migration Preparation and Business Planning
* Phase 2: Discovery and Planning
* Phase 3: Designing the Migration
* Phase 4: Migrating and Validating Applications
* Phase 5: OperationsIn the second stage, organizations start to map out existing on-premise environments, understand the possibilities offered by their cloud provider, and consider what shape each application should take in the public cloud.

This is where a migration strategy comes in. Your cloud migration strategy is your vision of how to take your applications into the cloud. A successful strategy will maximize your value from cloud infrastructure while minimizing migration time, effort, cost and risk.
