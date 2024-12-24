## **AWS Database Services Cheat Sheet**

---

### **1. Grouping by Database Characteristics**

AWS databases are categorized by their functionality and core features:

| **Database Type**         | **Description**                                                                  | **Examples**                         |
| ------------------------- | -------------------------------------------------------------------------------- | ------------------------------------ |
| **Relational Databases**  | Structured data with SQL support, ACID compliance, and transactional processing. | Amazon RDS, Amazon Aurora.           |
| **Key-Value Stores**      | Optimized for high-speed, low-latency access to key-value pairs.                 | Amazon DynamoDB, Amazon ElastiCache. |
| **Document Databases**    | Designed for storing and querying JSON or semi-structured data.                  | Amazon DocumentDB.                   |
| **Graph Databases**       | Focused on relationships and connected datasets.                                 | Amazon Neptune.                      |
| **Ledger Databases**      | Immutable, verifiable records for tracking data changes.                         | Amazon QLDB.                         |
| **Time-Series Databases** | Optimized for analyzing time-stamped data.                                       | Amazon Timestream.                   |
| **Data Warehousing**      | Scalable OLAP databases for analytics and business intelligence.                 | Amazon Redshift, Athena, EMR.        |
| **Search Databases**      | Full-text search and indexing for structured and unstructured data.              | Amazon OpenSearch.                   |
| **Object Storage**        | Storing large objects and files with infinite scalability.                       | Amazon S3, Amazon Glacier.           |

##### **Simplified View**
- **DocumentDB:** Think **MongoDB compatibility** for structured, queryable JSON-like documents.  
- **DynamoDB:** Think **simpler, fast key-value store** that supports JSON but with fewer complex query capabilities.
- **Amazon QLDB** : Think  **immutable log keeping** -Amazon Quantum Ledger Database

Both work with JSON, but **DocumentDB** is better for **query complexity**, while **DynamoDB** excels in **scalability and speed**.
---

### **2. Databases Summary: Key Features and Use Cases**

| **Service**            | **Type**             | **Key Features**                                                                               | **Use Cases**                                                                |
| ---------------------- | -------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **Amazon RDS**         | Relational Database  | Supports PostgreSQL, MySQL, Oracle, SQL Server, MariaDB. Multi-AZ, backups, read replicas.     | OLTP, transactional systems, financial apps, e-commerce.                     |
| **Amazon Aurora**      | Relational Database  | Cloud-native PostgreSQL/MySQL, serverless, low-latency replication (<1s globally).             | Enterprise applications, high scalability, large-scale RDBMS workloads.      |
| **Amazon DynamoDB**    | Key-Value Store      | Serverless, low latency, global tables, TTL for session data, streams for event processing.    | IoT apps, session stores, gaming leaderboards, distributed systems.          |
| **Amazon ElastiCache** | Key-Value Store      | Managed in-memory store (Redis/Memcached), sub-millisecond latency.                            | High-speed caching, real-time analytics, session storage.                    |
| **Amazon DocumentDB**  | Document Database    | Managed MongoDB-compatible database for JSON, highly available with multi-AZ replication.      | Content management, catalogs, semi-structured data.                          |
| **Amazon Neptune**     | Graph Database       | Optimized for querying relationships, low-latency queries, supports billions of relationships. | Social networks, fraud detection, recommendation engines, knowledge graphs.  |
| **Amazon QLDB**        | Ledger Database      | Immutable, cryptographically verifiable ledger database.                                       | Financial systems, audit trails, compliance.                                 |
| **Amazon Timestream**  | Time-Series Database | Built for time-stamped data, serverless, SQL-compatible, tiered storage.                       | IoT apps, operational analytics, real-time monitoring.                       |
| **Amazon Redshift**    | Data Warehouse       | Fully managed data warehouse, MPP, scalable, integrates with BI tools like QuickSight.         | Big data analytics, enterprise reporting, business intelligence.             |
| **Amazon Athena**      | Data Warehouse       | Serverless SQL querying directly on S3, pay-per-query pricing.                                 | Ad-hoc analysis, log analysis, querying data lakes.                          |
| **Amazon EMR**         | Data Warehouse       | Big data processing using Hadoop and Spark.                                                    | Machine learning pipelines, ETL workflows, large-scale data transformations. |
| **Amazon OpenSearch**  | Search Database      | Full-text search and indexing for unstructured/JSON data, real-time log analysis.              | Website search, operational monitoring, enterprise search.                   |
| **Amazon S3**          | Object Storage       | Scalable key-value store for objects, lifecycle management, encryption, serverless.            | Data lakes, backups, media storage, static website hosting.                  |
| **Amazon Glacier**     | Object Storage       | Cost-effective archival storage for long-term backups.                                         | Archiving regulatory/compliance data, rarely accessed backups.               |

---

### **3. Decision Matrix: Choosing the Right Database**

| **Requirement**                    | **Recommended Services**                    |
| ---------------------------------- | ------------------------------------------- |
| **Transactional workloads (OLTP)** | Amazon RDS, Amazon Aurora.                  |
| **High-speed key-value access**    | Amazon DynamoDB, Amazon ElastiCache.        |
| **Flexible schema/JSON data**      | Amazon DocumentDB, DynamoDB.                |
| **Highly connected datasets**      | Amazon Neptune.                             |
| **Caching for low-latency access** | Amazon ElastiCache.                         |
| **Data analytics/BI**              | Amazon Redshift, Amazon Athena, Amazon EMR. |
| **Immutable, auditable data**      | Amazon QLDB.                                |
| **IoT and time-series data**       | Amazon Timestream, DynamoDB, Keyspaces.     |
| **Object/file storage**            | Amazon S3, Amazon Glacier.                  |
| **Search and indexing**            | Amazon OpenSearch.                          |
| **Ad-hoc SQL analysis on S3 data** | Amazon Athena.                              |
| **Big data processing**            | Amazon EMR.                                 |

##### **Simplified View**
- **DocumentDB:** Think **MongoDB compatibility** for structured, queryable JSON-like documents.  
- **DynamoDB:** Think **simpler, fast key-value store** that supports JSON but with fewer complex query capabilities.
- **Amazon QLDB** : Think  **immutable log keeping** -Amazon Quantum Ledger Database


Both work with JSON, but **DocumentDB** is better for **query complexity**, while **DynamoDB** excels in **scalability and speed**.
