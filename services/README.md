## Table of Contents

1. [Analytics](#1-analytics)
2. [Application Integration](#2-application-integration)
3. [AWS Cost Management](#3-aws-cost-management)
4. [Compute](#4-compute)
5. [Containers](#5-containers)
6. [Database](#6-database)
7. [Developer Tools](#7-developer-tools)
8. [Front-End Web and Mobile](#8-front-end-web-and-mobile)
9. [Machine Learning](#9-machine-learning)
10. [Management and Governance](#10-management-and-governance)
11. [Media Services](#11-media-services)
12. [Migration and Transfer](#12-migration-and-transfer)
13. [Networking and Content Delivery](#13-networking-and-content-delivery)
14. [Networking and Content Delivery](#14-networking-and-content-delivery)
15. [Security, Identity, and Compliance](#15-security-identity-and-compliance)
16. [Serverless](#16-serverless)
17. [Storage](#17-storage)

### **1. Analytics:**

| **Service Name**                                           | **Description**                                                                                                                                               |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon Athena**                                          | Serverless interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL queries.                                              |
| **AWS Data Exchange**                                      | Service for discovering, subscribing to, and using third-party data in AWS.                                                                                   |
| **AWS Data Pipeline**                                      | Web service for processing and moving data between AWS compute and storage services, as well as on-premises data sources, on a scheduled basis.               |
| **Amazon EMR**                                             | Managed cluster platform for processing large amounts of data using tools like Hadoop, Spark, and Hive.                                                       |
| **AWS Glue**                                               | Fully managed ETL service to prepare data for analytics, machine learning, and application development.                                                       |
| **Amazon Kinesis**                                         | Platform for real-time data streaming, enabling users to easily collect, process, and analyze video, audio, application logs, website clickstreams, and more. |
| **AWS Lake Formation**                                     | Service for setting up, securing, and managing a data lake for analytics, enabling faster insights and reducing management overhead.                          |
| **Amazon Managed Streaming for Apache Kafka (Amazon MSK)** | Fully managed service for Apache Kafka to handle real-time streaming data and integrate it with AWS services for analytics.                                   |
| **Amazon OpenSearch Service**                              | Managed service for deploying, operating, and scaling OpenSearch clusters for log and performance data analysis, search, and visualizations.                  |
| **Amazon QuickSight**                                      | Business intelligence (BI) service for visualizing and analyzing data to gain insights using interactive dashboards.                                          |
| **Amazon Redshift**                                        | Data warehouse service for running complex queries and analytics on large datasets with high performance.                                                     |

### **2. Application Integration:**

| **Service Name**       | **Description**                                                                                                                              |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon AppFlow**     | Managed integration service for securely transferring data between AWS services and SaaS apps like Salesforce, ServiceNow, and more.         |
| **AWS AppSync**        | Managed service to develop GraphQL APIs that allow real-time data synchronization between applications.                                      |
| **Amazon EventBridge** | Serverless event bus service for building event-driven architectures with integration to AWS and external SaaS apps.                         |
| **Amazon MQ**          | Managed message broker service that supports JMS, AMQP, and other messaging protocols, simplifying the management of message queues.         |
| **Amazon SNS**         | Fully managed messaging service for sending notifications, alerts, and messages to subscribers through multiple channels (SMS, email, etc.). |
| **Amazon SQS**         | Managed message queue service for decoupling and scaling microservices, distributed systems, and serverless applications.                    |
| **AWS Step Functions** | Orchestrates workflows for automating business processes by coordinating multiple AWS services into serverless workflows.                    |

### **3. AWS Cost Management:**

| **Service Name**              | **Description**                                                                                                       |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **AWS Budgets**               | Service to set custom cost and usage budgets, monitor and receive alerts when exceeding thresholds.                   |
| **AWS Cost and Usage Report** | Detailed report of AWS usage and costs, helping users analyze resource consumption and optimize costs.                |
| **AWS Cost Explorer**         | Tool for visualizing, understanding, and managing AWS costs and usage patterns over time.                             |
| **Savings Plans**             | Flexible pricing plans to save money on AWS services based on long-term usage commitment, offering up to 72% savings. |

### **4. Compute:**

| **Service Name**                          | **Description**                                                                                                                                  |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **AWS Batch**                             | Fully managed batch computing service for efficiently running thousands of batch computing jobs on AWS.                                          |
| **Amazon EC2**                            | Scalable compute capacity in the cloud, offering resizable compute instances for hosting applications.                                           |
| **Amazon EC2 Auto Scaling**               | Automatically adjusts the number of EC2 instances in response to demand, ensuring optimal performance and cost efficiency.                       |
| **AWS Elastic Beanstalk**                 | Platform-as-a-Service (PaaS) for deploying and managing applications in various languages, automatically handling scaling, monitoring, and more. |
| **AWS Outposts**                          | Fully managed service extending AWS infrastructure and services to on-premises environments for hybrid cloud solutions.                          |
| **AWS Serverless Application Repository** | A repository for deploying serverless applications and components with pre-built templates, for faster application deployment.                   |
| **VMware Cloud on AWS**                   | A hybrid cloud service running VMware’s software stack on AWS infrastructure, offering consistent workloads and seamless migration.              |
| **AWS Wavelength**                        | Brings AWS services to the edge of the 5G network, enabling ultra-low latency applications.                                                      |

### **5. Containers:**

| **Service Name**        | **Description**                                                                                                                              |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon ECS Anywhere** | Extends Amazon ECS to manage containers on servers outside of AWS, including on-premises or edge locations.                                  |
| **Amazon EKS Anywhere** | Runs and manages Kubernetes clusters on-premises, extending Amazon EKS’s capabilities to your on-premises infrastructure.                    |
| **Amazon EKS Distro**   | Distribution of the Kubernetes software that powers Amazon EKS, allowing users to run Kubernetes clusters on-premises or in any environment. |
| **Amazon ECR**          | Managed container registry for storing, managing, and deploying Docker container images.                                                     |
| **Amazon ECS**          | Fully managed container orchestration service for deploying Docker containers and running containerized applications on AWS.                 |
| **Amazon EKS**          | Managed Kubernetes service for deploying, scaling, and managing containerized applications using Kubernetes.                                 |

### **6. Database:**

| **Service Name**                                   | **Description**                                                                                                                                |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon Aurora**                                  | Relational database service that is compatible with MySQL and PostgreSQL, offering high performance and availability.                          |
| **Amazon Aurora Serverless**                       | On-demand, auto-scaling version of Amazon Aurora for variable database workloads.                                                              |
| **Amazon DocumentDB (with MongoDB compatibility)** | Managed NoSQL database compatible with MongoDB, offering scalability and performance for document-based applications.                          |
| **Amazon DynamoDB**                                | Managed NoSQL database service for low-latency, high-throughput applications.                                                                  |
| **Amazon ElastiCache**                             | In-memory caching service that enhances the performance of databases and applications by reducing latency.                                     |
| **Amazon Keyspaces (for Apache Cassandra)**        | Managed Cassandra-compatible database for scalable and highly available data storage.                                                          |
| **Amazon Neptune**                                 | Managed graph database service for building and running applications that work with highly connected data.                                     |
| **Amazon QLDB**                                    | Managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log for tracking changes in data. |
| **Amazon RDS**                                     | Managed relational database service supporting various database engines, including MySQL, PostgreSQL, SQL Server, and more.                    |
| **Amazon Redshift**                                | Fully managed data warehouse service for running complex queries on large datasets with high performance.                                      |

### **7. Developer Tools:**

| **Service Name** | **Description**                                                                                                                                          |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **AWS X-Ray**    | Service for debugging and analyzing distributed applications, identifying performance bottlenecks and troubleshooting issues in production environments. |

### **8. Front-End Web and Mobile:**

| **Service Name**       | **Description**                                                                                                                           |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **AWS Amplify**        | Full-stack development platform for building web and mobile applications with built-in hosting, authentication, and serverless functions. |
| **Amazon API Gateway** | Fully managed service for creating and managing RESTful APIs for your applications, supporting WebSocket and HTTP protocols.              |
| **AWS Device Farm**    | App testing service on real devices to ensure app compatibility across multiple device types, operating systems, and browsers.            |
| **Amazon Pinpoint**    | Marketing analytics and engagement service for targeted messaging, including email, SMS, and push notifications to users.                 |

### **9. Machine Learning:**

| **Service Name**          | **Description**                                                                                                                           |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon Comprehend**     | Natural language processing (NLP) service for extracting insights from text, including sentiment analysis and entity recognition.         |
| **Amazon Forecast**       | Time series forecasting service that uses machine learning to deliver accurate predictions for demand planning, resource allocation, etc. |
| **Amazon Fraud Detector** | Managed machine learning service for detecting fraudulent activities in transactions, identity verification, and other use cases.         |
| **Amazon Kendra**         | AI-powered enterprise search service that delivers precise and relevant search results from vast amounts of unstructured data.            |
| **Amazon Lex**            | Service for building conversational interfaces using voice and text, enabling the creation of chatbots and virtual assistants.            |
| **Amazon Polly**          | Text-to-speech service that turns text into lifelike speech, with support for multiple languages and voices.                              |
| **Amazon Rekognition**    | Image and video analysis service that can identify objects, people, text, and scenes in images or videos using deep learning.             |
| **Amazon SageMaker**      | Comprehensive platform for building, training, and deploying machine learning models at scale.                                            |
| **Amazon Textract**       | Service for extracting text, forms, and tables from scanned documents without requiring any manual effort.                                |
| **Amazon Transcribe**     | Automatic speech recognition (ASR) service for converting speech to text in real time or from audio files.                                |
| **Amazon Translate**      | Neural machine translation service for dynamically translating text between languages.                                                    |

### **10. Management and Governance:**

| **Service Name**                          | **Description**                                                                                                                                            |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **AWS Auto Scaling**                      | Service for automatically adjusting the number of Amazon EC2 instances, DynamoDB tables, and other AWS resources based on demand.                          |
| **AWS CloudFormation**                    | Service for creating and managing AWS resources using templates, enabling users to automate infrastructure provisioning.                                   |
| **AWS CloudTrail**                        | Enables governance, compliance, and auditing by logging AWS account activity, providing visibility into API calls made on AWS.                             |
| **Amazon CloudWatch**                     | Monitoring service for collecting and tracking metrics, log files, and setting alarms to react to changes in resources and applications.                   |
| **AWS Command Line Interface (CLI)**      | Command-line tool to manage AWS services and resources through scripting and automation.                                                                   |
| **AWS Compute Optimizer**                 | Service for recommending optimal Amazon EC2 instance types based on your usage patterns to save costs while maintaining performance.                       |
| **AWS Config**                            | Service for tracking AWS resource configurations and changes, allowing users to assess compliance and manage configurations across resources.              |
| **AWS Control Tower**                     | Service for setting up and governing multi-account AWS environments with best practices for security, compliance, and resource management.                 |
| **AWS Health Dashboard**                  | Personalized dashboard providing visibility into the status and health of AWS services and resources, including outages and maintenance schedules.         |
| **AWS License Manager**                   | Service for managing licenses across AWS and on-premises environments, allowing organizations to track, manage, and control their software licenses.       |
| **Amazon Managed Grafana**                | Fully managed service for visualizing and analyzing operational metrics from multiple sources using Grafana.                                               |
| **Amazon Managed Service for Prometheus** | Managed service for monitoring and alerting on containerized applications using Prometheus, integrated with other AWS monitoring tools.                    |
| **AWS Management Console**                | Web interface for managing AWS services and resources.                                                                                                     |
| **AWS Organizations**                     | Service for managing multiple AWS accounts, providing consolidated billing and enabling organization-wide governance and resource sharing.                 |
| **AWS Proton**                            | Service for deploying and managing infrastructure as code, allowing developers to provision application stacks and environments.                           |
| **AWS Service Catalog**                   | Service for creating and managing catalogs of IT services and products, helping organizations to control and manage the AWS resources their teams can use. |
| **AWS Systems Manager**                   | Suite of services for operational tasks like patch management, inventory, and automation across AWS and on-premises resources.                             |
| **AWS Trusted Advisor**                   | Real-time recommendations for optimizing AWS infrastructure, improving security, and reducing costs based on best practices.                               |
| **AWS Well-Architected Tool**             | Helps review workloads against AWS best practices to improve security, reliability, performance efficiency, and cost optimization.                         |

### **11. Media Services:**

| **Service Name**                 | **Description**                                                                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Amazon Elastic Transcoder**    | Cloud-based service for transcoding video files into various formats, optimizing them for playback on different devices. |
| **Amazon Kinesis Video Streams** | Service for streaming video data to AWS for real-time processing, storage, and analytics.                                |

### **12. Migration and Transfer:**

| **Service Name**                             | **Description**                                                                                                                                        |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **AWS Application Discovery Service**        | Helps plan migration projects by identifying and understanding on-premises workloads and their dependencies.                                           |
| **AWS Application Migration Service**        | Simplifies the process of migrating workloads to AWS by automating the lift-and-shift process with minimal downtime.                                   |
| **AWS Database Migration Service (AWS DMS)** | Service for migrating databases to AWS with minimal downtime, supporting multiple source and target databases.                                         |
| **AWS DataSync**                             | Service for transferring large amounts of data between on-premises storage and AWS with high speed and security.                                       |
| **AWS Migration Hub**                        | Centralized location for tracking the progress of migrations across multiple AWS services and tools.                                                   |
| **AWS Snow Family**                          | Family of services (Snowcone, Snowball, Snowmobile) for physically transferring large datasets to AWS, even in environments with limited connectivity. |
| **AWS Transfer Family**                      | Managed service for transferring files securely over SFTP, FTP, and FTPS into and out of Amazon S3.                                                    |

### **13. Networking and Content Delivery:**

| **Service Name**                 | **Description**                                                                                                                              |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **AWS Client VPN**               | Securely connects users to AWS and on-premises resources through a managed VPN.                                                              |
| **Amazon CloudFront**            | Content delivery network (CDN) that delivers websites, APIs, and media to users globally with low latency.                                   |
| **AWS Direct Connect**           | Provides a dedicated network connection between on-premises data centers and AWS for more reliable, faster connectivity.                     |
| **Elastic Load Balancing (ELB)** | Service for distributing incoming application traffic across multiple targets (EC2 instances, containers, etc.) to ensure high availability. |
| **AWS Global Accelerator**       | Service for improving the availability and performance of global applications, directing users to the nearest AWS edge location.             |
| **AWS PrivateLink**              | Private connectivity to services across VPCs, reducing the need for public IPs and improving security.                                       |
| **Amazon Route 53**              | Scalable DNS service for routing end-user requests to AWS resources and managing domain names.                                               |
| **AWS Site-to-Site VPN**         | Service for securely connecting on-premises networks to AWS over an encrypted VPN connection.                                                |
| **AWS Transit Gateway**          | Centralized hub for connecting multiple VPCs, on-premises networks, and VPNs, simplifying network architecture.                              |
| **Amazon VPC**                   | Service for provisioning isolated networks within AWS and controlling resource access securely.                                              |

### **14. Networking and Content Delivery:**

| **Service Name**                 | **Description**                                                                                                                                 |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Amazon CloudFront**            | Content delivery network (CDN) that delivers websites, APIs, and videos with low latency and high transfer speeds.                              |
| **AWS Direct Connect**           | Private dedicated network connection from on-premises environments to AWS for secure, reliable data transfer.                                   |
| **Elastic Load Balancing (ELB)** | Automatically distributes incoming traffic across multiple targets, like Amazon EC2 instances, to ensure high availability and fault tolerance. |
| **AWS Global Accelerator**       | Service that improves the performance and availability of applications by directing traffic through the nearest AWS edge location.              |
| **AWS PrivateLink**              | Service that provides private connectivity between VPCs and AWS services without exposing traffic to the public internet.                       |
| **Amazon Route 53**              | Scalable Domain Name System (DNS) web service that routes user requests to endpoints and ensures high availability.                             |
| **AWS Site-to-Site VPN**         | Securely connects on-premises networks to AWS VPCs via an encrypted VPN tunnel.                                                                 |
| **AWS Transit Gateway**          | Central hub to connect VPCs and on-premises networks, simplifying network architecture.                                                         |
| **Amazon VPC**                   | Virtual Private Cloud that allows you to create isolated networks within AWS, providing control over network configurations and security.       |

### **15. Security, Identity, and Compliance:**

| **Service Name**                                 | **Description**                                                                                                                                  |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **AWS Artifact**                                 | Provides access to AWS compliance reports and agreements, enabling customers to manage compliance requirements.                                  |
| **AWS Audit Manager**                            | Service to automate the collection and management of audit evidence for compliance and auditing.                                                 |
| **AWS Certificate Manager (ACM)**                | Manages SSL/TLS certificates for securing websites, applications, and network traffic.                                                           |
| **AWS CloudHSM**                                 | Hardware security module service that enables you to generate and use your own encryption keys for securing sensitive data.                      |
| **Amazon Cognito**                               | Provides user authentication, authorization, and user management for web and mobile apps.                                                        |
| **Amazon Detective**                             | Service that helps you investigate security issues by analyzing and visualizing AWS resource activity to identify the root cause.                |
| **AWS Directory Service**                        | Managed Microsoft Active Directory (AD) service for integrating AWS workloads with your existing AD or creating a new cloud-based directory.     |
| **AWS Firewall Manager**                         | Centralized security management service that simplifies configuring and managing AWS WAF, AWS Shield, and VPC security across multiple accounts. |
| **Amazon GuardDuty**                             | Threat detection service that continuously monitors for malicious or unauthorized activity across AWS environments.                              |
| **AWS IAM Identity Center (AWS Single Sign-On)** | Manages access across AWS accounts and applications with single sign-on (SSO).                                                                   |
| **AWS Identity and Access Management (IAM)**     | Service for securely controlling access to AWS resources through fine-grained permissions and roles.                                             |
| **Amazon Inspector**                             | Automated security assessment service to identify vulnerabilities and compliance violations in your AWS resources.                               |
| **AWS Key Management Service (KMS)**             | Managed service for creating and controlling encryption keys to secure data.                                                                     |
| **Amazon Macie**                                 | Security service that uses machine learning to automatically discover, classify, and protect sensitive data like personal information.           |
| **AWS Network Firewall**                         | Managed firewall service that protects your VPCs from threats by filtering traffic.                                                              |
| **AWS Resource Access Manager (RAM)**            | Service that enables resource sharing between AWS accounts within an organization.                                                               |
| **AWS Secrets Manager**                          | Service for securely storing and managing sensitive information such as passwords, API keys, and database credentials.                           |
| **AWS Security Hub**                             | Centralized security and compliance service that aggregates, organizes, and prioritizes findings from various AWS security services.             |
| **AWS Shield**                                   | Managed DDoS protection service that safeguards applications from volumetric, state-exhaustion, and small-scale application layer attacks.       |
| **AWS WAF**                                      | Web application firewall service that protects applications from common web exploits and traffic filtering.                                      |

### **16. Serverless:**

| **Service Name** | **Description**                                                                                                        |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **AWS AppSync**  | Service for building real-time, scalable applications with GraphQL, simplifying data retrieval and synchronization.    |
| **AWS Fargate**  | Serverless compute engine for containers that lets you run containers without managing the underlying infrastructure.  |
| **AWS Lambda**   | Serverless compute service that allows you to run code in response to events without provisioning or managing servers. |

### **17. Storage:**

| **Service Name**                     | **Description**                                                                                                                                    |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **AWS Backup**                       | Centralized backup service that automates and manages backups for AWS resources.                                                                   |
| **Amazon Elastic Block Store (EBS)** | Persistent block storage for Amazon EC2 instances that provides low-latency and high-performance data access.                                      |
| **Amazon Elastic File System (EFS)** | Fully managed file storage that can be mounted across multiple EC2 instances for scalable and shared storage.                                      |
| **Amazon FSx**                       | Managed Windows and Lustre file systems that provide scalable storage for high-performance computing and Windows workloads.                        |
| **Amazon S3**                        | Object storage service that provides highly scalable, durable, and low-latency storage for any type of data.                                       |
| **Amazon S3 Glacier**                | Low-cost archive storage service for long-term data retention with retrieval times ranging from minutes to hours.                                  |
| **AWS Storage Gateway**              | Hybrid cloud storage service that enables on-premises environments to connect with AWS cloud storage for backup, archiving, and disaster recovery. |
