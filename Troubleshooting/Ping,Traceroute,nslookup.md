# 🛠️ Troubleshooting with ping, traceroute, nslookup

---

## 🔑 Main Troubleshooting Tools

### 1️⃣ `ping`
- Tests **basic connectivity** between devices.  
- If reply = network works.  
- If no reply = possible network, DNS, or firewall issue.  
```bash
ping google.com
````

---

### 2️⃣ `traceroute` (Linux/macOS) / `tracert` (Windows)

* Shows the **path (hops)** data takes to reach a destination.
* Helps find where traffic is getting stuck.

```bash
traceroute google.com   # Linux/macOS
tracert google.com      # Windows
```

---

### 3️⃣ `nslookup`

* Queries DNS for the IP address of a domain.

```bash
nslookup google.com
```

* Confirms DNS is resolving correctly.

---

## 🚦 Troubleshooting Workflow

**Scenario: "I can’t reach a website."**

1. ✅ **Check basic connectivity**

   * `ping google.com` → If it works, internet is fine.
   * If not, try `ping 8.8.8.8` (Google DNS IP).

     * Works = DNS problem.
     * Doesn’t = network problem.

2. 🔎 **Check DNS resolution**

   * `nslookup google.com`
   * Confirms if DNS can translate name → IP.

3. 🧭 **Trace the path**

   * `traceroute google.com`
   * See if packets drop at a certain hop.

4. 🗂️ **Other checks**

   * Hosts file (`/etc/hosts`) → make sure no bad entries.
   * Firewall rules → not blocking outgoing traffic.
   * Browser issues → restart browser.
   * Clear DNS cache.
   * Check system logs for errors.

---

## ✅ Recap

* `ping` → is the host reachable?
* `traceroute` → where does traffic stop?
* `nslookup` → is DNS resolving names to IPs?
* Combine these tools to **pinpoint the issue fast** 🔍.

