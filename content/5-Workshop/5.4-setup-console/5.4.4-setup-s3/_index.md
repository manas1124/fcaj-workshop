---
title: "5.4.4 Setup S3 | Setup S3"
date: 2026-08-09
draft: false
weight: 544
---

# 5.4.4. Setup S3
## 5.4.4. Setup S3

### Tiếng Việt

Tạo S3 bucket để lưu trữ ảnh khuôn mặt cho chức năng Biometric.

**Trên AWS Console:**

1. Truy cập **S3 → Create bucket**
2. **Bucket name:** `smart-campus-images`
3. **AWS Region:** Asia Pacific (Sydney) `ap-southeast-2`
4. **Object Ownership:** ACLs disabled (recommended)
5. **Block Public Access settings:**
   - Chọn **Block all public access** (mặc định)
   - Lambda sẽ truy cập qua IAM role, không cần public
6. **Bucket Versioning:** Disable
7. **Tags:** (tùy chọn)
8. **Create bucket**

### English

Create an S3 bucket for storing face images for the Biometric feature.

**On AWS Console:**

1. Go to **S3 → Create bucket**
2. **Bucket name:** `smart-campus-images`
3. **AWS Region:** Asia Pacific (Sydney) `ap-southeast-2`
4. **Object Ownership:** ACLs disabled (recommended)
5. **Block Public Access settings:**
   - Select **Block all public access** (default)
   - Lambda will access via IAM role, no public access needed
6. **Bucket Versioning:** Disable
7. **Tags:** (optional)
8. **Create bucket**

<!-- [SCREENSHOT: AWS Console → S3 → Buckets → smart-campus-images] -->
<!-- [SCREENSHOT: AWS Console → S3 → Buckets → smart-campus-images] -->
