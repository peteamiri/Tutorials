# Big Data

* Processing of large amout of data

## Characteristics of Big data
* Varisity: vlidaty of data
* Velocity: speed at which data is generated
* Volume : size of data
* Veriety : type of data,
  - Structured
  - Semi-Structured
  - Unstructured data

## Apache Hadoop

* There are two parts to Hadoop
  - Distributed storage `Hadoop Distributed File System (HDFS)`
  - Distributed processing

# Distrubuted Storage
* Data is stored in blocks across multipe computers;
  - There are mulipe copies of data in multipe Node
  - The nodes can be added as storage is needed (Horizontal Cluster)
  - Accessingg files on HDFS is very similar to Linux Filesyste, commands are very similar to Linux CLI

## Distributed Processing
* Haddop uses cluster of computr to perfrom process
* Originally is geared for batch processing. Howver, some interactive proccing also can be done
* This approach is called map reduce;
  - each node in the computer maps the data into key value pairs
  - each computer reudce the result of the data from previous stage into key walue pair

#### See for more information
* [Youtube introduction to Hadoop](https://www.youtube.com/watch?v=DCaiZq3aBSc)
* [Hadoop Kafka andImport Hortonwork VM](https://www.youtube.com/watch?v=sIevsR_JmcM&list=PL6cactdCCnTLBuBazhz4cRaak1hTVzdpH)
