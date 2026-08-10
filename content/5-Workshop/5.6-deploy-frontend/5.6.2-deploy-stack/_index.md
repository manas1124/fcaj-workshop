---
title: "5.6.2 Deploy Frontend Stack | Deploy Frontend Stack"
date: 2026-08-09
draft: false
weight: 562
---

# 5.6.2. Deploy Frontend Stack
## 5.6.2. Deploy Frontend Stack

### Tiếng Việt

Deploy stack frontend để tạo S3 bucket và CloudFront distribution.

**Bước 1 — Validate template:**

```bash
sam validate -t template-frontend.yaml
```

**Bước 2 — Build:**

```bash
sam build -t template-frontend.yaml
```

**Bước 3 — Deploy với guided mode:**

```bash
sam deploy -t template-frontend.yaml --guided
```

**Trả lờ từng prompt:**

```
Stack Name [sam-app]: smart-campus-frontend-dev
```

```
AWS Region [us-east-1]: ap-southeast-2
```

```
Parameter Environment [dev]: dev
```

```
Parameter ApiGatewayUrl []: <dán API_URL từ Step 5.5.3>
```
> Dán URL API Gateway đã lấy ở Step 5.5.3.

```
Confirm changes before deploy [Y/n]: Y
```

```
Allow SAM CLI IAM role creation [Y/n]: Y
```

```
Disable rollback [y/N]: N
```

```
Save arguments to configuration file [Y/n]: Y
```

```
SAM configuration file [samconfig.toml]: <nhấn Enter>
```

```
SAM configuration environment [default]: <nhấn Enter>
```

Xác nhận changeset:

```
Deploy this changeset? [y/N]: Y
```

**Kết quả mong đợi:**
```
Successfully created/updated stack - smart-campus-frontend-dev in ap-southeast-2
```

> **Lưu ý quan trọng:** Trong `template-frontend.yaml`, nếu có dòng `OriginRequestPolicyId: 88a5a4b4-2e20-42ea-a9d0-1a7d56eb62c2`, hãy **xóa dòng này** trước khi deploy. ID này không tồn tại và sẽ gây lỗi `ROLLBACK_COMPLETE`.

### English

Deploy the frontend stack to create the S3 bucket and CloudFront distribution.

**Step 1 — Validate template:**

```bash
sam validate -t template-frontend.yaml
```

**Step 2 — Build:**

```bash
sam build -t template-frontend.yaml
```

**Step 3 — Deploy with guided mode:**

```bash
sam deploy -t template-frontend.yaml --guided
```

**Answer each prompt:**

```
Stack Name [sam-app]: smart-campus-frontend-dev
```

```
AWS Region [us-east-1]: ap-southeast-2
```

```
Parameter Environment [dev]: dev
```

```
Parameter ApiGatewayUrl []: <paste API_URL from Step 5.5.3>
```
> Paste the API Gateway URL from Step 5.5.3.

```
Confirm changes before deploy [Y/n]: Y
```

```
Allow SAM CLI IAM role creation [Y/n]: Y
```

```
Disable rollback [y/N]: N
```

```
Save arguments to configuration file [Y/n]: Y
```

```
SAM configuration file [samconfig.toml]: <press Enter>
```

```
SAM configuration environment [default]: <press Enter>
```

Confirm changeset:

```
Deploy this changeset? [y/N]: Y
```

**Expected result:**
```
Successfully created/updated stack - smart-campus-frontend-dev in ap-southeast-2
```

> **Important note:** In `template-frontend.yaml`, if there is a line `OriginRequestPolicyId: 88a5a4b4-2e20-42ea-a9d0-1a7d56eb62c2`, **remove this line** before deploying. This ID does not exist and will cause a `ROLLBACK_COMPLETE` error.

<!-- [SCREENSHOT: Terminal — output `sam deploy --guided` cho frontend] -->
<!-- [SCREENSHOT: Terminal — `sam deploy --guided` output for frontend] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → smart-campus-frontend-dev → CREATE_COMPLETE] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → smart-campus-frontend-dev → CREATE_COMPLETE] -->
