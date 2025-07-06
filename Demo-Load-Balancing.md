# 🚀 OCI Load Balancer Demo – Summary

## 🗺️ Topology Overview
- **VCN** with:
  - 🔹 **Public Subnet** (for Load Balancer)
  - 🔹 **Private Subnet** (for Web Servers)
- **2 Web Servers** hosted in the **Private Subnet**
- **Public Load Balancer** in the **Public Subnet**
- **Load Balancer** handles HTTP traffic and distributes to backends

---

## 🛠️ Step-by-Step Breakdown

### 1. **Create VCN with Internet Connectivity**
- Use the **VCN Wizard** in the **Networking** section.
- Accept defaults:
  - VCN CIDR: `10.0.0.0/16`
  - Public Subnet: `10.0.0.0/24`
  - Private Subnet: `10.0.1.0/24`

---

### 2. **Update Security List**
- Navigate to:
  - VCN → Security Lists → Default Security List
- Add **ingress rule** to allow HTTP traffic:
  - Source CIDR: `0.0.0.0/0`
  - Destination Port: `80`

---

### 3. **Create Web Server Instances (Compute)**
- Create two **instances**:
  - **Web Server 1**
  - **Web Server 2**
- Use **Private Subnet** (no public IP)
- No SSH required
- Add **startup script** to install Apache and modify index.html:
```bash
#!/bin/bash
sudo yum -y install httpd
echo "Hello World! My name is web server 1" > /var/www/html/index.html
sudo systemctl enable httpd
sudo systemctl start httpd
```

(For Web Server 2, change the message accordingly.)

---

### 4. **Provision the Load Balancer**
- Go to Networking → Load Balancer
- Choose Layer 7 (HTTP) Public Load Balancer
- Select:
  - Public Subnet for the LB
  - Ephemeral public IP
- Use Weighted Round Robin as the load balancing policy
- Add both Web Server 1 and Web Server 2 as backends
- Health Check:
  - Protocol: `HTTP`
  - Port: `80`

---

### 5. **Configure Listener*
- Listener Type: `HTTP`
- Port: `80`
- Disable logging for demo simplicity

---

### 6. **Validate Setup*
- After provisioning:
  - Backend status should show "OK"
  - Load balancer will display a public IP
- Open the IP in a browser:
  - Refreshing alternates between:
    - "Hello World! My name is web server 1"
    - "Hello World! My name is web server 2"
- Confirms weighted round-robin is working

---

## ✅ Key Outcomes
- Public traffic is routed to private web servers securely.
- No need to expose backend servers with public IPs.
- Load balancer ensures high availability and scalability.

---

## 🎯 Key Takeaways
- OCI Load Balancer supports backend in private subnet via public frontend.
- Weighted round robin helps in evenly distributing requests.
- Startup scripts are effective for rapid provisioning.
- Layer 7 LB is simple to configure for HTTP-based applications.

>💡 Ideal for deploying scalable, secure web apps without exposing compute nodes.
