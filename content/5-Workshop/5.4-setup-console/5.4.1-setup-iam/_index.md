---
title: "5.4.1 Setup IAM | Setup IAM"
date: 2026-08-09
draft: false
weight: 541
---

# 5.4.1. Setup IAM
## 5.4.1. Setup IAM

### Tiếng Việt

Tạo IAM User hoặc sử dụng IAM Role với quyền đầy đủ để deploy CloudFormation và các dịch vụ AWS.

**Trên AWS Console:**

1. Truy cập **IAM → Users → Create user**
2. Đặt tên: `smart-campus-deployer`
3. Chọn **Attach policies directly**
4. Chọn policy: `AdministratorAccess`
   - Hoặc các policy cụ thể:
     - `AmazonS3FullAccess`
     - `AWSLambda_FullAccess`
     - `AmazonAPIGatewayAdministrator`
     - `AWSCloudFormationFullAccess`
     - `IAMFullAccess`
     - `AmazonDynamoDBFullAccess`
     - `AmazonSQSFullAccess`
     - `AmazonEventBridgeFullAccess`
     - `CloudFrontFullAccess`
     - `AmazonSESFullAccess`
     - `AmazonRekognitionFullAccess`
     - `AmazonBedrockFullAccess`
     - `AmazonAthenaFullAccess`
5. Hoàn tất → **Create user**
6. Vào user → **Security credentials → Create access key**
7. Chọn **CLI** → Download CSV

### English

Create an IAM User or use an IAM Role with sufficient permissions to deploy CloudFormation and AWS services.

**On AWS Console:**

1. Go to **IAM → Users → Create user**
2. Name: `smart-campus-deployer`
3. Select **Attach policies directly**
4. Select policy: `AdministratorAccess`
   - Or specific policies:
     - `AmazonS3FullAccess`
     - `AWSLambda_FullAccess`
     - `AmazonAPIGatewayAdministrator`
     - `AWSCloudFormationFullAccess`
     - `IAMFullAccess`
     - `AmazonDynamoDBFullAccess`
     - `AmazonSQSFullAccess`
     - `AmazonEventBridgeFullAccess`
     - `CloudFrontFullAccess`
     - `AmazonSESFullAccess`
     - `AmazonRekognitionFullAccess`
     - `AmazonBedrockFullAccess`
     - `AmazonAthenaFullAccess`
5. Complete → **Create user**
6. Go to user → **Security credentials → Create access key**
7. Select **CLI** → Download CSV

<!-- [SCREENSHOT: AWS Console → IAM → Users → smart-campus-deployer → Permissions tab] -->
<!-- [SCREENSHOT: AWS Console → IAM → Users → smart-campus-deployer → Security credentials → Access keys] -->
