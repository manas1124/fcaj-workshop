---
title: "5.1 Tổng quan | Overview"
date: 2026-08-09
draft: false
weight: 51
---

# 5.1. Tổng quan
## 5.1. Overview

### Tiếng Việt

**Smart Campus** là hệ thống quản lý khuôn viên thông minh, tích hợp các tính năng:

- **Identity:** Xác thực và quản lý ngườ dùng qua Amazon Cognito.
- **Biometric:** Nhận diện khuôn mặt và chấm công qua Amazon Rekognition.
- **Workforce:** Quản lý nghỉ phép, công việc và thông báo.
- **Intelligence:** Trợ lý AI và báo cáo phân tích.
- **Security:** Quản lý sự cố bảo mật.

Hệ thống sử dụng kiến trúc **event-driven serverless**, dữ liệu được lưu trữ trên DynamoDB, ảnh trên S3, và giao tiếp giữa các service qua EventBridge + SQS.

### English

**Smart Campus** is a smart campus management system with the following features:

- **Identity:** Authentication and user management via Amazon Cognito.
- **Biometric:** Face recognition and attendance via Amazon Rekognition.
- **Workforce:** Leave management, tasks, and notifications.
- **Intelligence:** AI assistant and analytics reports.
- **Security:** Security incident management.

The system uses an **event-driven serverless** architecture, with data stored in DynamoDB, images in S3, and inter-service communication via EventBridge + SQS.

<!-- [SCREENSHOT: Sơ đồ kiến trúc tổng quan — draw.io] -->
<!-- [SCREENSHOT: Overall architecture diagram — draw.io] -->
