| **Topic**                        | **Details**                                                                                                    |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Disaster Recovery (DR)**       | - **Definition**: Preparing for and recovering from disasters.                                                 |
|                                  | - **Types**:                                                                                                   |
|                                  | - On-premise → On-premise (traditional, expensive).                                                            |
|                                  | - On-premise → AWS Cloud (hybrid recovery).                                                                    |
|                                  | - AWS Region A → Region B (cloud-based DR).                                                                    |
| **Key Metrics**                  | - **RPO**: Recovery Point Objective (acceptable data loss).                                                    |
|                                  | - **RTO**: Recovery Time Objective (acceptable downtime).                                                      |
| **Disaster Recovery Strategies** | - **Backup & Restore**: High RPO, uses S3, Glacier, Snapshots.                                                 |
|                                  | - **Pilot Light**: Core app components pre-deployed in AWS.                                                    |
|                                  | - **Warm Standby**: Full system at minimal scale, scales up during disaster.                                   |
|                                  | - **Hot Site**: Active-active setup, high cost, minimal RTO.                                                   |
| **High Availability**            | - Use Multi-AZ for databases (RDS, ElastiCache, EFS).                                                          |
|                                  | - Route 53 for DNS failover.                                                                                   |
|                                  | - Site-to-Site VPN as a backup for Direct Connect.                                                             |
| **AWS Backup**                   | - Fully managed, supports: EC2, EBS, S3, RDS, Aurora, FSx, DynamoDB, etc.                                      |
|                                  | - Features: PITR, cross-region, cross-account backups.                                                         |
|                                  | - **Backup Vault Lock**: WORM (Write Once, Read Many) to prevent deletions.                                    |
|                                  | - Backup Plan: Scheduled, retention periods, transition to cold storage.                                       |
| **Migration Services**           | - **DMS**: Migrates databases; supports both homogeneous (e.g., Oracle → Oracle) and heterogeneous migrations. |
|                                  | - **SCT**: Converts schemas (e.g., Oracle to PostgreSQL).                                                      |
|                                  | - **Application Migration Service**: Lift-and-shift (rehosting).                                               |
|                                  | - **Application Discovery Service**: Maps dependencies for migration planning.                                 |
| **RDS/Aurora Migrations**        | - **MySQL**: Use snapshots, Aurora Read Replica, or DMS for migration.                                         |
|                                  | - **PostgreSQL**: Import backups using AWS S3 or Aurora extensions.                                            |
|                                  | - Both support DMS for live migrations.                                                                        |
| **VMware Cloud on AWS**          | - Extend VMware workloads to AWS while maintaining VMware tools.                                               |
|                                  | - Use cases: Disaster recovery, hybrid setups, workload migration.                                             |
| **Data Transfer Options**        | - **Internet/VPN**: Slow for large volumes (e.g., 200 TB).                                                     |
|                                  | - **Direct Connect**: Faster but has setup overhead.                                                           |
|                                  | - **Snowball**: Best for bulk data, supports parallel transfers.                                               |
|                                  | - **Ongoing transfers**: Use DataSync, DMS, or VPN for replication.                                            |
| **Automation & Tools**           | - **CloudFormation**: Recreate entire environments.                                                            |
|                                  | - **AWS Lambda**: Custom automations.                                                                          |
|                                  | - **Elastic Beanstalk**: Simplifies app deployment and scaling.                                                |
| **Database Replication**         | - Cross-region replication: RDS, Aurora Global Databases.                                                      |
|                                  | - Storage Gateway for on-premise to AWS storage.                                                               |
| **Chaos Engineering**            | - Simian Army (Netflix): Test systems by random failures.                                                      |
