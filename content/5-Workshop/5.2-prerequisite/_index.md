---
title: "5.2 Điều kiện tiên quyết | Prerequisite"
date: 2026-08-09
draft: false
weight: 52
---

# 5.2. Điều kiện tiên quyết
## 5.2. Prerequisite

### Tiếng Việt

Trước khi bắt đầu, bạn cần chuẩn bị:

1. **Tài khoản AWS** đã kích hoạt và verify phương thức thanh toán.
2. **AWS CLI** đã cài đặt.
3. **AWS SAM CLI** đã cài đặt.
4. **Node.js ≥ 18** và npm để build frontend.
5. **Region:** `ap-southeast-2` (Sydney).
6. **Git** để clone repository.

### English

Before starting, prepare the following:

1. **Active AWS account** with verified payment method.
2. **AWS CLI** installed.
3. **AWS SAM CLI** installed.
4. **Node.js ≥ 18** and npm for frontend build.
5. **Region:** `ap-southeast-2` (Sydney).
6. **Git** to clone the repository.

---

### B.1. Kiểm tra công cụ | Verify Tools

Mở terminal và kiểm tra:

```bash
aws --version
```

**Kết quả mong đợi:**
```
aws-cli/2.x.x
```

```bash
sam --version
```

**Kết quả mong đợi:**
```
SAM CLI, version 1.x.x
```

```bash
node --version
```

**Kết quả mong đợi:**
```
v20.x.x
```

<!-- [SCREENSHOT: Terminal — output của 3 lệnh trên] -->

---

### B.2. Cấu hình AWS CLI | Configure AWS CLI

```bash
aws configure
```

Nhập từng dòng:

```
AWS Access Key ID: AKIAxxxxxxxxxxxxxxxx
AWS Secret Access Key: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
Default region name: ap-southeast-2
Default output format: json
```

Kiểm tra:

```bash
aws sts get-caller-identity
```

**Kết quả mong đợi:**
```json
{
    "UserId": "AIDAXXXXXXXXXXXXXXXXX",
    "Account": "811391287455",
    "Arn": "arn:aws:iam::811391287455:user/your-username"
}
```

<!-- [SCREENSHOT: Terminal — aws sts get-caller-identity output] -->

---

### B.3. Clone Repository

```bash
git clone https://github.com/manas1124/smart-campus.git
cd smart-campus
```

Kiểm tra cấu trúc:

```bash
tree -L 2
```

**Kết quả mong đợi:**
```
smart-campus/
├── backend/
│   ├── template.yaml
│   ├── samconfig.toml
│   ├── layer/
│   └── lambdas/
├── frontend/
│   ├── template-frontend.yaml
│   ├── vite.config.ts
│   ├── package.json
│   └── src/
└── .github/
    └── workflows/
```

<!-- [SCREENSHOT: VS Code Explorer hoặc terminal tree output] -->
