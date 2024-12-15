### **1. Mobile Application (MyTodoList)**

#### Architecture Overview

| **Requirement**                       | **AWS Service**                   |
| ------------------------------------- | --------------------------------- |
| REST API with HTTPS                   | Amazon API Gateway                |
| Serverless compute                    | AWS Lambda                        |
| User authentication                   | Amazon Cognito                    |
| Scalable database                     | Amazon DynamoDB                   |
| User access to personal folders in S3 | Temporary credentials via Cognito |

#### Enhancements

- **Caching**: Use DAX (DynamoDB Accelerator) for high read throughput.
- **API Caching**: Implement caching in Amazon API Gateway.

---

### **2. Serverless Website (MyBlog.com)**

#### Architecture Components

| **Feature**              | **AWS Service**                       |
| ------------------------ | ------------------------------------- |
| Static content delivery  | Amazon S3 + Amazon CloudFront         |
| REST API                 | Amazon API Gateway + AWS Lambda       |
| Global data availability | DynamoDB Global Tables                |
| Email notifications      | Amazon SES                            |
| Thumbnail generation     | S3 triggers Lambda (optional SNS/SQS) |

#### Key Highlights

- Use **Origin Access Control (OAC)** to secure S3 access via CloudFront.
- Leverage **DynamoDB Streams** for event-driven workflows like email notifications.

---

### **3. Microservices Architecture**

#### Design Principles

| **Pattern**               | **AWS Services**                                 |
| ------------------------- | ------------------------------------------------ |
| Synchronous APIs          | Amazon API Gateway, Elastic Load Balancers       |
| Asynchronous interactions | SQS, Kinesis, SNS, Lambda triggers (e.g., S3)    |
| Microservices hosting     | AWS Lambda, ECS, EC2, RDS, DynamoDB, ElastiCache |

#### Challenges

- High overhead for managing multiple microservices.
- Serverless solutions (e.g., Lambda, API Gateway) simplify scaling and cost management.

---

### **4. Optimizing Software Updates**

#### Current Issue

- EC2 instances distribute updates, leading to high costs and CPU usage during peak requests.

#### Solution

| **Approach**   | **Details**                                             |
| -------------- | ------------------------------------------------------- |
| Add CloudFront | Cache update files at edge locations.                   |
| Benefits       | Reduced load on EC2, lower costs, improved scalability. |

---

### **5. General Serverless Patterns**

#### Key Takeaways

- Use **Amazon Cognito** for secure authentication and temporary credentials.
- Cache frequently accessed data using **DAX** and **API Gateway caching**.
- Use event-driven models like **Lambda with SQS/SNS** to process workflows efficiently.
- CloudFront is a powerful solution to distribute static content globally with minimal changes.
