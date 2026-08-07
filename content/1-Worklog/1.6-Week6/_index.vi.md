---
title: "Worklog Tuần 6"
date: 2026-07-27
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6

* Khởi tạo dự án Smart Campus Platform theo kiến trúc Serverless.
* Xây dựng cấu trúc repository theo hướng Production.
* Thiết lập Infrastructure as Code bằng AWS SAM và AWS CloudFormation.
* Chuẩn bị quy trình CI/CD sử dụng GitHub Actions.

---

### Công việc thực hiện trong tuần

| Thứ   | Công việc                                                                                                | Ngày       |
| ----- | -------------------------------------------------------------------------------------------------------- | ---------- |
| Thứ 2 | Khởi tạo GitHub Repository và xây dựng cấu trúc thư mục cho dự án theo hướng Production.                 | 27/07/2026 |
| Thứ 3 | Khởi tạo dự án bằng AWS SAM, cấu hình `template.yaml` và tổ chức hạ tầng theo CloudFormation.            | 28/07/2026 |
| Thứ 4 | Thiết kế các template hạ tầng cho API Gateway, Amazon Cognito, Amazon S3, DynamoDB và EventBridge.       | 29/07/2026 |
| Thứ 5 | Thiết lập môi trường phát triển, cấu hình AWS CLI, AWS SAM CLI và thực hiện validate, build dự án.       | 30/07/2026 |
| Thứ 6 | Xây dựng quy trình CI/CD với GitHub Actions, bao gồm Unit Test, SAM Validate, SAM Build và SAM Deploy.   | 31/07/2026 |
| Thứ 7 | Kiểm tra quy trình build, deploy, rà soát cấu trúc dự án và chuẩn bị cho giai đoạn phát triển chức năng. | 01/08/2026 |

---

### Nội dung đã thực hiện

Trong tuần thứ sáu, tôi bắt đầu triển khai dự án Smart Campus Platform theo kiến trúc Serverless đã thiết kế ở tuần trước.

Đầu tiên, tôi khởi tạo GitHub Repository và xây dựng cấu trúc thư mục của dự án theo hướng Production, bao gồm các thư mục dành cho backend, infrastructure, frontend, tài liệu kỹ thuật và workflow của GitHub Actions.

Tiếp theo, tôi sử dụng AWS Serverless Application Model (AWS SAM) để khởi tạo dự án và quản lý hạ tầng bằng AWS CloudFormation. Tôi thiết kế các template hạ tầng cho API Gateway, Amazon Cognito, Amazon S3, Amazon DynamoDB, Amazon EventBridge và các thành phần hỗ trợ khác nhằm đảm bảo khả năng mở rộng và dễ dàng bảo trì.

Sau đó, tôi thiết lập môi trường phát triển, cấu hình AWS CLI và AWS SAM CLI, đồng thời thực hiện kiểm tra cấu hình bằng các lệnh `sam validate` và `sam build`.

Cuối tuần, tôi xây dựng quy trình CI/CD với GitHub Actions để tự động hóa quá trình kiểm tra mã nguồn, build ứng dụng và triển khai hạ tầng lên AWS. Đây là nền tảng để các milestone tiếp theo có thể được triển khai một cách nhất quán và hạn chế thao tác thủ công.

---

### Khó khăn gặp phải

* Chưa quen với cấu trúc dự án của AWS SAM và cách tổ chức nhiều template CloudFormation.
* Gặp lỗi khi validate template do khai báo tài nguyên chưa chính xác.
* Phát sinh lỗi cấu hình AWS Credentials trong quá trình build và deploy.
* Cần nhiều thời gian để thiết kế cấu trúc repository phù hợp với kiến trúc Production.

---

### Cách giải quyết

* Nghiên cứu tài liệu chính thức của AWS SAM và CloudFormation.
* Chia hạ tầng thành nhiều template nhỏ để dễ quản lý và mở rộng.
* Kiểm tra lại cấu hình AWS CLI và IAM Credentials trước khi thực hiện deploy.
* Áp dụng cấu trúc repository theo hướng Domain-oriented và Infrastructure as Code để tăng khả năng bảo trì.

---

### Kiến thức đạt được

Sau tuần thứ sáu, tôi đã:

* Hiểu quy trình xây dựng hạ tầng bằng AWS SAM và CloudFormation.
* Biết cách tổ chức repository cho một dự án Serverless theo hướng Production.
* Hiểu cách quản lý hạ tầng bằng Infrastructure as Code.
* Biết cách sử dụng `sam validate`, `sam build` và `sam deploy`.
* Hiểu quy trình CI/CD sử dụng GitHub Actions cho dự án AWS Serverless.

---

### Kết quả đạt được (Deliverables)

* Repository của Smart Campus Platform được khởi tạo.
* Cấu trúc thư mục dự án hoàn chỉnh.
* AWS SAM Project được thiết lập.
* Các template CloudFormation cho hạ tầng được xây dựng.
* GitHub Actions Workflow cho CI/CD được cấu hình.
* Quy trình validate, build và deploy ban đầu hoạt động thành công.

---

### Tài liệu tham khảo

* AWS Serverless Application Model (AWS SAM) Documentation.
* AWS CloudFormation Documentation.
* GitHub Actions Documentation.
* AWS Documentation – Amazon API Gateway.
* AWS Documentation – Amazon Cognito.
* AWS Well-Architected Framework.
