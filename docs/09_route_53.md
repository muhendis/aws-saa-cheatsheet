
### **Amazon Route 53**

| **Feature**                     | **Details**                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------|
| **Overview**                    | Highly available, scalable, managed DNS. Provides 100% SLA availability.                    |
| **Purpose**                     | Maps domain names to resources (e.g., IPs, AWS resources). Functions as a domain registrar. |
| **DNS Record Types**            | A, AAAA, CNAME, NS (must-know) + advanced types like CAA, TXT, SRV, etc.                    |

---

### **DNS Record Types**

| **DNS Record Type**             | **Details**                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------|
| **Alias**                       | Maps your root domain (example.com) to AWS resources (ELB, CloudFront, or S3); free and supports health checks.    |
| **CNAME**                       | Maps subdomain (e.g., www.example.com) to another domain (e.g., example.com).               |
| **A Records**                   | Associate a domain with a specific IP address.                                              |

TL;DR:

- Use Alias for AWS services (e.g., ELB, CloudFront).
- Use CNAME for mapping subdomains to other domains (e.g., www.example.com → example.com).
- Use A Record to map domains/subdomains to IPv4 addresses.

---

### **Hosted Zones**

| **Type**                        | **Details**                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------|
| **Public Hosted Zone**          | Routes traffic to resources accessible from the internet (e.g., websites).                  |
| **Private Hosted Zone**         | Routes traffic within VPCs (e.g., internal APIs, DBs).                                      |
| **Cost**                        | $0.50 per hosted zone/month.                                                                |

---

### **Routing Policies**

| **Policy**                      | **Details**                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------|
| **Simple**                      | Routes traffic to a single resource or randomly across multiple values. No health checks.   |
| **Weighted**                    | Distributes traffic based on assigned weights (e.g., for testing new versions).             |
| **Latency-based**               | Routes to the lowest latency resource (region-based).                                       |
| **Failover**                    | Active-passive routing for disaster recovery; requires health checks.                       |
| **Geolocation**                 | Routes based on user's geographic location (country/continent/US state).                   |
| **Geoproximity**                | Routes based on user/resource location; allows bias adjustments (requires Traffic Flow).    |
| **Multi-Value**                 | Returns multiple healthy resources (up to 8). Not a substitute for load balancers.          |
| **IP-based Routing**            | Routes based on user IP (uses CIDR blocks).                                                |

---

### **Health Checks**

| **Feature**                     | **Details**                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------|
| **Types**                       | Endpoint monitoring, calculated health checks, CloudWatch alarm checks.                     |
| **Thresholds**                  | Healthy/Unhealthy after 3 checks (default). Check intervals: 30 sec (default) or 10 sec.    |
| **Private Resources**           | Requires CloudWatch metrics & alarms to monitor private endpoints.                         |

---

### **Key Points for Alias Records**

| **Alias Target**                | **Supported AWS Resources**                                                                |
|---------------------------------|---------------------------------------------------------------------------------------------|
| Elastic Load Balancers          | CloudFront Distributions, API Gateway, S3 Websites, Elastic Beanstalk, etc.               |
| **Advantages**                  | Supports root domains, free, auto-updates with resource changes.                           |
| **Limitations**                 | Cannot target EC2 DNS names.                                                               |

---

### **Route 53 Pricing**

| **Service**                     | **Cost**                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------|
| Hosted Zone                     | $0.50 per month.                                                                           |
| DNS Queries                     | $0.40 per million queries (first billion).                                                |
| Health Checks                   | $0.50 per health check per month.                                                         |
