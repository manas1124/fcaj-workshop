---
title: "5.6.4 Invalidate CloudFront | Invalidate CloudFront"
date: 2026-08-09
draft: false
weight: 564
---

# 5.6.4. Invalidate CloudFront
## 5.6.4. Invalidate CloudFront

### Tiếng Việt

Lấy Distribution ID và tạo invalidation để xóa cache cũ.

**Bước 1 — Lấy Distribution ID:**

```bash
export DIST_ID=$(aws cloudformation describe-stacks   --stack-name smart-campus-frontend-dev   --query 'Stacks[0].Outputs[?OutputKey==`CloudFrontDistributionId`].OutputValue'   --output text   --region ap-southeast-2)

echo $DIST_ID
```

**Kết quả mong đợi:**
```
E3PJRUZFQHW8CE
```

**Bước 2 — Tạo invalidation:**

```bash
aws cloudfront create-invalidation   --distribution-id ${DIST_ID}   --paths "/*"   --region ap-southeast-2
```

**Kết quả mong đợi:**
```json
{
    "Location": "https://cloudfront.amazonaws.com/2020-05-31/distribution/E3PJRUZFQHW8CE/invalidation/I3Q1FQOH68FLJTD8D61NZAVZDN",
    "Invalidation": {
        "Id": "I3Q1FQOH68FLJTD8D61NZAVZDN",
        "Status": "InProgress",
        "CreateTime": "2026-08-09T12:06:45.340000+00:00",
        "InvalidationBatch": {
            "Paths": {
                "Quantity": 1,
                "Items": [
                    "/*"
                ]
            },
            "CallerReference": "cli-1786277205-437730"
        }
    }
}
```

**Bước 3 — Lấy CloudFront Domain:**

```bash
aws cloudformation describe-stacks   --stack-name smart-campus-frontend-dev   --query 'Stacks[0].Outputs[?OutputKey==`CloudFrontDomain`].OutputValue'   --output text   --region ap-southeast-2
```

**Kết quả mong đợi:**
```
d1234abcd5e6fg.cloudfront.net
```

Mở trình duyệt và truy cập:
```
https://d1234abcd5e6fg.cloudfront.net
```

### English

Get the Distribution ID and create an invalidation to clear old cache.

**Step 1 — Get Distribution ID:**

```bash
export DIST_ID=$(aws cloudformation describe-stacks   --stack-name smart-campus-frontend-dev   --query 'Stacks[0].Outputs[?OutputKey==`CloudFrontDistributionId`].OutputValue'   --output text   --region ap-southeast-2)

echo $DIST_ID
```

**Expected result:**
```
E3PJRUZFQHW8CE
```

**Step 2 — Create invalidation:**

```bash
aws cloudfront create-invalidation   --distribution-id ${DIST_ID}   --paths "/*"   --region ap-southeast-2
```

**Expected result:**
```json
{
    "Location": "https://cloudfront.amazonaws.com/2020-05-31/distribution/E3PJRUZFQHW8CE/invalidation/I3Q1FQOH68FLJTD8D61NZAVZDN",
    "Invalidation": {
        "Id": "I3Q1FQOH68FLJTD8D61NZAVZDN",
        "Status": "InProgress",
        ...
    }
}
```

**Step 3 — Get CloudFront Domain:**

```bash
aws cloudformation describe-stacks   --stack-name smart-campus-frontend-dev   --query 'Stacks[0].Outputs[?OutputKey==`CloudFrontDomain`].OutputValue'   --output text   --region ap-southeast-2
```

**Expected result:**
```
d1234abcd5e6fg.cloudfront.net
```

Open browser and navigate to:
```
https://d1234abcd5e6fg.cloudfront.net
```

<!-- [SCREENSHOT: Terminal — output `aws cloudfront create-invalidation` với Status: InProgress] -->
<!-- [SCREENSHOT: Terminal — `aws cloudfront create-invalidation` output with Status: InProgress] -->
<!-- [SCREENSHOT: AWS Console → CloudFront → Distributions → Invalidations → Status: Completed] -->
<!-- [SCREENSHOT: AWS Console → CloudFront → Distributions → Invalidations → Status: Completed] -->
<!-- [SCREENSHOT: Trình duyệt mở CloudFront URL hiển thị giao diện Smart Campus] -->
<!-- [SCREENSHOT: Browser showing Smart Campus UI loaded from CloudFront URL] -->
