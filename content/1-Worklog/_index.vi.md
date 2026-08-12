---
title: "Nhật ký làm việc"
date: 2026-06-22
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

## Về Worklog này

Worklog này ghi lại hành trình thực tập 8 tuần của tôi tại **FCAJ**, với dự án **Smart Campus Platform** sử dụng Amazon Web Services (AWS). Chương trình thực tập diễn ra từ **ngày 22/06/2026 đến ngày 14/08/2026**.

Trong suốt quá trình này, tôi đã tiến bộ từ một người mới bắt đầu tìm hiểu hệ sinh thái AWS đến việc xây dựng một hệ thống serverless theo mô hình event-driven hoàn chỉnh, có giám sát, bảo mật và tự động hóa CI/CD. Mỗi tuần tập trung vào một nhóm nhiệm vụ cụ thể, xây dựng dựa trên nền tảng của tuần trước.

## Tổng quan theo tuần

| Tuần | Lĩnh vực trọng tâm | Hoạt động chính |
|---|---|---|
| **Tuần 1** | [Làm quen với AWS](1.1-Week1/) | Tạo tài khoản AWS Free Tier, thiết lập cảnh báo chi phí, cài đặt và cấu hình AWS CLI, triển khai EC2 instance đầu tiên với web server đơn giản. |
| **Tuần 2** | [Thiết kế kiến trúc](1.2-Week2/) | Brainstorm và chốt đề tài Smart Campus Platform; phân tích yêu cầu nghiệp vụ (Face Attendance, Task Management); chọn AWS service cho từng module; thiết kế sơ đồ kiến trúc tổng thể, data flow, database schema và wireframe. |
| **Tuần 3** | [Kiến trúc Event-Driven](1.3-Week3/) | Tìm hiểu VPC, Security Groups và bảo mật mạng; khởi tạo Amazon EventBridge Custom Event Bus; xây dựng JSON Event Schema chuẩn hóa; tích hợp boto3 để emit event bất đồng bộ; định nghĩa Event Rules và xác minh qua CloudWatch Logs. |
| **Tuần 4** | [Hàng đợi SQS & Thông báo](1.4-Week4/) | Tạo SQS Queue với Dead Letter Queue (DLQ); thiết lập EventBridge Rules để phân nhánh luồng; viết Notification Worker Lambda; tích hợp Amazon SES gửi email xác nhận điểm danh dạng HTML; cấu hình IAM policies. |
| **Tuần 5** | [Broadcasting & Lập lịch Cronjob](1.5-Week5/) | Tạo SNS Topic cho kênh phát tín khẩn cấp; thiết lập EventBridge Scheduler (30 phút/lần); viết Cronjob Worker Lambda quét DynamoDB tìm task quá hạn; tích hợp SES gửi email nhắc nhở tự động; điều chỉnh IAM security policies. |
| **Tuần 6** | [Bảo mật hệ thống với WAF](1.6-Week6/) | Khởi tạo AWS WAF WebACL gắn vào API Gateway và CloudFront; bật AWS Managed Rules (SQL Injection, XSS); tạo Rate-Based Rule (1000 req/5phút) và Geo-Match rule (chặn ngoài Việt Nam); mô phỏng tấn công và xác nhận auto-block. |
| **Tuần 7** | [Giám sát & CI/CD](1.7-Week7/) | Cấu hình CloudWatch Logs Insights và X-Ray SDK; tạo CloudWatch Alarms tích hợp SNS; thiết lập AWS CodePipeline kết nối GitHub; viết buildspec.yml cho Frontend (npm build → S3) và Backend (Unit Tests → Lambda); tìm hiểu cơ bản CloudFormation/Terraform. |
| **Tuần 8** | [Tổng kết & Báo cáo](1.8-Week8/) | Thực hiện End-to-End Testing và fix bug cuối; biên soạn tài liệu kỹ thuật (Architecture, API Docs, Database Schema); quay video demo trình diễn các luồng chính; soạn thảo và hoàn thiện báo cáo thực tập cuối kỳ. |
