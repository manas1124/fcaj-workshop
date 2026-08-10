---
title: "5.5.3 Lấy API URL | Get API URL"
date: 2026-08-09
draft: false
weight: 553
---

# 5.5.3. Lấy API URL
## 5.5.3. Get API URL

### Tiếng Việt

Sau khi backend deploy thành công, lấy URL của API Gateway để frontend sử dụng.

**Bước 1 — Lấy URL từ CloudFormation Output:**

```bash
aws cloudformation describe-stacks   --stack-name smart-campus-backend-dev   --query 'Stacks[0].Outputs[?OutputKey==`ApiUrl`].OutputValue'   --output text   --region ap-southeast-2
```

**Kết quả mong đợi:**
```
https://xxxxx.execute-api.ap-southeast-2.amazonaws.com/dev/
```

**Bước 2 — Lưu vào biến môi trường:**

```bash
export API_URL=https://xxxxx.execute-api.ap-southeast-2.amazonaws.com/dev/
echo $API_URL
```

**Kết quả mong đợi:**
```
https://xxxxx.execute-api.ap-southeast-2.amazonaws.com/dev/
```

> **Lưu ý:** Copy URL này để dùng ở Step 5.6.2 (Deploy Frontend).

### English

After backend deployment succeeds, get the API Gateway URL for the frontend.

**Step 1 — Get URL from CloudFormation Output:**

```bash
aws cloudformation describe-stacks   --stack-name smart-campus-backend-dev   --query 'Stacks[0].Outputs[?OutputKey==`ApiUrl`].OutputValue'   --output text   --region ap-southeast-2
```

**Expected result:**
```
https://xxxxx.execute-api.ap-southeast-2.amazonaws.com/dev/
```

**Step 2 — Save to environment variable:**

```bash
export API_URL=https://xxxxx.execute-api.ap-southeast-2.amazonaws.com/dev/
echo $API_URL
```

**Expected result:**
```
https://xxxxx.execute-api.ap-southeast-2.amazonaws.com/dev/
```

> **Note:** Copy this URL for use in Step 5.6.2 (Deploy Frontend).

<!-- [SCREENSHOT: Terminal — echo $API_URL hiển thị URL] -->
<!-- [SCREENSHOT: Terminal — echo $API_URL showing URL] -->
<!-- [SCREENSHOT: AWS Console → API Gateway → smart-campus-api → Stages → dev → Invoke URL] -->
<!-- [SCREENSHOT: AWS Console → API Gateway → smart-campus-api → Stages → dev → Invoke URL] -->
