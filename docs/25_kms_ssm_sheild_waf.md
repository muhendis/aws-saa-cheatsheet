### **AWS Security and Encryption Overview**

| **Topic**                            | **Key Details**                                                                                                                  |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **Encryption**                       | - **In-flight**: TLS/SSL encrypts data during transfer. Prevents MITM attacks. Uses HTTPS (TLS certificates).                    |
|                                      | - **At-rest**: Data stored encrypted on the server; keys are managed securely.                                                   |
|                                      | - **Client-side**: Data encrypted by the client; server cannot decrypt. Envelope encryption is used.                             |
| **AWS Key Management Service (KMS)** | - Centralized key management for encryption. Fully integrates with AWS services (S3, EBS, etc.).                                 |
|                                      | - Key Types: Symmetric (AES-256) and Asymmetric (RSA/ECC). Multi-Region Keys enable cross-region operations.                     |
|                                      | - Cost: AWS Managed Keys are free; Customer-Managed Keys are $1/month.                                                           |
| **SSM Parameter Store**              | - Secure storage for configurations and secrets. Encrypts data with KMS. Tracks versions.                                        |
|                                      | - Tiers: Standard (10,000 params, free) and Advanced (100,000 params, $0.05/month).                                              |
| **Secrets Manager**                  | - Stores secrets (e.g., database passwords). Automates rotation with Lambda. Supports replication for multi-region applications. |

---

### **Networking and Resiliency**

| **Topic**            | **Key Details**                                                                                                                         |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **DDoS Protection**  | - AWS Shield Standard: Free protection for Layer 3/4 attacks. Shield Advanced: $3k/month for sophisticated attacks and WAF integration. |
| **Best Practices**   | - Use CloudFront, Route 53, and Global Accelerator for edge protection.                                                                 |
|                      | - Elastic Load Balancer (ELB) distributes traffic; Auto Scaling handles traffic spikes.                                                 |
| **AWS WAF**          | - Web ACLs filter traffic by IP, headers, geo-location, and size. Protects against SQL injection and XSS.                               |
|                      | - Supports rate-based rules for DDoS mitigation.                                                                                        |
| **Firewall Manager** | - Centralized management of WAF, Shield, and security policies for AWS Organizations.                                                   |
| **Amazon GuardDuty** | - Detects threats using ML and VPC/DNS logs. Can identify anomalies and unauthorized deployments.                                       |

---

### **Data Replication and Key Policies**

| **Topic**            | **Key Details**                                                                                                    |
| -------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **S3 Replication**   | - Default replicates unencrypted objects and SSE-S3 encrypted objects. SSE-KMS requires permissions and IAM roles. |
| **Snapshot Sharing** | - Across accounts: Requires Customer-Managed Keys with specific IAM policies.                                      |
|                      | - Across regions: Re-encrypts data with keys in the target region.                                                 |

---

### **Certificate Management and API Gateways**

| **Topic**                         | **Key Details**                                                                                                            |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **AWS Certificate Manager (ACM)** | - Manages TLS certificates for HTTPS. Integrates with CloudFront, ALB, and API Gateway. Free for public certificates.      |
| **API Gateway**                   | - Supports Edge-Optimized and Regional endpoints. Edge uses CloudFront for global clients; Regional for in-region clients. |

---

### **Application Layer and Monitoring**

| **Topic**            | **Key Details**                                                                                                             |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Amazon Inspector** | - Automated security scans for EC2, Lambda, and ECR. Finds vulnerabilities and provides risk scores.                        |
| **Amazon Macie**     | - Uses ML to detect sensitive data (e.g., PII) in S3 buckets.                                                               |
| **AWS WAF**          | - Blocks bad traffic patterns using custom rules and managed rules. Protects resources integrated with CloudFront and ALBs. |

---

### **DDoS and Security Best Practices**

| **Best Practices**        | **Details**                                                                                                              |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Edge Location Defense** | - Use CloudFront and Route 53 to protect at the edge. Global Accelerator can route traffic securely to backend services. |
| **Application Security**  | - Use WAF and CloudFront to filter malicious traffic. Apply rate-based rules and geo-blocking for additional protection. |
| **Obfuscation**           | - Hide backend resources with CloudFront and API Gateway. Secure with Security Groups and Network ACLs.                  |
