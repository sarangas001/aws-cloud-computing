# Chapter 12 – Introduction to AWS Serverless Computing

> **Course:** AWS Cloud Computing Masterclass  
> **Chapter:** Introduction to AWS Serverless Computing  
> **Level:** Beginner

---

# 📚 Learning Objectives

After completing this chapter, you will be able to:

- Understand what Serverless Computing is.
- Learn why "Serverless" does not mean "No Servers."
- Compare traditional server management with serverless architecture.
- Understand the benefits of serverless applications.
- Learn the pricing model of AWS Serverless.
- Understand automatic scaling in serverless environments.
- Get introduced to AWS Lambda.

---

# What is Serverless Computing?

Serverless Computing is a cloud computing model where **you only focus on writing your application code**, while the cloud provider (AWS) manages the servers behind the scenes.

> **Important:** Serverless does **NOT** mean there are no servers.

Servers still exist, but AWS manages them for you.

---

# Common Misconception

Many beginners think:

```text
Serverless = No Servers
```

This is **incorrect**.

The correct understanding is:

```text
Serverless

↓

Servers Exist

↓

AWS Manages Them

↓

You Only Write Code
```

---

# Traditional Server-Based Deployment

When deploying an application using services like EC2, you are responsible for managing the servers.

Typical responsibilities include:

- Managing operating systems
- Installing software
- Applying security patches
- Updating applications
- Monitoring servers
- Scaling infrastructure
- Recovering failed servers
- Maintaining uptime

Example:

```text
Developer

↓

EC2 Instance

↓

Install OS

↓

Install Software

↓

Deploy Application

↓

Monitor Server

↓

Patch Server

↓

Scale Server
```

Everything related to infrastructure is managed by you.

---

# Serverless Deployment

With Serverless Computing:

- AWS manages the servers.
- AWS manages scaling.
- AWS manages operating systems.
- AWS manages security patches.
- AWS manages infrastructure.

You simply:

- Write code
- Deploy code
- Configure triggers

Example:

```text
Developer

↓

Write Code

↓

Deploy Code

↓

AWS Runs It
```

No server management is required.

---

# What Does AWS Manage?

In a serverless environment, AWS automatically handles:

- Server provisioning
- Operating system updates
- Security patches
- Infrastructure maintenance
- Automatic scaling
- Server monitoring
- Availability
- Fault tolerance

You only focus on your application's business logic.

---

# What Do Developers Manage?

Developers are responsible for:

- Writing application code
- Business logic
- Configuring triggers
- Testing applications
- Deploying code

Everything else is handled by AWS.

---

# What are Triggers?

A **Trigger** is an event that tells your code to execute.

Examples include:

- API request
- HTTP request
- File upload to S3
- Database event
- Scheduled task
- Queue message

Example:

```text
User Uploads File

↓

S3 Event

↓

Lambda Function Executes
```

---

# Hotel vs House Analogy

The instructor compares Serverless Computing to staying in a hotel.

## Renting a House (Traditional Servers)

When renting a house, you manage everything:

- Electricity
- Plumbing
- Repairs
- Cleaning
- Maintenance

Similarly, with EC2:

- You manage servers.
- You maintain infrastructure.

---

## Staying in a Hotel (Serverless)

When staying in a hotel:

- Electricity is managed.
- Repairs are managed.
- Maintenance is managed.
- Cleaning is managed.

You simply enjoy the service.

Similarly, with Serverless:

- AWS manages servers.
- AWS manages infrastructure.
- You only use the service.

---

# Traditional vs Serverless

| Traditional Servers | Serverless |
|----------------------|------------|
| Manage servers | AWS manages servers |
| Install operating system | AWS manages OS |
| Apply security patches | AWS applies patches |
| Configure scaling | AWS scales automatically |
| Monitor servers | AWS monitors servers |
| Pay for server uptime | Pay only when code executes |

---

# Pricing Model

## Traditional Servers (EC2)

You generally pay for:

- Running server
- CPU
- Memory
- Storage
- Time the server is running

Even if nobody is using your application,

you are still paying.

Example:

```text
Server Running

↓

24 Hours

↓

Charged for 24 Hours
```

---

## Serverless Pricing

With Serverless:

You pay only when your code executes.

AWS charges based on:

- Number of requests
- Execution time

Example:

```text
Application

↓

100 Requests

↓

Pay for 100 Executions
```

If nobody uses your application,

your cost is extremely low (or even zero depending on the service and free tier).

---

# Scaling

## Traditional Servers

Scaling is your responsibility.

You must configure:

- Auto Scaling Groups
- Load Balancers
- Additional servers

Example:

```text
Traffic Increases

↓

Launch More EC2 Instances
```

---

## Serverless

AWS automatically scales.

Example:

```text
1 User

↓

1 Execution

1000 Users

↓

1000 Executions

Automatically
```

No manual scaling is required.

---

# Benefits of Serverless Computing

- No server management
- Automatic scaling
- High availability
- Pay only for usage
- Faster application development
- Reduced operational overhead
- Focus entirely on business logic

---

# AWS Lambda

AWS provides a serverless compute service called **AWS Lambda**.

Lambda allows you to:

- Run application code
- Without managing servers
- Without provisioning infrastructure

AWS automatically executes your code whenever a configured trigger occurs.

---

# What is AWS Lambda?

AWS Lambda is a compute service that allows you to run code **without provisioning or managing servers**.

Example:

```text
Write Code

↓

Upload to Lambda

↓

AWS Executes It
```

---

# Lambda Execution Flow

```text
User Request

↓

Trigger

↓

AWS Lambda

↓

Execute Code

↓

Return Response
```

---

# Example Triggers for Lambda

Lambda can be triggered by:

- API Gateway request
- Amazon S3 upload
- DynamoDB event
- CloudWatch scheduled event
- SNS notification
- SQS message

Example:

```text
Upload Image

↓

Amazon S3

↓

Lambda Function

↓

Resize Image
```

---

# EC2 vs Lambda

| EC2 | AWS Lambda |
|------|------------|
| Virtual server | Serverless compute |
| Manage infrastructure | AWS manages infrastructure |
| Always running | Runs only when triggered |
| Pay for server uptime | Pay per request and execution time |
| Manual scaling | Automatic scaling |
| Install software manually | Upload code only |

---

# AWS Lambda Free Tier

AWS Lambda includes a generous Free Tier.

Typical benefits include:

- Millions of free requests every month (subject to AWS Free Tier limits)
- Ideal for learning and small applications

Always check the latest AWS pricing page for current limits.

---

# When Should You Use Serverless?

Serverless is ideal for:

- REST APIs
- Backend services
- Event-driven applications
- File processing
- Image resizing
- Automation scripts
- Scheduled jobs
- Microservices
- IoT applications

---

# When EC2 May Be Better

Traditional servers are often better when:

- Long-running applications
- Full operating system access is required
- Custom software installation
- Legacy applications
- Specialized networking requirements

---

# Serverless Workflow

```text
Write Code

↓

Deploy to Lambda

↓

Configure Trigger

↓

User Sends Request

↓

AWS Executes Code

↓

Response Returned
```

---

# Advantages of Serverless

- No infrastructure management
- Reduced operational effort
- Automatic scaling
- Cost-effective
- Faster deployments
- High availability
- Built-in fault tolerance
- Focus on application development

---

# Key Terms

| Term | Meaning |
|------|---------|
| Serverless | Cloud model where AWS manages servers |
| AWS Lambda | AWS serverless compute service |
| Trigger | Event that starts code execution |
| Execution | Running a Lambda function |
| Scaling | Increasing or decreasing computing resources |
| Infrastructure | Servers, networking, storage, and operating systems |

---

# Interview Questions

### 1. What is Serverless Computing?

Serverless Computing is a cloud computing model where developers focus only on writing application code while the cloud provider manages the servers and infrastructure.

---

### 2. Does Serverless mean there are no servers?

No. Servers still exist, but AWS manages them instead of the developer.

---

### 3. What are the benefits of Serverless?

- No server management
- Automatic scaling
- Pay only for usage
- Faster development
- High availability

---

### 4. What is AWS Lambda?

AWS Lambda is a serverless compute service that allows developers to run code without provisioning or managing servers.

---

### 5. How does AWS Lambda charge customers?

AWS Lambda charges based on:

- Number of requests
- Execution duration

---

### 6. What is a Trigger?

A Trigger is an event that invokes a Lambda function, such as an API request, file upload, or scheduled event.

---

### 7. What is the difference between EC2 and Lambda?

EC2 provides virtual servers that you manage, whereas Lambda executes code without requiring server management.

---

# Quick Revision

- ✅ Serverless does **NOT** mean there are no servers.
- ✅ AWS manages the infrastructure.
- ✅ Developers only write and deploy code.
- ✅ AWS Lambda is AWS's serverless compute service.
- ✅ Lambda executes code only when triggered.
- ✅ Serverless automatically scales based on demand.
- ✅ Pricing is based on requests and execution time.
- ✅ No operating system or server maintenance is required.
- ✅ Ideal for event-driven applications and APIs.

---

# Summary

Serverless Computing allows developers to build and run applications without managing servers. Although servers still exist, AWS handles provisioning, scaling, operating system maintenance, security patches, and monitoring. Developers focus only on writing application code and configuring triggers. **AWS Lambda** is the primary serverless compute service in AWS, executing code in response to events such as API requests or file uploads. Compared to traditional EC2 instances, serverless applications offer automatic scaling, lower operational overhead, and a pay-per-use pricing model, making them an efficient choice for modern cloud-native applications.