---
title: "5.8 Dọn dẹp | Clean-up"
date: 2026-08-09
draft: false
weight: 58
---

# 5.8. Dọn dẹp
## 5.8. Clean-up

### Tiếng Việt

Thực hiện theo đúng thứ tự để tránh lỗi dependency. Nếu xóa sai thứ tự (ví dụ: xóa S3 bucket trước khi empty), CloudFormation sẽ báo lỗi.

### English

Follow this exact order to avoid dependency errors. If you delete in the wrong order (e.g., delete S3 bucket before emptying it), CloudFormation will report an error.

<!-- [SCREENSHOT: Checklist clean-up với các bước được đánh số] -->
