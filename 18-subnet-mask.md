# 🧩 Subnet Masks in Computer Networking

---

## 🧠 What Is a Subnet Mask?

A **subnet mask** is a 32-bit number that tells devices **which part of an IP address** represents the **network** and which part represents the **host**.

> Think of it like a filter 🔍 that separates the neighborhood (network) from the house number (host).

---

## 💡 How It Works

### Example:
```
IP Address:      192.168.10.15
Subnet Mask:     255.255.255.0
```
Breakdown in binary:
```
IP:   11000000.10101000.00001010.00001111
Mask: 11111111.11111111.11111111.00000000
```

- `1`s in the subnet mask = network part
- `0`s in the subnet mask = host part

So here:
- Network = `192.168.10`
- Host = `15`

---

## 📊 Common Subnet Masks (with CIDR)

| CIDR | Subnet Mask         | Hosts per Subnet |
|------|----------------------|------------------|
| /8   | 255.0.0.0            | 16,777,214       |
| /16  | 255.255.0.0          | 65,534           |
| /24  | 255.255.255.0        | 254              |
| /25  | 255.255.255.128      | 126              |
| /26  | 255.255.255.192      | 62               |
| /27  | 255.255.255.224      | 30               |
| /28  | 255.255.255.240      | 14               |
| /29  | 255.255.255.248      | 6                |
| /30  | 255.255.255.252      | 2                |

> ⚠️ Always subtract 2: one for network address, one for broadcast.

---

## 🎯 Why Are Subnet Masks Important?

- They **enable subnetting**
- Help routers **know where to send packets**
- Prevent IP conflicts and **organize networks**
- Allow **more efficient IP address usage**

---

## 🧪 Pro Tip: Quick Binary Guide

| Octet Value | Binary        |
|-------------|---------------|
| 255         | 11111111      |
| 254         | 11111110      |
| 252         | 11111100      |
| 248         | 11111000      |
| 240         | 11110000      |
| 224         | 11100000      |
| 192         | 11000000      |
| 128         | 10000000      |
| 0           | 00000000      |

> 🔍 Use this table to calculate subnet masks fast in exams/interviews.

---

## 📱 Real-World Analogy

> Imagine a phone number:
> - Country Code = Network
> - Local Number = Host
> 
> Subnet mask tells your phone where the **area code ends** and **local number starts**. Without it? Pure chaos.

---

## 💎 Hidden Gems (Stuff Interviewers Love)

- The default subnet mask for:
  - Class A = `255.0.0.0`
  - Class B = `255.255.0.0`
  - Class C = `255.255.255.0`
- Subnet mask must be **contiguous 1s from left to right** (no mix like `11111110.11111111.00000001.00000000`)
- CIDR was introduced to **break away from rigid classes**

---

## 📌 TL;DR Summary

- Subnet mask tells which part of an IP is **network** and which is **host**
- Works hand-in-hand with IP address and CIDR
- Essential for **routing**, **subnetting**, and **IP planning**
- The sharper you get with binary, the easier subnetting becomes

> _“Without subnet masks, IP addresses are just confused numbers.”_ 🧠

---
