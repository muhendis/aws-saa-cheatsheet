
### **Amazon Route 53**

| **Feature**                     | **Details**                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------|
| **Overview**                    | Highly available, scalable, managed DNS. Provides 100% SLA availability.                    |
| **Purpose**                     | Maps domain names to resources (e.g., IPs, AWS resources). Functions as a domain registrar. |
| **DNS Record Types**            | A, AAAA, CNAME, NS (must-know) + advanced types like CAA, TXT, SRV, etc.                    |


### **DNS Record Types - AWS Exam Cheat Sheet**

| **Record Type**       | **Purpose**                                                                 | **Example Use Case**                       | **Key Exam Tips**                                                                                     |
|------------------------|-----------------------------------------------------------------------------|--------------------------------------------|-------------------------------------------------------------------------------------------------------|
| **A (Address)**        | Maps a domain name to an IPv4 address.                                     | `www.example.com` → `192.0.2.1`           | Use for mapping to IPv4 addresses.                                                                   |
| **AAAA**               | Maps a domain name to an IPv6 address.                                     | `www.example.com` → `2001:db8::1`         | Use for IPv6 setups.                                                                                 |
| **CNAME**              | Maps a domain name to another domain name (alias).                        | `app.example.com` → `www.example.com`     | Cannot be used for root domains (use ALIAS instead in Route 53).                                     |
| **MX (Mail Exchange)** | Specifies mail servers for a domain.                                       | Directs emails to `mail.example.com`.     | Essential for email services like SES.                                                              |
| **NS (Name Server)**   | Delegates a domain to specific name servers.                               | Points `example.com` to Route 53 NS.      | Automatically set when creating a hosted zone in Route 53.                                           |
| **PTR (Pointer)**      | Resolves an IP address to a domain name (reverse DNS lookup).              | `192.0.2.1` → `www.example.com`.          | Used for compliance or reverse DNS lookups, often in conjunction with email services.                |
| **SOA (Start of Authority)** | Contains administrative details about the zone (e.g., TTL, refresh rate).        | DNS zone metadata.                        | Automatically included in Route 53 hosted zones.                                                    |
| **TXT (Text)**         | Stores arbitrary text, often used for verification or policies (e.g., SPF, DKIM). | Domain verification for SES or ACM.       | Commonly used for domain ownership verification and email authentication (SPF, DKIM, DMARC).         |
| **SRV (Service)**      | Specifies services and ports for a domain.                                | `sip.example.com` → `host:port`.          | Used for protocols like SIP or LDAP to define service locations.                                     |
| **ALIAS** (AWS-specific) | Points a domain to an AWS resource (e.g., ELB, CloudFront) without additional charge. | `example.com` → `my-ELB.amazonaws.com`.   | Preferred over CNAME for root domains in Route 53. No additional DNS query costs for AWS resources. |

---

### **Quick Notes:**
- **A vs. CNAME:** Use **A** for direct IP mapping, **CNAME** for aliases (but not root domains).  
- **ALIAS vs. CNAME:** Use **ALIAS** for root domains and AWS resources (like ELB, CloudFront).  
- **TXT Records:** Crucial for domain verification (e.g., SES, ACM).  
- **SOA and NS Records:** Automatically handled by Route 53, but know their purpose for the exam.
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
