# Resources

* (Wiki)(https://en.wikipedia.org/wiki/Data_warehouse)

# Business Intellignece (BI)
Business intelligence is a collection of activities to understand business situations by performing various types of analysis on the company data as well as on external data from third parties to help make strategic, tactical, and operational business decisions and take necessary actions for improving business performance.
This includes;

* gathering,
* analyzing,
* understanding,
* managing data about operation performance,
* customer and supplier activities,
* financial performance,
* market movements,
* competition,
* regulatory compliance,
* quality controls

Examples of business intelligence are the following:

• Business performance management, including producing key performance indicators
such as daily sales, resource utilization, and main operational costs for each region,
product line, and time period, as well as their aggregates, to enable people to take tac-
tical actions to get operational performance on the desired tracks.

• Customer profitability analysis, that is, to understand which customers are profitable
and worth keeping and which are losing money and therefore need to be acted upon.
The key to this exercise is allocating the costs as accurately as possible to the smallest
unit of business transaction, which is similar to activity-based costing.

• Statistical analysis such as purchase likelihood or basket analysis. Basket analysis is a
process of analyzing sales data to determine which products are likely to be purchased
or ordered together. This likelihood is expressed in terms of statistical measures such as
support and confidence level. It is mainly applicable for the retail and manufacturing
industries but also to a certain degree for the financial services industry.

• Predictive analysis such as forecasting the sales, revenue, and cost figures for the pur-
pose of planning for next year’s budgets and taking into account other factors such as
organic growth, economic situations, and the company’s future direction.

### Business intelligence activities;

All activities can be categorized into three categories:

• Reporting, such as key performance indicators, global sales figures by business unit and service codes, worldwide customer accounts, consolidated delivery status, and resource utilization rates across different branches in many countries

• OLAP such as aggregation, drill down, slice and dice, and drill across

• Data mining, such as data characterization, data discrimination, association analysis, classification, clustering, prediction, trend analysis, deviation analysis, and similarity analysis




## What is Data warehouse.
* Data warehouse is also knows as `Dimensional Data Store (DDS)`.
* Data warehouse or DDS is a data storage area that is mainly the historical data is maintaned, and it is used for `Analytical` or `Business Intelligence (BI), using `online analytical processing (OLAP).

* A data warehouse is a system that retrieves and consolidates the operational data periodically from the `Online Transactional Processing (OLAP)` data source into a `dimensional` or `Online analytical Process` data store. It usually keeps years of history and is queried for `business intelligence (BI)`` or other analytical activities. It is typically updated in batches.

* `Online Transaction Processing (OLTP)` : is a system whose main purpose is to capture and store the business transactions, or `operatinal data`.

## Extract Transorm and Load (ETL)
* `The extract, transform, and load (ETL)` : ETL is basically a tool used to traansfer a bulkd of data for any purpose. It is mainly a tool that system exttracts the data from various sources, transform them into the desired form and upload them into a destination data storage. ETL is a system that has the capability to connect to the source systems, read the data, transform the data, and load it into a target system (the target system doesn’t have to be a data warehouse). The data source and data storage can be anything. Generally,  in the context of the data warehouseing, this process can be done in stages. The followings are two promary stages;

  1. The data is transfered usiing ETL from the `Operational Data storage` into the and destination that could be `Operational Data Storage (ODS)` or `Data lakes`. Both `Operational Data Storage (ODS)` or `Data lakes` are staging area.
  2. Some ETL tools provide a `Data Cleansing` capabilites. or `Data Cleansing` is done manually.
  3. Eventally, the data is transformed and transfered into the `Data Warehouse`.

# OnLine Transaction Processing

In `Online transaction processing (OLTP)`, information systems typically facilitate and manage transaction-oriented applications.

The term `transaction` can have two different meanings, both of which might apply:

* in the realm of computers or database `transactions` it denotes an atomic change of state of data,

* in the realm of business or finance, the term `transaction` typically denotes an exchange of economic entities (as used by, e.g., Transaction Processing Performance Council or commercial transactions.)

OLTP may use transactions of the first type to record transactions of the second.

OLTP has also been used to refer to processing in which the system responds immediately to user requests. An automated teller machine (ATM) for a bank is an example of a commercial transaction processing application. Online transaction processing applications have high throughput and are insert- or update-intensive in database management. These applications are used concurrently by hundreds of users. The key goals of OLTP applications are availability, speed, concurrency and recoverability.[2] Reduced paper trails and the faster, more accurate forecast for revenues and expenses are both examples of how OLTP makes things simpler for businesses. However, like many modern online information technology solutions, some systems require offline maintenance, which further affects the cost-benefit analysis of an online transaction processing system.

OLTP is typically contrasted to OLAP (online analytical processing), which is generally characterized by much more complex queries, in a smaller volume, for the purpose of business intelligence or reporting rather than to process transactions. Whereas OLTP systems process all kinds of queries (read, insert, update and delete), OLAP is generally optimized for read only and might not even support other kinds of queries. OLTP also operates differently from batch processing and grid computing.[1]:15

In addition, OLTP is often contrasted to OLEP (online event processing), which is based on distributed event logs to offer strong consistency in large-scale heterogeneous systems. Whereas OLTP is associated with short atomic transactions, OLEP allows for more flexible distribution patterns and higher scalability, but with increased latency and without guaranteed upper bound to the processing time.

An OLTP system is an accessible data processing system in today's enterprises. Some examples of OLTP systems include order entry, retail sales, and financial transaction systems.[4] Online transaction processing systems increasingly require support for transactions that span a network and may include more than one company. For this reason, modern online transaction processing software uses client or server processing and brokering software that allows transactions to run on different computer platforms in a network.

In large applications, efficient OLTP may depend on sophisticated transaction management software (such as CICS) and/or database optimization tactics to facilitate the processing of large numbers of concurrent updates to an OLTP-oriented database.

For even more demanding decentralized database systems, OLTP brokering programs can distribute transaction processing among multiple computers on a network. OLTP is often integrated into service-oriented architecture (SOA) and Web services.

Online transaction processing (OLTP) involves gathering input information, processing the data and updating existing data to reflect the collected and processed information. As of today, most organizations use a database management system to support OLTP. OLTP is carried in a client-server system.

Online transaction process concerns about `concurrency` and `atomicity`.

* `Concurrency controls` guarantee that two users accessing the same data in the database system will not be able to change that data or the user has to wait until the other user has finished processing, before changing that piece of data.

*  `Atomicity controls` guarantee that all the steps in a transaction are completed successfully as a group. That is, if any steps between the transaction fail, all other steps must fail also.

#### Some of the commonly used terms in Transactional Database

The ralational database is optimzed for storage. That is why the data is normilized and redundancies are removed.

To build an OLTP system, a designer must know that the large number of concurrent users does not interfere with the system's performance. To increase the performance of an OLTP system, a designer must avoid excessive use of indexes and clusters.

The following elements are crucial for the performance of OLTP systems:[2]

* `Rollback segments` : Rollback segments are the portions of database that record the actions of transactions in the event that a transaction is rolled back. Rollback segments provide read consistency, rollback transactions, and recovery of the database.[6]
Clusters A cluster is a schema that contains one or more tables that have one or more columns in common. Clustering tables in a database improves the performance of join operations.[7]

`Discrete transactions` : A discrete transaction defers all change to the data until the transaction is committed. It can improve the performance of short, non-distributed transactions.[8]
Block size The data block size should be a multiple of the operating system's block size within the maximum limit to avoid unnecessary I/O.[9]

`Buffer cache size` : SQL statements should be tuned to use the database buffer cache to avoid unnecessary resource consumption.[10] Dynamic allocation of space to tables and rollback segments Transaction processing monitors and the multi-threaded server A transaction processing monitor is used for coordination of services. It is like an operating system and does the coordination at a high level of granularity and can span multiple computing devices.[11]

`Data Partition` :
Partition use increases performance for sites that have regular transactions while still maintaining availability and security.
Database tuning With database tuning, an OLTP system can maximize its performance as efficiently and rapidly as possible.
There are two types of data partitioniing;

* `Horizontal Data Partitioning` :

* `Vertical Data Partitioning` :
# Types of Relational Database
Databases configured for OLAP use a
* multidimensional data model, allowing for complex analytical and ad hoc queries with a rapid execution time.[7] They borrow aspects of
* navigational databases,
* hierarchical databases (Legacy Seldom used)
* relational databases.

### ACID

## Online analytical processing (OLAP)

Online analytical processing, or OLAP, is an approach to answer `multi-dimensional analytical (MDA)`` queries.

OLAP is part of the broader category of `business intelligence`, which also encompasses `relational databases`, `report writing` and `data mining`.

Exampple of use of OLAP may include;

* business reporting for sales,
* marketing, management reporting,
* business process management (BPM),
* budgeting and forecasting,
* financial reporting and similar areas,
* with new applications emerging, such as agriculture.

OLAP tools enable users to analyze multidimensional data interactively from multiple perspectives. OLAP consists of three basic analytical operations:

* `Consolidation (roll-up)`: Consolidation involves the aggregation of data that can be accumulated and computed in one or more dimensions. For example, all sales offices are rolled up to the sales department or sales division to anticipate sales trends.

* `Drill-down` : is a technique that allows users to navigate through the details. For instance, users can view the sales by individual products that make up a region's sales.

* `Slicing and dicing` : is a feature whereby users can take out (slicing) a specific set of data of the OLAP cube and view (dicing) the slices from different viewpoints. These viewpoints are sometimes called dimensions (such as looking at the same sales by salesperson, or by date, or by customer, or by product, or by region, etc.)

Databases configured for OLAP use a `multidimensional data model`, allowing for complex analytical and ad hoc queries with a rapid execution time. They borrow aspects of navigational databases, hierarchical databases and relational databases.

OLAP is typically contrasted to OLTP (online transaction processing), which is generally characterized by much less complex queries, in a larger volume, to process transactions rather than for the purpose of business intelligence or reporting. Whereas OLAP systems are mostly optimized for read, OLTP has to process all kinds of queries (read, insert, update and delete).

## Relational Data Model
### Multidimensional Data Model

## Data Wrangling

`Data wrangling`, or `data munging`, is the process of transforming and mapping data from one "raw" data form into another format with the intent of making it more appropriate and valuable for a variety of downstream purposes such as analytics. A data wrangler is a person who performs these transformation operations.

This may include further munging for;

  * data visualization,
  * data aggregation,
  * training a statistical model,

as well as many other potential uses. Data munging as a process typically follows a set of general steps which begin with extracting the data in a raw form from the data source, "munging" the raw data using algorithms (e.g. sorting) or parsing the data into predefined data structures, and finally depositing the resulting content into a data sink for storage and future use.

## Data Cleansing

`Data cleansing` : or data cleaning is the process of detecting and correcting corrupt or inaccurate records from a record set, table, or database and refers to identifying incomplete, incorrect, inaccurate or irrelevant parts of the data and then replacing, modifying, or deleting the dirty or coarse data.

`Data cleansing` or data cleaning is the process of detecting and correcting (or removing) corrupt or inaccurate records from a record set, table, or database and refers to identifying incomplete, incorrect, inaccurate or irrelevant parts of the data and then replacing, modifying, or deleting the dirty or coarse data.[1] Data cleansing may be performed interactively with data wrangling tools, or as batch processing through scripting.

After cleansing, a data set should be consistent with other similar data sets in the system. The inconsistencies detected or removed may have been originally caused by user entry errors, by corruption in transmission or storage, or by different data dictionary definitions of similar entities in different stores. Data cleaning differs from data validation in that validation almost invariably means data is rejected from the system at entry and is performed at the time of entry, rather than on batches of data.

The actual process of data cleansing may involve removing typographical errors or validating and correcting values against a known list of entities. The validation may be strict (such as rejecting any address that does not have a valid postal code) or fuzzy (such as correcting records that partially match existing, known records). Some data cleansing solutions will clean data by cross-checking with a validated data set. A common data cleansing practice is data enhancement, where data is made more complete by adding related information. For example, appending addresses with any phone numbers related to that address. Data cleansing may also involve harmonization (or normalization) of data, which is the process of bringing together data of "varying file formats, naming conventions, and columns",[2] and transforming it into one cohesive data set; a simple example is the expansion of abbreviations ("st, rd, etc." to "street, road, etcetera").

### Data Quality (DQ)

High-quality data needs to pass a set of quality criteria. These quality may include:

* `Validity` : The degree to which the measures conform to defined business rules or constraints (see also Validity (statistics)). When modern database technology is used to design data-capture systems, validity is fairly easy to ensure: invalid data arises mainly in legacy contexts (where constraints were not implemented in software) or where inappropriate data-capture technology was used (e.g., spreadsheets, where it is very hard to limit what a user chooses to enter into a cell, if cell validation is not used). Data constraints fall into the following categories:
Data-Type Constraints – e.g., values in a particular column must be of a particular data type, e.g., Boolean, numeric (integer or real), date, etc.

* `Range Constraints`: typically, numbers or dates should fall within a certain range. That is, they have minimum and/or maximum permissible values.

* `Mandatory Constraints`: Certain columns cannot be empty.
Unique Constraints: A field, or a combination of fields, must be unique across a dataset. For example, no two persons can have the same social security number.

* `Set-Membership constraints`: The values for a column come from a set of discrete values or codes. For example, a person's gender may be Female, Male or Unknown (not recorded).

* `Foreign-key constraints`: This is the more general case of set membership. The set of values in a column is defined in a column of another table that contains unique values. For example, in a US taxpayer database, the "state" column is required to belong to one of the US's defined states or territories: the set of permissible states/territories is recorded in a separate State table. The term foreign key is borrowed from relational database terminology.

* `Regular expression patterns`: Occasionally, text fields will have to be validated this way. For example, phone numbers may be required to have the pattern (999) 999-9999.

* `Cross-field validation`: Certain conditions that utilize multiple fields must hold. For example, in laboratory medicine, the sum of the components of the differential white blood cell count must be equal to 100 (since they are all percentages). In a hospital database, a patient's date of discharge from the hospital cannot be earlier than the date of admission.

* `Accuracy`: The degree of conformity of a measure to a standard or a true value - see also Accuracy and precision. Accuracy is very hard to achieve through data-cleansing in the general case because it requires accessing an external source of data that contains the true value: such "gold standard" data is often unavailable. Accuracy has been achieved in some cleansing contexts, notably customer contact data, by using external databases that match up zip codes to geographical locations (city and state) and also help verify that street addresses within these zip codes actually exist.

* `Completeness`: The degree to which all required measures are known. Incompleteness is almost impossible to fix with data cleansing methodology: one cannot infer facts that were not captured when the data in question was initially recorded. (In some contexts, e.g., interview data, it may be possible to fix incompleteness by going back to the original source of data, i,e., re-interviewing the subject, but even this does not guarantee success because of problems of recall - e.g., in an interview to gather data on food consumption, no one is likely to remember exactly what one ate six months ago. In the case of systems that insist certain columns should not be empty, one may work around the problem by designating a value that indicates "unknown" or "missing", but the supplying of default values does not imply that the data has been made complete.

* `Consistency`: The degree to which a set of measures are equivalent in across systems (see also Consistency). Inconsistency occurs when two data items in the data set contradict each other: e.g., a customer is recorded in two different systems as having two different current addresses, and only one of them can be correct. Fixing inconsistency is not always possible: it requires a variety of strategies - e.g., deciding which data were recorded more recently, which data source is likely to be most reliable (the latter knowledge may be specific to a given organization), or simply trying to find the truth by testing both data items (e.g., calling up the customer).

* `Uniformity`: The degree to which a set data measures are specified using the same units of measure in all systems ( see also Unit of measure). In datasets pooled from different locales, weight may be recorded either in pounds or kilos and must be converted to a single measure using an arithmetic transformation.
The term integrity encompasses accuracy, consistency and some aspects of validation (see also data integrity) but is rarely used by itself in data-cleansing contexts because it is insufficiently specific. (For example, "referential integrity" is a term used to refer to the enforcement of foreign-key constraints above.)

* `Data auditing`: The data is audited with the use of statistical and database methods to detect anomalies and contradictions: this eventually indicates the characteristics of the anomalies and their locations. Several commercial software packages will let you specify constraints of various kinds (using a grammar that conforms to that of a standard programming language, e.g., JavaScript or Visual Basic) and then generate code that checks the data for violation of these constraints. This process is referred to below in the bullets "workflow specification" and "workflow execution." For users who lack access to high-end cleansing software, Microcomputer database packages such as Microsoft Access or File Maker Pro will also let you perform such checks, on a constraint-by-constraint basis, interactively with little or no programming required in many cases.
Workflow specification: The detection and removal of anomalies are performed by a sequence of operations on the data known as the workflow. It is specified after the process of auditing the data and is crucial in achieving the end product of high-quality data. In order to achieve a proper workflow, the causes of the anomalies and errors in the data have to be closely considered.
Workflow execution: In this stage, the workflow is executed after its specification is complete and its correctness is verified. The implementation of the workflow should be efficient, even on large sets of data, which inevitably poses a trade-off because the execution of a data-cleansing operation can be computationally expensive.

* `Post-processing and controlling`: After executing the cleansing workflow, the results are inspected to verify correctness. Data that could not be corrected during the execution of the workflow is manually corrected, if possible. The result is a new cycle in the data-cleansing process where the data is audited again to allow the specification of an additional workflow to further cleanse the data by automatic processing.
Good quality source data has to do with “Data Quality Culture” and must be initiated at the top of the organization. It is not just a matter of implementing strong validation checks on input screens, because almost no matter how strong these checks are, they can often still be circumvented by the users. There is a nine-step guide for organizations that wish to improve data quality:

1. Declare a high-level commitment to a data quality culture
1. Drive process reengineering at the executive level
1. Spend money to improve the data entry environment
1. Spend money to improve application integration
1. Spend money to change how processes work
1. Promote end-to-end team awareness
1. Promote interdepartmental cooperation
1. Publicly celebrate data quality excellence
1. Continuously measure and improve data quality


### Data Cleansing Process

`Parsing`: for the detection of syntax errors. A parser decides whether a string of data is acceptable within the allowed data specification. This is similar to the way a parser works with grammars and languages.

`Data transformation`: Data transformation allows the mapping of the data from its given format into the format expected by the appropriate application. This includes value conversions or translation functions, as well as normalizing numeric values to conform to minimum and maximum values.

`Duplicate elimination`: Duplicate detection requires an algorithm for determining whether data contains duplicate representations of the same entity. Usually, data is sorted by a key that would bring duplicate entries closer together for faster identification.

`Statistical methods`: By analyzing the data using the values of mean, standard deviation, range, or clustering algorithms, it is possible for an expert to find values that are unexpected and thus erroneous. Although the correction of such data is difficult since the true value is not known, it can be resolved by setting the values to an average or other statistical value. Statistical methods can also be used to handle missing values which can be replaced by one or more plausible values, which are usually obtained by extensive data augmentation algorithms.
