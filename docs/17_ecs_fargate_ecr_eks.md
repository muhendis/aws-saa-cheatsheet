### **1. Containerization Overview**

| **Topic**               | **Key Points**                                                                                                                                                                      | **Use Cases**                                               |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| **Docker**              | - Platform to deploy apps packaged in containers<br>- Containers can run on any OS without compatibility issues<br>- Works with any language/technology                             | Microservices architecture, lift-and-shift apps to AWS      |
| **Docker Repositories** | - **Docker Hub**: Public repository with base images for many OS and technologies (e.g., Ubuntu, MySQL)<br>- **Amazon ECR**: Private repository, public option (ECR Public Gallery) | Store and manage Docker images in a secure, scalable manner |
| **Docker vs. VMs**      | - Docker shares host resources, allowing for multiple containers on one machine<br>- VMs are more isolated, with their own guest OS                                                 | Optimize server resource usage and reduce overhead from VMs |

---

### **2. AWS Container Services (Amazon ECS & Fargate)**

| **Topic**                  | **Key Points**                                                                                                                                                                              | **Use Cases**                                                          |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **Amazon ECS**             | - Elastic Container Service for managing containerized apps<br>- Launch types: EC2 and Fargate<br>- Integrated with IAM, EFS, and CloudWatch                                                | Running scalable containerized apps                                    |
| **ECS Launch Types**       | - **EC2 Launch Type**: Requires EC2 instances, manually provisioned and maintained<br>- **Fargate Launch Type**: Serverless, no infrastructure management                                   | Flexible container hosting options: manual vs. serverless              |
| **ECS + EventBridge**      | - Automates tasks with event triggers (e.g., file uploads to S3)<br>- Supports scheduling tasks (e.g., batch processing)                                                                    | Event-driven architectures, automated workflows                        |
| **ECS + SQS**              | - Uses SQS queues to poll for messages<br>- Triggers ECS tasks based on queued events                                                                                                       | Asynchronous task processing, decoupled systems                        |
| **ECS Auto Scaling**       | - Auto-scales ECS tasks based on various metrics (e.g., CPU, memory usage)<br>- Scaling methods: Target Tracking, Step Scaling, Scheduled Scaling                                           | Efficient resource utilization, scaling ECS tasks automatically        |
| **ECS IAM Roles**          | - EC2 Instance Profile: Used by ECS agent for API calls, log management, accessing container images from ECR<br>- ECS Task Role: Specific roles for tasks (e.g., access to S3)              | Fine-grained access control for ECS tasks                              |
| **ECS Load Balancers**     | - **Application Load Balancer**: For most ECS use cases<br>- **Network Load Balancer**: High throughput or AWS PrivateLink<br>- **Classic Load Balancer**: Less preferred, limited features | Distribute traffic to containers effectively, ensure high availability |
| **ECS Data Volumes (EFS)** | - Mount EFS (Elastic File System) on ECS tasks for persistent, shared multi-AZ storage<br>- Supports both EC2 and Fargate launch types                                                      | Persistent storage for containers, multi-AZ data sharing               |

---

### **3. Serverless Options (Fargate + App Runner)**

| **Topic**          | **Key Points**                                                                                                                                                                                                               | **Use Cases**                                                    |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Amazon Fargate** | - Serverless container service<br>- Automatically handles provisioning, scaling, and managing containers<br>- Requires no EC2 instance management                                                                            | Ideal for serverless architectures, simple scaling of containers |
| **Fargate + EFS**  | - Fargate integrates with EFS for persistent storage<br>- Suitable for serverless applications needing shared file systems                                                                                                   | Serverless, persistent storage solutions for containers          |
| **AWS App Runner** | - Fully managed service for deploying web apps and APIs<br>- Supports source code or container images<br>- Auto-scaling, health checks, and load balancing<br>- VPC access for connecting to databases or other AWS services | Web apps, APIs, microservices, and rapid production deployments  |

---

### **4. Kubernetes on AWS (Amazon EKS)**

| **Topic**               | **Key Points**                                                                                                                                                                                             | **Use Cases**                                                |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| **Amazon EKS Overview** | - Managed Kubernetes service for deploying, managing, and scaling containerized applications<br>- Integrates with EC2 or Fargate for running worker nodes<br>- Cloud-agnostic (can migrate from any cloud) | Kubernetes workloads, multi-cloud deployment                 |
| **EKS Node Types**      | - **Managed Node Groups**: EKS manages the EC2 instances (On-Demand/Spot)<br>- **Self-Managed Nodes**: User-managed EC2 instances<br>- **AWS Fargate**: No need to manage nodes                            | Flexible node management, from fully managed to self-managed |
| **EKS Data Volumes**    | - Supports EBS, EFS, FSx for Lustre/NetApp for persistent storage<br>- Needs to specify StorageClass in EKS manifest                                                                                       | Persistent storage options for Kubernetes workloads          |

---

### **5. App Modernization Tools (App2Container)**

| **Topic**                  | **Key Points**                                                                                                                                                                                                                                                                          | **Use Cases**                                              |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| **AWS App2Container**      | - CLI tool for migrating .NET and Java apps into Docker containers<br>- Supports lift-and-shift of apps from on-premises or other clouds to AWS<br>- Generates CloudFormation templates for easy deployment                                                                             | App modernization, legacy app migration                    |
| **App2Container Workflow** | - **Discover & Analyze**: Inventory and runtime dependencies<br>- **Extract & Containerize**: Create Docker images<br>- **Create Deployment Artifacts**: Generate ECS Task/EKS Pod definitions, CI/CD pipelines<br>- **Deploy**: Store images in ECR, deploy to ECS, EKS, or App Runner | Streamlining containerization and migration of legacy apps |
