## **Amazon S3 Security and Management**

| **Topic**                     | **Details**                                                                                                                                                 | **Examples/Notes**                                                                                      |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Object Encryption**          | Protect data at rest in S3 using server-side or client-side encryption.                                                                                      | **Encryption Types**: SSE-S3, SSE-KMS, SSE-C, Client-Side Encryption.                                   |
| **SSE-S3**                      | Encryption using AWS-managed keys (AES-256). Enabled by default for new objects.                                                                            | Automatically applied to objects unless overridden by other encryption methods.                          |
| **SSE-KMS**                     | Encryption using keys managed in AWS Key Management Service (KMS). Allows better key control and audit with CloudTrail.                                      | Ideal for controlling and auditing access to sensitive data.                                            |
| **SSE-C**                       | Encryption where the customer provides the encryption keys. S3 does not store the key.                                                                       | Requires HTTPS and key inclusion in the request header for each API call.                               |
| **Client-Side Encryption**     | Customers encrypt data before uploading it to S3, and decrypt it when retrieving.                                                                            | Full control over the encryption cycle; requires client-side libraries.                                 |
| **Encryption in Transit (SSL/TLS)** | Encrypts data during transit using SSL/TLS. S3 provides both HTTP and HTTPS endpoints. **HTTPS** is recommended for all operations.                          | **Mandatory** for SSE-C, recommended for all S3 access.                                                 |
| **MFA Delete**                  | Adds extra security by requiring multi-factor authentication (MFA) to permanently delete objects or suspend versioning.                                       | **Requires Versioning** to be enabled; only the root user can enable or disable MFA Delete.              |
| **Access Logs**                 | Logs all requests to S3 buckets for auditing and analysis. Logs are stored in a separate S3 bucket in the same region.                                        | Logs can be analyzed using tools like Amazon Athena or S3 Select.                                        |
| **Pre-Signed URLs**            | Generate time-limited URLs that allow temporary access to specific objects in S3 for users who don't have direct permissions.                                 | Used for sharing private objects or allowing limited-time uploads/downloads.                             |
| **S3 Glacier Vault Lock**       | Implements a **Write Once, Read Many** (WORM) model, useful for compliance and data retention policies. Once locked, policies cannot be edited or deleted.    | Helps ensure that archived data cannot be tampered with or deleted before the retention period ends.     |
| **S3 Object Lock**             | Protects objects from being overwritten or deleted by using retention policies (compliance or governance).                                                     | **Compliance mode**: No deletion allowed, even by root user. **Governance mode**: Restrictions can be bypassed by specific users. |
| **Access Points**              | Simplifies S3 security management, especially for large datasets or shared access. Each access point has a unique DNS and can have its own policy.              | Can be configured for **VPC** or internet access. Example: Grant access to specific prefixes like `/finance/` or `/sales/`. |
| **VPC Origin Access Points**   | Access Points restricted to VPC-only access using VPC Endpoints, providing secure access to S3 from within a private network.                                 | Provides more controlled access for applications in a VPC, reducing exposure to the public internet.    |
| **S3 Object Lambda**           | Allows using AWS Lambda functions to modify objects on the fly before returning them to the user.                                                             | Example: Redact personally identifiable information (PII) before sending data to an analytics system.   |

---

### **Key Security Controls:**

1. **Encryption**: 
   - **SSE-S3**: Default encryption for simplicity.
   - **SSE-KMS**: Best for additional control, auditing, and using custom keys.
   - **SSE-C**: For customer-managed encryption keys.
   - **Client-Side Encryption**: For fully encrypted data before upload.

###### **Kritik Farklar** (SSE-KMS vs SSE-C)
- **SSE-KMS:** AWS anahtarları yönetir, CloudTrail ile loglanır. Denetim ve uyumluluk için ideal.  
- **SSE-C:** Anahtarlar tamamen müşteri kontrolündedir. AWS sadece şifreleme/deşifreleme yapar.

###### **Seçim Kılavuzu** (SSE-KMS vs SSE-C)
- **SSE-KMS:** Daha fazla denetim ve uyumluluk istediğinizde.  
- **SSE-C:** Anahtar yönetimini tamamen kontrol etmek istediğinizde.

2. **Access Management**: 
   - Use **Bucket Policies** and **Access Points** to manage permissions at a large scale.
   - **MFA Delete** adds another layer of security for critical operations.

3. **Compliance and Retention**: 
   - **Vault Lock** and **Object Lock** help enforce retention policies (WORM model) for regulatory compliance.

4. **Monitoring and Logging**: 
   - **Access Logs** and **Pre-Signed URLs** are key for monitoring and temporarily allowing access to S3 data.
