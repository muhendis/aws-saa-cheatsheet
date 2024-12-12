### **Elastic Load Balancer (ELB) and Auto Scaling Group (ASG) Cheat Sheet**

---

#### **Elastic Load Balancer (ELB)**

| **Feature**                | **Details**                                                                                     |
|----------------------------|-------------------------------------------------------------------------------------------------|
| **Purpose**                | Distributes incoming traffic across multiple targets (EC2, Lambda, etc.).                      |
| **Benefits**               | High availability, fault tolerance, single point of access, health checks, SSL termination.    |
| **Health Checks**          | Ensures instances are healthy before routing traffic; checks HTTP response (e.g., `/health`).  |
| **Cross-Zone Load Balancing** | Distributes traffic evenly across AZs (enabled by default for ALB, configurable for others).    |

---

#### **ELB Types**

| **Type**                   | **Layer**       | **Use Cases**                                    | **Protocols**                       |
|----------------------------|----------------|------------------------------------------------|-------------------------------------|
| **Classic Load Balancer**  | Layer 4 & 7    | Legacy applications.                           | TCP, HTTP, HTTPS.                   |
| **Application Load Balancer (ALB)** | Layer 7       | HTTP/HTTPS traffic, microservices, containers. | HTTP, HTTPS, WebSocket.             |
| **Network Load Balancer (NLB)** | Layer 4       | High performance, low-latency applications.    | TCP, UDP, TLS.                      |
| **Gateway Load Balancer (GWLB)** | Layer 3       | Virtual network appliances (firewalls).        | IP Protocol (GENEVE on port 6081).  |

---

#### **ELB Advanced Features**

| **Feature**                | **Details**                                                                                     |
|----------------------------|-------------------------------------------------------------------------------------------------|
| **SSL/TLS Certificates**   | Managed via AWS Certificate Manager (ACM); supports SNI for multi-domain hosting.              |
| **Sticky Sessions**        | Ensures a client is routed to the same instance (uses cookies).                                |
| **Connection Draining**    | Allows existing requests to complete while de-registering an instance (default: 300 seconds).  |

---

#### **Auto Scaling Group (ASG)**

| **Feature**                  | **Details**                                                                                     |
|------------------------------|-------------------------------------------------------------------------------------------------|
| **Purpose**                  | Automatically scales EC2 instances based on load or defined policies.                         |
| **Components**               | Launch template (AMI, instance type), min/max capacity, scaling policies.                     |
| **Scaling Types**            | Vertical (instance size) and horizontal (number of instances).                                |
| **Health Checks**            | Monitors instance health; replaces unhealthy instances.                                       |

---

#### **ASG Scaling Policies**

| **Type**                  | **Details**                                                                                     | **Use Cases**                         |
|---------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------|
| **Target Tracking**       | Maintain a metric at a specific value (e.g., CPUUtilization = 40%).                            | Simple and effective scaling.         |
| **Step Scaling**          | Scale based on thresholds (e.g., CPU > 70% → add 2 instances).                                | Fine-grained control.                 |
| **Scheduled Scaling**     | Scale at predictable times (e.g., increase to 10 instances at 5 PM on Fridays).               | Workload patterns.                    |
| **Predictive Scaling**    | Forecast future load and scale in advance.                                                    | Prevent bottlenecks in high-traffic periods. |

---

#### **Scaling Metrics**

| **Metric**                 | **Use Cases**                                                                                  |
|----------------------------|-----------------------------------------------------------------------------------------------|
| **CPUUtilization**         | Average CPU usage across instances.                                                          |
| **RequestCountPerTarget**  | Balances requests per instance for consistent performance.                                   |
| **Average Network In/Out** | Tracks network-bound workloads.                                                              |
| **Custom Metrics**         | Define your own metrics in CloudWatch.                                                       |

---

#### **Key Points for ELB and ASG**

| **Aspect**                 | **ELB**                                           | **ASG**                                   |
|----------------------------|---------------------------------------------------|------------------------------------------|
| **Purpose**                | Distributes traffic across multiple targets.      | Scales EC2 instances up or down.         |
| **Health Monitoring**      | Performs health checks on targets.                | Replaces unhealthy EC2 instances.        |
| **Cost**                   | Charged per hour + data processed.                | ASG is free; pay for EC2 instances only. |
| **Integration**            | Works with ASG, Route 53, CloudWatch.             | Uses CloudWatch metrics and alarms.      |
