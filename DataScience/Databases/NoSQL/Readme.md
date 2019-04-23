# NoSQL

[Source](https://en.wikipedia.org/wiki/NoSQL)

A NoSQL (originally referring to "non SQL" or "non relational") database provides a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases. Such databases have existed since the late 1960s, but did not obtain the "NoSQL" moniker until a surge of popularity in the early twenty-first century, triggered by the needs of Web 2.0 companies such as Facebook, Google, and Amazon.com. NoSQL databases are increasingly used in big data and real-time web applications. NoSQL systems are also sometimes called "Not only SQL" to emphasize that they may support SQL-like query languages.

Motivations for this approach include: simplicity of design, simpler "horizontal" scaling to clusters of machines (which is a problem for relational databases), and finer control over availability. The data structures used by NoSQL databases (e.g. key-value, wide column, graph, or document) are different from those used by default in relational databases, making some operations faster in NoSQL. The particular suitability of a given NoSQL database depends on the problem it must solve. Sometimes the data structures used by NoSQL databases are also viewed as "more flexible" than relational database tables.

Many NoSQL stores compromise consistency (in the sense of the CAP theorem) in favor of availability, partition tolerance, and speed. Barriers to the greater adoption of NoSQL stores include the use of low-level query languages (instead of SQL, for instance the lack of ability to perform ad-hoc joins across tables), lack of standardized interfaces, and huge previous investments in existing relational databases. Most NoSQL stores lack true ACID transactions, although a few databases, such as MarkLogic, Aerospike, FairCom c-treeACE, Google Spanner (though technically a NewSQL database), Symas LMDB, and OrientDB have made them central to their designs. (See ACID and join support.)

Instead, most NoSQL databases offer a concept of "eventual consistency" in which database changes are propagated to all nodes "eventually" (typically within milliseconds) so queries for data might not return updated data immediately or might result in reading data that is not accurate, a problem known as stale reads. Additionally, some NoSQL systems may exhibit lost writes and other forms of data loss. Fortunately, some NoSQL systems provide concepts such as write-ahead logging to avoid data loss. For distributed transaction processing across multiple databases, data consistency is an even bigger challenge that is difficult for both NoSQL and relational databases. Even current relational databases "do not allow referential integrity constraints to span databases." There are few systems that maintain both ACID transactions and X/Open XA standards for distributed transaction processing.


## NoSQL vs. Relational
* NoSQL are optimized for performance
* Relational Database are optimized for storage size.

SQL has several very big advantages:

* Strong mathematical basis.
* Declarative syntax.
* A well-known language in Structured Query Language (SQL).

It's a mistake to think about this as an either/or argument. NoSQL is an alternative that people need to consider when it fits, that's all.

NoSQL is better than RDBMS because of the following reasons/properities of NoSQL

1. It supports semi-structured data and volatile data
2. It does not have schema
3. Read/Write throughput is very high
4. Horizontal scalability can be achieved easily
5. Will support Bigdata in volumes of Terra Bytes & Peta Bytes
6. Provides good support for Analytic tools on top of Bigdata
7. Can be hosted in cheaper hardware machines
8. In-memory caching option is available to increase the performance of queries
9. Faster development life cycles for developers

* RDBMS's: have challenges in handling huge data volumes of Terabytes & Peta bytes. Even if you have Redundant Array of Independent/Inexpensive Disks (RAID) & data shredding, it does not scale well for huge volume of data. You require very expensive hardware.

* Logging: Assembling log records and tracking down all changes in database structures slows performance. Logging may not be necessary if recoverability is not a requirement or if recoverability is provided through other means (e.g., other sites on the network).

* Locking: Traditional two-phase locking poses a sizeable overhead since all accesses to database structures are governed by a separate entity, the Lock Manager.

* Latching: In a multi-threaded database, many data structures have to be latched before they can be accessed. Removing this feature and going to a single-threaded approach has a noticeable performance impact.

* Buffer management: A main memory database system does not need to access pages through a buffer pool, eliminating a level of indirection on every record access.

This does not mean that we have to use NoSQL over SQL.

Still, RDBMS is better than NoSQL for the following reasons/properties of RDBMS

1. Transactions with ACID properties - Atomicity, Consistency, Isolation & Durability
2. Adherence to Strong Schema of data being written/read
3. Real time query management ( in case of data size < 1 0 10 Tera bytes )
4. Execution of complex queries involving join & group by clauses

See Also
* [NoSQL Explained](https://www.mongodb.com/nosql-explained)
* [SQL vs. NoSQL](https://www.sitepoint.com/sql-vs-nosql-differences/)
* [Nosql](https://www.datastax.com/nosql-databases)
* [More Information](https://www.quora.com/When-should-you-use-NoSQL-vs-regular-RDBMS)

## Types and examples of NoSQL databases

There have been various approaches to classify NoSQL databases, each with different categories and subcategories, some of which overlap. What follows is a basic classification by data model, with examples:

<ul>
    <li><b><a href="https://en.wikipedia.org/wiki/Column_(data_store)">Column</a></b>:
        <a href="https://en.wikipedia.org/wiki/Accumulo">Accumulo</a>,
        <a href="https://en.wikipedia.org/wiki/Apache_Cassandra">Cassandra</a>,
        <a href="https://en.wikipedia.org/wiki/Druid_(open-source_data_store)">Druid</a>,
        <a href="https://en.wikipedia.org/wiki/HBase">HBase</a>,
        <a href="https://en.wikipedia.org/wiki/Vertica">Vertica</a>,
        <a href="https://en.wikipedia.org/wiki/SAP_HANA">SAP HANA</a>
    </li>
    <li><b><a href="https://en.wikipedia.org/wiki/Document-oriented_database">Document</a></b>:
        <a href="https://en.wikipedia.org/wiki/Apache_CouchDB">Apache CouchDB</a>,
        <a href="https://en.wikipedia.org/wiki/ArangoDB">ArangoDB</a>,
        <a href="https://en.wikipedia.org/wiki/Clusterpoint">Clusterpoint</a>,
        <a href="https://en.wikipedia.org/wiki/Couchbase">Couchbase</a>,
        <a href="https://en.wikipedia.org/wiki/Cosmos_DB">Cosmos DB</a>,
        <a href="https://en.wikipedia.org/wiki/HyperDex">HyperDex</a>,
        <a href="https://en.wikipedia.org/wiki/Lotus_Notes">IBM Domino</a>,
        <a href="https://en.wikipedia.org/wiki/MarkLogic">MarkLogic</a>,
        <a href="https://en.wikipedia.org/wiki/MongoDB">MongoDB</a>,
        <a href="https://en.wikipedia.org/wiki/OrientDB">OrientDB</a>,
        <a href="https://en.wikipedia.org/wiki/Qizx">Qizx</a>,
        <a href="https://en.wikipedia.org/wiki/RethinkDB">RethinkDB</a>
    </li>
    <li><b><a href="https://en.wikipedia.org/wiki/Key-value_store">Key-value</a></b>:
        <a href="https://en.wikipedia.org/wiki/Aerospike_database">Aerospike</a>,
        <a href="https://en.wikipedia.org/wiki/ArangoDB">ArangoDB</a>,
        <a href="https://en.wikipedia.org/wiki/Couchbase">Couchbase</a>,
        <a href="https://en.wikipedia.org/wiki/Dynamo_(storage_system)">Dynamo</a>, FairCom
        <a href="https://en.wikipedia.org/wiki/C-treeACE">c-treeACE</a>,
        <a href="https://en.wikipedia.org/wiki/FoundationDB">FoundationDB</a>,
        <a href="https://en.wikipedia.org/wiki/HyperDex">HyperDex</a>,
        <a href="https://en.wikipedia.org/wiki/InfinityDB">InfinityDB</a>,
        <a href="https://en.wikipedia.org/wiki/MemcacheDB">MemcacheDB</a>,
        <a href="https://en.wikipedia.org/wiki/MUMPS">MUMPS</a>,
        <a href="https://en.wikipedia.org/wiki/Oracle_NoSQL_Database">Oracle NoSQL Database</a>,
        <a href="https://en.wikipedia.org/wiki/OrientDB">OrientDB</a>,
        <a href="https://en.wikipedia.org/wiki/Redis">Redis</a>,
        <a href="https://en.wikipedia.org/wiki/Riak">Riak</a>,
        <a href="https://en.wikipedia.org/wiki/Berkeley_DB">Berkeley DB</a>, SDBM/Flat File
        <a href="https://en.wikipedia.org/wiki/Dbm">dbm</a>
    </li>
    <li><b><a href="https://en.wikipedia.org/wiki/Graph_database">Graph</a></b>:
        <a href="https://en.wikipedia.org/wiki/AllegroGraph">AllegroGraph</a>,
        <a href="https://en.wikipedia.org/wiki/ArangoDB">ArangoDB</a>,
        <a href="https://en.wikipedia.org/wiki/InfiniteGraph">InfiniteGraph</a>,
        <a href="https://en.wikipedia.org/wiki/Apache_Giraph">Apache Giraph</a>,
        <a href="https://en.wikipedia.org/wiki/MarkLogic">MarkLogic</a>,
        <a href="https://en.wikipedia.org/wiki/Neo4J">Neo4J</a>,
        <a href="https://en.wikipedia.org/wiki/OrientDB">OrientDB</a>,
        <a href="https://en.wikipedia.org/wiki/Virtuoso_Universal_Server">Virtuoso</a>
    </li>
    <li><b><a href="https://en.wikipedia.org/wiki/Multi-model_database">Multi-model</a></b>:
        <a href="https://en.wikipedia.org/wiki/ArangoDB">ArangoDB</a>,
        <a href="https://en.wikipedia.org/wiki/Couchbase">Couchbase</a>,
        <a href="https://en.wikipedia.org/wiki/FoundationDB">FoundationDB</a>,
        <a href="https://en.wikipedia.org/wiki/InfinityDB">InfinityDB</a>,
        <a href="https://en.wikipedia.org/wiki/MarkLogic">MarkLogic</a>,
        <a href="https://en.wikipedia.org/wiki/OrientDB">OrientDB</a>
    </li>
</ul>
<p>A more detailed classification is the following, based on one from Stephen Yen:</p>
<table>
    <tr>
        <th>Type</th>
        <th>Examples of this type</th>
    </tr>
    <tr>
        <td>Key-Value Cache</td>
        <td><a href="https://en.wikipedia.org/wiki/Oracle_Coherence">Coherence</a>,
            <a href="https://en.wikipedia.org/wiki/IBM_WebSphere_eXtreme_Scale">eXtreme Scale</a>,
            <a href="https://en.wikipedia.org/wiki/Hazelcast">Hazelcast</a>,
            <a href="https://en.wikipedia.org/wiki/Infinispan">Infinispan</a>, JBoss Cache,
            <a href="https://en.wikipedia.org/wiki/Memcached">Memcached</a>, Repcached,
            <a href="https://en.wikipedia.org/wiki/Velocity_(memory_cache)">Velocity</a>
        </td>
    </tr>
    <tr>
        <td>Key-Value Store</td>
        <td><a href="https://en.wikipedia.org/wiki/ArangoDB">ArangoDB</a>, Flare, Keyspace, RAMCloud, SchemaFree,
            <a href="https://en.wikipedia.org/wiki/Hyperdex">Hyperdex</a>,
            <a href="https://en.wikipedia.org/wiki/Aerospike_database">Aerospike</a>,
            <a href="https://en.wikipedia.org/wiki/Quasardb">quasardb</a>
        </td>
    </tr>
    <tr>
        <td>Key-Value Store (Eventually-Consistent)</td>
        <td>DovetailDB, <a href="https://en.wikipedia.org/wiki/Oracle_NoSQL_Database">Oracle NoSQL Database</a>,
            <a href="https://en.wikipedia.org/wiki/Dynamo_(storage_system)">Dynamo</a>,
            <a href="https://en.wikipedia.org/wiki/Riak">Riak</a>, Dynomite,
            <a href="https://en.wikipedia.org/wiki/Voldemort_(distributed_data_store)">Voldemort</a>, SubRecord</td>
    </tr>
    <tr>
        <td>Key-Value Store (Ordered)</td>
        <td>Actord, <a href="https://en.wikipedia.org/wiki/FoundationDB">FoundationDB</a>,
            <a href="https://en.wikipedia.org/wiki/InfinityDB">InfinityDB</a>, Lightcloud,
            <a href="https://en.wikipedia.org/wiki/Lightning_Memory-Mapped_Database">LMDB</a>, Luxio,
            <a href="https://en.wikipedia.org/wiki/MemcacheDB">MemcacheDB</a>, NMDB, TokyoTyrant</td>
    </tr>
    <tr>
        <td>Data-Structures Server</td>
        <td><a href="https://en.wikipedia.org/wiki/Redis">Redis</a>
        </td>
    </tr>
    <tr>
        <td>Tuple Store</td>
        <td><a href="https://en.wikipedia.org/wiki/Jini">Apache River</a>, Coord,
            <a href="https://en.wikipedia.org/wiki/GigaSpaces">GigaSpaces</a>
        </td>
    </tr>
    <tr>
        <td>Object Database</td>
        <td>DB4O, <a href="https://en.wikipedia.org/wiki/Objectivity/DB">Objectivity/DB</a>,
            <a href="https://en.wikipedia.org/wiki/Perst">Perst</a>, Shoal,
            <a href="https://en.wikipedia.org/wiki/Zope_Object_Database">ZopeDB</a>
        </td>
    </tr>
    <tr>
        <td>Document Store</td>
        <td><a href="https://en.wikipedia.org/wiki/ArangoDB">ArangoDB</a>,
            <a href="https://en.wikipedia.org/wiki/Clusterpoint">Clusterpoint</a>,
            <a href="https://en.wikipedia.org/wiki/Couchbase">Couchbase</a>,
            <a href="https://en.wikipedia.org/wiki/CouchDB">CouchDB</a>,
            <a href="https://en.wikipedia.org/wiki/DocumentDB">DocumentDB</a>,
            <a href="https://en.wikipedia.org/wiki/Lotus_Notes">IBM Domino</a>,
            <a href="https://en.wikipedia.org/wiki/MarkLogic">MarkLogic</a>,
            <a href="https://en.wikipedia.org/wiki/MongoDB">MongoDB</a>,
            <a href="https://en.wikipedia.org/wiki/Qizx">Qizx</a>,
            <a href="https://en.wikipedia.org/wiki/RethinkDB">RethinkDB</a>,
            <a href="https://en.wikipedia.org/wiki/XML_database">XML-databases</a>
        </td>
    </tr>
    <tr>
        <td><a href="https://en.wikipedia.org/wiki/Wide_column_store">Wide Column Store</a>
        </td>
        <td><a href="https://en.wikipedia.org/wiki/Amazon_DynamoDB">Amazon DynamoDB</a>,
            <a href="https://en.wikipedia.org/wiki/BigTable">BigTable</a>,
            <a href="https://en.wikipedia.org/wiki/Apache_Cassandra">Cassandra</a>,
            <a href="https://en.wikipedia.org/wiki/Druid_(open-source_data_store)">Druid</a>,
            <a href="https://en.wikipedia.org/wiki/Apache_HBase">HBase</a>,
            <a href="https://en.wikipedia.org/wiki/Hypertable">Hypertable</a>, KAI, KDI, OpenNeptune, Qbase
        </td>
    </tr>
</table>
