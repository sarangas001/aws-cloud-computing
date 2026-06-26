# Chapter 02 – What is Cloud Computing?

> **Course:** AWS Cloud Computing Masterclass
> **Chapter:** 02 - What is Cloud Computing?
> **Level:** Beginner
> **Notes Prepared By:** ChatGPT

---

# 📚 Learning Objectives

After completing this chapter, you should be able to:

* Understand what Cloud Computing is.
* Explain the meaning of "Cloud" and "Computing."
* Identify the benefits of Cloud Computing.
* Understand the three cloud service models:

  * SaaS
  * PaaS
  * IaaS
* Know real-world examples of each service model.
* Understand why businesses are moving to the cloud.

---

# ☁️ What is Cloud Computing?

## Definition

**Cloud Computing** is the delivery of computing services such as:

* Servers
* Storage
* Databases
* Networking
* Software
* Processing Power

over the **Internet**, instead of purchasing and managing physical hardware yourself.

### Simple Definition

> Cloud Computing means using computing resources over the Internet rather than owning and maintaining your own computers or servers.

---

# Breaking Down the Word

Cloud Computing consists of two words.

## 1. Cloud

Cloud simply means:

> Services that are available through the Internet.

Instead of installing software on your own computer, you access it online.

Examples:

* Gmail
* Google Drive
* Dropbox
* Netflix
* YouTube
* Microsoft Teams
* Zoom

---

## 2. Computing

Computing refers to:

* Processing data
* Running applications
* Storing files
* Managing databases
* Performing calculations

When these tasks happen over the Internet, it becomes **Cloud Computing**.

---

# Real-Life Examples of Cloud

You already use cloud services every day.

| Service         | Why it is Cloud               |
| --------------- | ----------------------------- |
| Gmail           | Email accessed via browser    |
| Google Drive    | Online file storage           |
| Dropbox         | Cloud storage                 |
| Netflix         | Video streaming over Internet |
| YouTube         | Online video platform         |
| Zoom            | Video conferencing            |
| Microsoft Teams | Collaboration platform        |
| Canva           | Online graphic design         |

Notice:

You never install or update these services manually.

The provider handles everything.

---

# Why Cloud is Popular

Cloud Computing has become popular because it offers many advantages.

## 1. Accessible Anywhere

As long as you have:

* Internet
* Device

you can access your applications from anywhere.

Example:

A student can access Google Drive from:

* Laptop
* Mobile
* Tablet

without copying files manually.

---

## 2. Pay As You Go

You only pay for the resources you actually use.

Example:

Instead of buying an expensive server,

you rent one only when needed.

Benefits:

* Lower cost
* No upfront investment
* Better budgeting

---

## 3. Scalability

Cloud resources can grow or shrink based on demand.

Example:

A shopping website during Black Friday.

Traffic increases dramatically.

Cloud allows you to:

* Increase server capacity instantly.
* Reduce it after the sale.

No need to buy new hardware.

---

## 4. Better Security

Cloud providers invest heavily in:

* Firewalls
* Encryption
* Monitoring
* Data Backup
* Disaster Recovery

Most companies cannot build this level of security on their own.

---

## 5. No Maintenance

Cloud providers manage:

* Hardware
* Operating Systems
* Updates
* Repairs
* Power
* Cooling

Developers only focus on building applications.

---

# Cloud Service Models

Cloud services are divided into **three major categories**.

```
Cloud Services
│
├── SaaS
├── PaaS
└── IaaS
```

---

# 1. SaaS (Software as a Service)

## Definition

Software that is already built and available online.

Users simply access it through a web browser.

No installation required.

---

## Characteristics

✔ Ready to use

✔ No installation

✔ Automatic updates

✔ Accessible through browser

✔ Provider manages everything

---

## Examples

* Gmail
* Google Docs
* Canva
* Zoom
* Microsoft 365
* Dropbox

---

## Real World Example

When using Gmail:

You simply visit:

```
gmail.com
```

You don't:

* Install Gmail
* Update Gmail
* Maintain Gmail

Google handles everything.

---

## Advantages

* Easy to use
* No maintenance
* Works on any device
* Accessible anywhere

---

## Disadvantages

* Limited customization
* Requires Internet

---

# 2. PaaS (Platform as a Service)

## Definition

A cloud platform where developers can build, test, deploy, and run applications without managing servers.

The cloud provider manages:

* Servers
* Operating System
* Runtime
* Networking

Developers only write code.

---

## Examples

* Heroku
* Google App Engine
* Azure App Service

---

## Characteristics

✔ Focus on development

✔ No server management

✔ Easy deployment

✔ Automatic scaling

---

## Real World Example

Suppose you create a Node.js application.

Instead of buying a server:

* Push code to GitHub
* Connect Heroku
* Deploy

Heroku handles:

* Server
* Updates
* Scaling
* Maintenance

You only write code.

---

## Advantages

* Faster development
* Easy deployment
* Automatic scaling
* Less infrastructure work

---

## Disadvantages

* Less control over infrastructure
* Platform limitations

---

# 3. IaaS (Infrastructure as a Service)

## Definition

Instead of receiving software or a platform,

you receive **virtual infrastructure**.

You manage almost everything yourself.

The provider supplies:

* Virtual Machines
* Storage
* Networking

You manage:

* Operating System
* Applications
* Security
* Software Installation

---

## Examples

AWS:

* Amazon EC2

Microsoft:

* Azure Virtual Machines

Google:

* Google Compute Engine

---

## Characteristics

✔ Maximum flexibility

✔ Full server control

✔ Custom software installation

✔ Suitable for large businesses

---

## Real World Example

Suppose you rent an EC2 server.

AWS gives you:

* CPU
* RAM
* Disk
* Network

You install:

* Ubuntu
* Nginx
* Java
* Node.js
* MySQL

Everything else is your responsibility.

---

## Advantages

* Full control
* Highly customizable
* Suitable for enterprise applications

---

## Disadvantages

* Requires technical knowledge
* Infrastructure maintenance is your responsibility

---

# SaaS vs PaaS vs IaaS

| Feature                     | SaaS      | PaaS       | IaaS                           |
| --------------------------- | --------- | ---------- | ------------------------------ |
| Ready-to-use Software       | ✅         | ❌          | ❌                              |
| Build Applications          | ❌         | ✅          | ✅                              |
| Manage Servers              | ❌         | ❌          | ✅                              |
| Full Infrastructure Control | ❌         | ❌          | ✅                              |
| Best For                    | End Users | Developers | System Administrators & DevOps |

---

# Easy Way to Remember

Think of transportation.

### SaaS

Ride a Taxi

Just sit.

Someone else drives.

---

### PaaS

Rent a Car

You drive.

Company maintains the car.

---

### IaaS

Build Your Own Car

You control everything.

But you also maintain everything.

---

# When Should You Use Each?

### SaaS

Use when:

* You only need software.

Examples:

* Gmail
* Canva
* Zoom

---

### PaaS

Use when:

* You are building applications.

Examples:

* Heroku
* Google App Engine

---

### IaaS

Use when:

* You need complete control.

Examples:

* Amazon EC2
* Azure VM

---

# Why Developers Love Cloud Computing

Cloud Computing allows developers to:

* Deploy applications quickly.
* Scale automatically.
* Reduce infrastructure costs.
* Focus on coding instead of hardware.
* Access resources from anywhere.

---

# Key Terms

| Term          | Meaning                        |
| ------------- | ------------------------------ |
| Cloud         | Internet-based services        |
| Computing     | Processing and storage         |
| SaaS          | Software as a Service          |
| PaaS          | Platform as a Service          |
| IaaS          | Infrastructure as a Service    |
| Scalability   | Increase or decrease resources |
| Pay-as-you-go | Pay only for what you use      |

---

# Interview Questions

### 1. What is Cloud Computing?

Cloud Computing is the delivery of computing services such as servers, storage, networking, databases, and software over the Internet instead of using physical infrastructure.

---

### 2. What is SaaS?

Software delivered over the Internet that users access through a browser without installation.

---

### 3. Give examples of SaaS.

* Gmail
* Google Docs
* Canva
* Zoom

---

### 4. What is PaaS?

A cloud platform that allows developers to build and deploy applications without managing servers.

---

### 5. What is IaaS?

Infrastructure provided over the cloud where users manage virtual machines, operating systems, and applications themselves.

---

### 6. Which AWS service is an example of IaaS?

**Amazon EC2 (Elastic Compute Cloud).**

---

### 7. Which cloud model gives the highest level of control?

**Infrastructure as a Service (IaaS).**

---

# Quick Revision

✔ Cloud = Internet-based computing

✔ Computing = Processing + Storage

✔ SaaS = Ready-made software

✔ PaaS = Platform for developers

✔ IaaS = Virtual infrastructure

✔ Pay only for usage

✔ Scale resources anytime

✔ No physical server management

---

# Summary

Cloud Computing enables individuals and businesses to access computing resources over the Internet without owning physical infrastructure. It offers flexibility, scalability, cost savings, and easier maintenance. The three primary service models—**SaaS**, **PaaS**, and **IaaS**—serve different needs, from end users who simply consume software to developers building applications and organizations requiring full control over their infrastructure. Understanding these models is the foundation for learning AWS and other cloud platforms.
