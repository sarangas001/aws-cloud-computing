# Chapter 03 – Why Do We Need Cloud Computing?

> **Course:** AWS Cloud Computing Masterclass
> **Chapter:** 03 - Why Do We Need Cloud Computing?
> **Level:** Beginner
> **Notes Prepared By:** ChatGPT

---

# 📚 Learning Objectives

After completing this chapter, you should be able to:

* Understand why Cloud Computing was introduced.
* Explain the problems with traditional physical servers.
* Understand how cloud providers solve these problems.
* Learn the concept of **Pay-As-You-Go**.
* Understand scalability in cloud computing.
* Learn how **Amazon Web Services (AWS)** was created.
* Compare traditional hosting with cloud hosting.

---

# 🌍 Why Was Cloud Computing Introduced?

Before Cloud Computing existed, companies had to purchase and manage their own physical servers.

This approach worked for small applications but became a major problem as businesses grew.

Cloud Computing was introduced to solve these infrastructure challenges.

---

# 🏢 Traditional Infrastructure (Before Cloud)

In the early days, companies followed this process:

```text
Company
   │
   ▼
Buy Physical Servers
   │
   ▼
Install in Office/Data Center
   │
   ▼
Deploy Website/Application
```

Everything had to be managed by the company itself.

---

# Problems with Physical Servers

## 1. High Initial Cost

Companies had to purchase:

* Physical servers
* Networking equipment
* Storage devices
* Cooling systems
* UPS & Power Generators

This required a large upfront investment.

---

## 2. Maintenance

Companies had to maintain:

* Hardware
* Operating Systems
* Network Devices
* Security
* Server Updates

This required a dedicated IT team.

---

## 3. Cooling Requirements

Servers generate a lot of heat.

Companies needed:

* Air-conditioned server rooms
* Cooling systems
* Temperature monitoring

Without cooling, hardware could fail.

---

## 4. Electricity Costs

Servers run 24/7.

This leads to:

* High electricity bills
* Backup power requirements
* Diesel generators for outages

---

## 5. Security

Organizations were responsible for protecting servers from:

* Physical theft
* Unauthorized access
* Cyber attacks
* Hardware failures

---

## 6. Difficult to Scale

Suppose a company owns **5 servers**.

During a major sale, they suddenly require **100 servers**.

They must:

* Purchase new hardware
* Install it
* Configure it
* Connect it
* Test it

This process could take days or weeks.

---

# Example – Black Friday Sale

Imagine an online shopping company.

Normal Days:

```text
Traffic
↓

5 Servers
```

Black Friday:

```text
Traffic
↓↓↓↓↓↓↓↓↓↓↓

150 Servers Required
```

The company must buy additional servers.

After the sale:

```text
Traffic
↓

Only 5 Servers Needed
```

The remaining servers sit unused.

Money is wasted.

---

# Problems Summary

Traditional hosting is:

* Expensive
* Slow to scale
* Difficult to maintain
* Hard to manage
* Risky for startups

---

# Cloud Computing Solution

Instead of buying servers...

Companies **rent computing resources** from a Cloud Provider.

```text
Application
      │
      ▼
Cloud Provider
      │
      ▼
Virtual Servers
Storage
Databases
Networking
```

The cloud provider manages the infrastructure.

The company focuses on building its application.

---

# Cloud Provider

A Cloud Provider owns:

* Data Centers
* Physical Servers
* Networking Equipment
* Storage Systems

Customers simply rent the resources they need.

Examples:

* AWS
* Microsoft Azure
* Google Cloud Platform (GCP)

---

# How Cloud Computing Works

Imagine three startups.

```text
Startup A
Startup B
Startup C
      │
      ▼
Cloud Provider
      │
      ▼
Large Data Centers
```

Instead of buying their own servers,

all startups share the provider's infrastructure.

Each customer only pays for their own usage.

---

# Pay-As-You-Go Model

One of the biggest advantages of cloud computing is:

> **Pay only for what you use.**

Example:

Suppose you upgrade your server for **3 days** during a sale.

The cloud provider bills you for **only those 3 days**.

You are **not** charged for the entire month.

This greatly reduces costs.

---

# Scalability

Scalability means increasing or decreasing resources whenever required.

There are two types.

## Scale Up

Increase:

* CPU
* RAM
* Storage

Used when traffic increases.

---

## Scale Down

Reduce:

* CPU
* RAM
* Storage

Used when traffic decreases.

This helps avoid unnecessary costs.

---

# Example

Before Sale:

```text
2 CPU
4 GB RAM
```

During Sale:

```text
8 CPU
32 GB RAM
```

After Sale:

```text
2 CPU
4 GB RAM
```

This process may take only a few clicks in the cloud.

---

# Benefits of Cloud Computing

## Lower Cost

No need to purchase expensive hardware.

---

## Faster Deployment

Servers can be created within minutes.

---

## Automatic Scaling

Increase or decrease resources whenever required.

---

## Better Reliability

Cloud providers have multiple data centers around the world.

If one data center fails,

another can continue running the application.

---

## Less Maintenance

Developers focus on coding.

The cloud provider handles:

* Hardware
* Cooling
* Power
* Networking

---

## Business Focus

Companies spend time improving:

* Products
* Services
* Customer Experience

instead of managing hardware.

---

# Traditional Hosting vs Cloud Computing

| Traditional Hosting | Cloud Computing             |
| ------------------- | --------------------------- |
| Buy servers         | Rent servers                |
| High upfront cost   | Pay only for usage          |
| Manual scaling      | Automatic scaling           |
| Maintain hardware   | Provider maintains hardware |
| Slow deployment     | Fast deployment             |
| Difficult to manage | Easy to manage              |

---

# Real World Example

Imagine opening a restaurant.

## Traditional Approach

You purchase:

* Building
* Furniture
* Kitchen
* Equipment

Huge investment.

---

## Cloud Approach

You rent a fully equipped kitchen.

You only pay rent while using it.

Cloud Computing works the same way.

---

# How AWS Was Created

AWS stands for:

**Amazon Web Services**

It is the cloud computing platform created by Amazon.

---

## The Problem Amazon Faced

Amazon's e-commerce website experienced huge traffic spikes during events like **Black Friday**.

During these events:

* Millions of customers visited Amazon.
* Amazon had to purchase many physical servers.
* After the sale, most servers remained idle.

Maintaining these unused servers was expensive.

---

## Jeff Bezos' Idea

Amazon founder **Jeff Bezos** realized:

> "Instead of leaving these servers unused, why not rent them to other businesses?"

This idea led to the creation of **Amazon Web Services (AWS).**

---

# Birth of AWS

Amazon transformed its internal infrastructure into cloud services that other companies could rent.

Early AWS services included:

* **Amazon EC2** – Virtual Servers
* **Amazon S3** – Cloud Storage

Businesses could now:

* Rent servers
* Rent storage
* Scale resources on demand
* Pay only for usage

---

# Why AWS Became Popular

AWS solved a problem faced by almost every startup.

Companies no longer needed to:

* Buy expensive servers
* Build data centers
* Hire large infrastructure teams

Instead, they could launch applications quickly using AWS.

---

# Other Cloud Providers

After AWS became successful, other companies launched their own cloud platforms.

| Provider  | Cloud Platform              |
| --------- | --------------------------- |
| Amazon    | AWS                         |
| Microsoft | Azure                       |
| Google    | Google Cloud Platform (GCP) |

Today, cloud computing is the default choice for most modern businesses.

---

# Key Terms

| Term            | Meaning                                       |
| --------------- | --------------------------------------------- |
| Physical Server | A real computer used for hosting applications |
| Cloud Provider  | Company that provides cloud services          |
| Scalability     | Increase or decrease resources                |
| Pay-As-You-Go   | Pay only for resources used                   |
| Data Center     | Facility containing thousands of servers      |
| Compute Power   | CPU, RAM, and processing resources            |
| AWS             | Amazon Web Services                           |

---

# Interview Questions

### 1. Why was Cloud Computing introduced?

Cloud Computing was introduced to eliminate the high cost, complexity, and maintenance of physical servers while providing scalable, on-demand computing resources.

---

### 2. What problems did traditional hosting have?

* High upfront costs
* Difficult scaling
* Hardware maintenance
* Cooling requirements
* High electricity usage
* Need for dedicated IT staff

---

### 3. What is the Pay-As-You-Go model?

Users pay only for the cloud resources they consume instead of purchasing infrastructure in advance.

---

### 4. What is Scalability?

Scalability is the ability to increase or decrease computing resources according to application demand.

---

### 5. Why was AWS created?

AWS was created because Amazon wanted to utilize its unused server infrastructure by renting computing resources to other businesses, reducing waste and creating a new business model.

---

### 6. Name two early AWS services.

* Amazon EC2 (Virtual Servers)
* Amazon S3 (Cloud Storage)

---

# Quick Revision

✔ Physical servers are expensive and difficult to maintain.

✔ Cloud Computing allows businesses to rent computing resources instead of buying hardware.

✔ Cloud providers manage infrastructure, security, power, and maintenance.

✔ Businesses can scale resources up or down based on demand.

✔ The **Pay-As-You-Go** pricing model reduces costs.

✔ AWS was created after Amazon recognized that its unused infrastructure could be rented to other businesses.

✔ Today, AWS, Azure, and Google Cloud are the leading cloud providers.

---

# Summary

Cloud Computing revolutionized the way organizations build and deploy applications by replacing expensive, difficult-to-manage physical infrastructure with on-demand cloud services. It enables businesses to rent computing resources, scale instantly, reduce operational costs, and focus on innovation instead of hardware management. **Amazon Web Services (AWS)** emerged from Amazon's own infrastructure challenges and has become one of the world's leading cloud platforms, offering scalable, reliable, and cost-effective services for organizations of all sizes.
