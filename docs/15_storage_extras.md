### **AWS Storage Services**

#### **1. Snow Family (Offline data transfer)**
| **Service**          | **Description**                                                                 | **Capacity**               | **Use Case**                                                                                   |
|-----------------------|---------------------------------------------------------------------------------|----------------------------|-----------------------------------------------------------------------------------------------|
| **Snowcone**          | Small, portable edge computing device.                                          | 8 TB HDD / 14 TB SSD       | Data collection at remote locations with limited connectivity.                                |
| **Snowball Edge**     | Large, rugged device for edge computing and data migration.                     | 80–210 TB                  | Petabyte-scale data migration or edge computing in remote locations.                          |
| **Snowmobile**        | Massive-scale data transfer (truck-sized).                                      | Up to 100 PB               | Large-scale migrations like data center shutdowns.                                            |

---

#### **2. Amazon FSx**
Amazon FSx is a fully managed service for launching third-party file systems on AWS. Each FSx type is optimized for specific workloads.

| **FSx Type**              | **Purpose**                                             | **Use Case**                                             | **Key Features**                                                                 |
|---------------------------|---------------------------------------------------------|---------------------------------------------------------|----------------------------------------------------------------------------------|
| **FSx for Windows**        | Fully managed Windows file system.                     | Home directories, CMS, Active Directory integration.     | SMB protocol, NTFS, user quotas, daily backups to S3, multi-AZ availability.    |
| **FSx for Lustre**         | Parallel distributed file system for HPC.              | Machine learning, video rendering, financial modeling.   | Seamless S3 integration, low latency, SSD or HDD storage.                       |
| **FSx for NetApp ONTAP**   | Managed NetApp ONTAP file system.                      | Enterprise storage, VMware, database backups.            | NFS, SMB, iSCSI support, snapshots, data compression, and deduplication.        |
| **FSx for OpenZFS**        | Managed ZFS file system.                               | POSIX-compliant workloads, Linux environments.           | Snapshots, <0.5 ms latency, high performance.                                   |

---

#### **3. AWS Storage Gateway**
AWS Storage Gateway bridges on-premises data with cloud storage, enabling seamless integration between local environments and AWS.
| **Gateway Type**       | **Description**                                                                 | **Protocol**         | **Use Case**                                                                 |
|------------------------|---------------------------------------------------------------------------------|----------------------|------------------------------------------------------------------------------|
| **File Gateway**       | Provides NFS/SMB access to S3.                                                  | NFS, SMB             | Backup and archiving, S3 file storage for on-premises apps.                  |
| **Volume Gateway**     | Provides iSCSI access backed by S3, snapshots stored in EBS.                    | iSCSI                | Low-latency access to frequently used data, disaster recovery.               |
| **Tape Gateway**       | Virtual tape library (VTL) backed by S3 and Glacier.                            | iSCSI                | Replace physical tapes for backup and archiving.                             |

---

#### **4. AWS DataSync**
| **Feature**            | **Description**                                                                 | **Use Case**                                                                 |
|------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| **Purpose**            | Synchronize data between on-premises storage (NFS, SMB) and AWS (S3, EFS, FSx). | Migrate large datasets, keep data in sync, or schedule replication tasks.    |
| **Transfer Speed**     | Up to 10 Gbps with bandwidth throttling.                                        | Fast, secure, automated transfers.                                           |
| **Preserves Metadata** | File permissions, timestamps, etc.                                              | Maintain file integrity during migration.                                    |

---

#### **5. AWS Transfer Family**
| **Protocol**           | **Description**                                                                 | **Use Case**                                                                 |
|------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| **SFTP/FTPS/FTP**      | Managed file transfers to/from S3 or EFS.                                        | Secure file sharing, ERP, CRM, or third-party integrations.                  |
| **Features**           | Integrates with Active Directory, IAM, or custom authentication.                 | Multi-AZ, scalable, and cost-efficient.                                      |

---

#### **6. Comparison of Major Storage Options**
| **Service**            | **Type**           | **Use Case**                                                                 | **Key Features**                                                              |
|------------------------|--------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| **S3**                | Object Storage     | Scalable storage for static data, backups, and archiving.                   | Lifecycle management, intelligent tiering, global availability.              |
| **EBS**               | Block Storage      | Persistent storage for EC2 instances.                                       | High IOPS, SSD/HDD options, AZ-specific.                                      |
| **EFS**               | File Storage       | Shared storage for Linux instances (POSIX-compliant).                       | Scalable, multi-AZ, supports bursting.                                        |
| **FSx**               | File Storage       | High-performance specialized workloads.                                     | Fully managed third-party file systems.                                       |
| **Instance Store**    | Local Disk         | Ephemeral storage for temporary data or caching.                            | High throughput, only valid during instance lifecycle.                        |
