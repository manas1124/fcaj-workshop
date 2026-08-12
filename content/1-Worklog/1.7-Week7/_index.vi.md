---
title: "Worklog tuần 7"
date: 2026-08-03
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

## 1. Mục tiêu công việc
Triển khai pipeline tự động hóa build/deploy, tích hợp giám sát toàn diện với CloudWatch và X-Ray.

## 2. Nhật ký công việc chi tiết

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | - Cấu hình CloudWatch Logs Insights.<br>- Cài đặt AWS X-Ray SDK trong Python đo thời gian thực thi. | 03/08/2026 | 03/08/2026 | Tài liệu AWS |
| 3 | - Tạo CloudWatch Alarm kích hoạt khi Lambda error vượt 5%, tích hợp Alarm với SNS Topic. | 04/08/2026 | 04/08/2026 | Tài liệu AWS |
| 4 | - Khởi tạo AWS CodePipeline kết nối GitHub.<br>- Viết `buildspec.yml` cho Frontend: chạy `npm build` và deploy lên S3. | 05/08/2026 | 05/08/2026 | Tài liệu AWS |
| 5 | - Viết `buildspec.yml` cho Backend: chạy Unit Tests, zip thư viện và mã nguồn. | 06/08/2026 | 06/08/2026 | AWS Blogs |
| 6 | - Cấu hình `update-function-code` trong CodeBuild để deploy Lambda zero-downtime.<br>- Tìm hiểu cơ bản CloudFormation/Terraform (IaC) nếu có thời gian. | 07/08/2026 | 07/08/2026 | Báo cáo tuần |


## 3. Các kết quả đạt được
- Cấu hình thành công CloudWatch Logs Insights.
- Cài đặt thành công AWS X-Ray SDK trong Python đo thời gian thực thi.
- Tạo thành công CloudWatch Alarm kích hoạt khi Lambda error vượt 5%, tích hợp với SNS Topic.
- Khởi tạo thành công AWS CodePipeline kết nối GitHub.
- Viết thành công `buildspec.yml` cho Frontend: chạy `npm build` và deploy lên S3.
- Viết thành công `buildspec.yml` cho Backend: chạy Unit Tests, zip thư viện và mã nguồn.
- Cấu hình thành công `update-function-code` trong CodeBuild để deploy Lambda zero-downtime.
- Đã tìm hiểu cơ bản CloudFormation/Terraform (IaC).
- Triển khai thành công pipeline tự động hóa build/deploy với giám sát toàn diện qua CloudWatch và X-Ray.

## 4. Khó khăn & Hướng giải quyết
- **Khó khăn:** Quá trình tìm hiểu và tích hợp đôi lúc gặp lỗi không mong muốn. Cần nhiều thời gian đọc log và tài liệu kỹ thuật của AWS.
- **Giải pháp:** Phối hợp cùng các thành viên khác trong nhóm để trao đổi, đọc kỹ tài liệu hướng dẫn và tham khảo thêm ý kiến của Mentor.

## 5. Kế hoạch tuần tiếp theo
- Rà soát lại công việc của tuần này (Review).
- Bắt tay vào nghiên cứu và triển khai các nhiệm vụ của Tuần 8.
