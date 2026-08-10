---
title: "5.4.5 Setup SNS | Setup SNS"
date: 2026-08-09
draft: false
weight: 545
---

# 5.4.5. Setup SNS
## 5.4.5. Setup SNS

### Tiếng Việt

Tạo SNS Topic để gửi thông báo từ Notification Worker.

**Trên AWS Console:**

1. Truy cập **Amazon SNS → Topics → Create topic**
2. **Type:** Standard
3. **Name:** `smart-campus-notifications-dev`
4. **Display name:** (tùy chọn)
5. **Create topic**

Sau khi tạo xong, ghi lại **Topic ARN** (ví dụ: `arn:aws:sns:ap-southeast-2:811391287455:smart-campus-notifications-dev`).

**Tùy chọn — Subscribe email:**

6. Trong topic vừa tạo → **Create subscription**
7. **Protocol:** Email
8. **Endpoint:** `your-email@example.com`
9. **Create subscription**
10. Kiểm tra email và xác nhận

### English

Create an SNS Topic for sending notifications from the Notification Worker.

**On AWS Console:**

1. Go to **Amazon SNS → Topics → Create topic**
2. **Type:** Standard
3. **Name:** `smart-campus-notifications-dev`
4. **Display name:** (optional)
5. **Create topic**

After creation, save the **Topic ARN** (e.g., `arn:aws:sns:ap-southeast-2:811391287455:smart-campus-notifications-dev`).

**Optional — Subscribe email:**

6. In the new topic → **Create subscription**
7. **Protocol:** Email
8. **Endpoint:** `your-email@example.com`
9. **Create subscription**
10. Check email and confirm

<!-- [SCREENSHOT: AWS Console → SNS → Topics → smart-campus-notifications-dev → Details → ARN] -->
<!-- [SCREENSHOT: AWS Console → SNS → Topics → smart-campus-notifications-dev → Subscriptions] -->
