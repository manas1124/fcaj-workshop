---
title: "5.3 Kiến trúc hệ thống | Architecture"
date: 2026-08-09
draft: false
weight: 53
---

# 5.3. Kiến trúc hệ thống
## 5.3. System Architecture

### Tiếng Việt

Hệ thống được chia thành **2 stack CloudFormation**:

#### Backend Stack (`template-backend.yaml`)

| Thành phần | Mô tả |
|-----------|-------|
| API Gateway (HTTP API) | Entry point cho tất cả API requests |
| Lambda — Identity | Auth + User Management |
| Lambda — Biometric | Face Recognition + Attendance |
| Lambda — Workforce | Leaves + Tasks + Notifications |
| Lambda — Intelligence | AI Assistant + Reports |
| Lambda — Security | Security Incidents |
| Lambda — Analytics Worker | Stream data từ SQS → Firehose |
| Lambda — Notification Worker | Gửi SNS từ SQS events |
| Lambda — Cron Worker | Check task deadlines mỗi 10 phút |
| SQS Queues | Analytics Queue + Notification Queue + DLQ |
| EventBridge EventBus | Routing events giữa các service |
| Lambda Layer | Shared Python dependencies |

#### Frontend Stack (`template-frontend.yaml`)

| Thành phần | Mô tả |
|-----------|-------|
| S3 Bucket | Static hosting cho React app |
| CloudFront Distribution | CDN phân phối toàn cầu |
| Origin Access Control (OAC) | Bảo mật truy cập S3 từ CloudFront |
| Security Headers Policy | CSP, HSTS, Frame Options |

### English

The system is split into **2 CloudFormation stacks**:

#### Backend Stack (`template.yaml`)

| Component | Description |
|-----------|-------------|
| API Gateway (HTTP API) | Entry point for all API requests |
| Lambda — Identity | Auth + User Management |
| Lambda — Biometric | Face Recognition + Attendance |
| Lambda — Workforce | Leaves + Tasks + Notifications |
| Lambda — Intelligence | AI Assistant + Reports |
| Lambda — Security | Security Incidents |
| Lambda — Analytics Worker | Stream data from SQS → Firehose |
| Lambda — Notification Worker | Send SNS from SQS events |
| Lambda — Cron Worker | Check task deadlines every 10 minutes |
| SQS Queues | Analytics Queue + Notification Queue + DLQ |
| EventBridge EventBus | Routing events between services |
| Lambda Layer | Shared Python dependencies |

#### Frontend Stack (`template-frontend.yaml`)

| Component | Description |
|-----------|-------------|
| S3 Bucket | Static hosting for React app |
| CloudFront Distribution | Global CDN distribution |
| Origin Access Control (OAC) | Secure S3 access from CloudFront |
| Security Headers Policy | CSP, HSTS, Frame Options |

<!-- [SCREENSHOT: Sơ đồ kiến trúc chi tiết — API Gateway → Lambda → DynamoDB/S3/Rekognition] -->
<!-- [SCREENSHOT: Detailed architecture diagram — API Gateway → Lambda → DynamoDB/S3/Rekognition] -->
