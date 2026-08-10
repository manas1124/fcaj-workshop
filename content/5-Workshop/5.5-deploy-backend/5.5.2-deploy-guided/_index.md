---
title: "5.5.2 Deploy với Guided Mode | Deploy with Guided Mode"
date: 2026-08-09
draft: false
weight: 552
---

# 5.5.2. Deploy với Guided Mode
## 5.5.2. Deploy with Guided Mode

### Tiếng Việt

Chạy deploy với `--guided` để SAM CLI hỏi từng thông số.

```bash
sam deploy --guided
```

**Trả lờ từng prompt:**

```
Stack Name [sam-app]: smart-campus-backend-dev
```
> Đặt tên stack để dễ nhận diện.

```
AWS Region [us-east-1]: ap-southeast-2
```
> Chọn Sydney region.

```
Parameter CognitoUserPoolId [ap-southeast-2_e4uVmc3uy]: <nhập User Pool ID của bạn>
```
> Dán ID từ Step 5.4.2.

```
Parameter CognitoClientId [19a7ai4gko0f1japfp59h5qdmc]: <nhập Client ID của bạn>
```
> Dán ID từ Step 5.4.2.

```
Parameter NotificationTopicArn []: <nhập SNS Topic ARN hoặc để trống>
```
> Nếu đã tạo SNS ở Step 5.4.5, dán ARN vào. Nếu chưa, nhấn Enter để để trống.

```
Parameter SecurityAlertTopicArn []: <để trống>
```
> Nhấn Enter.

```
Parameter SesSenderEmail []: <nhập email SES hoặc để trống>
```
> Nếu đã verify SES ở Step 5.4.6, nhập email. Nếu chưa, nhấn Enter.

```
Parameter AthenaOutputLocation []: <để trống>
```
> Nhấn Enter.

```
Parameter Environment [dev]: dev
```
> Giữ mặc định `dev`.

```
Confirm changes before deploy [Y/n]: Y
```
> Chọn Y để xem changeset trước khi deploy.

```
Allow SAM CLI IAM role creation [Y/n]: Y
```
> Chọn Y để SAM tạo IAM role cần thiết.

```
Disable rollback [y/N]: N
```
> Giữ N để nếu lỗi thì tự động rollback.

```
Save arguments to configuration file [Y/n]: Y
```
> Chọn Y để lưu cấu hình vào `samconfig.toml`.

```
SAM configuration file [samconfig.toml]: <nhấn Enter>
```
> Giữ mặc định.

```
SAM configuration environment [default]: <nhấn Enter>
```
> Giữ mặc định.

SAM sẽ hiển thị **Changeset** — danh sách resource sẽ được tạo. Xem xong:

```
Deploy this changeset? [y/N]: Y
```

**Kết quả mong đợi:**
```
Successfully created/updated stack - smart-campus-backend-dev in ap-southeast-2
```

### English

Run deploy with `--guided` so SAM CLI asks for each parameter.

```bash
sam deploy --guided
```

**Answer each prompt:**

```
Stack Name [sam-app]: smart-campus-backend-dev
```
> Name the stack for easy identification.

```
AWS Region [us-east-1]: ap-southeast-2
```
> Select Sydney region.

```
Parameter CognitoUserPoolId [ap-southeast-2_e4uVmc3uy]: <enter your User Pool ID>
```
> Paste ID from Step 5.4.2.

```
Parameter CognitoClientId [19a7ai4gko0f1japfp59h5qdmc]: <enter your Client ID>
```
> Paste ID from Step 5.4.2.

```
Parameter NotificationTopicArn []: <enter SNS Topic ARN or leave empty>
```
> If you created SNS in Step 5.4.5, paste the ARN. Otherwise, press Enter.

```
Parameter SecurityAlertTopicArn []: <leave empty>
```
> Press Enter.

```
Parameter SesSenderEmail []: <enter SES email or leave empty>
```
> If you verified SES in Step 5.4.6, enter the email. Otherwise, press Enter.

```
Parameter AthenaOutputLocation []: <leave empty>
```
> Press Enter.

```
Parameter Environment [dev]: dev
```
> Keep default `dev`.

```
Confirm changes before deploy [Y/n]: Y
```
> Select Y to review the changeset before deploying.

```
Allow SAM CLI IAM role creation [Y/n]: Y
```
> Select Y to let SAM create necessary IAM roles.

```
Disable rollback [y/N]: N
```
> Keep N so it auto-rolls back on failure.

```
Save arguments to configuration file [Y/n]: Y
```
> Select Y to save configuration to `samconfig.toml`.

```
SAM configuration file [samconfig.toml]: <press Enter>
```
> Keep default.

```
SAM configuration environment [default]: <press Enter>
```
> Keep default.

SAM will display the **Changeset** — list of resources to be created. After reviewing:

```
Deploy this changeset? [y/N]: Y
```

**Expected result:**
```
Successfully created/updated stack - smart-campus-backend-dev in ap-southeast-2
```

<!-- [SCREENSHOT: Terminal — toàn bộ output `sam deploy --guided` từ đầu đến CREATE_COMPLETE] -->
<!-- [SCREENSHOT: Terminal — full `sam deploy --guided` output from start to CREATE_COMPLETE] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → Stacks → smart-campus-backend-dev → Events tab → CREATE_COMPLETE] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → Stacks → smart-campus-backend-dev → Events tab → CREATE_COMPLETE] -->
