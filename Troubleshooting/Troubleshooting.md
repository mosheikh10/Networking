# 🛠️ Network Troubleshooting Essentials

---

## 🚦 Why troubleshooting matters
- ✅ Keeps networks healthy (like routine car servicing 🚗).  
- 🕵️ Lets you **find & fix issues** fast.  
- ⏱️ Reduces downtime — saves time, money, and headaches.

---

## ⚡ Typical network problems
1. **Connectivity loss**  
   - Symptoms: sudden disconnection, no internet access.  
   - Possible causes: faulty hardware, broken cables, router misconfig, ISP outage.

2. **Slow performance**  
   - Symptoms: pages load slowly, downloads are sluggish.  
   - Possible causes: congestion, bad configs, failing equipment.

3. **IP address conflicts**  
   - Symptoms: devices intermittently drop off the network.  
   - Cause: two devices using the same IP (like two houses sharing one address 🏠🏠).

4. **DNS failures**  
   - Symptoms: domain names won’t resolve (browser can’t find sites).  
   - Causes: DNS misconfiguration, stale cache, unreachable DNS servers.

---

## 🔍 Simple troubleshooting process

### 1. Observe
- Is it a full outage or just slow?  
- A single device affected or many?  
- Any physical signs (loose/damaged cables, LED errors)?

### 2. Verify configuration
- Inspect router/firewall settings.  
- Check IP address, subnet mask, gateway, DNS entries on affected devices.  
- Look for duplicates or obvious misconfigs.

### 3. Test basic connectivity
- Try a basic ping:
```bash
ping google.com
````

* Success = device can reach network/Internet.
* Failure = problem with network config, DNS, or connection.

### 4️⃣ Use Basic Tools

* **`ping`** → check connectivity.
* **`traceroute` / `tracert`** → check packet path.
* **`nslookup` / `dig`** → check DNS.

---

## 📝 Quick Checklist

* 🔌 Are cables plugged in?
* 📶 Is Wi-Fi connected?
* 🖥️ Does the device have a valid IP?
* 🌍 Can you ping a public address (e.g., 8.8.8.8)?
* 🧾 Any recent config changes?

---

## ✅ Recap

* Troubleshooting = detective work 🕵️.
* Start **simple** (cables, IPs, configs).
* Use **commands/tools** to test step by step.
* Goal: identify root cause, fix fast, reduce downtime.
