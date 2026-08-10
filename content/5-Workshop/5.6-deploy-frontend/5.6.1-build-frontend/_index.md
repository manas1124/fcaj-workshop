---
title: "5.6.1 Build Frontend | Build Frontend"
date: 2026-08-09
draft: false
weight: 561
---

# 5.6.1. Build Frontend
## 5.6.1. Build Frontend

### Tiếng Việt

Di chuyển vào thư mục frontend, cài dependencies và build.

```bash
cd ../frontend
```

**Bước 1 — Cài dependencies:**

```bash
npm ci
```

**Kết quả mong đợi:**
```
added xxx packages in xxs
```

**Bước 2 — Build với API URL:**

```bash
VITE_API_URL=${API_URL} npm run build
```

**Kết quả mong đợi:**
```
dist/                     0.05 kB │ gzip: 0.07 kB
✓ built in x.xxs
```

**Bước 3 — Kiểm tra output:**

```bash
ls dist/
```

**Kết quả mong đợi:**
```
index.html  assets/
```

> **Lưu ý quan trọng:** Vite output vào thư mục `dist/`, không phải `build/` như Create React App.

### English

Navigate to the frontend directory, install dependencies, and build.

```bash
cd ../frontend
```

**Step 1 — Install dependencies:**

```bash
npm ci
```

**Expected result:**
```
added xxx packages in xxs
```

**Step 2 — Build with API URL:**

```bash
VITE_API_URL=${API_URL} npm run build
```

**Expected result:**
```
dist/                     0.05 kB │ gzip: 0.07 kB
✓ built in x.xxs
```

**Step 3 — Verify output:**

```bash
ls dist/
```

**Expected result:**
```
index.html  assets/
```

> **Important note:** Vite outputs to `dist/`, not `build/` like Create React App.

<!-- [SCREENSHOT: Terminal — output `npm ci` và `npm run build`] -->
<!-- [SCREENSHOT: Terminal — `npm ci` and `npm run build` output] -->
<!-- [SCREENSHOT: VS Code Explorer → thư mục dist/ với index.html và assets/] -->
<!-- [SCREENSHOT: VS Code Explorer → dist/ folder with index.html and assets/] -->
