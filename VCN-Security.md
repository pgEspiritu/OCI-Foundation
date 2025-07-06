# 🔐 OCI VCN Security – Summary

## 🔸 Security Lists
- Acts as **virtual firewalls** for **subnets**.
- Rules apply to **all instances** in the associated subnet.
- Rules define **inbound (ingress)** and **outbound (egress)** traffic.
- Can be:
  - **Stateful**: Response traffic is automatically allowed.
  - **Stateless**: Requires explicit return traffic rules.

### ✅ Example Rules
| Direction | Source CIDR            | Port  | Protocol | Description                        |
|----------|------------------------|-------|----------|------------------------------------|
| Ingress  | `0.0.0.0/0`            | 80    | TCP      | Allow HTTP traffic from internet   |
| Egress   | `10.0.0.0/24`          | 1521  | TCP      | DB traffic from public to private  |

### 🔒 Limitations
- **Applies to subnets** only.
- Rules use **CIDR blocks** for source/destination (no NSG reference).
- All instances in a subnet share the same rules.

---

## 🟢 Network Security Groups (NSGs)
- Acts as **firewall rules applied to individual VNICs**.
- Offers **more granular control** compared to Security Lists.
- NSGs can be **used as source/destination** in rules (not just CIDRs).
- Ideal for **instances in the same subnet** needing different rules.

### ✅ Benefits
- NSG rules can reference **other NSGs**.
- Allows **differentiated security** within the same subnet.
- More **modular and reusable**.

### 🆚 Security List vs NSG
| Feature                  | Security Lists         | Network Security Groups (NSGs)     |
|--------------------------|------------------------|-------------------------------------|
| Scope                   | Subnet-wide            | Individual VNICs                   |
| Source/Destination      | Only CIDR              | CIDR or NSG                        |
| Use Case                | Basic, broad rules     | Fine-grained, flexible control     |
| Reusability             | Low                    | High (can share across resources)  |
| Best For                | Simple architectures   | Complex or multi-tier setups       |

---

## 🧠 Key Takeaways
- Use **Security Lists** for **basic subnet-level protection**.
- Use **NSGs** for **instance-level control** and **microsegmentation**.
- Both constructs can be **used together** for layered security.
- Choose **stateful vs stateless** rules based on traffic requirements.

> 💡 Pro Tip: NSGs are best for complex applications with multiple tiers needing independent access control (e.g., Web → App → DB).
