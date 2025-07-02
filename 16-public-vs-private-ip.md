# 🌍 Public vs Private IP Addresses

---

## 🧠 What Is an IP Address Again?

An **IP address** uniquely identifies a device on a network. But not all IPs are the same—some stay in your house (private), and some go out to the world (public).

---

## 🏠 Private IP Addresses

Private IPs are **used inside local networks** like your home Wi-Fi, school LAN, or office network.

### 🔒 Key Points:
- Not routable on the internet
- Used for internal communication only
- Assigned by your router via DHCP
- You can reuse the same private IPs in different networks

### 📦 Reserved Private Ranges:

| Class | Private IP Range              | Example         |
|-------|-------------------------------|-----------------|
| A     | 10.0.0.0 – 10.255.255.255     | 10.0.0.5        |
| B     | 172.16.0.0 – 172.31.255.255   | 172.16.1.100    |
| C     | 192.168.0.0 – 192.168.255.255 | 192.168.1.1     |

> 🔁 Devices within the same private network can talk to each other using private IPs only.

---

## 🌐 Public IP Addresses

Public IPs are **globally unique** and **routable over the internet**.

### 🌎 Key Points:
- Assigned by ISPs or hosting providers
- Required to communicate on the internet
- You only get **one public IP** per router in most homes
- Cost money for companies to own in bulk

Example: `8.8.8.8` (Google DNS) or your home router’s IP like `43.245.87.10`

---

## 🔄 How They Work Together

> 🔧 Your router uses **NAT (Network Address Translation)** to map all your local devices (private IPs) to the single public IP you have.

### Example:
- Your phone: `192.168.1.5`
- Your PC: `192.168.1.10`
- Your router: `192.168.1.1` (internal) + `45.72.98.13` (public)

When both devices request Google.com, the router sends them using its **public IP**, and Google sees the request from one IP: `45.72.98.13`.

NAT handles the traffic separation internally.

---

## 🧪 Pro Tip: Find Yours

- **Private IP** (your device):
```bash
# Windows
ipconfig

# Linux/macOS
ifconfig or ip addr
```

- **Public IP** (your router):
Visit [https://whatismyipaddress.com](https://whatismyipaddress.com) or just Google “What is my IP”

---

## 🔐 Why Keep Some IPs Private?

- 🔒 Security: Avoid exposing devices directly to the internet
- 🤑 Conservation: IPv4 address space is limited
- 🔁 Reusability: No conflict when used in different networks

---

## 📌 TL;DR Summary

| Property         | Private IP                  | Public IP               |
|------------------|-----------------------------|--------------------------|
| Scope            | Local network only          | Internet-wide            |
| Unique globally? | ❌ No                       | ✅ Yes                  |
| Can access web?  | ❌ Needs NAT                | ✅ Directly              |
| Who assigns it?  | Router/DHCP                 | ISP/IANA                 |

> _“Private IPs keep it in the fam. Public IPs go out there and represent you to the world.”_ 🌐🧍

---
