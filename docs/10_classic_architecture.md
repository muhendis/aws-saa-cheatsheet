
### **Stateless Web App: "WhatIsTheTime.com"**

| **Aspect**                     | **Details**                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| **Scenario**                   | A simple app that doesn't require a database.                                              |
| **Scaling Strategies**         | - Vertical Scaling: Upgrading instance types (e.g., M5).                                   |
|                                | - Horizontal Scaling: Adding multiple instances with DNS or a Load Balancer (ELB).         |
| **Multi-AZ Setup**             | Use an Auto Scaling Group (ASG) with instances in multiple Availability Zones (AZs).        |
| **DNS & Load Balancing**       | - Route 53 Alias Records for DNS.<br>- ELB with health checks to distribute traffic.       |

---

### **Stateful Web App: "MyClothes.com"**

| **Aspect**                     | **Details**                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| **Scenario**                   | E-commerce app with a shopping cart and database for user data.                            |
| **Session Management**         | - Stickiness (session affinity) via ELB.<br>- Store session data in ElastiCache or DynamoDB.|
| **Database**                   | - User data in RDS.<br>- Read replicas or ElastiCache for scaling reads.                   |
| **Scaling & Disaster Recovery**| - Multi-AZ for RDS and ElastiCache.<br>- ASG for EC2 instances.                            |
| **Security**                   | Use Security Groups to restrict traffic between ELB, EC2, RDS, and ElastiCache.            |

---

### **Stateful Web App: "MyWordPress.com"**

| **Aspect**                     | **Details**                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| **Scenario**                   | Scalable WordPress site with MySQL database and media storage.                             |
| **Database**                   | - Use RDS with Multi-AZ for high availability.<br>- Use Aurora for scaling and efficiency.  |
| **Storage for Media**          | - EBS: Good for single-instance storage.<br>- EFS: Shared storage for distributed setup.    |
| **Scaling Reads**              | Aurora read replicas or caching with ElastiCache.                                          |

---

### **Elastic Beanstalk**

| **Aspect**                     | **Details**                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| **Overview**                   | Fully managed service to deploy applications using AWS resources like EC2, ELB, and ASG.   |
| **Advantages**                 | - Automatically manages scaling, load balancing, and health checks.<br>- Developer-focused.|
| **Supported Platforms**        | Node.js, Python, PHP, Java, Ruby, Docker, etc.                                             |
| **Environment Tiers**          | - Web Server Tier: For handling HTTP/S requests.<br>- Worker Tier: For background tasks via SQS. |
| **Deployment Modes**           | - Single Instance (for dev).<br>- High Availability (for prod) with Auto Scaling and Multi-AZ.|

---

### **Common Architectures**

| **Aspect**                     | **Details**                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| **3-Tier Web Application**     | - Public Subnet: Load Balancer (ALB/ELB).<br>- Private Subnet: Application EC2 instances.<br>- Data Subnet: RDS or ElastiCache. |
| **Auto Scaling Group (ASG)**   | Automatically adjusts the number of instances based on demand.                             |
| **Multi-AZ**                   | Ensures high availability for resources like RDS, ElastiCache, and EC2 instances.          |
| **Security**                   | - Restrict access using Security Groups.<br>- Use IAM for fine-grained permissions.        |

---

### **General Optimization Tips**

| **Aspect**                     | **Details**                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| **Faster Deployments**         | - Use Golden AMIs for pre-configured EC2 instances.<br>- Use RDS and EBS snapshots for restoration. |
| **Caching**                    | ElastiCache (Redis/Memcached) for reducing database load and improving performance.         |
| **Cost Savings**               | Use reserved instances for predictable workloads and ASG for dynamic scaling.              |
