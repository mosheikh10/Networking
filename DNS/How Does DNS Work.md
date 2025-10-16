# 🌍 How DNS Works – Resolution, Hierarchy & Process

DNS = the process of turning **domain names → IP addresses** so browsers can find websites.  





<img width="1256" height="635" alt="Screenshot 2025-10-16 at 17 28 15" src="https://github.com/user-attachments/assets/ce8fea41-2271-4c1d-b25a-87fb79591958" />



- **Root Servers** 👑 → Know where to find TLDs (but not domains directly).  
- **TLD Servers** 🏢 → Store info for extensions like `.com`, `.org`.  
- **Authoritative Servers** 👨‍💼 → Store actual DNS records (A, MX, CNAME, etc.).  
- **Zone File** 📂 → Lives inside authoritative servers and contains the records.

  ## 🔎 Step-by-Step example of  DNS Resolution


<img width="1248" height="674" alt="Screenshot 2025-10-16 at 17 42 49" src="https://github.com/user-attachments/assets/88763be1-5c94-4978-9512-98862065daea" />


- When you type `google.com` into your browser:

- Browser checks local cache + /etc/hosts 🖥️
│
└─> If found → returns IP ✅ Done.
│
▼
 If not found :

### **1️⃣ User → DNS Resolver**
- You type `www.google.com` in your browser.
- Your computer sends the request to the **DNS Resolver** .
- Think of the DNS Resolver as a librarian who knows where to find books/information.

---

### **2️⃣ Resolver → Root Server**
- The resolver asks:  
  > “Hey Root Server, do you know where `www.google.com` is?”
- The **Root Server** doesn’t know the exact IP, but it knows who handles `.com` domains.

---

### **3️⃣ Root Server → Resolver**
- The root server replies:  
  > “Go ask the `.com` TLD server.”

---

### **4️⃣ Resolver → TLD Server**
- The resolver asks the **TLD Server** (Top-Level Domain Server):  
  > “Do you know where `www.google.com` is?”

---

### **5️⃣ TLD Server → Resolver**
- The TLD server replies:  
  > “I don’t know the IP, but I know which **Authoritative Name Server** manages `google.com`.”

---

### **6️⃣ Resolver → Authoritative Name Server**
- The resolver now asks:  
  > “Hey Authoritative Name Server, what’s the IP for `www.google.com`?”

---

### **7️⃣ Authoritative Name Server → Resolver**
- The authoritative server replies with the **final answer**:  
  > `142.250.180.14`

---

### **8️⃣ Resolver → User**
- The resolver sends that IP address back to your browser.
- Your browser can now connect directly to Google’s web server ✅

---

## 🧩 Summary Table

| Step | Who Talks to Who | What Happens |
|------|------------------|---------------|
| 1 | User → DNS Resolver | User requests `www.google.com` |
| 2 | Resolver → Root Server | Resolver asks who handles `.com` |
| 3 | Root Server → Resolver | Root tells to go to `.com` TLD |
| 4 | Resolver → TLD Server | Asks `.com` server about `google.com` |
| 5 | TLD Server → Resolver | TLD points to Authoritative Name Server |
| 6 | Resolver → Authoritative Server | Asks for the IP |
| 7 | Authoritative Server → Resolver | Returns `142.250.180.14` |
| 8 | Resolver → User | Sends IP back to the browser |

---

## 🔁 Bonus: Caching

- After the resolver finds the IP, it **stores (caches)** the result temporarily.
- Next time you visit the same website, it loads **much faster** since it skips all previous steps.



## 🏢 Domain Registrar vs DNS Hosting

- **Domain Registrar** → The company where you **purchase and register** your domain name (e.g., GoDaddy, Namecheap, Google Domains).  
- **DNS Hosting Provider** → The service that **stores and manages your DNS records** (e.g., Cloudflare, AWS Route 53, Azure DNS).  
- These can be **the same provider** or **completely separate**, depending on where you choose to host and manage your domain settings.  

---

## ✅ Summary

- The **DNS system** follows a **hierarchical structure**: **Root 👑 → TLD 🏢 → Authoritative 👨‍💼**.  
- **Resolvers** handle the job of moving through each layer to find the right IP.  
- **Typical flow:** Local Cache → Resolver → Root Server → TLD Server → Authoritative Server → IP → Browser.  
- **Registrars** handle domain ownership, while **DNS hosts** handle how those domains are connected to actual IP addresses.  
