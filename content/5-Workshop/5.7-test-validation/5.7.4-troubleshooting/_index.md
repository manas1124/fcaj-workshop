---
title: "5.7.4 Xử lý lỗi | Troubleshooting"
date: 2026-08-09
draft: false
weight: 574
---

# 5.7.4. Xử lý lỗi
## 5.7.4. Troubleshooting

### Tiếng Việt

Dưới đây là các lỗi thường gặp trong quá trình deploy và cách khắc phục:

| Lỗi | Nguyên nhân | Cách fix |
|-----|-------------|----------|
| `The specified origin request policy does not exist` | `OriginRequestPolicyId` trong `template-frontend.yaml` không hợp lệ | Xóa dòng `OriginRequestPolicyId` trong `DefaultCacheBehavior` |
| `Stack is in ROLLBACK_COMPLETE state` | Deploy thất bại trước đó | Chạy `sam delete --stack-name <name>` rồi deploy lại |
| `frontend/build does not exist` | Vite output là `dist/`, không phải `build/` | Dùng `aws s3 sync dist/ ...` thay vì `build/` |
| `CreateOAuth2Token invalid` | Credential hết hạn (SSO) hoặc OIDC lỗi | Chạy `aws sso login` lại hoặc kiểm tra IAM Role trust policy |
| `ResourceNotFoundException` (DynamoDB) | Table chưa được tạo trước khi deploy | Quay lại Step 5.4.3 để tạo 8 bảng DynamoDB |
| `NoSuchBucket` | S3 bucket chưa tạo hoặc sai region | Tạo bucket đúng region trước khi deploy |
| `Cognito Identity Provider does not exist` | User Pool ID sai hoặc ở region khác | Kiểm tra ID và đảm bảo cùng region `ap-southeast-2` |
| `CloudFront Distribution not deployed` | Distribution đang ở trạng thái `InProgress` | Đợi 5-10 phút sau khi create invalidation |

### English

Below are common errors during deployment and how to fix them:

| Error | Cause | Fix |
|-------|-------|-----|
| `The specified origin request policy does not exist` | Invalid `OriginRequestPolicyId` in `template-frontend.yaml` | Remove the `OriginRequestPolicyId` line in `DefaultCacheBehavior` |
| `Stack is in ROLLBACK_COMPLETE state` | Previous deployment failed | Run `sam delete --stack-name <name>` then redeploy |
| `frontend/build does not exist` | Vite outputs to `dist/`, not `build/` | Use `aws s3 sync dist/ ...` instead of `build/` |
| `CreateOAuth2Token invalid` | Expired credentials (SSO) or bad OIDC | Re-run `aws sso login` or check IAM Role trust policy |
| `ResourceNotFoundException` (DynamoDB) | Tables not pre-created before deploy | Go back to Step 5.4.3 to create 8 DynamoDB tables |
| `NoSuchBucket` | S3 bucket not created or wrong region | Create bucket in correct region before deploying |
| `Cognito Identity Provider does not exist` | Wrong User Pool ID or different region | Verify ID and ensure same region `ap-southeast-2` |
| `CloudFront Distribution not deployed` | Distribution in `InProgress` state | Wait 5-10 minutes after creating invalidation |

<!-- [SCREENSHOT: AWS Console → CloudFormation → Events → hiển thị lỗi chi tiết] -->
<!-- [SCREENSHOT: AWS Console → CloudFormation → Events → showing detailed error] -->
