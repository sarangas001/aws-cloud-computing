# Chapter 09 – Understanding IP Address in AWS (Public vs Private IPs)

> **Course:** AWS Cloud Computing Masterclass  
> **Chapter:** Understanding IP Address in AWS (Public vs Private IPs)  
> **Level:** Beginner

---

# 📚 Learning Objectives

After completing this chapter, you will be able to:

- Understand what an IP Address is.
- Learn what Internet Protocol (IP) means.
- Understand how devices communicate over a network.
- Differentiate between IPv4 and IPv6.
- Understand the difference between Public and Private IP addresses.
- Learn how AWS uses Private IP, Public IP, and Elastic IP.

---

# What is an IP Address?

An **IP Address (Internet Protocol Address)** is a unique address assigned to every device connected to a network.

It acts like a home address for computers and allows devices to communicate with each other.

Without an IP address, devices cannot send or receive data correctly.

> **Definition:** An IP Address is a unique identifier that allows devices to communicate over a network.

---

# What is the Internet?

The **Internet** is a **network of networks**.

It consists of many smaller networks connected together.

Examples:

- Home Wi-Fi
- Office Network
- School Network
- AWS Cloud Network

```text
                 Internet
                     │
      ┌──────────────┼──────────────┐
      │              │              │
 Home Network   Office Network   AWS Network
      │              │              │
 Laptop        Desktop PC      EC2 Instance
 Phone         Printer         Database
```

---

# What is a Protocol?

A **Protocol** is a set of rules that defines how devices communicate.

It controls:

- Data transmission
- Data formatting
- Addressing
- Routing

Without protocols, computers would not understand each other.

---

# Why Do Devices Need an IP Address?

Imagine sending a parcel.

The delivery company needs your address.

Similarly, computers need an IP address to know where data should be delivered.

```text
Computer A
     │
IP Address
     │
Computer B
```

Without an IP address:

- Data cannot reach the correct device.
- Communication becomes impossible.

---

# Types of IP Addresses

There are two major versions of IP addresses.

1. IPv4
2. IPv6

---

# IPv4 (Internet Protocol Version 4)

IPv4 is the older IP addressing system.

Example:

```text
192.168.1.1
```

Characteristics:

- Uses 32-bit addresses
- Four decimal numbers separated by dots
- Supports approximately **4.3 billion** unique addresses
- Still widely used today

Example format:

```text
XXX.XXX.XXX.XXX
```

---

# Why IPv6 Was Introduced

Today, billions of devices are connected to the internet.

Examples:

- Smartphones
- Laptops
- Tablets
- Smart TVs
- IoT Devices

IPv4 addresses became insufficient because every connected device requires a unique IP address.

---

# IPv6 (Internet Protocol Version 6)

IPv6 is the newer addressing system.

Example:

```text
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

Characteristics:

- Uses 128-bit addresses
- Much longer format
- Supports an enormous number of unique addresses
- Designed to replace IPv4

---

# IPv4 vs IPv6

| IPv4 | IPv6 |
|------|------|
| Older version | Newer version |
| 32-bit | 128-bit |
| Around 4.3 billion addresses | Virtually unlimited addresses |
| Decimal format | Hexadecimal format |
| Most commonly used | Growing adoption |

---

# Public IP Address

A **Public IP Address** is accessible from the Internet.

Characteristics:

- Visible to everyone
- Assigned by an Internet Service Provider (ISP)
- Globally unique
- Used for internet communication

Example:

```text
Internet
      │
Public IP
      │
Web Server
```

Use Cases:

- Websites
- APIs
- Public servers

---

# Private IP Address

A **Private IP Address** is used only inside a private network.

Characteristics:

- Not accessible from the internet
- Used within homes, offices, and private cloud networks
- Enables internal communication

Example:

```text
Home Wi-Fi

Laptop
   │
192.168.1.10
   │
Router
```

The internet cannot directly access this IP.

---

# Public IP vs Private IP

| Public IP | Private IP |
|-----------|------------|
| Accessible from the Internet | Internal network only |
| Globally unique | Unique only within the local network |
| Assigned by ISP | Assigned within the private network |
| Used for websites and servers | Used for internal communication |

---

# IP Addresses in AWS

AWS uses three important types of IP addresses:

- Private IP
- Public IP
- Elastic IP

---

# Private IP in AWS

Every EC2 instance automatically receives a **Private IP Address**.

Purpose:

- Communication within the AWS Virtual Private Cloud (VPC)
- Communication between AWS resources

Example:

```text
VPC

EC2 Instance A
Private IP: 10.0.1.10

        │

EC2 Instance B
Private IP: 10.0.1.20
```

Private IPs cannot be accessed directly from the Internet.

---

# Public IP in AWS

A Public IP allows an EC2 instance to be accessed from the Internet.

Example:

```text
Internet
      │
Public IP
      │
EC2 Instance
      │
Private IP
```

Use Cases:

- Hosting websites
- REST APIs
- SSH connections

---

# Elastic IP

An **Elastic IP (EIP)** is a **static public IP address** provided by AWS.

Unlike a normal Public IP:

- It remains the same even after restarting the EC2 instance.
- It can be reassigned to another EC2 instance if required.

---

# Why Use an Elastic IP?

Without Elastic IP:

```text
Restart EC2

↓

Public IP Changes
```

With Elastic IP:

```text
Restart EC2

↓

Same Public IP
```

Useful for:

- Production servers
- Fixed DNS records
- Stable public endpoints

---

# AWS IP Address Overview

```text
                EC2 Instance
                     │
      ┌──────────────┼──────────────┐
      │              │              │
 Private IP     Public IP     Elastic IP
      │              │              │
 Internal      Internet       Static Public
Communication    Access            Access
```

---

# Best Practices

- Use **Private IPs** for communication between AWS resources.
- Assign **Public IPs** only when internet access is required.
- Use **Elastic IPs** for production servers requiring a permanent public IP.
- Avoid exposing unnecessary resources to the internet.

---

# Key Terms

| Term | Meaning |
|------|---------|
| IP Address | Unique address assigned to a device |
| Internet | Network of interconnected networks |
| Protocol | Rules that govern communication |
| IPv4 | 32-bit Internet Protocol Version 4 |
| IPv6 | 128-bit Internet Protocol Version 6 |
| Public IP | Internet-accessible IP address |
| Private IP | Internal network IP address |
| Elastic IP | Static public IP in AWS |
| EC2 | Virtual server in AWS |
| VPC | Virtual Private Cloud |

---

# Interview Questions

### 1. What is an IP Address?

An IP Address is a unique identifier assigned to a device that enables communication over a network.

---

### 2. What is the difference between IPv4 and IPv6?

IPv4 uses 32-bit addresses and supports around 4.3 billion unique addresses, whereas IPv6 uses 128-bit addresses and supports a vastly larger address space.

---

### 3. What is the difference between Public IP and Private IP?

A Public IP is accessible from the internet, while a Private IP is used only within a private network.

---

### 4. What is a Private IP in AWS?

A Private IP is automatically assigned to every EC2 instance and is used for communication within the AWS VPC.

---

### 5. What is an Elastic IP?

An Elastic IP is a static public IP address that remains unchanged even if an EC2 instance is restarted.

---

### 6. Why is Elastic IP useful?

It provides a fixed public IP for production workloads, ensuring consistent connectivity and stable DNS mapping.

---

# Quick Revision

- ✅ IP stands for **Internet Protocol**.
- ✅ Every device connected to a network requires a unique IP address.
- ✅ IPv4 is the older addressing system.
- ✅ IPv6 provides a much larger address space.
- ✅ Public IPs are accessible from the internet.
- ✅ Private IPs are used for internal communication.
- ✅ Every EC2 instance automatically receives a Private IP.
- ✅ Elastic IP is a static Public IP that does not change after restarting an EC2 instance.

---

# Summary

An **IP Address** uniquely identifies devices on a network and enables communication between them. The Internet is a network of interconnected networks that follows Internet Protocol rules to transmit data. AWS assigns every EC2 instance a **Private IP** for internal communication within a VPC. If internet access is required, a **Public IP** can be assigned. For production workloads that require a permanent public address, AWS provides **Elastic IP**, a static public IP that remains unchanged even after instance restarts. Understanding IPv4, IPv6, Public IPs, Private IPs, and Elastic IPs is fundamental to designing secure and scalable AWS cloud environments.