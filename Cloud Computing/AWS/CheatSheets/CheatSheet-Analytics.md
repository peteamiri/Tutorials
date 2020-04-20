# AWS Certification – Analytics Services – Cheat Sheet

## Kinesis Data Streams

*   enables real-time processing of streaming data at massive scale
*   provides ordering of records, as well as the ability to read and/or replay records in the same order to multiple Kinesis applications
*   data is replicated across three data centers within a region and preserved for 24 hours, by default and can be extended to 7 days
*   streams can be scaled using multiple shards, based on the partition key, with each shard providing the capacity of 1MB/sec data input and 2MB/sec data output with 1000 PUT requests per second
*   Data encryption can be supported either using client side encryption before pushing the data to data streams or server side encryption.
*   **Kinesis vs SQS**
    *   real-time processing of streaming big data vs reliable, highly scalable hosted queue for storing messages
    *   ordered records, as well as the ability to read and/or replay records in the same order vs no guarantee on data ordering (with the standard queues before the FIFO queue feature was released)
    *   data storage up to 24 hours, extended to 7 days vs up to 14 days, can be configured from 1 minute to 14 days but cleared if deleted by the consumer
    *   supports multiple consumers vs single consumer at a time and requires multiple queues to deliver message to multiple consumers
*   **Producer & Consumers**
    *   API PutRecord and PutRecords are **synchronous**, while KPL producer supports synchronous or **asynchronous** use cases
    *   KCL uses a unique DynamoDB table to keep track of the application’s state, so if Kinesis Data Streams application receives provisioned-throughput exceptions, increase the provisioned throughput for the DynamoDB table

#### Detailed Reading

*   [AWS Kinesis Data Streams](https://jayendrapatil.com/aws-kinesis/)

## **Kinesis Firehose**

*   is a fully managed service
*   data transfer solution for delivering real time streaming data to destinations such as **S3,  Redshift,  Elasticsearch service, and Splunk**.
*   is <span style="color: #ff0000;">**NOT real time** (**min. 60 secs**)</span> as it buffers incoming streaming data to a certain size or for a certain period of time before delivering it
*   supports multiple producers as datasource, which include Kinesis data stream, Kinesis Agent, or the Kinesis Data Firehose API using the AWS SDK, CloudWatch Logs, CloudWatch Events, or AWS IoT
*   supports out of box data transformation as well as custom transformation using Lambda function to transform incoming source data and deliver the transformed data to destinations
*   supports interface VPC endpoint to keep traffic between the Amazon VPC and Kinesis Data Firehose from leaving the Amazon network.

#### Detailed Reading

*   [AWS Kinesis Data Firehose](https://jayendrapatil.com/aws-kinesis-data-firehose/)

## Kinesis Data Streams vs Kinesis Firehose

![](https://secureservercdn.net/160.153.138.177/3d9.249.myftpupload.com/wp-content/uploads/2019/08/Kinesis-Data-Streams-vs.-Firehose.png)

## Kinesis Data Analytics

*   helps analyze streaming data, gain actionable insights, and respond to the business and customer needs in real time.
*   reduces the complexity of building, managing, and integrating streaming applications with other AWS service

## Redshift

*   Redshift is a fast, fully managed data warehouse
*   provides simple and cost-effective solution to analyze all the data using standard SQL and the existing Business Intelligence (BI) tools.
*   manages the work needed to set up, operate, and scale a data warehouse, from provisioning the infrastructure capacity to automating ongoing administrative tasks such as backups, and patching.
*   automatically monitors your nodes and drives to help you recover from failures.
*   **only supports Single-AZ** deployments.
*   replicates all the data within the data warehouse cluster when it is loaded and also continuously backs up your data to S3.
*   attempts to maintain at least three copies of your data (the original and replica on the compute nodes and a backup in S3).
*   supports cross-region snapshot replication to another region for disaster recovery
*   Redshift supports four distribution styles; AUTO, EVEN, KEY, or ALL.
    *   KEY distribution uses a single column as distribution key (DISTKEY) and helps place matching values on the same node slice
    *   Even distribution distributes the rows across the slices in a **round-robin fashion**, regardless of the values in any particular column
    *   ALL distribution replicates whole table in every compute node.
    *   AUTO distribution lets Redshift assigns an optimal distribution style based on the size of the table data
*   Redshift supports Compound and Interleaved sort keys
    *   A compound key is made up of all of the columns listed in the sort key definition, in the order they are listed and is more efficient when **query predicates use a _prefix_, or query’s filter applies conditions, such as filters and joins, which is a subset of the sort key columns in order.**
    *   An interleaved sort key gives **equal weight to each column in the sort key, so query predicates can use any subset of the columns that make up the sort key, in any order.**
*   Column encodings **CANNOT** be changed once created.
*   Redshift provides **query queues for Workload Management**, in order to manage concurrency and resource planning. It is a best practice to have separate queues for long running resource-intensive queries and fast queries that don’t require big amounts of memory and CPU

#### Detailed Reading

*   [AWS Redshift](https://jayendrapatil.com/aws-redshift/)
*   [AWS Redshift Advanced](https://jayendrapatil.com/aws-redshift-advanced/)
*   [AWS Redshift Best Practices](https://jayendrapatil.com/aws-redshift-best-practices/)

## EMR

*   is a web service that utilizes a hosted **Hadoop** framework running on the web-scale infrastructure of EC2 and S3
*   launches all nodes for a given cluster in the **same Availability Zone**, which improves performance as it provides higher data access rate
*   seamlessly supports Reserved, On-Demand and Spot Instances
*   consists of Master Node for management and Slave nodes, which consists of Core nodes holding data and Task nodes for performing tasks only
*   is fault tolerant for slave node failures and continues job execution if a slave node goes down
*   does not automatically provision another node to take over failed slaves
*   supports Persistent and Transient cluster types
    *   Persistent which continue to run
    *   Transient which terminates once the job steps are completed
*   supports **EMRFS** which allows S3 to be used as a durable HA data storage

#### Detailed Reading

*   [EMR](https://jayendrapatil.com/aws-emr-certification/)
*   [EMR Best Practices](https://jayendrapatil.com/amazon-emr-best-practices/)

## Glue

*   fully-managed ETL service that automates the time-consuming steps of data preparation for analytics
*   recommends and generates ETL code to transform the source data into target schemas, and runs the ETL jobs on a fully managed, scale-out Apache Spark environment to load your data into its destination.
*   helps setup, orchestrate, and monitor complex data flows.
*   **AWS Glue Data Catalog**
    *   is a central repository to store structural and operational metadata for all the data assets.
    *   automatically discovers and profiles the data
    *   automatically discover both structured and semi-structured data stored in the data lake on S3, data warehouse in Redshift, and other databases
    *   provides a unified view of the data that is available for ETL, querying and reporting using services like Athena, EMR, and Redshift Spectrum.
*   **AWS Glue crawler**
    *   connects to a data store, progresses through a prioritized list of classifiers to extract the schema of the data and other statistics, and then populates the Glue Data Catalog with this metadata

## Data Pipeline

*   orchestration service that helps define **data-driven workflows** to automate and schedule regular data movement and data processing activities
*   integrates with **on-premises and cloud-based** storage systems
*   allows scheduling, **retry, and failure logic** for the workflows

#### Detailed Reading

*   [Data Pipeline](https://jayendrapatil.com/aws-data-pipeline/)
