# 🚀 OCI Compute Instance Demo

In this demo, we'll:
- Manually build a **Virtual Cloud Network (VCN)**
- Set up **routing**, **internet gateway**, and **security list**
- Launch a **Compute Instance**
- Install **Apache Web Server** on it

---

## 🏗️ Step 1: Create VCN (Manually)

1. **Go to:** OCI Console > Virtual Cloud Network
2. **Click:** Create VCN
3. **Name:** `IAD-VCN-demo`
4. **CIDR Block:** Use default (e.g., `10.0.0.0/16`)
5. **Create VCN**

---

## 🌐 Step 2: Create Public Subnet

1. **Click:** Create Subnet
2. **Name:** `subnet-1`
3. **Type:** Regional
4. **CIDR Block:** `10.0.0.0/24`
5. **Subnet Access Type:** Public
6. Use default **Route Table** and **Security List**
7. **Create Subnet**

---

## 🌍 Step 3: Create Internet Gateway

1. **Name:** `IGW`
2. **Click:** Create Internet Gateway

---

## 📡 Step 4: Update Route Table

1. Go to **Default Route Table**
2. Click **Add Route Rule**
3. **Target Type:** Internet Gateway
4. **Destination CIDR Block:** `0.0.0.0/0`
5. **Target:** Select `IGW`
6. Click **Add Route Rule**

---

## 🔐 Step 5: Modify Security List

1. Go to **Default Security List**
2. Add **Ingress Rule**:
   - **Source CIDR:** `0.0.0.0/0`
   - **Port:** 80 (HTTP)
   - **Protocol:** TCP
3. Save the rule

---

## ☁️ Step 6: Create Compute Instance

1. **Go to:** Compute > Instances
2. **Click:** Create Instance
3. **Name:** Any
4. **AD & Fault Domain:** Leave default
5. **Image:** Oracle Linux
6. **Shape:** VM.Standard.A1.Flex (1 OCPU, 6 GB RAM)
7. **VCN/Subnet:** Select the VCN and `subnet-1`
8. **Public IP:** Assign Automatically
9. **SSH Key:**
   - Use your **public key** from Cloud Shell
   - Paste under "Paste Public Keys"
10. Click **Create**

---

## 🔑 Step 7: SSH Into Instance

From Cloud Shell or terminal:

```bash
ssh -i demo_key opc@<public-ip>
```

---

## 🧰 Step 8: Install Apache Web Server
Once connected via SSH, run:

```bash
sudo yum -y install httpd
sudo systemctl start httpd
sudo systemctl enable httpd
echo "This is a web server running on OCI" | sudo tee /var/www/html/index.html
```
Ensure firewall is open (already done in security list).

---

## 🌐 Step 9: Access Web Server
Open your browser and go to:

```http
http://<public-ip>
```
✅ You should see:
> This is a web server running on OCI

---

## 🧠 Recap
- Built network infrastructure manually
- Configured routing and security
- Launched a compute instance
- Installed and tested Apache web server


