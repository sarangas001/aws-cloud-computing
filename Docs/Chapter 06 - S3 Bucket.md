# Chapter 07 – Amazon S3 Hands-On Guide (Buckets, Objects & Static Website Hosting)

> **Course:** AWS Cloud Computing Masterclass
> **Chapter:** 07 - Amazon S3 Hands-On Tutorial & Static Website Hosting
> **Level:** Beginner
> **Notes Prepared By:** ChatGPT

---

# 📚 Learning Objectives

After completing this chapter, you should be able to:

* Create an Amazon S3 Bucket.
* Upload and manage files (Objects).
* Understand Bucket settings.
* Learn Bucket naming rules.
* Understand Storage Classes.
* Configure Bucket Policies.
* Enable Public Access.
* Host a Static Website using Amazon S3.

---

# What is Amazon S3?

Amazon **S3 (Simple Storage Service)** is AWS's object storage service.

Instead of storing files inside folders like a traditional file system, S3 stores files as **Objects** inside **Buckets**.

```text
Amazon S3
│
├── Bucket
│      ├── image.png
│      ├── video.mp4
│      ├── index.html
│      └── report.pdf
```

---

# Important Terminology

| Term          | Description                                 |
| ------------- | ------------------------------------------- |
| Bucket        | A container that stores objects             |
| Object        | Any uploaded file                           |
| Object Key    | Unique name/path of an object               |
| Region        | AWS location where the bucket is created    |
| Bucket Policy | JSON policy that controls bucket access     |
| Storage Class | Determines storage cost and retrieval speed |

---

# Buckets and Objects

Every file uploaded to Amazon S3 is called an **Object**.

Objects **cannot exist without a Bucket**.

```text
Bucket
│
├── photo.jpg
├── notes.pdf
├── video.mp4
└── index.html
```

Think of it like:

* Bucket → Folder
* Object → File

---

# Creating an S3 Bucket

Navigate to:

```text
AWS Console
    ↓
Search "S3"
    ↓
Amazon S3
    ↓
Create Bucket
```

During creation, AWS asks for:

* AWS Region
* Bucket Name
* Public Access Settings
* Versioning
* Tags
* Encryption

---

# Selecting the AWS Region

A bucket must be created in a specific AWS Region.

Examples:

* US East (N. Virginia)
* Europe (Stockholm)
* Asia Pacific (Mumbai)

Choose a region close to your users for lower latency and based on pricing requirements.

---

# Bucket Naming Rules

Bucket names must follow AWS rules.

✔ 3–63 characters

✔ Globally unique

✔ Start with a letter or number

✔ Lowercase only

✔ Numbers and hyphens allowed

Example:

```text
student-files-2026
```

Invalid:

```text
MyBucket
```

because uppercase letters are not allowed.

---

# Bucket Ownership

By default:

* Bucket owner owns uploaded objects.
* Access is controlled by the bucket owner.

---

# Public Access Settings

When creating a bucket, AWS enables:

```text
✅ Block All Public Access
```

This means:

* Files are private.
* No one on the Internet can access them.

AWS recommends keeping this enabled unless public access is required.

---

# Bucket Versioning

Versioning allows S3 to store **multiple versions** of the same object.

Example:

```text
report.pdf (Version 1)

↓

report.pdf (Version 2)

↓

report.pdf (Version 3)
```

Benefits:

* Recover deleted files
* Restore previous versions
* Protect against accidental overwrites

Similar to version history in Git or Dropbox.

---

# Bucket Encryption

Amazon S3 supports server-side encryption to protect stored data.

Encryption secures data even if the storage media is compromised.

---

# Uploading Objects

Inside the bucket:

```text
Upload
    ↓
Add Files
    ↓
Select Local File
    ↓
Upload
```

Example:

```text
hello.txt
```

After upload:

```text
Bucket

└── hello.txt
```

---

# Object Details

Every uploaded object includes:

* Object URL
* Object Key
* Object Size
* Storage Class
* ETag
* ARN
* S3 URI

These details are available from the object's information page.

---

# Amazon S3 Storage Classes

Amazon S3 provides multiple storage classes depending on how frequently data is accessed.

---

## 1. Standard

Used for:

* Frequently accessed data
* Websites
* Images
* Videos

Features:

* Millisecond access
* High durability
* Multi-AZ replication

---

## 2. Intelligent-Tiering

Suitable for:

* Unknown or changing access patterns

AWS automatically moves data between storage tiers to reduce costs.

---

## 3. Standard-Infrequent Access (Standard-IA)

Used when:

* Files are accessed occasionally (e.g., monthly reports)

Lower storage cost than Standard.

---

## 4. One Zone-IA

Stores data in a single Availability Zone.

Best for:

* Re-creatable data
* Backup copies

Lower cost than Standard-IA.

---

## 5. Glacier Instant Retrieval

Used for archived data that needs occasional access.

Example:

* Quarterly reports
* Archived documents

Lower storage cost with fast retrieval.

---

# Storage Class Comparison

| Storage Class             | Best For                   |
| ------------------------- | -------------------------- |
| Standard                  | Frequently accessed files  |
| Intelligent-Tiering       | Unknown access patterns    |
| Standard-IA               | Occasionally accessed data |
| One Zone-IA               | Re-creatable backups       |
| Glacier Instant Retrieval | Archived files             |

---

# High Availability

Amazon S3 automatically replicates data across multiple **Availability Zones (AZs)**.

```text
Availability Zone A
        │
        ▼
      Object

Availability Zone B
        │
        ▼
      Copy

Availability Zone C
        │
        ▼
      Copy
```

Benefits:

* High durability
* Fault tolerance
* Improved availability

If one Availability Zone fails, your data remains accessible from another.

---

# Why is My Object Not Accessible?

Even after uploading a file, accessing its URL may return:

```text
Access Denied
```

Reason:

Objects are **private by default**.

To make them public:

1. Disable Block Public Access.
2. Add a Bucket Policy granting public read access.

---

# Bucket Policy

A **Bucket Policy** is a JSON document that controls access to a bucket and its objects.

It defines:

* Who can access the bucket.
* What actions are allowed.
* Which resources are affected.

Bucket policies are written in **JSON**.

---

# Policy Components

## Effect

Specifies whether access is:

* Allow
* Deny

---

## Principal

Specifies **who** the policy applies to.

Example:

```text
*
```

means everyone.

---

## Action

Specifies permitted operations.

Common S3 actions:

* GetObject
* PutObject
* DeleteObject

For public websites, **GetObject** is commonly allowed.

---

## Resource

Specifies which bucket or objects the policy applies to.

Example:

```text
arn:aws:s3:::my-bucket/*
```

The `*` means **all objects** inside the bucket.

---

# Public Read Access

A common public bucket policy allows:

* Everyone
* Read-only access
* GetObject permission

Users can:

* View images
* Download files
* Open HTML pages

Users **cannot** upload, modify, or delete objects.

---

# Static Website Hosting

Amazon S3 can host **static websites**.

A static website contains:

* HTML
* CSS
* JavaScript
* Images

No backend code is executed.

Examples:

* Portfolio websites
* Landing pages
* Documentation
* Company websites

---

# Enabling Static Website Hosting

Navigate to:

```text
Bucket
    ↓
Properties
    ↓
Static Website Hosting
    ↓
Enable
```

AWS asks for the:

```text
Index Document
```

Usually:

```text
index.html
```

---

# Creating index.html

Create a simple HTML page.

Example:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <h1>Hello!</h1>
    <p>Welcome to my S3 Website.</p>
</body>
</html>
```

Save as:

```text
index.html
```

Upload it to your bucket.

---

# Hosting Workflow

```text
Create Bucket
        │
        ▼
Upload index.html
        │
        ▼
Enable Static Website Hosting
        │
        ▼
Specify index.html
        │
        ▼
Use Website Endpoint
        │
        ▼
Website Live
```

---

# Website Endpoint

After enabling static hosting, AWS provides a **Bucket Website Endpoint**.

Example:

```text
http://bucket-name.s3-website-region.amazonaws.com
```

Opening this URL loads your `index.html` page.

---

# Typical Static Website Structure

```text
Bucket

├── index.html
├── about.html
├── css/
│     └── style.css
├── js/
│     └── app.js
└── images/
      └── logo.png
```

---

# Common Use Cases of Amazon S3

Amazon S3 is widely used for:

* Website hosting
* Image storage
* Video storage
* File backups
* Document storage
* Log files
* Application assets
* Data archiving

---

# Best Practices

* Use globally unique bucket names.
* Keep buckets private unless public access is required.
* Enable Versioning for important data.
* Select the appropriate Storage Class.
* Encrypt sensitive data.
* Grant only the minimum required permissions (Principle of Least Privilege).
* Use Bucket Policies instead of making everything public unnecessarily.

---

# Key Terms

| Term               | Meaning                                  |
| ------------------ | ---------------------------------------- |
| Bucket             | Container that stores objects            |
| Object             | Uploaded file                            |
| Object Key         | Unique object name/path                  |
| Bucket Policy      | JSON permissions document                |
| Versioning         | Maintains multiple versions of objects   |
| Storage Class      | Determines storage cost and access speed |
| Website Endpoint   | URL for a static website hosted on S3    |
| Public Read Access | Allows anyone to download/read objects   |

---

# Interview Questions

### 1. What is Amazon S3?

Amazon S3 (Simple Storage Service) is AWS's scalable object storage service used to store and retrieve files (objects) inside buckets.

---

### 2. What is an S3 Bucket?

An S3 Bucket is a logical container that stores objects in Amazon S3.

---

### 3. Can objects exist without a bucket?

No. Every object must be stored inside a bucket.

---

### 4. Why must bucket names be globally unique?

Bucket names form part of the S3 service's global namespace, so no two AWS customers can use the same bucket name.

---

### 5. What is Bucket Versioning?

Bucket Versioning stores multiple versions of an object, enabling recovery from accidental deletion or modification.

---

### 6. What is a Bucket Policy?

A Bucket Policy is a JSON-based access control document that specifies who can access a bucket and what actions they can perform.

---

### 7. What is Amazon S3 Static Website Hosting?

It is a feature that allows an S3 bucket to host static websites containing HTML, CSS, JavaScript, and images.

---

# Quick Revision

✔ Amazon S3 stores **Objects** inside **Buckets**.

✔ Bucket names must be **globally unique**.

✔ Objects are **private by default**.

✔ Versioning protects against accidental overwrites.

✔ Storage Classes optimize cost based on access frequency.

✔ Bucket Policies control permissions.

✔ Static Website Hosting allows S3 to host HTML/CSS/JavaScript websites.

✔ The website is accessed using the **Bucket Website Endpoint**.

✔ S3 automatically replicates data across multiple Availability Zones for high durability.

---

# Summary

Amazon S3 (Simple Storage Service) is AWS's highly durable and scalable object storage service. Data is organized into **Buckets**, while individual files are stored as **Objects**. During bucket creation, users choose a region, configure public access, versioning, encryption, and other settings. S3 supports multiple **Storage Classes** to balance cost and performance based on access patterns. Access to objects is controlled using **Bucket Policies**, which are JSON-based permission documents. Amazon S3 can also host **static websites** by enabling Static Website Hosting and uploading an `index.html` file, making it an excellent solution for hosting portfolios, documentation sites, and other static web applications.
