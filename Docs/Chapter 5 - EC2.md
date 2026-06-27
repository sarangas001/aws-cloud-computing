# Chapter 06 – Amazon EC2 (Elastic Compute Cloud)

> **Course:** AWS Cloud Computing Masterclass
> **Chapter:** 06 - Amazon EC2 (Elastic Compute Cloud)
> **Level:** Beginner
> **Notes Prepared By:** ChatGPT

---

# 📚 Learning Objectives

After completing this chapter, you should be able to:

* Understand what Amazon EC2 is.
* Learn why EC2 is one of the most important AWS services.
* Understand the meaning of **Elastic**, **Compute**, and **Cloud**.
* Learn the core EC2 concepts:

  * EC2 Instance
  * AMI
  * EBS
* Understand different use cases of EC2.
* Learn how organizations use EC2 instead of maintaining physical servers.

---

# 🚀 What is Amazon EC2?

**Amazon EC2 (Elastic Compute Cloud)** is an AWS service that allows users to **rent virtual servers in the cloud**.

Instead of purchasing physical servers, AWS provides virtual machines that you can create, configure, and manage on demand.

> **Definition:** Amazon EC2 is a cloud computing service that provides scalable virtual servers, allowing users to run applications without owning physical hardware.

---

# Understanding the Name "Elastic Compute Cloud"

The name **Elastic Compute Cloud** has three parts.

## 1. Elastic

Elastic means **flexible**.

You can:

* Launch one server
* Launch hundreds of servers
* Increase CPU or RAM
* Decrease resources when no longer needed

This flexibility allows businesses to scale according to demand.

---

## 2. Compute

Compute refers to the processing power provided by a virtual machine.

This includes:

* CPU
* RAM
* Operating System
* Installed Software
* Networking

An EC2 instance behaves like your own computer hosted in the cloud.

---

## 3. Cloud

Cloud means the server is hosted inside AWS data centers rather than on your local computer or office.

You access it through the Internet.

---

# Traditional Servers vs Amazon EC2

## Traditional Infrastructure

```text
Company
│
├── Buy Physical Servers
├── Install in Office
├── Maintain Hardware
├── Upgrade Hardware
└── Replace Failed Components
```

Problems:

* Expensive
* Time-consuming
* Requires IT staff
* Difficult to scale

---

## Using Amazon EC2

```text
Company
│
└── AWS EC2
      │
      ├── Create Server
      ├── Select CPU
      ├── Select RAM
      ├── Launch
      └── Pay Only for Usage
```

No physical hardware is required.

AWS manages the infrastructure while you focus on your applications.

---

# Why Organizations Use EC2

Instead of maintaining expensive physical servers, organizations simply rent virtual servers from AWS.

Benefits include:

* No hardware purchase
* Fast deployment
* Easy scaling
* Global availability
* Pay-as-you-go pricing
* High reliability

---

# Pay-As-You-Go Pricing

Amazon EC2 follows a **Pay-As-You-Go** pricing model.

This means you pay only for the time and resources you actually use.

Example:

* Launch a server for 2 hours.
* Stop the server.
* Pay only for those 2 hours (or per-second billing where applicable).

There is no need to purchase expensive hardware upfront.

---

# Core Concepts of Amazon EC2

Three important concepts are frequently used with EC2.

```text
Amazon EC2
│
├── Instance
├── AMI
└── EBS
```

---

# 1. EC2 Instance

## Definition

An **EC2 Instance** is a running virtual server created using the Amazon EC2 service.

Whenever you launch a virtual machine in AWS, it is called an **Instance**.

---

## Real-World Analogy

Imagine renting an apartment.

The apartment already exists.

Once you rent and occupy it,

it becomes **your living space**.

Similarly,

AWS provides virtual machines.

When you launch one,

it becomes **your EC2 Instance**.

---

## Example

You create:

* Ubuntu Server
* 2 vCPUs
* 4 GB RAM

After launching,

AWS creates an EC2 Instance.

---

# Instance Types

EC2 instances are available in many sizes.

You can choose:

* Number of CPUs
* Amount of RAM
* Network performance
* Storage capacity

Different applications require different instance sizes.

Example:

| Application      | Recommended Instance      |
| ---------------- | ------------------------- |
| Small Website    | Small Instance            |
| Business API     | Medium Instance           |
| Machine Learning | GPU Instance              |
| Large Database   | Memory Optimized Instance |

---

# 2. AMI (Amazon Machine Image)

## Definition

An **Amazon Machine Image (AMI)** is a pre-configured template used to launch an EC2 Instance.

It contains:

* Operating System
* Software Packages
* Configuration Settings

Think of it as a ready-made blueprint for creating servers.

---

# Common AMIs

Examples include:

* Ubuntu Linux
* Amazon Linux
* Red Hat Enterprise Linux
* Windows Server
* Debian Linux

When launching an EC2 Instance, you first choose an AMI.

---

# Example

Suppose you want an Ubuntu server.

AWS provides an Ubuntu AMI.

When you launch the instance,

AWS automatically installs Ubuntu using that AMI.

---

# AMI Workflow

```text
Select AMI
      │
      ▼
Launch EC2 Instance
      │
      ▼
Virtual Server Ready
```

---

# 3. Amazon EBS (Elastic Block Store)

## Definition

Amazon **Elastic Block Store (EBS)** provides **persistent storage** for EC2 instances.

It behaves like the **hard disk (HDD/SSD)** of your computer.

---

# Why is EBS Needed?

Every server requires storage for:

* Operating System
* Applications
* User Files
* Databases
* Logs

Amazon EBS provides this storage.

---

# Example

```text
EC2 Instance
      │
      ▼
Amazon EBS
```

Without EBS,

your EC2 instance would not have permanent storage.

---

# Characteristics of EBS

✔ Persistent storage

✔ Works like a hard drive

✔ Can be attached to EC2

✔ Stores operating system and data

✔ Data remains even after restarting the instance

---

# Relationship Between EC2, AMI and EBS

```text
Amazon Machine Image (AMI)
           │
           ▼
Launch EC2 Instance
           │
           ▼
Attach Amazon EBS Storage
           │
           ▼
Virtual Server Ready
```

---

# Where Can EC2 Be Used?

Amazon EC2 is one of the most versatile AWS services.

Common use cases include:

---

## 1. Hosting Websites

Host:

* Company Websites
* Blogs
* E-commerce Platforms

Example:

A React frontend and Node.js backend hosted on Ubuntu EC2.

---

## 2. Hosting APIs

Deploy backend applications such as:

* Express.js
* Spring Boot
* Django
* Flask
* Laravel

The APIs can then be accessed over the Internet.

---

## 3. Running Batch Jobs

Organizations execute scheduled tasks such as:

* Data Processing
* Report Generation
* ETL Pipelines
* Data Migration

EC2 is ideal for these workloads.

---

## 4. Background Workers

Applications often perform background processing, including:

* Sending Emails
* Processing Images
* Video Conversion
* Queue Processing

These tasks can run on EC2 instances.

---

## 5. Machine Learning

EC2 provides powerful instances with GPUs for:

* Training AI Models
* Deep Learning
* Data Science
* Large-scale Data Processing

---

## 6. Development & Testing

Developers create temporary environments for:

* Development
* Testing
* Quality Assurance
* Demonstrations

These instances can be launched and terminated whenever required.

---

# Advantages of Amazon EC2

* Highly scalable
* Flexible instance sizes
* Full control over the operating system
* Secure and reliable
* Pay-as-you-go pricing
* Fast deployment
* Supports Linux and Windows
* Easy integration with other AWS services

---

# Amazon EC2 vs Physical Server

| Physical Server      | Amazon EC2                 |
| -------------------- | -------------------------- |
| Buy hardware         | Rent virtual server        |
| High upfront cost    | Pay only for usage         |
| Manual upgrades      | Scale in minutes           |
| Limited capacity     | Virtually unlimited        |
| Hardware maintenance | AWS manages infrastructure |
| Slow deployment      | Launch within minutes      |

---

# Real-World Example

Suppose a startup wants to launch an e-commerce website.

Instead of purchasing servers,

they:

1. Log in to AWS.
2. Launch an EC2 Instance.
3. Select Ubuntu as the AMI.
4. Attach EBS storage.
5. Install Nginx, Node.js, and MySQL.
6. Deploy the application.

The website becomes available globally within minutes.

---

# Key Terms

| Term          | Meaning                                          |
| ------------- | ------------------------------------------------ |
| EC2           | Elastic Compute Cloud                            |
| Instance      | A running virtual server                         |
| AMI           | Amazon Machine Image used to launch instances    |
| EBS           | Elastic Block Store providing persistent storage |
| Compute       | CPU and memory resources                         |
| Elastic       | Ability to scale resources up or down            |
| Pay-As-You-Go | Pay only for the resources consumed              |

---

# Interview Questions

### 1. What is Amazon EC2?

Amazon EC2 (Elastic Compute Cloud) is an AWS service that provides scalable virtual servers in the cloud, enabling users to run applications without owning physical hardware.

---

### 2. Why is it called "Elastic" Compute Cloud?

It is called **Elastic** because computing resources such as CPU, memory, and the number of instances can be increased or decreased based on demand.

---

### 3. What is an EC2 Instance?

An EC2 Instance is a running virtual server created using the Amazon EC2 service.

---

### 4. What is an AMI?

An Amazon Machine Image (AMI) is a pre-configured template containing an operating system and software used to launch EC2 instances.

---

### 5. What is Amazon EBS?

Amazon Elastic Block Store (EBS) is persistent block storage that acts as the hard disk for an EC2 instance.

---

### 6. Give some use cases of Amazon EC2.

* Hosting websites
* Hosting APIs
* Running scheduled jobs
* Background processing
* Machine learning
* Development and testing environments

---

### 7. What pricing model does Amazon EC2 use?

Amazon EC2 uses a **Pay-As-You-Go** pricing model, where customers pay only for the compute resources they consume.

---

# Quick Revision

✔ EC2 stands for **Elastic Compute Cloud**.

✔ EC2 provides virtual servers in AWS.

✔ **Elastic** means resources can be scaled up or down.

✔ An **Instance** is a running virtual server.

✔ An **AMI** is the template used to create an instance.

✔ **EBS** provides persistent storage for EC2.

✔ EC2 is commonly used for hosting websites, APIs, machine learning workloads, batch processing, and development environments.

✔ AWS manages the physical infrastructure while users manage their virtual servers.

---

# Summary

Amazon EC2 (Elastic Compute Cloud) is one of the core AWS services that enables users to rent scalable virtual servers on demand. It eliminates the need for purchasing and maintaining physical hardware while providing complete control over the operating system, software, networking, and storage. Key concepts such as **EC2 Instances**, **Amazon Machine Images (AMI)**, and **Elastic Block Store (EBS)** form the foundation of EC2. Its flexibility, scalability, and pay-as-you-go pricing model make it one of the most widely used cloud computing services for hosting applications, APIs, machine learning workloads, and enterprise systems.
