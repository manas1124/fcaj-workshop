---
title: "5.6.3 Upload lên S3 | Upload to S3"
date: 2026-08-09
draft: false
weight: 563
---

# 5.6.3. Upload lên S3
## 5.6.3. Upload to S3

### Tiếng Việt

Lấy tên bucket từ stack output và sync file build lên S3.

**Bước 1 — Lấy tên bucket:**

```bash
export FRONTEND_BUCKET=$(aws cloudformation describe-stacks   --stack-name smart-campus-frontend-dev   --query 'Stacks[0].Outputs[?OutputKey==`FrontendBucketName`].OutputValue'   --output text   --region ap-southeast-2)

echo $FRONTEND_BUCKET
```

**Kết quả mong đợi:**
```
smart-campus-frontend-dev-811391287455
```

**Bước 2 — Sync lên S3:**

```bash
aws s3 sync dist/ s3://${FRONTEND_BUCKET}/ --delete --region ap-southeast-2
```

**Kết quả mong đợi:**
```
upload: dist/index.html to s3://smart-campus-frontend-dev-811391287455/index.html
upload: dist/assets/index-xxx.js to s3://smart-campus-frontend-dev-811391287455/assets/index-xxx.js
upload: dist/assets/index-xxx.css to s3://smart-campus-frontend-dev-811391287455/assets/index-xxx.css
...
```

### English

Get the bucket name from stack output and sync build files to S3.

**Step 1 — Get bucket name:**

```bash
export FRONTEND_BUCKET=$(aws cloudformation describe-stacks   --stack-name smart-campus-frontend-dev   --query 'Stacks[0].Outputs[?OutputKey==`FrontendBucketName`].OutputValue'   --output text   --region ap-southeast-2)

echo $FRONTEND_BUCKET
```

**Expected result:**
```
smart-campus-frontend-dev-811391287455
```

**Step 2 — Sync to S3:**

```bash
aws s3 sync dist/ s3://${FRONTEND_BUCKET}/ --delete --region ap-southeast-2
```

**Expected result:**
```
upload: dist/index.html to s3://smart-campus-frontend-dev-811391287455/index.html
upload: dist/assets/index-xxx.js to s3://smart-campus-frontend-dev-811391287455/assets/index-xxx.js
upload: dist/assets/index-xxx.css to s3://smart-campus-frontend-dev-811391287455/assets/index-xxx.css
...
```

<!-- [SCREENSHOT: Terminal — output `aws s3 sync` với các file uploaded] -->
<!-- [SCREENSHOT: Terminal — `aws s3 sync` output with uploaded files] -->
<!-- [SCREENSHOT: AWS Console → S3 → smart-campus-frontend-dev-xxx → Objects → hiển thị index.html và assets/] -->
<!-- [SCREENSHOT: AWS Console → S3 → smart-campus-frontend-dev-xxx → Objects → showing index.html and assets/] -->
