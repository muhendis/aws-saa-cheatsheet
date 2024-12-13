# **Elastic Load Balancer (ELB) and Auto Scaling Group (ASG) Cheat Sheet**

---

## **Elastic Load Balancer (ELB)**

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

#### **Routing Policies for Application Load Balancer (ALB)**

| **Routing Policy**            | **Description**                                                                                  | **Example**                                      | **Use Cases**                                                                                 |
|-------------------------------|--------------------------------------------------------------------------------------------------|------------------------------------------------|----------------------------------------------------------------------------------------------|
| **Path-Based Routing**         | Routes traffic based on the URL path in the request.                                             | `/images` → Target Group A. <br> `/api` → Target Group B. | Microservices or web apps with separate services like images, APIs, or frontend.             |
| **Host-Based Routing**         | Routes traffic based on the hostname in the request.                                             | `api.example.com` → Target Group A. <br> `www.example.com` → Target Group B. | Multi-tenant applications with separate domains or subdomains.                               |
| **Query String Routing**       | Routes traffic based on query parameters in the request.                                         | `?user=premium` → Target Group A.              | Direct traffic to premium or standard services based on user attributes.                     |
| **Header-Based Routing**       | Routes traffic based on HTTP headers in the request.                                             | Header `X-Region: US` → Target Group B.        | Region-specific routing or custom application logic based on headers.                        |
| **Target Group-Based Routing** | Routes traffic to different types of targets: EC2, IPs, or Lambda.                              | EC2 instances → Target Group A.                | Deploy workloads on different compute resources based on traffic type.                       |
| **HTTPS Redirects**            | Redirects HTTP traffic to HTTPS automatically.                                                  | `http://example.com` → `https://example.com`.   | Enforce secure connections for all web traffic.                                              |
| **Fixed Responses**            | Returns a predefined HTTP response for specific requests.                                       | Path `/maintenance` → Return `503`.            | Show maintenance or custom error messages for specific endpoints.                            |
| **Redirect Actions**           | Redirects users to another URL or endpoint.                                                     | `/old-path` → `/new-path`.                     | Handle URL structure changes or redirect deprecated endpoints.                               |
| **Weighted Target Group Routing** | Splits traffic between multiple target groups based on assigned weights.                        | 70% → Target Group A, 30% → Target Group B.    | Gradual traffic migration, blue-green deployments, or A/B testing.                           |


---

## **Auto Scaling Group (ASG)**

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
