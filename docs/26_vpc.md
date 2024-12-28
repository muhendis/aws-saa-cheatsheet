| **Section**                | **Key Concepts**                                                                                                                                                                                                                  | **Additional Notes**                                                                                                                                                           |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **VPC Basics**             | - A **VPC (Virtual Private Cloud)** is a logically isolated network.<br>- Define IPv4 and optional IPv6 CIDRs.<br>- Subnets are tied to **Availability Zones (AZs)**.<br>- Public subnets connect via **Internet Gateway (IGW)**. | - 5 IP addresses per subnet are reserved by AWS.<br>- Ensure non-overlapping CIDRs for corporate or peered VPCs.<br>- Limit of 5 VPC CIDRs per region by default (soft limit). |
| **CIDR & IP Allocation**   | - **CIDR (Classless Inter-Domain Routing)** determines IP ranges.<br>- Examples:<br> - `/16` = 65,536 IPs.<br> - `/24` = 256 IPs.<br> - `/28` = 16 IPs (minimum size for AWS).                                                    | - Public IP ranges: Internet routable.<br>- Private IP ranges: <br> - `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`.<br>- AWS accounts get a default VPC.                    |
| **Routing**                | - Use **Route Tables** for directing subnet traffic:<br> - Public subnet: Route to IGW.<br> - Private subnet: Route to **NAT Gateway**.<br>- VPC Peering requires custom routes.                                                  | - Route propagation can simplify **Direct Connect (DX)** or **Site-to-Site VPN** routing setups.                                                                               |
| **Security**               | - **Security Groups (SG):**<br> - Instance-level, stateful rules.<br> - Only allow rules supported.<br>- **NACL (Network ACLs):**<br> - Subnet-level, stateless rules.<br> - Support allow/deny.                                  | - Use ephemeral ports for dynamic connections:<br> - Linux: `32768–60999`.<br> - Windows: `49152–65535`.<br>- AWS reserves a default NACL per subnet.                          |
| **NAT Gateway & Instance** | - **NAT Gateway:** Managed by AWS for high availability; supports IPv4.<br>- **NAT Instance:** Custom EC2-based NAT setup, supports advanced configurations.                                                                      | - NAT Gateway is the recommended solution for production.<br>- NAT Instances require manual scaling and are less reliable.                                                     |
| **Bastion Host**           | - Public EC2 instance for SSH access to private instances.<br>- Deployed in a public subnet.<br>- Connect securely using Security Group rules.                                                                                    | - Limit inbound traffic to port `22` from specific corporate IPs for SSH.                                                                                                      |
| **VPC Peering**            | - Connects two VPCs (same/different accounts or regions).<br>- CIDRs must not overlap.<br>- Peering is **not transitive** (requires separate connections for each VPC pair).                                                      | - Update **Security Groups** and **Route Tables** for traffic to flow between VPCs.                                                                                            |
| **VPC Endpoints**          | - **Gateway Endpoint:** For S3/DynamoDB (no cost).<br>- **Interface Endpoint (PrivateLink):** For other AWS services (charges apply).                                                                                             | - Preferred for private connections to AWS services.<br>- Avoid public internet to save costs and enhance security.                                                            |
| **Traffic Monitoring**     | - **VPC Flow Logs**: Monitor traffic on VPC, Subnet, or ENI levels.<br>- Capture logs for accepted/rejected traffic.                                                                                                              | - Logs can be sent to CloudWatch, S3, or Kinesis for analysis.<br>- Helps troubleshoot connectivity issues and detect malicious activity.                                      |
| **Transit Gateway**        | - Centralized hub for connecting multiple VPCs, VPNs, and DX connections.<br>- Supports thousands of connections.<br>- Works across accounts and regions.                                                                         | - Use **Route Tables** to manage traffic flow between connected networks.<br>- Supports multicast and IP routing.                                                              |
| **Direct Connect (DX)**    | - Private, dedicated connection between on-premises and AWS.<br>- Lower latency and higher bandwidth compared to VPN.<br>- Supports hybrid cloud setups.                                                                          | - Requires a Virtual Private Gateway for VPC access.<br>- Use Direct Connect Gateway for multi-region or multi-VPC setups.                                                     |
| **IPv6 Support**           | - IPv6 is public and Internet-routable.<br>- Use **Egress-Only IGW** for outbound IPv6 traffic from private subnets.                                                                                                              | - IPv4 cannot be disabled; VPCs operate in dual-stack mode (IPv4 + IPv6).                                                                                                      |
| **Advanced Security**      | - **AWS Network Firewall:** Protects VPCs with Layer 3–7 filtering.<br>- **WAF/Shield:** Protects against DDoS or malicious web requests.                                                                                         | - Centralized management with **AWS Firewall Manager**.                                                                                                                        |
| **Cost Optimization**      | - Use private IPs within the same AZ.<br>- Gateway Endpoints are free for S3/DynamoDB.<br>- Minimize cross-region traffic to reduce egress costs.                                                                                 | - Consider **S3 Transfer Acceleration** for faster uploads but at additional cost.                                                                                             |
| **Miscellaneous**          | - **Egress-Only IGW:** IPv6-only NAT functionality.<br>- **Traffic Mirroring:** Debug and monitor network traffic.<br>- **ClassicLink:** Connect EC2-Classic instances to VPC.                                                    | - ClassicLink is outdated and discouraged for new setups.                                                                                                                      |




#kendi notlarım :

### **AWS VPC ve Networking Notları (Genişletilmiş ve Karşılaştırmalı)**

| **Konu**                      | **Açıklama**                                                                                                                                                                                                                                   |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **VPC (Region-based)**        | - Her VPC belirli bir AWS bölgesine özeldir.<br>- İzole bir ağ sağlar ve birden fazla **Subnet**, **Route Table**, **Gateway** barındırabilir.                                                                                                  |
| **Route Table**               | - Public ve Private Subnet’lerin yönlendirme işlemlerini yönetir.<br>- **Public Subnet:** Internet Gateway’e trafik yönlendirilir.<br>- **Private Subnet:** NAT Gateway üzerinden yönlendirilir.                                               |
| **Network ACL (Stateless)**   | - Subnet seviyesinde çalışır.<br>- İlk kural: **any → any deny** (her şey varsayılan olarak reddedilir).<br>- **Allow** ve **Deny** kurallarını destekler.<br>- IP ve port bazlı kurallar (ör. SSH, HTTP).                                       |
| **Security Groups (Stateful)**| - Instance seviyesinde çalışır (ör. EC2, RDS).<br>- Sadece **Allow** kurallarına izin verir.<br>- Port bazlı izinler: Örneğin, SSH (port 22), HTTP (port 80).<br>- Her şey varsayılan olarak reddedilir (Allow dışında).                           |
| **İşleme Sırası**             | - 1. **Network ACL (NACL):** Trafik önce subnet seviyesinde kontrol edilir.<br>- 2. **Security Groups (SG):** Trafik instance seviyesinde kontrol edilir.                                                                                     |
| **NAT Gateway**               | - Private Subnet’teki instanceların internete erişimini sağlar.<br>- **Public Subnet**’te yapılandırılmalıdır.<br>- Private instanceların public IP’leri olmadığı için dışarıdan erişim mümkün değildir.<br>- Daha kolay ve AWS tarafından yönetilir.|
| **NAT Instance**              | - NAT Gateway ile aynı işlevi görür ancak EC2 üzerinde özel bir **AMI** ile yapılandırılır.<br>- Daha karmaşık ihtiyaçlar için tercih edilir.<br>- Ölçeklendirilmesi zordur ve manuel yönetim gerektirir.                                       |
| **Routing NAT Gateway**       | - **Routing Table:**<br>  - **Destination:** `0.0.0.0/0` (internet).<br>  - **Target:** NAT Gateway üzerinden yönlendirilir.                                                                                                                 |
| **Endpoint**                  | - AWS servislerine (ör. S3, DynamoDB) internete çıkmadan özel bağlantı sağlar.<br>- **Route Table**’a eklenir.<br>  - Örnek: Hedef S3 ise, **Target:** S3 Endpoint olur.                                                                     |
| **VPC Peering**               | - İki farklı VPC arasında özel bir bağlantı kurar.<br>- CIDR bloklarının çakışmaması gerekir.<br>- Farklı regionlar arasında çalışabilir.<br>- **Route Table:** Peering Connection’a hedef yönlendirilir (ör. `pcx-0123456789`).                |
| **VPN Gateway**               | - On-premise ağ ile AWS arasında VPN bağlantısı sağlar.<br>- İnternet üzerinden güvenli iletişim sunar.<br>- Yüksek gecikmeyi tolere edebilen bağlantılar için uygundur.                                                                       |
| **Direct Connect**            | - On-premise ağ ile AWS arasında özel bir internet sağlayıcısı (ör. Türk Telekom) üzerinden doğrudan bağlantı sağlar.<br>- Genel internete gerek kalmaz.<br>- Daha düşük gecikme ve yüksek bant genişliği sunar.                                 |
| **Elastic Load Balancer (ELB)**| - Trafiği birden fazla instance arasında dağıtarak yüksek erişilebilirlik sağlar.<br>- **ALB (Application):** HTTP/HTTPS trafiği için.<br>- **NLB (Network):** TCP/UDP trafiği için.<br>- **GWLB:** Üçüncü taraf ağ cihazları için uygundur.    |
| **Elastic IP (EIP)**          | - AWS kaynaklarına atanabilen statik bir IP adresidir.<br>- Public IP adresi değiştiğinde kesintiyi önlemek için kullanılır.                                                                                                                   |
| **VPC Flow Logs**             | - VPC, subnet veya ENI düzeyinde ağ trafiğini loglar.<br>- CloudWatch veya S3 üzerinde loglama yapılabilir.<br>- Ağ analizi ve sorun giderme için kullanılır.                                                                                 |
| **Transit Gateway**           | - Birden fazla VPC ve on-premise ağı merkezi bir noktada bağlar.<br>- Transit Routing ile optimize edilmiş yönlendirme sunar.<br>- **Direct Connect** ve VPN ile entegre edilebilir.                                                           |
| **Bastion Host**              | - Private Subnet’teki kaynaklara güvenli SSH/RDP erişimi sağlar.<br>- Public Subnet’te yapılandırılır.<br>- **Session Manager** daha güvenli bir alternatif olarak kullanılabilir.                                                               |
| **High Availability (HA)**    | - **Multi-AZ:** Kaynakları birden fazla Availability Zone’a dağıtarak erişilebilirliği artırır.<br>- **Multi-Region:** Yedeklilik için farklı regionlarda yapılandırma sağlar.<br>- Felaket kurtarma stratejileri planlanmalıdır.               |
| **Route 53**                  | - AWS’in DNS hizmetidir.<br>- **Routing Policy Türleri:** Simple, Weighted, Latency-based, Failover, Geolocation.<br>- DNS yapılandırmaları ve domain yönetimi sağlar.                                                                          |
| **AWS Global Accelerator**    | - Global trafiği optimize eder ve düşük gecikme sunar.<br>- Anycast IP kullanır.<br>- Trafiği birden fazla bölgeye dağıtarak yüksek performans sağlar.                                                                                          |
| **PrivateLink**               | - AWS servislerine veya kendi uygulamalarına private bağlantı sağlar.<br>- Endpoint üzerinden özel erişim sağlar.<br>- SaaS uygulamalarına güvenli ve izole edilmiş erişim için uygundur.                                                      |
| **IPv6 ve Dual Stack**         | - VPC’yi hem IPv4 hem de IPv6’yı destekleyecek şekilde yapılandırır.<br>- IPv6 CIDR blokları ve NAT Gateway ile bağlantı yapılandırmaları.                                                                                                      |

---

### **Notlar Üzerine Ek Karşılaştırma**
- **NAT Gateway vs NAT Instance:**
  - NAT Gateway, AWS tarafından yönetilir ve daha kolay yapılandırılır.
  - NAT Instance, özel AMI ile özelleştirilebilir ama yönetimi zordur.
- **Endpoint vs VPC Peering:**
  - Endpoint, AWS servislerine internet çıkışı olmadan erişim sağlar.
  - VPC Peering, iki VPC arasında özel bağlantı kurar.

---

Bu tablo, senin notlarına ek olarak gerekli karşılaştırmaları ve açıklamaları içeriyor. Daha fazla detay veya düzenleme istersen, haber ver! 😊
















