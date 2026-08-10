---
title: "5.7.1 API Health Check | API Health Check"
date: 2026-08-09
draft: false
weight: 571
---

# 5.7.1. API Health Check
## 5.7.1. API Health Check

### Tiếng Việt

Kiểm tra API Gateway và Lambda Identity có hoạt động không.

```bash
curl -sSL ${API_URL}api/health
```

**Kết quả mong đợi:**
```json
{"status": "ok"}
```

Nếu trả về `{"status": "ok"}`, tức là:
- API Gateway đang chạy
- Lambda Identity đang chạy
- Route `/api/health` hoạt động

### English

Check if API Gateway and Lambda Identity are working.

```bash
curl -sSL ${API_URL}api/health
```

**Expected result:**
```json
{"status": "ok"}
```

If it returns `{"status": "ok"}`, it means:
- API Gateway is running
- Lambda Identity is running
- Route `/api/health` is working

<!-- [SCREENSHOT: Terminal — curl response với {"status": "ok"}] -->
<!-- [SCREENSHOT: Terminal — curl response with {"status": "ok"}] -->
