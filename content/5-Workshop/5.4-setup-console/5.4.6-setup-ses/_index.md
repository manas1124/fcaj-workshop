---
title: "5.4.6 Setup SES | Setup SES"
date: 2026-08-09
draft: false
weight: 546
---

# 5.4.6. Setup SES
## 5.4.6. Setup SES

### Tiếng Việt

Verify địa chỉ email để Lambda Biometric có thể gửi mail (tùy chọn).

**Trên AWS Console:**

1. Truy cập **Amazon SES → Verified identities → Create identity**
2. **Identity type:** Email address
3. **Email address:** `noreply@example.com` (hoặc email của bạn)
4. **Create identity**
5. Kiểm tra hộp thư đến và click link xác nhận
6. Quay lại SES console → trạng thái chuyển thành **Verified**

### English

Verify an email address so the Biometric Lambda can send emails (optional).

**On AWS Console:**

1. Go to **Amazon SES → Verified identities → Create identity**
2. **Identity type:** Email address
3. **Email address:** `noreply@example.com` (or your email)
4. **Create identity**
5. Check inbox and click the verification link
6. Return to SES console → status changes to **Verified**

<!-- [SCREENSHOT: AWS Console → SES → Verified identities → email đã verified] -->
<!-- [SCREENSHOT: AWS Console → SES → Verified identities → verified email] -->
