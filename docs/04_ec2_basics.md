
### **Amazon EC2 Overview**
- **EC2**: Elastic Compute Cloud, Infrastructure as a Service (IaaS).  
- **Capabilities**:  
  - Rent virtual machines (EC2 instances).  
  - Store data (EBS volumes).  
  - Load balancing (ELB).  
  - Auto-scaling (ASG).  

---

### **Instance Types**
1. **General Purpose**: Balanced compute, memory, networking (e.g., `t2.micro`).  
2. **Compute Optimized**: High-performance processors for batch processing, HPC, gaming.  
3. **Memory Optimized**: For large datasets in memory, caching, and real-time analytics.  
4. **Storage Optimized**: High sequential read/write for databases, data warehousing.  

---

### **Purchasing Options**
1. **On-Demand**:  
   - Short-term, flexible, pay-per-second.  
   - Ideal for unpredictable workloads.  

2. **Reserved Instances (RI)**:  
   - Up to 72% discount for steady-state usage.  
   - 1 or 3-year terms; payment options: no upfront, partial, or full upfront.  

3. **Savings Plans**:  
   - Commit to usage ($/hour) for 1 or 3 years.  
   - Flexible instance family and OS.  

4. **Spot Instances**:  
   - Up to 90% discount.  
   - Instances can be interrupted; ideal for fault-tolerant jobs.  

5. **Dedicated Hosts**:  
   - Entire physical server for compliance or license requirements.  
   - Most expensive option.  

6. **Capacity Reservations**:  
   - Reserve capacity in a specific AZ without time commitment.  

---

### **Security Groups**
- **Firewall for EC2 Instances**:  
  - Control inbound and outbound traffic.  
  - Rules based on ports, protocols, IP ranges.  

**Key Points**:  
- All inbound traffic is **blocked by default**.  
- All outbound traffic is **allowed by default**.  
- Security groups are **stateful** (responses to allowed traffic are automatically permitted).

---

### **Instance Lifecycle**
- **Start/Stop/Terminate**:  
  - Start/Stop retains the root volume (EBS-backed instances).  
  - Terminate deletes the instance and associated volumes unless set otherwise.  

---

### **Key Features**
1. **EC2 User Data**:  
   - Bootstrap instances with scripts (e.g., install updates, software).  
   - Runs only at first launch as the root user.

2. **Elastic Block Store (EBS)**:  
   - Persistent storage for EC2 instances.  
   - Can be detached or attached to another instance.  

3. **SSH Access**:  
   - Linux: Use OpenSSH.  
   - Windows: Use PuTTY.  

---

### **Classic Ports to Know**
| **Port** | **Protocol**      | **Usage**                          |
|----------|-------------------|------------------------------------|
| 22       | SSH               | Secure shell for Linux instances. |
| 80       | HTTP              | Unsecured web traffic.            |
| 443      | HTTPS             | Secured web traffic.              |
| 3389     | RDP               | Remote Desktop for Windows.       |

---