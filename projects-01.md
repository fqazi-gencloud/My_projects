## AWS Serverless Event-Driven Architecture


**Assigned By :** `Decode Project - NIC Peshawar`


# 🎯OBJECTIVE 

 ☁️We want to implement this architecture on cloud 

* ⚙️To optimize the workload 
* 📈Improve the scalability 
* 🚀Triggering different AWS services like S3, LAMBDA Function, SQS, DynamoDB and so on. 
* 🌐Understanding cloud orchestration 

# Understanding the Components

Triggers different AWS services 

# Lambda ⚡

AWS Lambda is a serverless compute service that means the server is already preconfigured and managed. It allows you to run code in response to events. It automatically scales to handle incoming requests, making it an ideal choice for event-driven applications.

 is a scalable, fully managed service that allows you to create, publish, and secure APIs for your applications, enabling developers to expose backend services as HTTP APIs, WebSocket APIs, or RESTful APIs with ease.
 # Amazon S3 📦

Amazon S3 is an object storage service that can store and retrieve large amounts of data. It can trigger events when objects are created, updated, or deleted, making it a natural choice for handling file uploads.

# SQS 📬

Amazon Simple Queue Service (SQS) is a managed message queue service. It allows decoupling of components in a distributed system and can be used to ensure reliable and asynchronous communication between services.

# Amazon DynamoDB 📊

Amazon DynamoDB is a NoSQL database service that provides fast and scalable data storage. It’s ideal for storing structured data with low-latency access.

# Event Bridge 🌉

AWS Event Bridge is a fully managed event bus service that makes it easy to connect and route events from various sources to AWS services, Lambda functions, and custom targets, enabling event-driven architectures.

# API Gateway 🌐

Amazon API Gateway is a scalable, fully managed service that allows you to create, publish, and secure APIs for your applications, enabling developers to expose backend services as HTTP APIs, WebSocket APIs, or RESTful APIs with ease.

# Use Case 1: Asynchronous File Processing 📂

Let us take the first workflow to process a file (refer to the diagram):

1. A CSV file is uploaded to an S3 bucket.
2. The S3 bucket is configured to trigger a Lambda function when a new file is uploaded.
3. The Lambda function processes the CSV data and sends individual records to an SQS queue.
4. Another Lambda function listens to the SQS queue and processes the messages.
5. The processed data is then stored in DynamoDB.
# Use Case 2: API Workflow 🌐

Probably the easiest way to get started with serverless. Let us take the second workflow (refer to the diagram):

1. **Client Request**: The process begins with a client making an HTTP request to an API Gateway. 🌍
2. **API Gateway**: The API Gateway acts as an entry point and routes the client request to a specific AWS Lambda function. 🚪
3. **AWS Lambda**: The Lambda function processes the incoming request, which can include data validation, transformation, or business logic. ⚙️
4. **Data Storage**: After processing, the Lambda function stores the relevant data efficiently in Amazon DynamoDB. 📊


## 🎉 Use Case 3: Event Producers for Distributed Computing Models

Let's dive into the third workflow (refer to the diagram):

### 🚀 Event Producer
An event producer generates an event, which could be a system event, user action, or any trigger-worthy occurrence.

### 📅 Event Occurrence
The event occurs, and the event producer sends this event to **AWS EventBridge**.

### 🌉 EventBridge
**AWS EventBridge** is used as an event bus that receives the event from the producer. It acts as a central hub for routing events to various targets based on defined rules.

### 🛠️ Lambda Function
An **AWS Lambda function** is configured as a target for a specific rule in EventBridge. When the event matches the rule, EventBridge invokes the Lambda function, which then processes the event data, executing custom logic, transformations, or other actions as needed.

### 💾 Data Storage
Following processing, the Lambda function stores the processed data in **Amazon DynamoDB**.



