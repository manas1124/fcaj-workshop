---
title: "5.7.3 CloudWatch Logs & Metrics | CloudWatch Logs & Metrics"
date: 2026-08-09
draft: false
weight: 573
---

# 5.7.3. CloudWatch Logs & Metrics
## 5.7.3. CloudWatch Logs & Metrics

### Tiếng Việt

#### Xem Logs

```bash
aws logs tail /aws/lambda/smart-campus-identity-dev --follow --region ap-southeast-2
```

**Kết quả mong đợi:**
```
2026-08-09T12:00:00.000000+00:00 START RequestId: xxx-xxx-xxx-xxx Version: $LATEST
2026-08-09T12:00:00.100000+00:00 END RequestId: xxx-xxx-xxx-xxx
2026-08-09T12:00:00.100000+00:00 REPORT RequestId: xxx-xxx-xxx-xxx Duration: 100.00 ms Billed Duration: 101 ms Memory Size: 512 MB Max Memory Used: 85 MB
```

Xem log các Lambda khác:

```bash
aws logs tail /aws/lambda/smart-campus-biometric-dev --follow --region ap-southeast-2
aws logs tail /aws/lambda/smart-campus-workforce-dev --follow --region ap-southeast-2
```

#### Check Metrics

Trên AWS Console:

1. Truy cập **CloudWatch → Metrics → Lambda**
2. Chọn function `smart-campus-identity-dev`
3. Xem các metric:
   - `Invocations` — số lần gọi
   - `Duration` — thờ gian xử lý
   - `Errors` — số lỗi
   - `Throttles` — số lần bị throttle

### English

#### View Logs

```bash
aws logs tail /aws/lambda/smart-campus-identity-dev --follow --region ap-southeast-2
```

**Expected result:**
```
2026-08-09T12:00:00.000000+00:00 START RequestId: xxx-xxx-xxx-xxx Version: $LATEST
2026-08-09T12:00:00.100000+00:00 END RequestId: xxx-xxx-xxx-xxx
2026-08-09T12:00:00.100000+00:00 REPORT RequestId: xxx-xxx-xxx-xxx Duration: 100.00 ms Billed Duration: 101 ms Memory Size: 512 MB Max Memory Used: 85 MB
```

View logs for other Lambdas:

```bash
aws logs tail /aws/lambda/smart-campus-biometric-dev --follow --region ap-southeast-2
aws logs tail /aws/lambda/smart-campus-workforce-dev --follow --region ap-southeast-2
```

#### Check Metrics

On AWS Console:

1. Go to **CloudWatch → Metrics → Lambda**
2. Select function `smart-campus-identity-dev`
3. View metrics:
   - `Invocations` — number of invocations
   - `Duration` — processing time
   - `Errors` — error count
   - `Throttles` — throttle count

<!-- [SCREENSHOT: Terminal — `aws logs tail` hiển thị START, END, REPORT] -->
<!-- [SCREENSHOT: Terminal — `aws logs tail` showing START, END, REPORT] -->
<!-- [SCREENSHOT: AWS Console → CloudWatch → Metrics → Lambda → Invocations & Duration graphs] -->
<!-- [SCREENSHOT: AWS Console → CloudWatch → Metrics → Lambda → Invocations & Duration graphs] -->
