# AWS Adminitration

## Monitoring

### CloudWatch

* Major part of Sysops Exam
* Monitoring the AWS resources and Applications

#### What to Monitor

* You can monitoring
  * Compute (EC2)
  * Autoscaling groups
  * Elastic Load Balancer
  * Route53 Health check
  * storage
  * Content delivery
    * EBS Volumes
    * Storage Gateway
    * CloudFront
  * Database and analytics
    * dynamoDB
    * Elastic Nodes
    * RDS Instances
    * RedShift
  * SNS Topics
  * SQS Queue
  * OpsWorks
  * Cloudwatch Logs
  * Estimated Charges on your Bills

### What Metrics

The followings are **Host Level metrics** by default;
* CPU
* Networks
* Disk
* Status Checks
* **NOT RAM Utilization** This is a **Custom Level Metrics**
* You can use Cloudwatch to monitor **On premise** applications, just download and install SSM agent and CLoudwatch agent.

### Metrics Granularity

* The **Normal/Standard Metrics Monitoring** are provided data every 5 minutes intervals, this is **the default**.
* The **Detailed Monitoring Metrics** are configured to provide data every 1 minute intervals, there are charges associated with this.
* On custom Monitoring, The minimum  

### How long the metrics are Stored

* you can get the data from API **GetMetricsStatistics** or use thrid party Tools
* You can store your **Application Logs** in Cloudwatch as long as you want
* As default Coludwatch maintains the **logs indefinitely**.
* You can change the log retentions for each **Log Group** at anytime
* You can retrieve data from any terminated EC2 or ELB instance even **after termination** as well.

### Cloudwatch alarms


# EBS Monitoring

## EBS Four types
* General Purpose SSD (gp2)
* Provisioned IOPs SSD (io1)
* Throughput Optimized HDD (st1)
* Cold HDD (sc1)
