### **AWS Organizations**

| Feature                        | Details                                                           |
| ------------------------------ | ----------------------------------------------------------------- |
| **Purpose**                    | Centralized management for multiple AWS accounts.                 |
| **Accounts**                   | - **Management account**: Full control.                           |
|                                | - **Member accounts**: Restricted; only part of one organization. |
| **Key Features**               | - Consolidated Billing with volume discounts (e.g., EC2, S3).     |
|                                | - Shared reserved instances and Savings Plans discounts.          |
|                                | - API support for automating account creation.                    |
| **Organizational Units (OUs)** | Group accounts by purpose (e.g., Dev, Prod, Finance).             |
| **Security with SCPs**         | - Permissions enforced by Service Control Policies (SCPs).        |
|                                | - Explicit allow required from root to the account.               |
| **Best Practices**             | - Enable CloudTrail logs in a central S3 account.                 |
|                                | - Establish cross-account roles for administrative access.        |

---

### **IAM Permissions and Conditions**

| IAM Feature                 | Description                                                               |
| --------------------------- | ------------------------------------------------------------------------- |
| **IAM Conditions**          | - `aws:SourceIp`: Restrict API calls by client IP.                        |
|                             | - `aws:RequestedRegion`: Restrict regions for API calls.                  |
|                             | - `aws:MultiFactorAuthPresent`: Enforce MFA.                              |
|                             | - `ec2:ResourceTag`: Use tags for conditional permissions.                |
| **S3-Specific Permissions** | - `s3:ListBucket`: Bucket-level permissions.                              |
|                             | - `s3:GetObject`, `s3:PutObject`: Object-level permissions.               |
| **Resource Policies**       | - `aws:PrincipalOrgID`: Restrict access to accounts in AWS Organizations. |

---

### **IAM Roles vs. Resource-Based Policies**

| IAM Roles                                               | Resource-Based Policies                                                     |
| ------------------------------------------------------- | --------------------------------------------------------------------------- |
| Assumes permissions of the assigned role.               | Principal retains their permissions.                                        |
| Cross-account actions require assuming a role.          | Cross-account actions use resource-based policies (e.g., S3 bucket policy). |
| Example: EC2 writes to an S3 bucket in another account. | Example: Policies on S3 buckets, SNS topics, or SQS queues.                 |

---

### **AWS Identity Center (Formerly AWS SSO)**

| Feature                  | Description                                                                              |
| ------------------------ | ---------------------------------------------------------------------------------------- |
| **Single Sign-On (SSO)** | - Login across AWS accounts and SAML 2.0 apps (e.g., Office 365, Salesforce).            |
|                          | - Built-in identity store or external providers (e.g., Okta, AD).                        |
| **Permission Sets**      | Assign IAM policies to users/groups for multi-account access.                            |
| **ABAC**                 | Attribute-Based Access Control for fine-grained permissions (e.g., by role or location). |

---

### **AWS Directory Services**

| Service                  | Description                                                       |
| ------------------------ | ----------------------------------------------------------------- |
| **Managed Microsoft AD** | Full-featured AD on AWS, integrates with on-premises AD.          |
| **AD Connector**         | Proxy for redirecting requests to on-premises AD.                 |
| **Simple AD**            | Lightweight, AWS-managed directory, no trust with on-premises AD. |

---

### **IAM Permission Boundaries**

| Feature       | Description                                                              |
| ------------- | ------------------------------------------------------------------------ |
| **Purpose**   | Limits maximum permissions granted to an IAM user or role.               |
| **Use Cases** | - Allow non-admin users to create IAM roles with restricted permissions. |
|               | - Prevent privilege escalation.                                          |

---

### **AWS Control Tower**

| Feature                   | Description                                                                            |
| ------------------------- | -------------------------------------------------------------------------------------- |
| **Purpose**               | Automates secure multi-account setups with best practices.                             |
| **Guardrails**            | - **Preventive**: Use SCPs to restrict actions globally (e.g., restrict regions).      |
|                           | - **Detective**: Use AWS Config to identify non-compliance (e.g., untagged resources). |
| **Compliance Monitoring** | Monitor violations and remediation actions through an interactive dashboard.           |

---

### **EventBridge and Security**

| EventBridge Security        | Description                                                                         |
| --------------------------- | ----------------------------------------------------------------------------------- |
| **Resource-Based Policies** | Allows EventBridge rules to invoke resources like S3, Lambda, SNS, etc.             |
| **IAM Roles**               | Used for services like EC2 Auto Scaling or ECS tasks when triggered by EventBridge. |

---

### **Example Scenarios and Policies**

| Use Case                       | Example                                                                 |
| ------------------------------ | ----------------------------------------------------------------------- |
| **SCP Deny Example**           | Block EC2 usage in a specific OU while allowing other services.         |
| **Cross-Account Role Example** | User in Account A assumes a role in Account B to access S3 or DynamoDB. |

---

### Additional Notes

- **IAM Policy Evaluation**: AWS uses a combination of explicit allows and denies with default deny as the fallback.
- **AWS Managed Services**: Leverage services like **AWS Directory Services** and **Control Tower** to simplify governance.
