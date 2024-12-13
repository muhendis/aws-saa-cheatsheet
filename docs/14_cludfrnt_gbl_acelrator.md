# **CloudFront vs. Global Accelerator**

| **Aspect**               | **Amazon CloudFront**                                                                 | **AWS Global Accelerator**                                                        |
|--------------------------|---------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| **Purpose**              | Content Delivery Network (CDN) for caching and delivering content globally.          | Optimizes performance and availability for applications via AWS global network.   |
| **Protocol Support**     | HTTP, HTTPS.                                                                          | TCP, UDP.                                                                         |
| **Content**              | Best for **cacheable content** (e.g., images, videos) and dynamic content acceleration.| Best for **non-HTTP** use cases (e.g., gaming, IoT) and applications requiring static IPs. |
| **Edge Locations**       | Delivers cached content from 216+ edge locations worldwide.                           | Routes traffic to the closest AWS region using 2 Anycast IPs.                     |
| **Caching**              | Yes. Caches content at edge locations based on Time-to-Live (TTL).                    | No caching; directly forwards requests to the origin.                             |
| **Dynamic Content**      | Accelerates dynamic content, including APIs and dynamic site delivery.                | Routes packets at the edge for dynamic applications.                              |
| **Static IP Support**    | Not supported; uses domain names for routing.                                         | Supports static IP addresses, ideal for applications requiring whitelisting.      |
| **Use Case**             | - Websites serving static/dynamic content. <br> - Media streaming, APIs, software downloads. | - Gaming (UDP), IoT (MQTT), VoIP. <br> - Disaster recovery with fast regional failover. |
| **Performance**          | Improves performance for cached content via edge locations.                          | Reduces latency by routing via AWS global backbone network.                       |
| **Failover**             | Not region-aware; relies on DNS TTL for failover.                                     | Regional failover within seconds, ideal for disaster recovery.                    |
| **DDoS Protection**      | Yes, integrates with AWS Shield.                                                     | Yes, integrates with AWS Shield Advanced.                                         |
| **Health Checks**        | No native health checks for origins.                                                 | Performs health checks on endpoints and reroutes traffic if unhealthy.            |
| **Pricing**              | Data transfer and requests are priced based on edge location usage.                   | Charged based on static IP provisioned and data transferred through the service.   |

---

### **When to Use Each**
- **Amazon CloudFront**:  
  - Best for serving **web content** like images, videos, and APIs.  
  - Use for **low-latency delivery of cacheable content**.  
  - Works seamlessly with S3, ALB, or EC2 as origins.  
  - Lambda@Edge for dynamic content acceleration.

- **AWS Global Accelerator**:  
  - Ideal for **low-latency, high-availability applications** with static IPs.  
  - Best for **non-HTTP protocols** (e.g., UDP for gaming or IoT).  
  - Use for **applications needing fast failover across AWS Regions**.  
