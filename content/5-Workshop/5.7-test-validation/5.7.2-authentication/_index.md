---
title: "5.7.2 Test Authentication | Test Authentication"
date: 2026-08-09
draft: false
weight: 572
---

# 5.7.2. Test Authentication
## 5.7.2. Test Authentication

### Tiếng Việt

Test đăng ký ngườ dùng qua API.

```bash
curl -X POST ${API_URL}api/auth/register   -H "Content-Type: application/json"   -d '{"email":"test@example.com","password":"Test123!","name":"Test User"}'
```

**Kết quả mong đợi:**
```json
{
  "user_id": "usr_xxx",
  "email": "test@example.com",
  "name": "Test User"
}
```

Hoặc HTTP 201 Created.

**Test đăng nhập:**

```bash
curl -X POST ${API_URL}api/auth/login   -H "Content-Type: application/json"   -d '{"email":"test@example.com","password":"Test123!"}'
```

**Kết quả mong đợi:**
```json
{
  "access_token": "eyJraWQiOi...",
  "id_token": "eyJraWQiOi...",
  "refresh_token": "eyJjdHkiOi..."
}
```

**Test API có Auth (JWT):**

```bash
curl -sSL ${API_URL}api/users/me   -H "Authorization: Bearer <ID_TOKEN>"
```

**Kết quả mong đợi:**
```json
{
  "user_id": "usr_xxx",
  "email": "test@example.com",
  "name": "Test User"
}
```

### English

Test user registration via API.

```bash
curl -X POST ${API_URL}api/auth/register   -H "Content-Type: application/json"   -d '{"email":"test@example.com","password":"Test123!","name":"Test User"}'
```

**Expected result:**
```json
{
  "user_id": "usr_xxx",
  "email": "test@example.com",
  "name": "Test User"
}
```

Or HTTP 201 Created.

**Test login:**

```bash
curl -X POST ${API_URL}api/auth/login   -H "Content-Type: application/json"   -d '{"email":"test@example.com","password":"Test123!"}'
```

**Expected result:**
```json
{
  "access_token": "eyJraWQiOi...",
  "id_token": "eyJraWQiOi...",
  "refresh_token": "eyJjdHkiOi..."
}
```

**Test protected API with JWT:**

```bash
curl -sSL ${API_URL}api/users/me   -H "Authorization: Bearer <ID_TOKEN>"
```

**Expected result:**
```json
{
  "user_id": "usr_xxx",
  "email": "test@example.com",
  "name": "Test User"
}
```

<!-- [SCREENSHOT: Terminal — curl response đăng ký với HTTP 201] -->
<!-- [SCREENSHOT: Terminal — curl registration response with HTTP 201] -->
<!-- [SCREENSHOT: Terminal — curl /api/users/me với Authorization header và user profile] -->
<!-- [SCREENSHOT: Terminal — curl /api/users/me with Authorization header and user profile] -->
