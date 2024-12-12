### **EBS, Instance Store, and EFS Cheat Sheet**

---

#### **EC2 Instance Store**

| **Feature**                 | **Details**                                                                                      |
|-----------------------------|--------------------------------------------------------------------------------------------------|
| **Type**                    | Temporary storage directly attached to EC2 instance hardware.                                    |
| **Performance**             | High IOPS for low-latency operations.                                                           |
| **Persistence**             | Data is ephemeral; lost upon instance stop/termination.                                         |
| **Use Cases**               | Cache, buffer, temporary files.                                                                 |

---

#### **Amazon EBS (Elastic Block Store)**

| **Feature**                 | **Details**                                                                                      |
|-----------------------------|--------------------------------------------------------------------------------------------------|
| **Type**                    | Network drive for persistent storage.                                                           |
| **Attached To**             | One EC2 instance at a time (Multi-Attach allowed for `io1/io2`).                                |
| **Bound To**                | Specific Availability Zone (AZ); requires snapshots to migrate.                                |
| **Data Persistence**        | Retains data even after instance termination (unless Delete-on-Termination is enabled).          |
| **Volume Types**            | General Purpose SSD (`gp2`, `gp3`), Provisioned IOPS SSD (`io1`, `io2`), Throughput Optimized HDD (`st1`), Cold HDD (`sc1`). |
| **Encryption**              | Supports encryption (AES-256 via KMS) for data at rest, in transit, and snapshots.              |
| **Snapshot Features**       | Backup at a point in time, Snapshot Archive (75% cost reduction), Recycle Bin for deleted snapshots. |

---

#### **EBS Volume Types**

| **Volume Type**              | **Use Cases**                                                  | **Max IOPS/Throughput**                      |
|------------------------------|---------------------------------------------------------------|---------------------------------------------|
| **gp2** (General SSD)        | Balanced workloads, boot volumes.                             | Up to 16,000 IOPS.                          |
| **gp3** (Enhanced SSD)       | High-performance SSD with customizable IOPS/throughput.       | Up to 16,000 IOPS, 1,000 MB/s throughput.   |
| **io1/io2 (PIOPS SSD)**      | Critical workloads needing sustained high IOPS (databases).   | io1: 64,000; io2 Block Express: 256,000.    |
| **st1 (HDD)**                | Throughput-intensive workloads (big data, logs).              | 500 MB/s throughput.                        |
| **sc1 (HDD)**                | Infrequently accessed workloads, lowest cost.                 | 250 MB/s throughput.                        |

---

#### **Amazon EFS (Elastic File System)**

| **Feature**                 | **Details**                                                                                      |
|-----------------------------|--------------------------------------------------------------------------------------------------|
| **Type**                    | Managed Network File System (NFS) for Linux-based workloads.                                    |
| **Multi-AZ Support**        | Accessible across multiple AZs; mountable on 100s of instances.                                |
| **Use Cases**               | Content management, web hosting, data sharing (e.g., WordPress).                                |
| **Storage Classes**         | Standard (frequently accessed), IA (Infrequent Access), Archive (rarely accessed).               |
| **Throughput Modes**        | Bursting (default), Provisioned (fixed), Elastic (auto-scales).                                 |
| **File System Type**        | POSIX-compliant; supports NFSv4.1.                                                              |
| **Encryption**              | Supports encryption at rest using KMS.                                                         |

---

#### **EBS vs EFS vs Instance Store**

| **Aspect**         | **EBS**                                | **EFS**                                | **Instance Store**                        |
|--------------------|----------------------------------------|----------------------------------------|------------------------------------------|
| **Type**           | Block Storage.                        | File Storage (shared).                 | Ephemeral Disk Storage.                  |
| **Attached To**    | One instance (Multi-Attach for `io2`). | 100s of instances across AZs.          | One instance.                            |
| **Persistence**    | Persistent.                           | Persistent.                            | Temporary; lost when stopped.            |
| **Use Cases**      | Databases, boot volumes.              | Shared website files, CMS, NFS.        | Cache, buffer, temporary data.           |
| **Cost**           | Lower than EFS.                       | Higher; supports lifecycle tiers.      | Included in EC2 pricing.                 |

---
