# Chapter 11 – What is CIDR in AWS Networking? (IP Address Ranges)

> **Course:** AWS Cloud Computing Masterclass  
> **Chapter:** CIDR (Classless Inter-Domain Routing)  
> **Level:** Beginner

---

# 📚 Learning Objectives

After completing this chapter, you will be able to:

- Understand what CIDR is.
- Learn the structure of an IPv4 address.
- Understand Network Bits and Host Bits.
- Learn how CIDR notation works.
- Calculate the number of IP addresses in a CIDR block.
- Understand why CIDR is used in AWS VPCs.
- Learn common CIDR ranges used in AWS.

---

# What is CIDR?

**CIDR (Classless Inter-Domain Routing)** is a notation used to define a range of IP addresses.

AWS uses CIDR blocks when creating a VPC to specify the IP address range available for resources within that network.

> **Definition:** CIDR is a compact way of representing a network's IP address range.

Example:

```text
10.0.0.0/16
```

or

```text
192.168.1.0/24
```

---

# Why Do We Need CIDR?

Every device connected to a network requires a unique IP address.

Examples:

- EC2 Instance
- RDS Database
- Load Balancer
- NAT Gateway

Instead of assigning random IP addresses, AWS reserves a defined range using CIDR.

Example:

```text
VPC

10.0.0.0/16

├── EC2
├── RDS
├── Lambda
├── ECS
```

Every resource receives an IP from this range.

---

# Understanding IPv4 Address

An IPv4 address looks like this:

```text
192.168.1.10
```

It contains four numbers separated by dots.

Each section is called an **Octet**.

```text
192 . 168 . 1 . 10
```

Each octet uses **8 bits**.

Therefore,

```text
8 + 8 + 8 + 8 = 32 bits
```

So,

> **An IPv4 address consists of 32 bits.**

---

# Binary Representation

Computers understand only binary values (0 and 1).

Example:

```text
192

=

11000000
```

Every octet is represented using 8 binary digits.

Example:

```text
192.168.1.10

11000000
10101000
00000001
00001010
```

---

# Structure of an IP Address

An IP address consists of two parts:

- Network Portion
- Host Portion

```text
Network | Host
```

---

# Network Bits

The **Network Bits** identify which network the device belongs to.

Example:

```text
192.168.1.xxx
```

Every device sharing this network belongs to the same network.

---

# Host Bits

The **Host Bits** uniquely identify individual devices within that network.

Example:

```text
192.168.1.10

192.168.1.11

192.168.1.12
```

Notice:

Network portion remains the same.

Only the Host portion changes.

---

# Example

Suppose we have:

```text
192.168.1.0/24
```

This means:

```text
Network Bits = 24

Host Bits = 8
```

Visualization:

```text
192.168.1 | 10

Network    Host
```

Devices:

```text
192.168.1.10

192.168.1.11

192.168.1.12
```

All belong to the same network.

---

# Why Separate Network and Host?

Imagine a company network.

```text
Company Network

├── Laptop 1
├── Laptop 2
├── Server
├── Printer
```

All devices belong to the same network.

Each device still needs a unique IP.

Network bits identify the network.

Host bits identify the device.

---

# Why is This Important?

Routers use the **Network Portion** to decide where packets should be sent.

Once inside the correct network,

the **Host Portion** identifies the exact device.

This makes networking efficient.

---

# CIDR Notation

CIDR is written as:

```text
IP Address / Prefix Length
```

Example:

```text
192.168.1.0/24
```

Structure:

```text
192.168.1.0

↓

Base Network Address

/

24

↓

Prefix Length
```

---

# What is Prefix Length?

The number after the slash indicates how many bits are used for the **Network Portion**.

Example:

```text
192.168.1.0/24
```

Means:

```text
24 bits

↓

Network

8 bits

↓

Host
```

---

# Visual Representation

```text
32 Bits Total

|-------------------------------|

24 Bits          8 Bits

Network          Host
```

---

# Example of /24

CIDR:

```text
192.168.1.0/24
```

Network:

```text
192.168.1
```

Host:

```text
0 - 255
```

Possible devices:

```text
192.168.1.1

192.168.1.2

192.168.1.50

192.168.1.100
```

---

# Formula to Calculate Number of IP Addresses

The formula is:

```text
2^(32 - Prefix Length)
```

Example:

CIDR:

```text
/24
```

Calculation:

```text
32 - 24 = 8

2^8 = 256
```

AWS reserves some addresses in every subnet, so a `/24` subnet has **256 total addresses**, but fewer are usable (the instructor simplified this to about **254 usable addresses**).

---

# Common CIDR Sizes

| CIDR | Total IP Addresses |
|------|-------------------:|
| /30 | 4 |
| /29 | 8 |
| /28 | 16 |
| /27 | 32 |
| /26 | 64 |
| /25 | 128 |
| /24 | 256 |
| /23 | 512 |
| /22 | 1,024 |
| /21 | 2,048 |
| /20 | 4,096 |
| /19 | 8,192 |
| /18 | 16,384 |
| /17 | 32,768 |
| /16 | 65,536 |

> **Note:** AWS reserves **5 IP addresses** in every subnet, so the number of usable IPs is slightly lower than the total.

---

# Example (/24)

```text
10.0.0.0/24
```

Network:

```text
10.0.0
```

Hosts:

```text
10.0.0.1

↓

10.0.0.254
```

---

# Example (/16)

```text
10.0.0.0/16
```

Network:

```text
10.0
```

Hosts:

```text
10.0.x.x
```

This provides a much larger address space.

---

# CIDR in AWS VPC

When creating a VPC, AWS asks for a CIDR block.

Example:

```text
VPC

CIDR

10.0.0.0/16
```

Every subnet and every AWS resource receives an IP from this range.

Example:

```text
VPC

10.0.0.0/16

├── Public Subnet

│      10.0.1.0/24

├── Private Subnet

│      10.0.2.0/24

├── EC2

│      10.0.1.10

├── RDS

│      10.0.2.50
```

---

# Online CIDR Calculator

You don't always have to calculate CIDR manually.

A CIDR calculator helps determine:

- Network Address
- Broadcast Address
- First Usable IP
- Last Usable IP
- Total IP Addresses
- Usable IP Addresses
- Netmask

These tools are useful when designing VPCs and subnets.

---

# Best Practices

- Plan CIDR blocks before creating a VPC.
- Avoid overlapping CIDR ranges.
- Leave room for future growth.
- Use larger CIDR blocks if many resources are expected.
- Separate environments (Development, Testing, Production) into different CIDR ranges.

---

# Key Terms

| Term | Meaning |
|------|---------|
| IPv4 | 32-bit Internet Protocol address |
| Bit | Smallest unit of binary data (0 or 1) |
| Octet | 8-bit section of an IPv4 address |
| Network Bits | Identify the network |
| Host Bits | Identify devices within the network |
| CIDR | Classless Inter-Domain Routing |
| Prefix Length | Number of bits reserved for the network |
| Base Network Address | Starting IP of the network |

---

# Interview Questions

### 1. What is CIDR?

CIDR (Classless Inter-Domain Routing) is a notation used to represent a range of IP addresses.

---

### 2. Why is CIDR used in AWS?

It defines the IP address range for a VPC or subnet, allowing AWS to allocate private IP addresses to resources.

---

### 3. What is the structure of an IPv4 address?

An IPv4 address is 32 bits long and consists of four 8-bit octets.

---

### 4. What are Network Bits?

Network Bits identify the network to which a device belongs.

---

### 5. What are Host Bits?

Host Bits uniquely identify devices within a network.

---

### 6. What does `/24` mean?

It means 24 bits are used for the network portion, leaving 8 bits for host addresses.

---

### 7. What is the formula for calculating the total number of IP addresses?

```text
2^(32 - Prefix Length)
```

---

### 8. How many total IP addresses are in a `/24` network?

A `/24` network contains **256 total IP addresses** (AWS reserves 5 addresses in each subnet).

---

### 9. What CIDR block is commonly used when creating an AWS VPC?

Examples include:

```text
10.0.0.0/16

172.31.0.0/16

192.168.0.0/16
```

---

# Quick Revision

- ✅ IPv4 addresses contain 32 bits.
- ✅ Each octet contains 8 bits.
- ✅ IP addresses consist of Network Bits and Host Bits.
- ✅ CIDR defines an IP address range.
- ✅ CIDR format is `IP Address/Prefix Length`.
- ✅ `/24` means 24 network bits and 8 host bits.
- ✅ Larger prefix = Smaller network.
- ✅ Smaller prefix = Larger network.
- ✅ AWS VPCs require a CIDR block.
- ✅ Plan CIDR ranges carefully to avoid overlap.

---

# Summary

CIDR (Classless Inter-Domain Routing) is a compact notation used to define IP address ranges in AWS networking. Every IPv4 address consists of **32 bits**, divided into **Network Bits** and **Host Bits**. The **prefix length** in CIDR notation determines how many bits identify the network, while the remaining bits identify individual hosts. AWS requires a CIDR block when creating a VPC so that private IP addresses can be assigned to resources such as EC2 instances and RDS databases. Understanding CIDR is fundamental for designing scalable, secure, and efficient AWS networks.