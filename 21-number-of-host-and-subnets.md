# 🧮 Number of Hosts & Subnets in Networking

---

## 🧠 The Big Idea

When subnetting, we split an IP network into **multiple smaller subnets**. This changes two things:

- 🔢 How many **subnets** you can make
- 👥 How many **hosts** (devices) can exist per subnet

The math behind it is simple—but powerful. Let’s break it down!

---

## 🔣 Formulae You MUST Know

### 🔹 Number of Subnets:
```
Number of subnets = 2^n
```
Where `n` = number of **borrowed bits** from the host portion

### 🔹 Number of Hosts per Subnet:
```
Number of hosts = 2^h - 2
```
Where `h` = number of **host bits** left

> 🧨 Subtract 2 for:
> - 1️⃣ Network Address (all 0s)
> - 📢 Broadcast Address (all 1s)

---

## 📊 Quick Reference Table

| CIDR | Subnet Mask         | # Subnets (from /24) | # Hosts/Subnet |
|------|----------------------|-----------------------|----------------|
| /24  | 255.255.255.0        | 1                     | 254            |
| /25  | 255.255.255.128      | 2                     | 126            |
| /26  | 255.255.255.192      | 4                     | 62             |
| /27  | 255.255.255.224      | 8                     | 30             |
| /28  | 255.255.255.240      | 16                    | 14             |
| /29  | 255.255.255.248      | 32                    | 6              |
| /30  | 255.255.255.252      | 64                    | 2              |

> 🔥 If you start with a /24 network and go down, you’re **borrowing bits** from the host side to make more subnets.

---

## 🧪 Examples You’ll Love

### Example 1:
```
Network: 192.168.10.0/26
CIDR = /26 → Host bits = 6
Number of hosts = 2^6 - 2 = 62
```

### Example 2:
```
You want 4 subnets from a /24 block
→ You need 2 bits (2^2 = 4)
→ /24 + 2 = /26
→ Subnet mask = 255.255.255.192
```

---

## 🧠 Binary Insight

Subnetting is all about **bit manipulation**:
- Borrow from host bits → More subnets, fewer hosts
- Leave more host bits → Fewer subnets, more hosts

Think of bits like LEGO blocks. Snap 'em how you want! 🧱

---

## 💎 Hidden Gems (Interview Juice)

- Maximum number of subnets = 2^n
- Maximum number of hosts = 2^h - 2
- /31 and /32 are special:
  - `/31` = 2 addresses but **no broadcast**, used for **point-to-point** links
  - `/32` = 1 address, often used for **loopbacks**
- More subnets = smaller broadcast domains → 🛡️ better performance

---

## 📌 TL;DR Summary

- More **borrowed bits** = more subnets, fewer hosts
- More **host bits** = fewer subnets, more hosts
- Use the 2^n and 2^h - 2 formulas to quickly calculate!
- Bitwise subnetting = Real power in networking

> _“It’s not just math—it’s control over your network’s DNA.”_ 💡

---
