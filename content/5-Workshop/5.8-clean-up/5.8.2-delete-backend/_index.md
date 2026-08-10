---
title: "5.8.2 Xóa Backend | Delete Backend"
date: 2026-08-09
draft: false
weight: 582
---

# 5.8.2. Xóa Backend
## 5.8.2. Delete Backend

### Tiếng Việt

```bash
sam delete --stack-name smart-campus-backend-dev --region ap-southeast-2 --no-prompts
```

**Kết quả mong đợi:**
```
Deleted successfully
```

Hoặc nếu `sam delete` lỗi:

```bash
aws cloudformation delete-stack --stack-name smart-campus-backend-dev --region ap-southeast-2
aws cloudformation wait stack-delete-complete --stack-name smart-campus-backend-dev --region ap-southeast-2
```

> **Lưu ý:** Backend stack không cần empty S3 trước vì artifacts bucket (`sam-deploy-artifacts-xxx`) được dùng chung và không bị xóa.

### English

```bash
sam delete --stack-name smart-campus-backend-dev --region ap-southeast-2 --no-prompts
```

**Expected result:**
```
Deleted successfully
```

Or if `sam delete` fails:

```bash
aws cloudformation delete-stack --stack-name smart-campus-backend-dev --region ap-southeast-2
aws cloudformation wait stack-delete-complete --stack-name smart-campus-backend-dev --region ap-southeast-2
```

> **Note:** The backend stack does not need S3 emptying beforehand because the artifacts bucket (`sam-deploy-artifacts-xxx`) is shared and not deleted.

<!-- [SCREENSHOT: Terminal — output `sam delete` backend stack] -->
<!-- [SCREENSHOT: Terminal — `sam delete` backend stack output] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → smart-campus-backend-dev → DELETE_COMPLETE] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → smart-campus-backend-dev → DELETE_COMPLETE] -->
