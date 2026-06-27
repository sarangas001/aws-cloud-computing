# Chapter 05 – AWS IAM (Identity and Access Management)

> **Course:** AWS Cloud Computing Masterclass
> **Chapter:** 05 - Introduction to AWS IAM (Identity and Access Management)
> **Level:** Beginner
> **Notes Prepared By:** ChatGPT

---

# 📚 Learning Objectives

After completing this chapter, you should be able to:

* Understand what AWS IAM is.
* Explain why IAM is important in AWS.
* Learn the four core IAM components:

  * IAM Users
  * IAM Groups
  * IAM Roles
  * IAM Policies
* Understand how permissions are managed in AWS.
* Learn the difference between Users, Groups, Roles, and Policies.
* Understand real-world IAM scenarios used in organizations.

---

# 🔐 What is AWS IAM?

**IAM (Identity and Access Management)** is an AWS service that allows you to securely control **who can access AWS resources and what actions they are allowed to perform**.

In simple terms,

> **IAM defines "Who can do What" in an AWS account.**

Every action performed in AWS is controlled through IAM.

---

# Why Do We Need IAM?

In an organization, many people use the same AWS account.

For example:

* Developers
* Testers
* DevOps Engineers
* Finance Team
* Project Managers
* System Administrators

Each team requires different permissions.

Without IAM:

* Anyone could delete resources.
* Anyone could access billing information.
* Anyone could create expensive AWS services.

IAM solves this problem by controlling access.

---

# Real-World Example

Imagine a software company.

There are three departments:

```text
Company
│
├── Developers
├── Finance Team
└── Managers
```

Each department needs different access.

### Developers

Need access to:

* EC2
* S3
* Lambda
* CloudWatch

Should **NOT** access:

* Billing
* Payment Methods
* Account Settings

---

### Finance Team

Need access to:

* Billing Dashboard
* Cost Reports
* AWS Budgets
* Payment Information

Should **NOT** launch EC2 instances or modify infrastructure.

---

### Managers

May require:

* Read-only access
* Monitoring dashboards
* Administrative reports

IAM allows each team to receive only the permissions they require.

This follows the **Principle of Least Privilege**, meaning users should receive **only the permissions necessary** to perform their job.

---

# Benefits of IAM

* Secure AWS resources
* Manage user permissions
* Prevent unauthorized access
* Improve security
* Easy permission management
* Free AWS service

> **Note:** IAM itself is free. You are not charged separately for using IAM.

---

# Core Components of IAM

IAM consists of four main building blocks.

```text
AWS IAM
│
├── Users
├── Groups
├── Roles
└── Policies
```

---

# 1. IAM User

## Definition

An **IAM User** represents an **individual person or application** that requires access to AWS.

Each user has a unique identity.

---

## An IAM User Can Have

* Username
* Password
* Console Access
* Access Keys
* Assigned Permissions

---

## Console Access

Console access allows users to log in through the AWS Management Console.

Example:

```text
https://console.aws.amazon.com/
```

Users sign in with:

* Username
* Password

---

## Access Keys

Developers often work from:

* AWS CLI
* SDKs
* Applications
* Automation Scripts

Instead of a username and password, they use:

* Access Key ID
* Secret Access Key

These credentials allow programmatic access to AWS services.

---

## Real-World Example

Suppose your company hires:

* John (Developer)
* Sarah (Tester)
* David (Finance)

Each employee receives their own IAM User account.

```text
AWS Account

├── John
├── Sarah
└── David
```

Each user can have different permissions.

---

# Characteristics of IAM Users

✔ Represents one person or application

✔ Has permanent credentials

✔ Can log in to AWS Console

✔ Can use Access Keys

✔ Can have permissions attached directly

---

# 2. IAM Groups

## Definition

An **IAM Group** is a collection of IAM Users who require the same permissions.

Instead of assigning permissions to every individual user,

assign permissions once to the group.

Every user inside the group automatically receives those permissions.

---

# Why Groups Exist

Imagine a company with:

* 150 Developers
* 40 Testers
* 25 Finance Staff

If permissions are assigned individually,

managing users becomes difficult.

Instead:

```text
Groups

Developers
Testers
Finance
Managers
```

Each group receives its required permissions.

---

# Example Without Groups

```text
Developer 1
│
└── EC2 Permission

Developer 2
│
└── EC2 Permission

Developer 3
│
└── EC2 Permission
```

Now imagine changing permissions for **200 developers**.

You must update each user individually.

This is inefficient.

---

# Example Using Groups

```text
Developer Group
│
├── EC2 Access
├── S3 Access
└── CloudWatch Access

│
├── Developer 1
├── Developer 2
├── Developer 3
└── Developer 4
```

Add a new developer?

Simply:

1. Create IAM User
2. Add to Developer Group

Done.

No additional permission assignment is required.

---

# Advantages of Groups

* Easier administration
* Faster onboarding
* Centralized permission management
* Consistent access control

---

# 3. IAM Roles

## Definition

An **IAM Role** is a temporary identity that provides permissions to AWS services, applications, or users.

Unlike IAM Users, roles **do not have permanent credentials** such as usernames or passwords.

Roles are **assumed temporarily** when needed.

---

# Why Roles Are Needed

Sometimes AWS services need permission to interact with other AWS services.

Example:

AWS Lambda needs to:

* Read files from Amazon S3
* Write logs to CloudWatch

Lambda itself cannot log in like a human user.

Instead, it assumes an IAM Role.

---

# Example

```text
AWS Lambda

      │
      ▼

IAM Role

      │
      ▼

Amazon S3
```

The IAM Role grants temporary permission to access S3.

Once the task is complete,

the temporary permissions expire.

---

# Real-World Analogy

Imagine visiting a secure office.

You receive:

* Visitor Badge

The badge grants temporary access.

After leaving,

the badge is returned.

IAM Roles work in a similar way.

---

# Characteristics of IAM Roles

✔ Temporary permissions

✔ No username

✔ No password

✔ No access keys

✔ Used by AWS services, applications, or external users

---

# Common AWS Services That Use Roles

* AWS Lambda
* Amazon EC2
* Amazon ECS
* Amazon EKS
* AWS CloudFormation

---

# 4. IAM Policies

## Definition

An **IAM Policy** is a document that defines **what actions are allowed or denied**.

Policies are the actual permissions in IAM.

They determine:

* What actions are allowed
* Which AWS resources can be accessed
* Which actions are denied

---

# Policies Can Be Attached To

* IAM Users
* IAM Groups
* IAM Roles

---

# Policy Example

A policy may allow:

* Start EC2
* Stop EC2
* Describe EC2

But deny:

* Delete EC2

---

# Policy Format

IAM Policies are written in **JSON (JavaScript Object Notation)**.

Example:

```json
{
  "Effect": "Allow",
  "Action": [
    "ec2:StartInstances",
    "ec2:StopInstances"
  ],
  "Resource": "*"
}
```

> Don't worry about writing policies yet. You will learn JSON-based IAM policies in later chapters.

---

# Relationship Between IAM Components

```text
IAM Policy
      │
      ▼
IAM Group
      │
      ▼
IAM Users
```

Or

```text
IAM Policy
      │
      ▼
IAM Role
      │
      ▼
AWS Service
```

---

# IAM Workflow

```text
Create IAM User
        │
        ▼
Add User to Group
        │
        ▼
Group has IAM Policy
        │
        ▼
User receives permissions
```

---

# Best Practices for IAM

✅ Create individual IAM Users for each person.

✅ Use IAM Groups to manage permissions.

✅ Assign permissions to Groups instead of individual Users whenever possible.

✅ Use IAM Roles for AWS services and applications.

✅ Follow the **Principle of Least Privilege**.

✅ Avoid sharing AWS Root Account credentials.

---

# User vs Group vs Role vs Policy

| Component  | Purpose             | Has Credentials? | Used By                     |
| ---------- | ------------------- | ---------------- | --------------------------- |
| IAM User   | Individual identity | ✅ Yes            | People & Applications       |
| IAM Group  | Collection of users | ❌ No             | Organizing Users            |
| IAM Role   | Temporary identity  | ❌ No             | AWS Services & Applications |
| IAM Policy | Permission document | ❌ No             | Users, Groups & Roles       |

---

# Real Organization Example

```text
AWS Account

├── Developers Group
│      ├── John
│      ├── Kevin
│      └── Sarah
│
├── Finance Group
│      ├── David
│      └── Emma
│
├── Managers Group
│      ├── Alex
│      └── Lisa
│
└── IAM Roles
       ├── Lambda Role
       ├── EC2 Role
       └── ECS Role
```

Each group has different policies attached based on its responsibilities.

---

# Key Terms

| Term            | Meaning                                             |
| --------------- | --------------------------------------------------- |
| IAM             | Identity and Access Management                      |
| IAM User        | Individual identity in AWS                          |
| IAM Group       | Collection of users with similar permissions        |
| IAM Role        | Temporary identity for AWS services or applications |
| IAM Policy      | JSON document defining permissions                  |
| Console Access  | Login through AWS Management Console                |
| Access Keys     | Credentials for CLI, SDKs, and applications         |
| Least Privilege | Grant only the permissions required                 |

---

# Interview Questions

### 1. What is AWS IAM?

AWS IAM (Identity and Access Management) is a service used to securely manage identities and permissions, controlling who can access AWS resources and what actions they can perform.

---

### 2. Why is IAM important?

IAM improves security by ensuring users receive only the permissions necessary to perform their job responsibilities.

---

### 3. What is an IAM User?

An IAM User is an individual identity with permanent credentials such as a username, password, and optional access keys.

---

### 4. What is an IAM Group?

An IAM Group is a collection of IAM Users who share the same permissions.

---

### 5. What is an IAM Role?

An IAM Role is a temporary identity assumed by AWS services, applications, or users to gain specific permissions without permanent credentials.

---

### 6. What is an IAM Policy?

An IAM Policy is a JSON document that defines permissions, specifying which AWS actions are allowed or denied.

---

### 7. What is the Principle of Least Privilege?

It is the security practice of granting users only the minimum permissions required to perform their tasks.

---

# Quick Revision

✔ IAM controls **who can do what** in AWS.

✔ IAM is a **free AWS service**.

✔ **IAM User** = Individual identity.

✔ **IAM Group** = Collection of users with shared permissions.

✔ **IAM Role** = Temporary permissions for AWS services or applications.

✔ **IAM Policy** = JSON document defining permissions.

✔ Groups simplify permission management.

✔ Roles are commonly used by services such as **AWS Lambda** and **Amazon EC2**.

✔ Follow the **Principle of Least Privilege** for better security.

---

# Summary

AWS Identity and Access Management (IAM) is the foundation of AWS security. It enables organizations to control access to AWS resources by defining identities and permissions. IAM consists of four key components: **Users**, **Groups**, **Roles**, and **Policies**. Users represent individual identities, Groups simplify permission management, Roles provide temporary access for AWS services and applications, and Policies define the permissions that determine what actions are allowed or denied. By following IAM best practices, organizations can build secure, scalable, and well-managed AWS environments.
