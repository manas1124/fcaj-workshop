---
title: "5.4.2 Setup Cognito | Setup Cognito"
date: 2026-08-09
draft: false
weight: 542
---

# 5.4.2. Setup Cognito
## 5.4.2. Setup Cognito

### Tiếng Việt

Tạo User Pool và App Client để xác thực ngườ dùng.

**Trên AWS Console:**

1. Truy cập **Amazon Cognito → User pools → Create user pool**
2. **Provider types:** Cognito user pool
3. **Sign-in options:** Email
4. **Security requirements:** để mặc định
5. **Sign-up options:** để mặc định
6. **Message delivery:** để mặc định
7. **Integrate your app:**
   - User pool name: `smart-campus-users`
8. **Review and create → Create user pool**

Sau khi tạo xong:

9. Vào User Pool vừa tạo → tab **App integration**
10. Kéo xuống **App clients → Create app client**
    - App client name: `smart-campus-client`
    - **Bỏ chọn** "Generate a client secret"
    - **Authentication flows:** chọn **ALLOW_USER_PASSWORD_AUTH** và **ALLOW_REFRESH_TOKEN_AUTH**
11. **Create app client**

**Ghi lại 2 giá trị quan trọng:**
- **User Pool ID** (ví dụ: `ap-southeast-2_e4uVmc3uy`)
- **Client ID** (ví dụ: `19a7ai4gko0f1japfp59h5qdmc`)

### English

Create a User Pool and App Client for user authentication.

**On AWS Console:**

1. Go to **Amazon Cognito → User pools → Create user pool**
2. **Provider types:** Cognito user pool
3. **Sign-in options:** Email
4. **Security requirements:** default
5. **Sign-up options:** default
6. **Message delivery:** default
7. **Integrate your app:**
   - User pool name: `smart-campus-users`
8. **Review and create → Create user pool**

After creation:

9. Go to the new User Pool → **App integration** tab
10. Scroll to **App clients → Create app client**
    - App client name: `smart-campus-client`
    - **Uncheck** "Generate a client secret"
    - **Authentication flows:** select **ALLOW_USER_PASSWORD_AUTH** and **ALLOW_REFRESH_TOKEN_AUTH**
11. **Create app client**

**Save these 2 important values:**
- **User Pool ID** (e.g., `ap-southeast-2_e4uVmc3uy`)
- **Client ID** (e.g., `19a7ai4gko0f1japfp59h5qdmc`)

<!-- [SCREENSHOT: AWS Console → Cognito → User pools → smart-campus-users → Overview → User Pool ID] -->
<!-- [SCREENSHOT: AWS Console → Cognito → User pools → smart-campus-users → App integration → App client list → Client ID] -->
