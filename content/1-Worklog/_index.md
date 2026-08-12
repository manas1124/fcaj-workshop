---
title: "Worklog"
date: 2026-06-22
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

## About This Worklog

This worklog documents my 8-week internship journey at **FCAJ**, where I worked on the **Smart Campus Platform** project using Amazon Web Services (AWS). The internship spanned from **June 22, 2026 to August 14, 2026**.

Throughout this program, I progressed from a beginner exploring the AWS ecosystem to building a complete event-driven, serverless system with monitoring, security, and CI/CD automation. Each week focused on a specific set of tasks, building upon the previous week's foundation.

## Weekly Overview

| Week | Focus Area | Key Activities |
|---|---|---|
| **Week 1** | [Getting Familiar with AWS](1.1-week1/) | Created AWS Free Tier account, set up billing alerts, installed and configured AWS CLI, and deployed the first EC2 instance with a simple web server. |
| **Week 2** | [Architecture Design](1.2-week2/) | Brainstormed and finalized the Smart Campus Platform topic; analyzed business requirements (Face Attendance, Task Management); selected AWS services for each module; designed the overall architecture diagram, data flow, database schema, and wireframes. |
| **Week 3** | [Event-Driven Architecture](1.3-Week3/) | Studied VPC, Security Groups, and network security; initialized Amazon EventBridge Custom Event Bus; built standardized JSON Event Schemas; integrated boto3 to emit events asynchronously; defined Event Rules and verified via CloudWatch Logs. |
| **Week 4** | [SQS Queues & Notifications](1.4-Week4/) | Created SQS Queues with Dead Letter Queue (DLQ); set up EventBridge Rules for stream branching; wrote Notification Worker Lambda; integrated Amazon SES to send HTML attendance confirmation emails; configured IAM policies. |
| **Week 5** | [Broadcasting & Cronjob Scheduling](1.5-Week5/) | Created SNS Topic for emergency broadcasting; set up EventBridge Scheduler (every 30 minutes); wrote Cronjob Worker Lambda to scan DynamoDB for overdue tasks; integrated SES for automated reminder emails; adjusted IAM security policies. |
| **Week 6** | [System Security with WAF](1.6-Week6/) | Initialized AWS WAF WebACL attached to API Gateway and CloudFront; enabled AWS Managed Rules (SQL Injection, XSS); created Rate-Based Rule (1000 req/5min) and Geo-Match rule (block outside Vietnam); simulated attacks and verified auto-block. |
| **Week 7** | [Monitoring & CI/CD](1.7-Week7/) | Configured CloudWatch Logs Insights and X-Ray SDK; created CloudWatch Alarms integrated with SNS; set up AWS CodePipeline with GitHub; wrote buildspec.yml for Frontend (npm build → S3) and Backend (Unit Tests → Lambda); explored CloudFormation/Terraform basics. |
| **Week 8** | [Project Summary & Report](1.8-Week8/) | Performed End-to-End Testing and fixed final bugs; compiled technical documentation (Architecture, API Docs, Database Schema); recorded demo video showcasing main Smart Campus flows; drafted and finalized the internship report. |
