* How do you negotiate
* How do you pesuade
  - Eliminate excuses and provide answer to all demands
* Top Technical AWS leadership
  - Customer Obesssions
  - Curious
  - Disagree andd Commit
  - Earn Trust
  - Treeat others with respect
  - Self critical


# Customer Obsession:

## Tell me about a time that you had to handle a dificualt customer

Situation 1: System performance
Database issue, I brouoght a DB expert and I optimized JVM and weblogic while she optimied the database

Sitiation 2: Major system issue
I go to the customer and I found a service on the developers machine

Situationn 3: Bad Coding practice and poor quality of the code
Instead of borrowing connections they open connections on the database level
Using expection as application control flow
Stack traced was writtien in Weblogic logs system spent resources wrting logs
Fixed as many as I could and system become ready for user acceptance testing

## Sometimes customers make unreasonable requests. Tell me about a time when you've had to push back or say no to a customer request. What did you say or do in response to that request?
Adding more servers in a environement where the vnedor garenteed a 3 nine, it was not going to improve me avaiablity.

## Tell me about a time when you pushed back against a decision that negatively impacted your team. What was the issue? How did it turn out? Would you have done anything differently?
I was in SEC and cotar wanted to deploy the code to production without testing it.
Issue as a spelling, the impact could have been downtime in production.

## How do you Wow customers

* Situation 2: I was working on ObamaCare for the State of Oregan, with very tight deadline. This was a B2B application with ESB, and database.
    - The team developed, tested the application and moved we moved it to production,
    - Eventually the team was desolved and everyone went home. I had to stay in for the waranty.
    - At this time I was informed that I need to move the entire application stack to a new set of hardware since we developed the application on a borrowed infrustructure.
    - Took lots of sleepleess night but sniff test and regression test was successful
    - My main concern was to make sure that application is fully functional and adhears to the requirments
    - what customer wants is what customer gets.


* Situation 1:
  - I responsible and the scope of my work to setup a oracle B2B portal to allow customer to recive EDI and process them with high availablity. I was the only person from Oracle.
  - I setup the portal, wrote a proof of concept to show them it works andd also to helpthem use that as part of actual application.
  - While I was there I also help them reosove some of their issue with Weblogic, that was totally outside of my SOW.

* situation 2 Was called on a customer for a performance issue on the service SLA's.
  - I was working of services and ddefining the response time on services. I found one of the utility services with a very poor response time.
  - After checking the IP on the service I foundout that the service in the production is still configured to a developers machine.

* Situation 3 : was sent to GM to identify a major performance issue.
  - HP Cloud, HP did not allow diagnotics on the system and network layer.
  - The system was over commited.
  - System performace was as expected after business hours.
  - Help the HP to alloccate more resources to improve the peorformance

## How do you develope client relationships

I generally promisse the moon and deliver the sun, I am honest, and open to share the information

* Situation 1: Customer created a cluster at the operating system level,
  - I showed them that they can have a clustering at Weblogic level, this enhanced their system avialablity.
  - 2 with min 3 node cluster with a node manager. each node shared the session infromation with its own secondary node.

* Situation 2: I was in to help customer to fix a major with system aviability and stability,
  - helped them to setup development process, that included utit testing and regrasion testing.

## How do you understand your customers needs

* Situation one: Go to customer for application server optimization and found that database needs to be optimized
- while in Oracle I used to go and talk to stakeholders and identify what they need, regardless of SOW I used to get,
- I had to deliver both SOW (Legally) and meet the customer needs
  - what are the needs, constraints, and expectations are.
  - I had a reource for Database and I did JVM and Weblogic optiomization

## Tell me about the time you could not meet your commitments

* Situation 1: I was just hired for a project in IBM
  - The customer was not happy with the response time of the system, the development wrote a stored procedure with over 3500 line of code, that was the heart of the application many issues including row-locking and many other issues. The rewrite was taking lot longer than the deadline due to the fact that code needed to be changes and all needed to be fully tested.
  - Step 1 to optimize it to be able to partially meet the customer expectation.
  - Step 2 commit to client to rewite it by next release as we did

# Ownership

## Tell me about a time beyond your responsiblity

* Situation one : Fredie Mac
  - Develp a three tiered application. Theway customer used to develop was to develop application in a jar and all the needed jar in the classpath. This is not a greates approach creates a versioning nightmare.
  - I started to create selfcontained jar files using maven that one wars or jars was self contained. and shared that with all other development teams to start as a practice

## Tell me about a time you took something significant outside my responsibility
* Situation 1: USDA employee portal

## Describe a project that was not your own but implemented becuase of my efforts
* Situation one : Farmesbill I started to adopt it as my own worked with business team,
* Situation two : Employee protal CTO needed this to be done due to the commitment she had to CEO

## Give an example when you saw a peer struggling and you steped in to help
* Situation one: NCIS
* Situation two: Configuring Server for system admin in CACI
* Situation three : Consultant had bad server configuration weblogc cluster using tar instead of implemention. This cuases the hostname to be copied and communications corssed and resulted in Production system to be down for a few hours.
* Create unix cluster vs. weblogic cluster.

# Invent and simplify
## Tell me about a time you invented something
I wrote a screen scraper reading the Maryland DMV, to get customer information and store it in database for insurance quoates.
  - removed all the scape codes
## what improvements you have made in your company
* Situation one: my last job I connected them to AWS to become a partner, also was trying to do same with salesforce, and mulesoft.
## Tell me about a time you gave a simple soltion to a complex problem
Situation 1: got audited by OMB and they realized that all the communications are done via cleared text. After a research I found a bouncycastel jar file that encryted the ftps, and other socket connections

Situation 2: Obama care in Oragan setup a site-2-site vpn and that saved the project

## Tell me about a time that I had to think outside of boxs  used it as starting point for the profiling system.
Situation 2: I was working on AIR reservation system updated the screens

# Are Right alot

## Tell me about a time you made an error in judgement or experience regrat
* I was workiing with this team, howwevere, I made assumption regarding thier capabilites. I questioned the design of the system. They toled the system was designed even before the program manager was born.

## Tell me about a time you disagreed with colegue or with your boss and explain tghe process to resolve it
* situation one: Disagreement with my boss, his view was financial and mine was technical. but always at the end we delivered.
* Situation 2 Serive Registry, one person get requirments, and another implement no overlaping period to communicate the requirments

## Tell me about a time you had to make decision in absence of data
I developed a system based on some of the system avilabilites which I eventually found out I was wrong.

## Tell me about a situation that you identifed 2 ROI and found out they are connected
* Moving systems out of NITC
* Moving applications to cloud and utilize managed services
* Save money on the NITC bills in term of less servers we had.


# Learn and be curious

## What can you teach me in 5 minutes that I dont already know
I can teach you how DNS works, Network Works, TOGAF ADM works.

## Tell me about a time you influence the situation only by only asking questions
* security team in USDA

## Tell me about a time you solve a problem by having superior knowledge or observation
* Sutiation one in the Hotel chain, solve the problem by obeservation

## Tell me about a time you hired someone smarter than myself


# Hire and develop the best
## How do you ensure you hire the best

## How do you help your employees to grow

## How do you manage your top performers differently

## Give and example when someone was permoted becuase of your coaching and not becuase they were star performer
* Sutiation one: Verisign rather inexprience new employee.
  - Pair programming, trusted her judgement
  - She was moved to full development team

## What is the composition of my team and how is my team is orgonized
* I am architect, but generally a team of engineers, project manager, testing team, deployment team, and operations team.

# Insist on the highest standard

## tell me about a time that I was unsttisfied with the status-quoe what dd you do to chenage it
* Situation 1 Fredie mac, implement CI-CD
* Situation 2 : puting jarfiles in classpath this could cause major issue

## Tell me about a situation that peole thought good enough is good and you did not sattle with it
* I was doing a Architecture Defintion Document for Fannie Mae, I did not sattle with the template, I created my own, and I wind up to be part of reviewing board.
* I was in Jacksonvill electirc company Development lifecycle
* Deployment of applications and put jarfiles in classpath

## what measures have you implemented to ensure the performance improvemenets and targets are achived

## Give me an example of a goal that you wish you have done better, what was the goal and how could you improve it
every project lookiing back I can see that could be better soltuions. In most cases those better solutions become requirments for the next release.
IBM performance improvement, move everything out of stoered procedure.

## Tell me about a time that you worked on improving a product or solution that was already good
Sutiation one: DotTV when we bought the dotTV (TLD) code was written in mysql, and perl.

# Think Big

## tell me about the time that I took a big risk and failed
I was iin AT&T and porting a database from DB2 to informix 4gl. I could not meet the deadlines due to the technology.
Installed CISAM with C and ported all the data

## Tell me about the time that I went behind the scop of a project and delivered
USDA using the cloud.

## Give me an example about a radical approach to a problem
Using an Sybase Openserver in MOMS. Military airspace reservation system

## How do you drive adoption for your vision, ideas, or approach

## How do you know your vision was adopted

## Tell me about the time you worked on a project an found an opertunity much beiger

# Bias action

## give me an example of a caltulated risk when speed was critical
USDA multifamily PDF file to be signed as a contract.

## Describe a situation when you had to make a decision on spot to make a major sale
I helped the workshop after a week being on thhe job.

## Tell me about a situation when you had to get information from someone that was unresponsive
* Situation One: System modernization in Rdian

# Frugality

## Tell me about a new way to save money
Neustar I moved the system into Java Stack instead of Oracle SOA Fussion (early realaes)

## Describe a time you had to manage budget could you get more out of less


## How do you manage a project with no money and resource


## Tell me about a time you had to work with limited time and resources
* AT&T system database migration

# Earn trust

## Describe a time you significantly improvide the moral and productivity what
Waterfall, to agile, first deployement

## Tell me about a time that someone critisied you about a work that you did
* situation 1: I was in neustar and one individual im marketing continusly critisizing my team about one of the payloads design. He was convinced that he can do it. This large payload had performaance issue.
  - what he did not know this payload had over 500 data elelemsts in it. after he saw the complexity of the work he realised that he underestimated the work.

* I was in Neustar andd marketing lady was telling me I need to define a API to an external system. when I was a consumer of the system.

## Tell me about a time you had to tell someone else about the harsh truth
* Situation one: colorado major system performance issue.
  - open jdbc connections and get a lists for drop down.
  - Used weblogic database connections
* I was in St Diego, and poor system performance.
  - The admin increased the JVM memory to improve the profrmance, but system start swaping and had a worst performance

## How do you convince someone that resisting what you are trying to do
USDA infrustructure resistence to implement DMZ

# Deep Dive

## Have you laverage data to develop strategy
* Not a strategy but fix the performance issues.

## Have you ever given insights behind data


## walk me through a larg problem in your organization that you tried to solve
Cultural issue in having vendors working together.

## Tell me about a specific metrix you used to make change in your organzation


# Have backbone and disagree and commit

## describe a situation that your other team member did not agree with your ideas
* Situation one use MuleSoft as a cloud vs. altrnative openSource implementaion
  - it is a managed service and we did not have resources to maintain the application

## Describe a situation when you had a conflict with one of team memberes
* I was in team the 2 of team members wanted  implented functionality above and behind functional requirments
  - I was developing a framework for microservice that they can easily customise for various service
    - they wanted pagination, field selection, select a subset of data... very complex URL
    - I impleented it. They realized that the framework had grown very complex and performance is degraded
    - All the API's become so complex that integration was  hard
* Installing SELinux on CACI,
  - you can harden the system after my installation
  - That made my job much much harder

## Tell me about an unpopular decision you made

* I was on a project we needed to design a very complex UI with over 2300 fields used by professional data entry people
  - The verndor designed a very fancy UI with accordians all the fancy stuff taabler phone friendly.
  - I found a data entry froms, that the customers used to file for application, I asked the team to redo the entire UI following the fileds from the forms, that was more relaied on the keyboard and less on the mouse navigation.
  - Eventually bth design was presented to the user community and mine was selected.

## Tell me about a time that you had to stand up and disagree with someones approach

* Situation One: we took over an existing contract and we neharit some of the developers
  - Using Make vs. Ant in a jave environement this is the EDGAR System for the SEC, the process took over 12 hours to build, with dependencies nightmare, and almost no agiility.
  - Tought the configuration management team ANT
  - Worked with them to modulirize the build
  - The Build was done in matter 1 hour instead of 12 hours.

# Deliver result

## Tell me about a time when you had significant, unanticipated obstacles to overcome in achieving a key goal. What was the obstacle? Were you eventually successful? Knowing what you know now, is there anything you would have done differently?

## describe a time when you faced a challenging situation and what you did to overcome it

* Situation 1: System modernization, no documents and no help from the SME's
  - Took one of the modules and reverse engineer COBAL parsed the data and consume the falt files and insered them into that database.
  - Did a major presentation to the customer
  - Start getting helps from the SME's

## Tell me about a time that you met a goal and you exceeded it

* Situation 1: I was in on a project infrusturcutre was poorly configured, using SELinux,
  - Issues I faced, I was given sets of VM with Llinux onit that they were security hardened with no GUI. most oracle products require GUI access for installations.
  - I had to configured the product stack manually.
  - Stablized the infrustructure and port the code into the new environement
  - Customer was very happy with the new stable infrustucture

## What is the most complex problem you ever worked on

* Situation One: Children Hospital infrustructure in PA, I was broght up to assist a Chief Architect to help implementation of active-active data center.
  - This was a technical and manegerial challenge.
  - Using Weblogic Cluster, extended oracle database cluster,
  - The management issue was too many people involved,

## Have you every worked on something extreamly hard and you failed

Yes, I did, I was on data migration from mainframe to a unix 3b2 in AT&T.
Using informix as a DMBS, this was one the largest database, contained residential phones of USA.
on the subsequent release I used a CISAM, using C, and unix that did not have all the over head of 4GL RDBMS.
