---
title: "5.8.1 Xóa Frontend | Delete Frontend"
date: 2026-08-09
draft: false
weight: 581
---

# 5.8.1. Xóa Frontend
## 5.8.1. Delete Frontend

### Tiếng Việt

**Bước 1 — Empty S3 Frontend Bucket:**

Trước khi xóa stack, phải xóa hết object trong bucket. CloudFormation không thể xóa bucket còn chứa file.

```bash
aws s3 rm s3://smart-campus-frontend-dev-811391287455 --recursive --region ap-southeast-2
```

**Kết quả mong đợi:**
```
delete: s3://smart-campus-frontend-dev-811391287455/index.html
delete: s3://smart-campus-frontend-dev-811391287455/assets/index-xxx.js
...
```

**Bước 2 — Delete Frontend Stack:**

```bash
sam delete --stack-name smart-campus-frontend-dev --region ap-southeast-2 --no-prompts
```

**Kết quả mong đợi:**
```
Deleted successfully
```

Hoặc nếu `sam delete` lỗi:

```bash
aws cloudformation delete-stack --stack-name smart-campus-frontend-dev --region ap-southeast-2
aws cloudformation wait stack-delete-complete --stack-name smart-campus-frontend-dev --region ap-southeast-2
```

### English

**Step 1 — Empty S3 Frontend Bucket:**

Before deleting the stack, you must delete all objects in the bucket. CloudFormation cannot delete a bucket that still contains files.

```bash
aws s3 rm s3://smart-campus-frontend-dev-811391287455 --recursive --region ap-southeast-2
```

**Expected result:**
```
delete: s3://smart-campus-frontend-dev-811391287455/index.html
delete: s3://smart-campus-frontend-dev-811391287455/assets/index-xxx.js
...
```

**Step 2 — Delete Frontend Stack:**

```bash
sam delete --stack-name smart-campus-frontend-dev --region ap-southeast-2 --no-prompts
```

**Expected result:**
```
Deleted successfully
```

Or if `sam delete` fails:

```bash
aws cloudformation delete-stack --stack-name smart-campus-frontend-dev --region ap-southeast-2
aws cloudformation wait stack-delete-complete --stack-name smart-campus-frontend-dev --region ap-southeast-2
```

<!-- [SCREENSHOT: Terminal — output `aws s3 rm` và `sam delete`] -->
<!-- [SCREENSHOT: Terminal — `aws s3 rm` and `sam delete` output] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → smart-campus-frontend-dev → DELETE_IN_PROGRESS] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → smart-campus-frontend-dev → DELETE_IN_PROGRESS] -->
