# 🌍 IP & MAC Addresses

Networking relies on two key identifiers — **IP addresses** and **MAC addresses** — that help devices recognise each other and exchange data correctly.

---

## 🖥️ 1. IP Addresses
**Definition:** A unique address assigned to every device on a network.  
**Purpose:** Lets devices find and communicate with one another.

### 📘 IPv4
- **32-bit address**, written in decimal form.  
- Example: `192.168.0.5`  
- Contains 4 groups of numbers (0–255), separated by dots.  
- Supports around **4.3 billion unique addresses**.  
- Running low due to the huge number of connected devices.

### 📗 IPv6
- **128-bit address**, written in hexadecimal form.  
- Example: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`  
- Supports roughly **340 undecillion unique addresses** 😮  
- Offers:
  - A much larger address pool  
  - Easier address assignment  
  - Built-in security improvements

### 🧠 Why It Matters
- Devices use IPs to **locate** and **talk** to each other.  
- Without them, data wouldn’t know where to travel.

---

## 🪪 2. MAC Addresses
**Definition:** Media Access Control (MAC) address — a hardware identifier for a network interface.  
**Analogy:** Like a **fingerprint** for your device — no two are the same.

### 🧩 Format
- **48-bit address**, written in hexadecimal.  
- Example: `00:18:2B:4C:9D:EF`  
- Uses digits **0–9** and letters **A–F**.

### ⚙️ Role
- Works at the **Data Link Layer** (Layer 2) of the OSI Model.  
- Handles **direct device-to-device** communication within a LAN.  
- Ensures:
  - Your laptop connects to *your* router, not someone else’s.  
  - Packets reach the correct device locally.

### 🔐 Importance
- Vital for secure and organised local communication.  
- Helps manage access and prevent network conflicts.

---

## 🧾 Summary

| Type | Full Form | Layer | Purpose | Example |
|------|------------|--------|----------|----------|
| **IP Address** | Internet Protocol | Network Layer | Identifies devices across networks (global) | 192.168.0.5 |
| **MAC Address** | Media Access Control | Data Link Layer | Identifies devices within a local network | 00:18:2B:4C:9D:EF |

Together, **IP and MAC addresses** keep data moving accurately and securely from one device to another — globally and locally. 🌐
