
### **AWS Global Infrastructure**  
#### 1. **Components**:  
   - **Regions**: Geographically isolated clusters of data centers.  
   - **Availability Zones (AZs)**: 3-6 AZs per region; fault-isolated but interconnected. Deliver compute and storage closer to end-users.  
   - **Edge Locations**: Over 400 globally, ensure low-latency content delivery.  

#### **Edge Locations vs. Availability Zones (AZs)**

| **Aspect**                  | **Edge Locations**                                                    | **Availability Zones (AZs)**                                     |
|-----------------------------|----------------------------------------------------------------------|-----------------------------------------------------------------|
| **Definition**              | Data centers used for **content delivery** and **caching**.          | Isolated data centers within an AWS **Region**.                |
| **Purpose**                 | Optimize **content delivery** and reduce latency for end-users.      | Provide **high availability** and **fault tolerance** for applications. |
| **Key Services**            | **Amazon CloudFront**, AWS Global Accelerator, Route 53.             | **EC2**, RDS, Lambda, S3, and other compute/storage services.  |
| **Scope**                   | **Global**: Located in 90+ cities across 40+ countries.              | **Regional**: Each AWS Region has multiple AZs (min 3).         |
| **Redundancy**              | Multiple Edge Locations in proximity for redundancy.                 | Redundant power, cooling, and networking in each AZ.           |
| **Networking**              | Ultra-low-latency connections for content delivery.                  | High-bandwidth, low-latency connections between AZs in a Region. |
| **Use Cases**               | Static content delivery, CDN caching, DNS routing.                  | Hosting databases, compute instances, multi-AZ architectures.  |
| **Examples**                | Edge Locations in cities (e.g., New York, Tokyo).                   | AZs in Regions (e.g., `us-east-1a`, `eu-west-1b`).             |
| **Disaster Isolation**      | Not disaster-isolated (primarily for caching).                       | Designed to handle failures independently.                     |

---

1. **Edge Locations** are primarily for **end-user latency improvements** (e.g., serving cached data via CloudFront).  
2. **Availability Zones (AZs)** are designed for application hosting with **fault-tolerant architectures** using multi-AZ deployments.  
3. For **disaster recovery**, focus on multi-AZ setups within a region, while Edge Locations serve non-critical cached content.

---

### **Choosing an AWS Region**  
1. Factors:  
   - **Compliance**: Data sovereignty and legal requirements.  
   - **Proximity**: Reduces latency.  
   - **Services**: New features roll out regionally.  
   - **Pricing**: Region-specific differences (e.g., us-east-1 is often cheapest).  
2. **Best Practice**: Use the **AWS Pricing Calculator** for cost planning.

---

### 1. **Region-Specific Services**:  
   - **EC2**: Compute (IaaS).  
   - **Elastic Beanstalk**: Managed PaaS.  
   - **Lambda**: Event-driven serverless compute (FaaS).  
   - **Rekognition**: AI/ML-powered image recognition.

### 2. **Global Services**:
#### **1. Identity and Security**  
- **Identity and Access Management (IAM)**:  
  Manage users, groups, roles, and policies globally.  
- **AWS Organizations**:  
  Manage multiple accounts and enforce policies at an organizational level.  
- **AWS Artifact**:  
  Access compliance reports and security-related documentation.  
- **AWS Trusted Advisor**:  
  Provides recommendations for security, performance, and cost efficiency.

---

#### **2. Networking and Content Delivery**  
- **Route 53**:  
  Domain Name System (DNS) service for global traffic routing and domain registration.  
- **CloudFront**:  
  Content Delivery Network (CDN) for low-latency delivery using global Edge Locations.  
- **AWS Global Accelerator**:  
  Improves the availability and performance of applications using AWS global network.

---

#### **3. Management and Governance**  
- **AWS Management Console**:  
  Unified global interface for accessing and managing AWS resources.  
- **AWS CloudFormation StackSets**:  
  Deploy CloudFormation templates across multiple AWS accounts and regions.  
- **AWS Control Tower**:  
  Set up and govern a secure multi-account AWS environment globally.  
- **AWS License Manager**:  
  Manage software licenses globally across AWS environments.  
- **AWS Service Catalog**:  
  Centralized management of approved IT service offerings globally.  

---

#### **4. Monitoring and Operations**  
- **AWS CloudTrail**:  
  Tracks user and API activity globally.  
- **AWS Config**:  
  Monitors resource configurations globally for compliance.  
- **AWS Health Dashboard**:  
  Centralized view of AWS service health status.  

---

#### **5. Developer and DevOps**  
- **AWS CodeArtifact**:  
  Centralized management of software package dependencies.  
- **AWS CodeStar**:  
  Manages development projects globally.  

---

#### **6. Analytics**  
- **Amazon QuickSight**:  
  BI tool accessible globally.  

---

#### **7. Support and Compliance**  
- **AWS Support Plans**:  
  Provide global technical support for accounts.  
- **AWS Abuse**:  
  Globally handles reports of abuse related to AWS resources.  