## **Detailed Analysis of AWS Services in the Slides**

### **1. Serverless Overview**

| **Aspect**           | **Details**                                                                                                                                                   |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**       | Serverless enables developers to deploy code without managing server infrastructure. AWS handles provisioning, scaling, and maintenance of backend resources. |
| **Key AWS Services** | - **AWS Lambda**: Event-driven compute.<br> - **DynamoDB**: Managed NoSQL database.<br> - **API Gateway**: API management and routing.<br> - **S3**: Storage. |

---

### **2. AWS Lambda**

#### **Features and Benefits**

| **Aspect**            | **Details**                                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **On-Demand Compute** | Execute code in response to triggers (S3 events, API Gateway calls).                                                    |
| **Pricing**           | Pay only for execution time and number of invocations. Includes a free tier (1M requests and 400,000 GB-seconds/month). |
| **Language Support**  | Node.js, Python, Java, Ruby, C#, PowerShell, and custom runtimes (Rust, Golang).                                        |
| **Integrations**      | Easily integrates with AWS services like S3, DynamoDB, CloudWatch, SNS, and SQS.                                        |
| **Use Cases**         | - Real-time file processing (e.g., creating thumbnails). <br> - Data pipelines. <br> - Event-driven microservices.      |

#### **Limits and Enhancements**

| **Limit**            | **Default Value**                                        |
| -------------------- | -------------------------------------------------------- |
| Execution Time       | 15 minutes per invocation.                               |
| Memory Allocation    | 128 MB to 10 GB (1 MB increments).                       |
| Disk Storage (tmp)   | 512 MB to 10 GB.                                         |
| Concurrency          | 1,000 invocations per region (adjustable).               |
| **SnapStart (Java)** | Enhances cold start times by pre-initializing functions. |

---

### **3. Amazon DynamoDB**

#### **Core Features**

| **Aspect**         | **Details**                                                                                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------------- |
| **Design**         | NoSQL database with schema-less design.                                                                             |
| **Performance**    | Consistent low latency (single-digit milliseconds).                                                                 |
| **Capacity Modes** | - **Provisioned**: Pre-allocate read/write units.<br> - **On-Demand**: Scale dynamically based on traffic patterns. |
| **Security**       | Integrated with IAM for resource access control.                                                                    |

#### **Advanced Capabilities**

| **Feature**       | **Details**                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| **TTL**           | Automatically deletes expired items to reduce storage.                   |
| **Global Tables** | Multi-region active-active replication for low-latency access.           |
| **Streams**       | Captures table changes in real-time (create/update/delete) for 24 hours. |
| **DAX**           | In-memory cache for DynamoDB, reducing read latency to microseconds.     |

---

### **4. API Gateway**

#### **Overview**

| **Aspect**         | **Details**                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| **Purpose**        | Managed service to create, deploy, and manage APIs for accessing backend resources (Lambda, HTTP endpoints, AWS services).           |
| **Endpoint Types** | - **Edge-Optimized:** Global clients via CloudFront.<br> - **Regional:** Localized APIs.<br> - **Private:** Secure APIs within VPCs. |

#### **Features**

| **Aspect**         | **Details**                                                                                                                                          |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security**       | - Authentication via Cognito, IAM roles, or custom authorizers.<br> - HTTPS with ACM integration.<br> - API keys and request throttling.             |
| **Transformation** | Validate and modify incoming requests and outgoing responses.                                                                                        |
| **Integrations**   | - AWS Lambda: Backend compute.<br> - AWS Services: Start workflows, process messages in SQS.<br> - HTTP: Route to on-premise APIs or load balancers. |

---

### **5. Cognito**

#### **User Pools**

| **Aspect**       | **Details**                                                     |
| ---------------- | --------------------------------------------------------------- |
| **Purpose**      | Manage user identities for web/mobile apps.                     |
| **Features**     | Password resets, MFA, federated logins (Google, Facebook).      |
| **Integrations** | API Gateway, Application Load Balancer for user authentication. |

#### **Identity Pools**

| **Aspect**        | **Details**                                                                   |
| ----------------- | ----------------------------------------------------------------------------- |
| **Purpose**       | Provides temporary AWS credentials for accessing resources like S3, DynamoDB. |
| **Customization** | Apply IAM policies for fine-grained access control based on user attributes.  |

---

### **6. CloudFront Functions vs. Lambda@Edge**

#### **Comparison**

| **Feature**        | **CloudFront Functions**                   | **Lambda@Edge**                                  |
| ------------------ | ------------------------------------------ | ------------------------------------------------ |
| **Purpose**        | Lightweight request/response manipulation. | Advanced compute at the edge.                    |
| **Execution Time** | Sub-millisecond.                           | 5-10 seconds.                                    |
| **Memory**         | Up to 2 MB.                                | 128 MB to 10 GB.                                 |
| **Use Cases**      | Header manipulation, token validation.     | Real-time image transformation, dynamic routing. |

---

### **7. Advanced Use Cases**

| **Service**              | **Example Use Case**                                                           |
| ------------------------ | ------------------------------------------------------------------------------ |
| **Lambda + S3**          | Trigger file processing pipelines (e.g., image resizing, document processing). |
| **DynamoDB Streams**     | Real-time analytics pipelines and event-driven systems.                        |
| **API Gateway + Lambda** | Backend for RESTful or WebSocket APIs.                                         |
| **Cognito + ALB**        | Authenticate and authorize users dynamically for backend access.               |
