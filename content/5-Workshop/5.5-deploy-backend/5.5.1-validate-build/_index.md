---
title: "5.5.1 Validate & Build | Validate & Build"
date: 2026-08-09
draft: false
weight: 551
---

# 5.5.1. Validate & Build
## 5.5.1. Validate & Build

### Tiếng Việt

Di chuyển vào thư mục backend và kiểm tra template.

```bash
cd backend
```

**Bước 1 — Validate template:**

```bash
sam validate
```

**Kết quả mong đợi:**
```
/Users/.../backend/template.yaml is a valid SAM Template
```

Nếu có lỗi, SAM sẽ hiển thị dòng lỗi cụ thể để bạn sửa.

**Bước 2 — Build:**

```bash
sam build
```

**Kết quả mong đợi:**
```
Building codeuri: ... runtime: python3.13 metadata: ... architecture: x86_64
Build Succeeded

Built Artifacts  : .aws-sam/build
Built Template   : .aws-sam/build/template.yaml
```

SAM sẽ tạo thư mục `.aws-sam/build/` chứa toàn bộ artifacts đã build.

### English

Navigate to the backend directory and verify the template.

```bash
cd backend
```

**Step 1 — Validate template:**

```bash
sam validate
```

**Expected result:**
```
/Users/.../backend/template.yaml is a valid SAM Template
```

If there are errors, SAM will show the specific line to fix.

**Step 2 — Build:**

```bash
sam build
```

**Expected result:**
```
Building codeuri: ... runtime: python3.13 metadata: ... architecture: x86_64
Build Succeeded

Built Artifacts  : .aws-sam/build
Built Template   : .aws-sam/build/template.yaml
```

SAM will create the `.aws-sam/build/` directory containing all built artifacts.

<!-- [SCREENSHOT: Terminal — output `sam validate` và `sam build`] -->
<!-- [SCREENSHOT: Terminal — `sam validate` and `sam build` output] -->
