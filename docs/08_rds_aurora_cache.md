
### **AWS RDS (Relational Database Service)**

| **Feature**              | **Details**                                                                                 |
|--------------------------|---------------------------------------------------------------------------------------------|
| **Supported Databases**   | PostgreSQL, MySQL, MariaDB, Oracle, MS SQL Server, IBM DB2, Aurora                          |
| **Advantages**            | Managed service, auto-provisioning, patching, backups, scaling (vertical & horizontal), DR (Multi-AZ) |
| **Storage Auto Scaling**  | Scales DB storage when free storage is low, requires setting max threshold                  |
| **Read Replicas**         | Up to 15 replicas, async replication (eventual consistency), used for read-heavy workloads   |
| **Multi-AZ for DR**       | Automatic failover, synchronous replication, increases availability                         |
| **Backups**               | Automated (1-35 days), manual snapshots, point-in-time restore, transaction logs every 5 mins |

---

### **AWS Aurora**

| **Feature**              | **Details**                                                                                 |
|--------------------------|---------------------------------------------------------------------------------------------|
| **Supported Engines**     | MySQL, PostgreSQL (Aurora MySQL and Aurora PostgreSQL)                                       |
| **Performance**           | 5x faster than MySQL, 3x faster than PostgreSQL on RDS                                       |
| **Storage**               | Auto-scales from 10GB to 128TB, self-healing, high availability                             |
| **Read Scaling**          | Up to 15 read replicas, automatic failover in < 30 seconds                                  |
| **Aurora Serverless**     | Auto-scaling, pay-per-second billing, cost-effective for unpredictable workloads             |
| **Global Database**       | Cross-region replication, <1 sec replication lag, RTO < 1 minute                           |
| **Backups & Cloning**     | Automated backups (1–35 days), point-in-time restore, cloning (fast, efficient)             |
| **Machine Learning**      | Integrates with SageMaker and Comprehend for predictions, fraud detection, etc.              |

---

### **AWS ElastiCache**

| **Feature**              | **Details**                                                                                 |
|--------------------------|---------------------------------------------------------------------------------------------|
| **Supported Engines**     | Redis, Memcached                                                                            |
| **Use Case**              | Caching for high-performance applications, reduces DB load                                 |
| **Caching Patterns**      | Lazy Loading (stale data), Write Through (no stale data), Session Store (user sessions)     |
| **Redis Features**        | Multi-AZ, read replicas, persistence, backup, supports advanced data types (Sorted Sets)    |
| **Memcached Features**    | Multi-node (sharding), non-persistent, simple use cases, no built-in HA                     |
| **Security**              | Redis: IAM Authentication, SSL; Memcached: SASL-based authentication                       |

---

### **Key Differences Between RDS and Aurora**

| **Aspect**               | **RDS**                                                     | **Aurora**                                            |
|--------------------------|-------------------------------------------------------------|------------------------------------------------------|
| **Performance**           | Standard performance                                       | 5x better than MySQL, 3x better than PostgreSQL      |
| **Storage**               | Scales with EBS                                            | Auto-scales (10GB to 128TB), self-healing            |
| **Availability**          | Multi-AZ setup for DR                                      | Built-in high availability with fast failover (< 30s)|
| **Replication**           | Async replication (Read Replicas)                           | Multi-AZ, fast replication, up to 15 replicas        |
| **Cost**                  | Less expensive, but less optimized than Aurora             | More expensive, but more efficient and performant    |

---

### **Security Features (RDS & Aurora)**

| **Feature**              | **Details**                                                                                 |
|--------------------------|---------------------------------------------------------------------------------------------|
| **Encryption (At-rest)**  | KMS encryption for both master DB and replicas                                                 |
| **Encryption (In-transit)**| TLS encryption, secure connections by default                                                |
| **IAM Authentication**    | Use IAM roles instead of passwords for DB access                                              |
| **Audit Logs**            | Enable logs for auditing, stored in CloudWatch Logs                                          |
