
# Deploying an NGINX Web Server on AWS EC2 with a Custom Domain using Route 53 🌐 🖥️

In this assignment, I deployed my own NGINX web server on an AWS EC2 instance and connected it to a custom domain purchased through **Amazon Route 53**.




---

## 🖥️ Demo
**My Domain:** http://nginx.mosheikh.co.uk/  


<img width="1022" height="470" alt="Screenshot 2025-10-19 at 23 48 38" src="https://github.com/user-attachments/assets/b7933d8b-e523-4a30-bbeb-b108c850ff09" />

---

## Stage 1 – Registered a Domain with Route 53

I purchased a domain directly through **Amazon Route 53**.

**Steps:**
1. Opened the **Route 53 console** in AWS.
2. Navigated to **Registered domains** → **Register domain**.
3. Searched for and selected an available domain name: `mosheikh`.
4. Completed the registration process (including contact info and payment).
5. Waited for the domain status to change to **"Active"** (usually within minutes).

> 💡 Route 53 automatically creates a **public hosted zone** with the same name as your domain once registration is complete.



---

## Stage 2 – Launched EC2 Instance and Installed NGINX
 Setting Up an AWS EC2 Instance with NGINX

Below is the process I followed to deploy a web server using **NGINX** on an **AWS EC2 instance**.

---

1. **Opened the EC2 Dashboard**  
   - Made sure I was in the same AWS region as my **Route 53 hosted zone** (`eu-north-1`).

2. **Launched a New Instance**  
   - Selected **Ubuntu Server 22.04 LTS** (Free Tier eligible).  
   - Chose **t3.micro** as the instance type.

3. **Configured Security Group Rules**  
   - ✅ **SSH (Port 22)** — allowed only from **my IP address**.  
   - 🌍 **HTTP (Port 80)** — allowed from **anywhere (0.0.0.0/0)** to make the website publicly accessible.

4. **Connected to the Instance**  
   - Used **AWS EC2 Instance Connect** (browser-based SSH terminal) to access the server.

---

✅ *Result:* The EC2 instance was successfully launched and connected, ready for NGINX installation to serve web content.



6. **Updated the system and installed NGINX:**

   ```
   sudo apt update && sudo apt upgrade -y
   sudo apt install nginx -y
   sudo systemctl start nginx
   sudo systemctl enable nginx
   ```
7. **Verified NGINX was running:**
   ```
   systemctl status nginx
   ```
   ---

## Stage 3 – Configured DNS Records in Route 53

I linked my Route 53 domain to the EC2 instance so the site could be reached via the custom domain.

**Steps:**

1. Went to **Route 53** → **Hosted zones**.
2. Clicked on my domain: mosheikh.
3. Clicked **Create record**.
4. Added an **A record**:
  - Record name: nginx (so the full URL becomes nginx.mosheikhnginx)
  - Record type: A
  - Value: Public IPv4 address of my EC2 instance
  - TTL: 300 seconds (default)

5. Clicked **Create records**.

   ---
##  Stage 4 – Verifying DNS and Link to domain

I verified that my domain was correctly resolving and that the NGINX website was publicly reachable.

---

**Steps:**

### 1️⃣ Check DNS Resolution

From my local machine, I confirmed that the domain resolves to the EC2 instance’s public IP:

```
dig +short nginx.mosheikh.co.uk
# Expected output: <EC2-public-IP>
```
### 🔎 Tested connectivity

```
ping nginx.mosheikh.co.uk
```
  - Opened the following URL in a web browser:

🔗 http://nginx.mosheikh.co.uk

### ☑️ Confirmed Website Availability
Saw the default NGINX welcome page, confirming that:
  - The domain’s DNS configuration is correct.
  - The EC2 instance is serving web content publicly via NGINX.

✅ **DNS and web connectivity** successfully verified!

   

   
   



