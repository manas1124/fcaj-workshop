---
title: "Project Proposal"
date: 2026-07-20
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

## 1. Project Overview
**Smart Campus Platform** is a comprehensive software system designed to modernize and digitize management processes within school and corporate campuses. The project transforms the model from "Passive Monitoring" to "Automated Operations", including AI-powered facial recognition attendance, Task & Leave Management, and a Big Data Analytics Command Center.

Notably, the system is designed as **100% Serverless on AWS**, applying an Event-Driven Microservices architecture to ensure high scalability, low cost, and resilient operations.

## 2. Problem Statement
The system addresses critical pain points in traditional management:
- **Manual Attendance & Fraud:** Using RFID cards or fingerprints is prone to loopholes, forgotten cards, or delays during peak hours.
- **Fragmented Data:** Personnel, task, and attendance data are scattered, making it difficult for Directors/Managers to view holistic reports.
- **High Server Operating Costs:** Internal systems typically do not have users 24/7 (evenings and weekends are usually empty), yet businesses still pay to maintain physical servers.
- **Lack of Proactive Alerts:** Management is not notified in a timely manner when employees are late, on leave, or when tasks are overdue.

## 3. Objectives
- **Automation & Accuracy:** Apply AI facial recognition combined with IP Whitelisting for fast, absolutely accurate attendance and fraud prevention.
- **Data Centralization (Data Lake):** Build an Analytics Pipeline that collects thousands of event streams to serve real-time reporting and analysis.
- **100% Cost Optimization:** Thoroughly apply Serverless architecture (pay-per-API-call), ensuring zero cost when no users are active.
- **Cloud-Standard Security:** Strict Role-Based Access Control (RBAC) and protection of sensitive data via Firewall and Token systems.

## 4. Workflows & Solution Architecture

> **[OVERALL ARCHITECTURE DIAGRAM]**
> <!-- TODO: When the architecture diagram is complete, insert the image here using the syntax: ![Architecture Diagram](/images/architecture.png) -->

The system is designed based on an **Event-Driven Microservices** architecture and leverages more than 15 AWS cloud services. Below are the details of 6 core business workflows and how AWS services collaborate to solve the problem:

### 4.1. Auth & Users Workflow
- **Business Logic:** Manage user account lifecycle, implement Role-Based Access Control (RBAC) for Admin, Manager, and Staff. Force new users to change their password on first login.
- **AWS Services:** Use **Amazon Cognito** as the Identity Provider to issue and authenticate JWT Tokens. The React/Vite Frontend interface is hosted on **Amazon S3** and distributed via **Amazon CloudFront**.

### 4.2. Face Registration Workflow
- **Business Logic:** Prevent fraud by allowing each employee to register only one genuine facial identity into the system.
- **AWS Services:** Call the `IndexFaces` API of **Amazon Rekognition** to extract biometric features and store the FaceID. Original JPEG/PNG images are stored with absolute security in an **Amazon S3 Private Bucket**.

### 4.3. Smart Attendance Workflow
- **Business Logic:** The check-in/check-out process is performed by presenting a face to the camera. The system automatically matches, validates the time window, and verifies whether the employee is using the correct office IP address (preventing fake GPS/VPN).
- **AWS Services:**
  - **AWS WAF (Web Application Firewall):** Blocks attendance requests originating from outside the company network (IP Whitelisting).
  - **Amazon Rekognition:** Calls the `SearchFacesByImage` function to compare the match confidence (Confidence > 95%).
  - **Amazon API Gateway & AWS Lambda:** API Gateway receives requests from the Frontend, passes them to Lambda (running FastAPI) to process logic and stores the status in **Amazon DynamoDB**.

### 4.4. Event-Driven Notifications
- **Business Logic:** When an employee successfully checks in or is assigned a new task, the system automatically pushes multi-channel notifications to relevant parties without slowing down the user experience.
- **AWS Services:**
  - **Amazon EventBridge:** Receives events (e.g., `AttendanceRecorded`) and routes them (Routing).
  - **Amazon SQS:** Acts as a queue to hold events from EventBridge and sends them to Lambda Background Workers.
  - **Amazon SNS & Amazon SES:** Sends Push Notifications, SMS (SNS), and Emails (SES) to management.

### 4.5. Task Management Workflow
- **Business Logic:** Assign tasks with strict deadlines and process leave request workflows. Managers can attach confidential documents to tasks.
- **AWS Services:**
  - **Amazon DynamoDB:** Stores Tasks and Leaves data structures with Global Secondary Indexes (GSI) for fast querying.
  - **Amazon S3 Pre-signed URL:** Generates dynamic, time-limited links for downloading confidential attachments, preventing data leakage.
  - **Amazon EventBridge (Cronjob):** Runs a scheduled job every 30 minutes to scan and alert on overdue tasks.

### 4.6. Data Lake Analytics Workflow
- **Business Logic:** Collect massive attendance logs from campuses, aggregate data so that Directors can view Performance Reports (Dashboards) comparing departments.
- **AWS Services:**
  - **Amazon Kinesis Data Firehose:** Receives attendance log streams, automatically partitions folders by date (Dynamic Partitioning), and stores large files into the **S3 Data Lake**.
  - **AWS Glue (Data Catalog):** Automatically collects the schema of JSON files on S3.
  - **Amazon Athena:** A serverless SQL query engine that reads data directly from S3 via the Glue Catalog to return ultra-fast statistics to the Frontend.

### 4.7. Core AWS Services Listing
Below is a summary table of AWS services applied in the architecture diagram:

| No. | AWS SERVICE | ROLE & MISSION IN SMART CAMPUS | REASON FOR SELECTION & TECHNICAL BENEFITS |
|:---:|:---|:---|:---|
| 1 | **Amazon CloudFront** | Distributes the React Frontend application from the S3 Bucket to users. Acts as the anchor for AWS WAF. | Accelerates page loading via caching at Edge Locations. Supports automatic HTTPS, reduces bandwidth load. |
| 2 | **AWS WAF** | Firewall protecting attendance, blocks IPs not belonging to the office. | Prevents remote attendance fraud, defends against Web attacks and spam requests. |
| 3 | **Amazon S3** | **Bucket 1:** Stores Frontend. <br> **Bucket 2:** Stores facial images & confidential documents. <br> **Bucket 3:** S3 Data Lake for logs. | Low storage cost, 99.999999999% durability. Supports S3 Presigned URL for hiding secure files. Integrates well with Athena. |
| 4 | **Amazon API Gateway** | RESTful/HTTP API gateway that receives requests from the Frontend and invokes AWS Lambda. | Supports Rate Limiting, built-in JWT authentication via Cognito Authorizer without writing code. |
| 5 | **AWS Lambda** | **API Handler:** Processes API logic. <br> **Workers:** Processes background events. | Serverless Pay-As-You-Go model (pay only when code runs). Auto-scales instantly, no server management. |
| 6 | **Amazon DynamoDB** | Stores all business data (Users, Tasks, Leaves, Attendance). | Serverless NoSQL database, millisecond response time, flexible with Global Secondary Index. |
| 7 | **Amazon Cognito** | Manages User Pool, authenticates login, and issues JWT Tokens. | No need to build your own Auth system. High security, supports mandatory password change on first login. |
| 8 | **Amazon EventBridge** | Event Bus that routes events (e.g., `AttendanceRecorded`) and runs Cronjobs. | Decouples modules following the Event-Driven standard, easily adds new business logic. |
| 9 | **Amazon SQS** | Message queue standing in front of Workers. | Ensures no data loss when errors occur. Integrates Dead Letter Queue (DLQ) for retry. |
| 10 | **Amazon Rekognition** | Matches employee faces via camera during check-in. | Powerful ready-to-use AI, no time spent training models. High accuracy (Confidence > 95%). |
| 11 | **Amazon Kinesis Data Firehose, Glue & Athena** | The trio pipeline that aggregates attendance logs on S3, analyzes, and queries with SQL. | Automatic file batching to save S3/Athena costs. Separates OLTP and OLAP systems. |
| 12 | **AWS SAM (Serverless Application Model)** | Infrastructure-as-Code framework to define, build, and deploy the entire Serverless stack (Lambda, API Gateway, DynamoDB, etc.) using a single `template.yaml`. | Simplifies deployment with local testing (`sam local invoke`), automatic packaging, and consistent environment replication. No dedicated CI/CD server costs. |

### 4.8. Architecture Assessment against the 5 Pillars of AWS Well-Architected Framework
The entire Smart Campus Platform architecture is designed to strictly adhere to the 5 Pillars of the AWS Well-Architected Framework:

1. **Operational Excellence:** Manage the entire application lifecycle via **AWS SAM** Infrastructure-as-Code (`template.yaml`), enabling repeatable, version-controlled deployments. Centralized monitoring of logs and event metrics through Amazon CloudWatch to detect bottlenecks early.
2. **Security:** Enforce the Least Privilege principle through specific IAM Roles for each Lambda function. Hide sensitive attachments via S3 Pre-signed URL, encrypt connections using CloudFront's HTTPS/TLS, and protect the API gateway with AWS WAF combined with Cognito JWT Authorizer.
3. **Reliability:** Ensure continuous High Availability thanks to the default Multi-AZ architecture of the Serverless ecosystem. Automatic retry mechanism and pushing failed messages to the Dead-Letter Queue (DLQ) of Amazon SQS helps prevent attendance log loss.
4. **Performance Efficiency:** Smoothly distribute static Frontend applications through CloudFront's Edge locations. Optimize data read/write time to the millisecond level with DynamoDB, while offloading the main OLTP system by pushing large queries to the Data Lake stream (Firehose & Athena).
5. **Cost Optimization:** Thoroughly apply the 100% Serverless Event-Driven model (pay only when the system is called). Set up S3 Lifecycle Rules to automatically tier storage (move old logs to Glacier), minimizing cold storage costs.

## 5. Estimated Timeline
| Week | Work Items |
|:---|:---|
| **Week 5** | **Foundation & IaC:** Write AWS SAM `template.yaml` for the entire stack (Lambda, API Gateway, DynamoDB, Cognito, S3, CloudFront, WAF). Deploy initial infrastructure. Build core Backend API skeleton (FastAPI) with DynamoDB models. |
| **Week 6** | **Auth, AI & Event-Driven:** Integrate Cognito JWT auth. Implement Rekognition face registration & smart attendance. Set up EventBridge + SQS + SNS/SES for event-driven notifications. |
| **Week 7** | **Frontend & Business Logic:** Build ReactJS/Vite Frontend. Implement Task & Leave Management APIs. Configure S3 Pre-signed URLs for confidential attachments. Set up EventBridge Cronjob for overdue task alerts. |
| **Week 8** | **Analytics, Testing & Optimization:** Build Data Lake Pipeline (Firehose → S3 → Glue → Athena). Run end-to-end automation testing. X-Ray performance tuning. Finalize SAM deployment, documentation, and demo preparation. |

## 6. Monthly Budget Estimation
The budget estimate is calculated based on actual operating scale at a medium-sized campus: **200 employees, each checking in an average of 1 to 4 times per day** (morning arrival, lunch break, afternoon return, evening departure). In total, the system will process approximately **20,000 attendance checks per month** and approximately **150,000 API requests per month** (including task assignments, reports, and leave requests).

To demonstrate the optimization of Serverless, the estimate below is calculated **based on the standard Pay-As-You-Go pricing** without relying on the AWS 12-month Free Tier package.

| AWS SERVICE | ESTIMATED MONTHLY USAGE | REFERENCE PRICE (AP-SOUTHEAST-1) | MONTHLY COST (USD) |
|:---|:---|:---|:---:|
| **AWS Lambda** | 150,000 API Requests + 40,000 Worker executions (Memory: 512MB, Avg: 1s) | $0.20 / 1M Requests + Compute time | **$1.62** |
| **Amazon API Gateway** | 150,000 HTTP API calls | $1.00 / 1M Requests | **$0.15** |
| **Amazon SQS** | 50,000 SQS Requests (Send & Receive) | $0.40 / 1M Requests | **$0.02** |
| **Amazon DynamoDB** | 500,000 WCU, 500,000 RCU (On-Demand Mode) + 2GB Storage | $1.25 / 1M WCU, $0.25 / 1M RCU + $0.25/GB | **$1.26** |
| **Amazon S3** | ~5GB Storage (Frontend, Images, Data Lake) + 100k GET/PUT | $0.025 / GB Storage + $0.004 / 1k PUT | **$0.53** |
| **Amazon CloudFront** | 20GB Data Transfer Out + 200k HTTPS Requests | $0.09 / GB | **$1.80** |
| **AWS WAF** | 1 Web ACL + 1 Rule (IP Match) + 150k Requests | $5.00/Web ACL + $1.00/Rule + $0.60/1M Req | **$6.09** |
| **Amazon Cognito** | Under 1,000 MAU (Monthly Active Users) | Free (Under 50,000 MAU permanently) | **$0.00** |
| **Amazon Rekognition** | 20,000 image scans for facial comparison (SearchFacesByImage) | $0.001 / image scan | **$20.00** |
| **Amazon Firehose & Athena** | ~1GB Data Ingestion & Scanned by Athena query | $0.03/GB Ingestion + $5.00/TB Scanned | **$0.04** |
| **Amazon CloudWatch** | 1GB Log Ingestion + 3 Custom Metrics | $0.57 / GB Logs | **$1.47** |
| **AWS SAM** | Infrastructure-as-Code deployment tool | Free (only billed for underlying resources created) | **$0.00** |
| **TOTAL** | **Smart Campus operating cost (200 Users)** | | **~ $32.98 / month** |

### 6.1. Cost Optimization Strategy
Although the base operating cost is already very low, the system applies additional in-depth optimization strategies:
1. **Pure Serverless Pay-As-You-Go Model:** Using AWS Lambda and **API Gateway HTTP API** (71% cheaper than REST API) ensures the system incurs no server maintenance costs during nighttime or weekend hours.
2. **Infrastructure-as-Code with AWS SAM:** Using **AWS SAM** instead of managed CI/CD pipelines (CodeBuild/CodePipeline) eliminates dedicated build server costs. SAM is free — you only pay for the underlying resources deployed.
3. **S3 Lifecycle Rules & Firehose Compression:** Automatically compress attendance logs into Parquet format via Firehose and transfer logs older than 90 days to **S3 Glacier Flexible Retrieval**, reducing long-term storage costs by 85%.
4. **Using SQS Long Polling:** Configuring `ReceiveMessageWaitTimeSeconds = 20` helps minimize the number of empty receive requests to SQS, significantly saving API call costs.
5. **AWS Lambda Power Tuning:** Perform a search for the optimal RAM level to balance response speed (Latency) and execution cost, ensuring Lambda is not over-provisioned with memory causing waste.

## 7. Risks & Mitigations

| No. | RISK TYPE | DETAILED RISK ANALYSIS | LEVEL | MITIGATION STRATEGY |
|:---:|:---|:---|:---:|:---|
| 1 | **Performance** | **API Bottleneck or Lambda Cold Start:** When hundreds of employees rush to check in simultaneously at 8:00 AM, Lambda latency may spike (Cold Start). | **HIGH** | - Set up **Provisioned Concurrency** for critical Lambda functions during peak hours.<br>- Use SQS as a buffer to absorb sudden traffic spikes, processing asynchronously. |
| 2 | **Security** | **Spam API Attack / Fraud:** Bad actors continuously send junk requests to drain the AWS budget (Financial Exhaustion) or use fake images. | **CRITICAL** | - Enable **AWS WAF** combined with Rate Limiting and block unknown IPs.<br>- Require JWT authentication via Cognito Authorizer before processing.<br>- Enforce Least Privilege for each Lambda Role. |
| 3 | **Operations** | **Data Loss:** The system is processing attendance when a Lambda Worker unexpectedly times out or crashes. | **MEDIUM** | - Configure appropriate SQS `VisibilityTimeout`.<br>- Enable **Dead-Letter Queue (DLQ)** to catch messages that fail more than 3 times, allowing engineers to review without losing attendance logs. |
| 4 | **Cost Management** | **Spike Cost:** Infinite loop bugs in Lambda code or excessive error logging to CloudWatch. | **MEDIUM** | - Set up **AWS Budgets Alert** to automatically alert via Email/Slack when costs exceed $40 USD/month.<br>- Configure CloudWatch Log Retention to a maximum of 14 days instead of indefinite. |

## 8. Expected Outcomes

After completing deployment, the **Smart Campus** system is expected to achieve the following technical indicators and business goals:

**Technical KPIs:**
- **Availability SLA:** Achieve a minimum of **99.9%** stable uptime thanks to AWS's Multi-AZ Serverless infrastructure.
- **API Latency:** **< 200ms** for standard data read/write operations via API Gateway & DynamoDB.
- **AI Processing Time:** **< 2.0 seconds** from sending the facial image to receiving the attendance result.
- **Concurrent Capacity:** Smoothly handle a minimum of **500 simultaneous attendance requests** without dropping requests or system congestion.

**Business Outcomes:**
- **Cost Optimization:** Save more than **80%** of infrastructure operating costs compared to traditional server rental (EC2/VPS), thanks to the serverless Pay-as-you-go model.
- **High Maintainability:** The entire architecture is modularized into separate Microservices (Event-Driven), allowing upgrades or bug fixes to one feature without disrupting the entire system.
- **Superior User Experience:** Fully digitize paperwork, providing a smart, modern, and transparent working environment for all personnel.
