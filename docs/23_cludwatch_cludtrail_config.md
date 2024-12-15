### **1. Amazon CloudWatch**

| **Feature**              | **Details**                                                                                                  |
| ------------------------ | ------------------------------------------------------------------------------------------------------------ |
| **Metrics**              | Tracks performance (e.g., CPUUtilization, NetworkIn). Custom metrics and dashboards available.               |
| **Metric Streams**       | Streams near-real-time metrics to Kinesis, Datadog, Splunk, etc., with filtering options.                    |
| **Logs**                 | Collects logs from services (EC2, Lambda, API Gateway, etc.). Supports encryption and expiration policies.   |
| **Logs Insights**        | Query and analyze logs with purpose-built query language. Save queries to dashboards.                        |
| **Logs Subscriptions**   | Real-time log events delivery to Kinesis, Lambda, Firehose, etc.                                             |
| **Unified Agent**        | Collects system-level metrics (CPU, RAM) and logs. Centralized config via SSM.                               |
| **Alarms**               | Triggers actions based on metric thresholds (e.g., restart EC2, notify via SNS). Composite alarms supported. |
| **Container Insights**   | Aggregates metrics and logs for ECS, EKS, Kubernetes on EC2/Fargate. Requires Kubernetes agent.              |
| **Lambda Insights**      | Provides detailed metrics for serverless applications (e.g., cold starts, CPU time).                         |
| **Contributor Insights** | Identifies top contributors from logs (e.g., top IPs, URLs causing errors).                                  |
| **Application Insights** | Automated dashboards for troubleshooting application health issues.                                          |

---

### **2. AWS CloudTrail**

| **Feature**             | **Details**                                                                               |
| ----------------------- | ----------------------------------------------------------------------------------------- |
| **Purpose**             | Governance, compliance, and auditing of AWS accounts. Tracks API calls (default enabled). |
| **Event Types**         | - **Management Events**: Changes to resources (e.g., EC2 subnet creation).                |
|                         | - **Data Events**: High-volume events (e.g., S3 object-level operations).                 |
|                         | - **Insights**: Detect unusual activities (e.g., service limit bursts).                   |
| **Retention**           | Default 90 days. Use S3 + Athena for long-term storage.                                   |
| **Integration**         | Works with Amazon S3, EventBridge (automation), and CloudWatch Logs.                      |
| **CloudTrail Insights** | Baseline analysis of management events to detect anomalies like resource overuse or gaps. |
| **Events Retention**    | Logs stored for 90 days. Use S3 for extended retention.                                   |

---

### **3. AWS Config**

| **Feature**             | **Details**                                                                                |
| ----------------------- | ------------------------------------------------------------------------------------------ |
| **Purpose**             | Auditing resource configurations and ensuring compliance.                                  |
| **Rules**               | Predefined rules (e.g., disk type validation) or custom rules via Lambda.                  |
| **Triggers**            | On config changes or regular intervals.                                                    |
| **Remediation**         | Auto-remediate issues with SSM Automation Documents (e.g., deactivating expired IAM keys). |
| **Compliance Tracking** | Monitor configurations over time for compliance.                                           |
| **Notifications**       | Integrates with EventBridge and SNS for alerts on non-compliance.                          |

---

### **4. Amazon EventBridge (formerly CloudWatch Events)**

| **Feature**         | **Details**                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------ |
| **Event Rules**     | Trigger events based on patterns or schedules (e.g., run Lambda every hour).                     |
| **Event Bus**       | Separate event processing pipelines. Allows cross-account access and event archiving for replay. |
| **Schema Registry** | Automatically infers and version-manages schemas for events.                                     |
| **Integration**     | Supports services like Lambda, Step Functions, SQS, SNS, and custom applications.                |

---

### **5. CloudWatch vs. CloudTrail vs. Config**

| **Aspect**      | **CloudWatch**                      | **CloudTrail**                 | **AWS Config**                                   |
| --------------- | ----------------------------------- | ------------------------------ | ------------------------------------------------ |
| **Purpose**     | Performance monitoring and alerting | API tracking and auditing      | Resource configuration monitoring and compliance |
| **Data Source** | Metrics, logs, events               | API calls                      | Configuration changes                            |
| **Retention**   | Varies by service                   | 90 days (default)              | Long-term with S3                                |
| **Best For**    | Operational performance insights    | Security and governance audits | Ensuring compliance with policies                |

---

### **6. Key Tools for Specific Use Cases**

| **Scenario**                       | **Service**                     | **Usage**                                                  |
| ---------------------------------- | ------------------------------- | ---------------------------------------------------------- |
| **Monitoring ELB**                 | CloudWatch                      | Monitor connection metrics, visualize error rates.         |
|                                    | AWS Config                      | Track configuration changes, enforce SSL compliance.       |
|                                    | CloudTrail                      | Audit who made changes to ELB configuration.               |
| **Serverless App Troubleshooting** | CloudWatch Lambda Insights      | Analyze cold starts, CPU, memory, and network utilization. |
| **Kubernetes Monitoring**          | CloudWatch Container Insights   | Collect and analyze metrics and logs.                      |
| **Top Network Talkers**            | CloudWatch Contributor Insights | Identify IPs and URLs causing high resource usage.         |
| **Security Compliance**            | AWS Config                      | Evaluate security group rules for unrestricted access.     |
| **Auditing API Activity**          | CloudTrail                      | Track all API calls in the account.                        |

---

### **7. Integrations and Automation**

| **Integration**              | **Description**                                                                        |
| ---------------------------- | -------------------------------------------------------------------------------------- |
| **CloudWatch + SNS/Lambda**  | Automate alerts and workflows based on metric thresholds.                              |
| **CloudTrail + EventBridge** | Trigger actions like sending alerts for specific API calls (e.g., deleting resources). |
| **AWS Config + S3 + Athena** | Long-term storage and analysis of configuration changes and compliance statuses.       |

---

### **8. Alarms and Notifications**

| **Alarm Type**        | **Details**                                                                             |
| --------------------- | --------------------------------------------------------------------------------------- |
| **Standard Alarms**   | Triggered by single metrics (e.g., CPU utilization, latency).                           |
| **Composite Alarms**  | Combine multiple alarms with AND/OR logic to reduce noise.                              |
| **CloudTrail Alerts** | Generate alerts for API events like unauthorized IAM changes or resource deletions.     |
| **AWS Config Alerts** | Notifies about non-compliant resources (e.g., public S3 buckets or missing encryption). |

---

### **9. Tips and Best Practices**

- **CloudWatch Logs Insights**:
  - Save queries for frequent analysis.
  - Use log groups effectively to organize data by application or environment.
- **CloudTrail**:

  - Enable multi-region trails for better visibility.
  - Use Insights to identify unusual patterns automatically.

- **AWS Config**:
  - Automate remediation with SSM where possible.
  - Use custom rules for specific compliance checks.
