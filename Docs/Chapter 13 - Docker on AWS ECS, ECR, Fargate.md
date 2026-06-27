# Docker on AWS | ECS, ECR & Fargate Overview

## Overview

Modern applications are often packaged into **Docker containers** before deployment. AWS provides several services to store and run these containers efficiently:

* **Docker** – Packages applications into portable containers.
* **Amazon ECR (Elastic Container Registry)** – Stores Docker images.
* **Amazon ECS (Elastic Container Service)** – Runs and manages Docker containers.
* **AWS Fargate** – Runs ECS containers without managing servers.

---

# 1. What is Docker?

Docker is a platform that packages an application together with everything it needs (libraries, dependencies, runtime, configurations) into a **container**.

### Problem Before Docker

Developers often faced the classic issue:

> "It works on my machine."

Applications behaved differently because each computer had different:

* Operating System settings
* Software versions
* Libraries
* Runtime versions
* Environment configurations

Example:

Developer A:

* Java 24
* Latest dependencies

Developer B:

* Java 21
* Different libraries

Result:

* Application fails on Developer B's machine.

---

## Docker Solution

Docker packages:

* Application
* Runtime
* Dependencies
* Libraries
* Configurations

into one portable package.

The application runs the **same way** on every machine.

---

# 2. Docker Image

A **Docker Image** is the blueprint or template for a container.

It contains:

* Application code
* Runtime (Java, Python, Node.js)
* Dependencies
* Libraries
* Environment variables
* Configuration files

Think of it like a recipe.

Example:

```
Docker Image

├── Java 21
├── Spring Boot
├── Dependencies
├── Configuration
└── Application Code
```

The image itself does **not** run.

---

# 3. Docker Container

A **Container** is a running instance of a Docker image.

Example flow:

```
Application
      ↓
Create Docker Image
      ↓
Run Image
      ↓
Docker Container
      ↓
Application Running
```

A container provides an isolated environment where the application runs consistently across systems.

---

# 4. Docker Registry

A **Docker Registry** is a storage location for Docker images.

Images can be:

* Public
* Private

Popular registries include:

* Docker Hub
* Amazon ECR
* Google Artifact Registry
* Azure Container Registry

---

# 5. Docker Hub

Docker Hub is Docker's official public registry.

It hosts thousands of ready-made images such as:

* Ubuntu
* Python
* MySQL
* PostgreSQL
* Redis
* RabbitMQ
* Nginx

Instead of installing software manually, developers can pull official images directly from Docker Hub.

---

# 6. Amazon ECR (Elastic Container Registry)

Amazon ECR is AWS's Docker image registry.

It stores Docker images securely inside AWS.

### Purpose

Instead of pushing images to Docker Hub, AWS users commonly push them to Amazon ECR.

Example deployment:

```
Local Machine
      │
Docker Image
      │
Push
      ▼
Amazon ECR
```

### Features

* Private image repositories
* Public repositories
* Secure storage
* Integrated with IAM
* Seamless integration with ECS

---

# 7. Amazon ECS (Elastic Container Service)

Amazon ECS is AWS's container orchestration service.

Its job is to:

* Pull Docker images from ECR
* Start containers
* Stop containers
* Restart failed containers
* Scale containers automatically
* Manage container deployment

Example:

```
Amazon ECR
      │
Pull Image
      ▼
Amazon ECS
      │
Run Container
      ▼
Application Running
```

---

# 8. What is Container Orchestration?

When applications grow, they may have many containers running simultaneously.

Example:

* Frontend Container
* Backend Container
* Database Container
* Redis Container
* RabbitMQ Container

Managing all these containers manually is difficult.

Container orchestration automatically handles:

* Deployment
* Scaling
* Networking
* Health checks
* Recovery
* Scheduling

Amazon ECS performs these tasks.

---

# 9. AWS Fargate

AWS Fargate is a **serverless launch type** for Amazon ECS.

Instead of managing EC2 servers yourself, AWS manages the infrastructure.

### With EC2 Launch Type

You manage:

* EC2 instances
* OS updates
* Security patches
* Scaling
* Server maintenance

### With Fargate

AWS manages:

* Servers
* Infrastructure
* Scaling
* Maintenance
* Availability

You only provide:

* Docker image
* CPU
* Memory
* Network configuration

AWS runs the container automatically.

---

# EC2 vs Fargate

| EC2 Launch Type                | Fargate Launch Type   |
| ------------------------------ | --------------------- |
| Manage servers                 | No server management  |
| Manual scaling                 | Automatic scaling     |
| OS maintenance required        | AWS manages OS        |
| More operational work          | Less operational work |
| Greater infrastructure control | Simpler deployment    |

---

# Complete Deployment Flow

```
Build Application
        │
        ▼
Create Docker Image
        │
        ▼
Push Image
        │
        ▼
Amazon ECR
        │
        ▼
Amazon ECS
        │
Choose Launch Type
        │
 ┌──────┴────────┐
 │               │
EC2          Fargate
 │               │
Manage       AWS Manages
Servers      Servers
        │
        ▼
Application Running
```

---

# Key Differences

| Service          | Purpose                                           |
| ---------------- | ------------------------------------------------- |
| Docker           | Packages applications into containers             |
| Docker Image     | Blueprint containing application and dependencies |
| Docker Container | Running instance of an image                      |
| Docker Registry  | Stores Docker images                              |
| Docker Hub       | Public Docker registry                            |
| Amazon ECR       | AWS Docker image registry                         |
| Amazon ECS       | Runs and manages Docker containers                |
| AWS Fargate      | Serverless way to run ECS containers              |

---

# Real-World Example

Suppose you develop a Node.js application.

### Step 1

Create a Docker image.

```
Node.js App
      ↓
Docker Image
```

### Step 2

Push the image to Amazon ECR.

```
Docker Image
      ↓
Amazon ECR
```

### Step 3

Amazon ECS pulls the image.

```
Amazon ECS
      ↓
Docker Image
```

### Step 4

Run the container using AWS Fargate.

```
Amazon ECS
      ↓
AWS Fargate
      ↓
Running Container
```

The application is now running in AWS without managing servers.

---

# Advantages of This Architecture

* Consistent application environment
* Eliminates "works on my machine" issues
* Easy deployment
* High scalability
* Improved reliability
* Simplified container management
* Secure image storage
* Automatic scaling
* Serverless container execution with Fargate

---

# Quick Revision

* **Docker** packages applications into portable containers.
* **Image** is the blueprint of a container.
* **Container** is a running image.
* **Registry** stores Docker images.
* **Docker Hub** is Docker's public registry.
* **Amazon ECR** stores Docker images on AWS.
* **Amazon ECS** runs and manages Docker containers.
* **AWS Fargate** runs ECS containers without requiring server management.
* Typical workflow: **Build → Docker Image → ECR → ECS → Fargate/EC2 → Running Application**.
