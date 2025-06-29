# 🧱 IPv4 Address Classes (A, B, C, D, E)

---

## 🧠 What Are IP Classes?

When IPv4 was designed, addresses were split into **classes** to accommodate networks of different sizes. This old-school method is called **classful addressing** (before CIDR came along).

Each class is defined by the **first few bits** of the IP address and has a fixed **range**.

---

## 📊 Overview Table

| Class | First Octet Range | Starting Bits | Default Subnet Mask | Hosts Per Network | Use Case           |
|-------|--------------------|----------------|----------------------|-------------------|--------------------|
| A     | 1 - 126            | 0xxx           | 255.0.0.0            | ~16 million       | Large networks     |
| B     | 128 - 191          | 10xx           | 255.255.0.0          | ~65,000           | Medium networks    |
| C     | 192 - 223          | 110x           | 255.255.255.0        | 254               | Small networks     |
| D     | 224 - 239          | 1110           | N/A                  | N/A               | Multicasting       |
| E     | 240 - 255          | 1111           | N/A                  | N/A               | Research (reserved) |

> ⚠️ 127.x.x.x is **reserved** for loopback testing (like 127.0.0.1)

---

## 🔍 Class A: The Giants
- **Range**: 1.0.0.0 to 126.255.255.255
- **Network Bits**: 8, **Host Bits**: 24
- **Default Mask**: 255.0.0.0
- **Total Hosts per Network**: 16,777,214

🧠 *Used by* ISPs and very large corps. Example: `10.0.0.1`

---

## 🔍 Class B: The Middle Ground
- **Range**: 128.0.0.0 to 191.255.255.255
- **Network Bits**: 16, **Host Bits**: 16
- **Default Mask**: 255.255.0.0
- **Total Hosts per Network**: 65,534

🧠 *Used by* universities, companies, and large orgs. Example: `172.16.0.1`

---

## 🔍 Class C: For the Locals
- **Range**: 192.0.0.0 to 223.255.255.255
- **Network Bits**: 24, **Host Bits**: 8
- **Default Mask**: 255.255.255.0
- **Total Hosts per Network**: 254

🧠 *Used by* small offices and home networks. Example: `192.168.1.1`

---

## 🔍 Class D: Multicast Masters
- **Range**: 224.0.0.0 to 239.255.255.255
- **Purpose**: Reserved for **multicasting**
- **No subnet mask**, not for host assignment.

🧠 Used for streaming, conference calls, routing protocols.

---

## 🔍 Class E: Research & Reserved
- **Range**: 240.0.0.0 to 255.255.255.255
- Reserved for **experimental and future use**.

🧠 Not used in public networks.

---

## 🧪 Pro Tip for Practicals

Run this Python snippet to find the class of an IP:

```python
ip = input("Enter IP address: ")
first_octet = int(ip.split('.')[0])

if 1 <= first_octet <= 126:
    print("Class A")
elif 128 <= first_octet <= 191:
    print("Class B")
elif 192 <= first_octet <= 223:
    print("Class C")
elif 224 <= first_octet <= 239:
    print("Class D")
elif 240 <= first_octet <= 255:
    print("Class E")
else:
    print("Invalid or reserved IP")
```

---

## 📌 TL;DR Summary

- Class A = Big bois 🏢
- Class B = Medium-sized orgs 🏫
- Class C = Homes and SMBs 🏠
- Class D = Multicast party 🎥
- Class E = Top-secret lab stuff 🧪

> _“Classes were the OG way of organizing the IP universe, before CIDR came and said, ‘Nah, we can do better.’”_ 💡

---
