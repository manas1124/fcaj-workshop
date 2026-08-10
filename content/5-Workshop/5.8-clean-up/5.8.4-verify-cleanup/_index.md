---
title: "5.8.4 Xác nhận dọn dẹp | Verify Clean-up"
date: 2026-08-09
draft: false
weight: 584
---

# 5.8.4. Xác nhận dọn dẹp
## 5.8.4. Verify Clean-up

### Tiếng Việt

Kiểm tra lại để đảm bảo không còn resource nào sót lại phát sinh chi phí.

**Kiểm tra CloudFormation Stacks:**

```bash
aws cloudformation list-stacks   --query 'StackSummaries[?contains(StackName, `smart-campus`)]'   --output table   --region ap-southeast-2
```

**Kết quả mong đợi:**
```
Empty list — không còn stack nào có tên smart-campus
```

Hoặc trạng thái `DELETE_COMPLETE`.

**Kiểm tra S3 Buckets:**

```bash
aws s3api list-buckets --query 'Buckets[].Name' --output table
```

**Kết quả mong đợi:** Không còn bucket `smart-campus-frontend-dev-xxx` và `smart-campus-images`.

**Kiểm tra DynamoDB:**

```bash
aws dynamodb list-tables --region ap-southeast-2
```

**Kết quả mong đợi:**
```
{
    "TableNames": []
}
```

**Kiểm tra Lambda Functions:**

```bash
aws lambda list-functions   --query 'Functions[?contains(FunctionName, `smart-campus`)].FunctionName'   --output table   --region ap-southeast-2
```

**Kết quả mong đợi:** Empty list.

### English

Verify that no resources remain to avoid incurring charges.

**Check CloudFormation Stacks:**

```bash
aws cloudformation list-stacks   --query 'StackSummaries[?contains(StackName, `smart-campus`)]'   --output table   --region ap-southeast-2
```

**Expected result:**
```
Empty list — no smart-campus stacks remaining
```

Or status `DELETE_COMPLETE`.

**Check S3 Buckets:**

```bash
aws s3api list-buckets --query 'Buckets[].Name' --output table
```

**Expected result:** No `smart-campus-frontend-dev-xxx` and `smart-campus-images` buckets.

**Check DynamoDB:**

```bash
aws dynamodb list-tables --region ap-southeast-2
```

**Expected result:**
```
{
    "TableNames": []
}
```

**Check Lambda Functions:**

```bash
aws lambda list-functions   --query 'Functions[?contains(FunctionName, `smart-campus`)].FunctionName'   --output table   --region ap-southeast-2
```

**Expected result:** Empty list.

<!-- [SCREENSHOT: Terminal — `aws cloudformation list-stacks` không còn stack nào] -->
<!-- [SCREENSHOT: Terminal — `aws cloudformation list-stacks` showing no stacks] -->
<!-- [SCREENSHOT: AWS Console → Billing → Cost Explorer → chi phí về 0 sau clean-up] -->
<!-- [SCREENSHOT: AWS Console → Billing → Cost Explorer → cost drops to 0 after clean-up] -->
