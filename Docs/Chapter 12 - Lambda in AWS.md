# AWS Lambda – Create Your First Serverless Function (Learning Notes)

## What is AWS Lambda?

**AWS Lambda** is a **serverless computing service** that allows you to run code without managing servers.

* You upload your code.
* AWS automatically runs it when an event occurs.
* AWS manages the servers, scaling, operating system, and infrastructure.
* You only pay for the time your code is executing.

> **Key Idea:** Servers still exist, but AWS manages them instead of you.

---

# Benefits of AWS Lambda

* No server management
* Automatic scaling
* Pay only when code runs
* Supports multiple programming languages
* Easy integration with other AWS services

Supported runtimes include:

* Node.js
* Python
* Java
* .NET
* Ruby
* Custom Runtime

---

# How Lambda Works

```
User/Event
      │
      ▼
AWS Lambda Function
      │
      ▼
Execute Code
      │
      ▼
Return Response
```

A Lambda function runs only when it is triggered.

Common triggers include:

* API requests
* S3 file uploads
* Database changes
* Scheduled events
* SNS/SQS messages

---

# Steps to Create Your First Lambda Function

## Step 1 – Open Lambda

AWS Console

→ Search **Lambda**

→ Open **AWS Lambda**

---

## Step 2 – Create Function

Click

```
Create Function
```

Three options are available:

### 1. Author from Scratch

Write your own code.

### 2. Blueprint

Use AWS-provided templates such as:

* Hello World
* Sample API
* Event Processing

### 3. Container Image

Deploy a Docker image stored in Amazon ECR.

---

## Step 3 – Configure Function

Example configuration:

```
Function Name:
my-first-function

Runtime:
Node.js 22

Architecture:
x86_64
```

---

# Execution Role (IAM Role)

Every Lambda function needs permissions.

Example:

If Lambda needs to:

* Read from S3
* Write to DynamoDB
* Access CloudWatch

It requires an **IAM Execution Role**.

AWS can automatically create this role during function creation.

Example role:

```
my-first-function-role
```

This role determines what resources Lambda is allowed to access.

---

# Lambda Boilerplate Code

AWS provides sample code like:

```javascript
export const handler = async (event) => {

    console.log(event.key1);
    console.log(event.key2);
    console.log(event.key3);

    return event.key1;

};
```

Here,

`event` contains data sent to the Lambda function.

Example event:

```json
{
    "key1": "value1",
    "key2": "value2",
    "key3": "value3"
}
```

Output:

```
value1
```

---

# Testing Lambda Inside AWS

Click

```
Test
```

Create a new test event.

Example:

```json
{
    "key1": "value1",
    "key2": "value2",
    "key3": "value3"
}
```

Save the event.

Click

```
Invoke
```

Lambda executes immediately.

You can view:

* Response
* Logs
* Execution time
* Memory usage

---

# Deploying Lambda

Whenever you change the code,

Click

```
Deploy
```

Only deployed code becomes available to users.

---

# Creating a Function URL

To call Lambda from a browser or Postman,

Go to:

```
Configuration

↓

Function URL

↓

Create Function URL
```

Authentication options:

* AWS IAM Authentication
* Public (No Authentication)

For testing:

```
Authentication Type

None (Public)
```

AWS generates a URL such as:

```
https://xxxxxxxx.lambda-url.region.on.aws/
```

This acts as a REST API endpoint.

---

# Why Initial Response Returned Null

Original code:

```javascript
return event.key1;
```

This works for Lambda testing but does **not** return a proper HTTP response for browsers or Postman.

---

# Correct HTTP Response Format

Instead, return:

```javascript
export const handler = async (event) => {

    return {
        statusCode: 200,
        headers: {
            "Content-Type": "application/json"
        },
        body: JSON.stringify({
            message: "Hello from Lambda Function"
        })
    };

};
```

This follows the HTTP response format expected by API clients.

---

# Deploy Again

After updating the code:

```
Deploy
```

Then call the Function URL again.

Response:

```json
{
    "message": "Hello from Lambda Function"
}
```

---

# Testing with Postman

Method:

```
POST
```

URL:

```
https://your-function-url.lambda-url.region.on.aws/
```

Body → Raw → JSON

Example:

```json
{
    "key1": "Value One",
    "key2": "Value Two",
    "key3": "Value Three"
}
```

Response:

```json
{
    "message": "Hello from Lambda Function"
}
```

---

# Lambda Execution Flow

```
Client
   │
   ▼
HTTP Request
   │
   ▼
Function URL
   │
   ▼
AWS Lambda
   │
   ▼
Execute Code
   │
   ▼
HTTP Response
```

---

# Lambda vs EC2

| EC2                     | AWS Lambda                 |
| ----------------------- | -------------------------- |
| Manage servers          | No server management       |
| Pay while server runs   | Pay only during execution  |
| Manual scaling          | Automatic scaling          |
| Continuous server       | Runs only when triggered   |
| OS maintenance required | AWS manages infrastructure |

---

# Important Concepts Learned

* Lambda is a serverless compute service.
* AWS manages all servers behind the scenes.
* You only pay while code executes.
* Lambda supports many programming languages.
* Functions execute only when triggered.
* IAM Execution Roles provide permissions to AWS resources.
* AWS offers Blueprint templates for quick function creation.
* Test events help verify function behavior.
* Changes must be deployed before becoming live.
* Function URLs expose Lambda as an HTTP endpoint.
* Browsers and Postman require a proper HTTP response (`statusCode`, `headers`, `body`).
* Lambda automatically scales based on incoming requests.

---

# Interview Questions

### 1. What is AWS Lambda?

AWS Lambda is a serverless computing service that runs code without requiring developers to manage servers.

---

### 2. Why is Lambda called serverless?

Because AWS manages the servers, operating system, scaling, and maintenance while developers focus only on writing code.

---

### 3. What triggers a Lambda function?

Examples include:

* API requests
* S3 uploads
* Database events
* Scheduled events
* SNS/SQS messages

---

### 4. What is an Execution Role?

An IAM Role attached to a Lambda function that grants permissions to access other AWS services.

---

### 5. Why should Lambda return `statusCode` and `body`?

Because HTTP clients like browsers and Postman expect a proper HTTP response format.

---

### 6. What happens if you modify Lambda code but do not deploy it?

The old deployed version continues to execute. Changes are not applied until you click **Deploy**.

---

# Quick Revision

* Lambda = Serverless compute
* No server management
* Event-driven execution
* Auto scaling
* Pay per execution
* Supports multiple languages
* IAM Role controls permissions
* Test using Test Events
* Deploy after code changes
* Function URL exposes Lambda as an API
* Return proper HTTP responses for API clients
