### **Amazon Athena**

| Feature               | Description                                                                                    |
| --------------------- | ---------------------------------------------------------------------------------------------- |
| **Purpose**           | Serverless SQL query service to analyze data stored in Amazon S3.                              |
| **Supported Formats** | CSV, JSON, ORC, Avro, Parquet.                                                                 |
| **Pricing**           | $5 per TB of data scanned.                                                                     |
| **Common Use Cases**  | Business intelligence, analytics, querying logs (e.g., VPC Flow Logs, CloudTrail).             |
| **Performance Tips**  | Use columnar formats (Parquet/ORC), compress data, partition datasets, and use large files.    |
| **Federated Query**   | Query across multiple sources (relational/non-relational) using Lambda Data Source Connectors. |

---

### **Amazon Redshift**

| Feature               | Description                                                                              |
| --------------------- | ---------------------------------------------------------------------------------------- |
| **Purpose**           | OLAP data warehousing for analytics and data storage.                                    |
| **Modes**             | Provisioned cluster or Serverless cluster.                                               |
| **Advantages**        | Columnar storage, parallel query engine, 10x performance improvement, supports BI tools. |
| **Snapshots**         | Automated/Manual backups, incremental storage in S3, restore or copy across regions.     |
| **Data Loading**      | Use S3 COPY command or Kinesis Firehose for batch writes.                                |
| **Redshift Spectrum** | Query data in S3 without loading into Redshift.                                          |

---

### **Amazon OpenSearch**

| Feature          | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| **Purpose**      | Successor to ElasticSearch, provides full-text search on various fields.    |
| **Modes**        | Managed or Serverless clusters.                                             |
| **Security**     | Supports Cognito, IAM, TLS, and KMS encryption.                             |
| **Integrations** | Works with DynamoDB, CloudWatch Logs, Kinesis Firehose, IoT data, and more. |
| **Dashboards**   | OpenSearch Dashboards for data visualization.                               |

---

### **Amazon EMR**

| Feature                | Description                                                                 |
| ---------------------- | --------------------------------------------------------------------------- |
| **Purpose**            | Managed Hadoop and Spark cluster service for big data processing.           |
| **Node Types**         | Master (management), Core (tasks and data storage), Task (temporary tasks). |
| **Use Cases**          | Data processing, machine learning, web indexing.                            |
| **Purchasing Options** | On-demand, reserved, or Spot Instances for cost savings.                    |

---

### **AWS Glue**

| Feature               | Description                                                                                   |
| --------------------- | --------------------------------------------------------------------------------------------- |
| **Purpose**           | Serverless ETL (Extract, Transform, Load) service.                                            |
| **Glue Data Catalog** | Centralized metadata repository used by Athena, Redshift Spectrum, EMR.                       |
| **Features**          | Glue Studio (GUI), Glue DataBrew (data cleaning), Glue Elastic Views (real-time replication). |
| **Data Conversion**   | Convert raw data into columnar formats like Parquet for analysis.                             |

---

### **Amazon QuickSight**

| Feature          | Description                                                        |
| ---------------- | ------------------------------------------------------------------ |
| **Purpose**      | BI service for creating interactive dashboards and visualizations. |
| **Features**     | Serverless, scalable, SPICE engine for in-memory computation.      |
| **Use Cases**    | Ad-hoc analysis, business insights, and data visualization.        |
| **Integrations** | RDS, Aurora, Athena, Redshift, S3, and more.                       |

---

### **AWS Lake Formation**

| Feature            | Description                                                                 |
| ------------------ | --------------------------------------------------------------------------- |
| **Purpose**        | Managed service for setting up and managing a data lake.                    |
| **Capabilities**   | Discover, cleanse, transform, and ingest data into a centralized data lake. |
| **Access Control** | Fine-grained access controls, including column-level security.              |
| **Built On**       | Leverages AWS Glue for ETL, cataloging, and schema management.              |

---

### **Amazon MSK (Managed Kafka)**

| Feature             | Description                                                                           |
| ------------------- | ------------------------------------------------------------------------------------- |
| **Purpose**         | Fully managed Apache Kafka for streaming data.                                        |
| **Capabilities**    | Create, update, delete clusters; auto-recovery, multi-AZ deployment, and EBS storage. |
| **Serverless Mode** | Automatically provisions and scales resources.                                        |

---

### **Kinesis Data Services**

| Feature           | Description                                                                        |
| ----------------- | ---------------------------------------------------------------------------------- |
| **Data Streams**  | Real-time data collection and processing.                                          |
| **Data Firehose** | Near real-time delivery to S3, Redshift, or OpenSearch.                            |
| **Analytics**     | SQL-based analytics on streaming data; supports time-series and real-time metrics. |

---

### **Big Data Ingestion Pipeline**

| Component                 | Purpose                                                        |
| ------------------------- | -------------------------------------------------------------- |
| **Kinesis Data Streams**  | Real-time data collection from IoT or other sources.           |
| **Kinesis Data Firehose** | Transforms and delivers data to S3 or Redshift.                |
| **AWS Lambda**            | Real-time data transformation and triggering downstream tasks. |
| **Amazon S3**             | Central storage for raw and processed data.                    |
| **Amazon Athena**         | Serverless SQL queries on S3 data.                             |
| **Amazon QuickSight**     | Reporting and dashboard creation from processed data.          |

---

### **Comparison: Kinesis Data Streams vs. MSK**

| Feature          | Kinesis Data Streams       | Amazon MSK                                 |
| ---------------- | -------------------------- | ------------------------------------------ |
| **Message Size** | 1 MB                       | Configurable up to 10 MB                   |
| **Scaling**      | Shard splitting/merging    | Add partitions to topics                   |
| **Encryption**   | TLS in-flight, KMS at-rest | TLS/PLAINTEXT, KMS at-rest                 |
| **Management**   | Fully serverless           | Managed Apache Kafka with granular control |
