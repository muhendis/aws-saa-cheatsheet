

#### **Networking Features**

| **Feature**          | **Details**                                                                                       | **Key Points**                                                                 |
|----------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| Public IP            | Allows direct access to the internet.                                                           | Changes after stop/start unless Elastic IP is used.                           |
| Private IP           | Internal communication within the AWS network.                                                  | Used in VPCs, NAT Gateway required for internet access.                        |
| Elastic IP           | Persistent public IP address attached to an instance.                                           | Limited to 5 per account; avoid using for large-scale architectures.           |
| Security Groups      | Act as a virtual firewall, controlling inbound/outbound traffic.                                 | Stateful; inbound and outbound rules automatically allow response traffic.     |

---

#### **Placement Groups**

| **Type**       | **Description**                                                                                | **Use Cases**                                      |
|----------------|-----------------------------------------------------------------------------------------------|--------------------------------------------------|
| Cluster        | Instances placed close for low-latency, high-throughput networking.                           | HPC, big data jobs.                              |
| Spread         | Instances distributed across hardware for high availability.                                  | Critical applications that require fault isolation. |
| Partition      | Instances spread across logical partitions on different racks.                                | Distributed systems like Hadoop, Kafka, Cassandra. |

---

#### **Advanced Features**

| **Feature**        | **Details**                                                                                   | **Use Cases**                              |
|--------------------|----------------------------------------------------------------------------------------------|--------------------------------------------|
| EC2 Hibernate      | Saves in-memory (RAM) state; boots faster than stop/start.                                   | Long-running jobs or applications needing fast recovery. |
| Elastic Network Interfaces (ENI) | Virtual network card; can be attached/detached to enable instance failover.                           | High-availability network setups.          |
