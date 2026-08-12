---
title: "Worklog tuần 4"
date: 2026-07-13
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

## 1. Mục tiêu công việc
Xây dựng cơ chế buffer message với SQS, xử lý bất đồng bộ và gửi email HTML qua Amazon SES.

## 2. Nhật ký công việc chi tiết

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | - Tạo Amazon SQS Queue.<br>- Cấu hình Dead Letter Queue (DLQ) cho message lỗi. | 13/07/2026 | 13/07/2026 | Tài liệu AWS |
| 3 | - Thiết lập EventBridge Rule để phân nhánh event stream (Notification & Analytics). | 14/07/2026 | 14/07/2026 | Tài liệu AWS |
| 4 | - Viết `Notification Worker Lambda`, trigger trực tiếp từ SQS qua Event Source Mapping. | 15/07/2026 | 15/07/2026 | AWS Blogs |
| 5 | - Khởi tạo và xác minh địa chỉ gửi email trên Amazon SES. | 16/07/2026 | 16/07/2026 | Tài liệu AWS |
| 6 | - Nhúng HTML template vào Python, gửi email xác nhận điểm danh qua Amazon SES.<br>- Cấu hình IAM policies cơ bản cho SQS và Lambda. | 17/07/2026 | 17/07/2026 | Báo cáo tuần |


## 3. Các kết quả đạt được
- Tạo thành công Amazon SQS Queue và cấu hình Dead Letter Queue (DLQ) cho message lỗi.
- Thiết lập thành công EventBridge Rule để phân nhánh event stream (Notification & Analytics).
- Viết thành công Notification Worker Lambda trigger trực tiếp từ SQS qua Event Source Mapping.
- Khởi tạo và xác minh thành công địa chỉ gửi email trên Amazon SES.
- Nhúng thành công HTML template vào Python và gửi email xác nhận điểm danh qua Amazon SES.
- Cấu hình thành công IAM policies cơ bản cho SQS và Lambda.
- Xây dựng cơ chế buffer message với SQS, xử lý bất đồng bộ và gửi email HTML qua Amazon SES.

## 4. Khó khăn & Hướng giải quyết
- **Khó khăn:** Quá trình tìm hiểu và tích hợp đôi lúc gặp lỗi không mong muốn. Cần nhiều thời gian đọc log và tài liệu kỹ thuật của AWS.
- **Giải pháp:** Phối hợp cùng các thành viên khác trong nhóm để trao đổi, đọc kỹ tài liệu hướng dẫn và tham khảo thêm ý kiến của Mentor.

## 5. Kế hoạch tuần tiếp theo
- Rà soát lại công việc của tuần này (Review).
- Bắt tay vào nghiên cứu và triển khai các nhiệm vụ của Tuần 5.
