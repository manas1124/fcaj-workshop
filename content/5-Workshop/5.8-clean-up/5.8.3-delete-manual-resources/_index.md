---
title: "5.8.3 Xóa Resource thủ công | Delete Manual Resources"
date: 2026-08-09
draft: false
weight: 583
---

# 5.8.3. Xóa Resource thủ công
## 5.8.3. Delete Manual Resources

### Tiếng Việt

Các resource tạo thủ công ở Step 5.4 cần xóa bằng tay vì không thuộc CloudFormation stack.

**Bước 1 — Xóa DynamoDB Tables:**

```bash
aws dynamodb delete-table --table-name smart-campus-users --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-faces --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-attendance --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-leaves --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-holidays --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-tasks --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-notifications --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-security --region ap-southeast-2
```

**Bước 2 — Xóa S3 Images Bucket:**

```bash
aws s3 rm s3://smart-campus-images --recursive --region ap-southeast-2
aws s3api delete-bucket --bucket smart-campus-images --region ap-southeast-2
```

**Bước 3 — Xóa Rekognition Collection (nếu đã tạo):**

```bash
aws rekognition delete-collection --collection-id smart-campus-faces --region ap-southeast-2
```

**Bước 4 — Xóa SNS Topic (nếu đã tạo):**

```bash
aws sns delete-topic --topic-arn arn:aws:sns:ap-southeast-2:811391287455:smart-campus-notifications-dev --region ap-southeast-2
```

**Bước 5 — Xóa SES Identity (nếu đã tạo):**

Trên AWS Console: **SES → Verified identities → Chọn email → Delete**

**Bước 6 — Xóa Cognito User Pool (nếu không dùng nữa):**

Trên AWS Console: **Cognito → User pools → smart-campus-users → Delete**

### English

Resources created manually in Step 5.4 need to be deleted by hand as they are not part of the CloudFormation stack.

**Step 1 — Delete DynamoDB Tables:**

```bash
aws dynamodb delete-table --table-name smart-campus-users --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-faces --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-attendance --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-leaves --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-holidays --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-tasks --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-notifications --region ap-southeast-2
aws dynamodb delete-table --table-name smart-campus-security --region ap-southeast-2
```

**Step 2 — Delete S3 Images Bucket:**

```bash
aws s3 rm s3://smart-campus-images --recursive --region ap-southeast-2
aws s3api delete-bucket --bucket smart-campus-images --region ap-southeast-2
```

**Step 3 — Delete Rekognition Collection (if created):**

```bash
aws rekognition delete-collection --collection-id smart-campus-faces --region ap-southeast-2
```

**Step 4 — Delete SNS Topic (if created):**

```bash
aws sns delete-topic --topic-arn arn:aws:sns:ap-southeast-2:811391287455:smart-campus-notifications-dev --region ap-southeast-2
```

**Step 5 — Delete SES Identity (if created):**

On AWS Console: **SES → Verified identities → Select email → Delete**

**Step 6 — Delete Cognito User Pool (if no longer needed):**

On AWS Console: **Cognito → User pools → smart-campus-users → Delete**

<!-- [SCREENSHOT: AWS Console → DynamoDB → Tables → không còn bảng nào] -->
<!-- [SCREENSHOT: AWS Console → DynamoDB → Tables → no tables remaining] -->
<!-- [SCREENSHOT: AWS Console → S3 → Buckets → không còn bucket images] -->
<!-- [SCREENSHOT: AWS Console → S3 → Buckets → images bucket removed] -->
