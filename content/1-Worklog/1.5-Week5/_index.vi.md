---
title: "Tuần 5: Broadcasting (SNS) & Lập lịch Cronjob"
date: 2026-07-20
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

## 1. Mục tiêu công việc
Tích hợp SNS để phát tín khẩn cấp (SMS/email), tự động hóa cronjob quét công việc quá hạn và gửi nhắc nhở.

## 2. Nhật ký công việc chi tiết

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | - Tạo Topic trên Amazon SNS cho kênh broadcasting cảnh báo khẩn cấp (SMS/email). | 20/07/2026 | 20/07/2026 | Tài liệu AWS |
| 3 | - Subscribe các endpoint nhận cảnh báo hệ thống vào SNS Topic. | 21/07/2026 | 21/07/2026 | Tài liệu AWS |
| 4 | - Thiết lập Amazon EventBridge Scheduler chạy định kỳ 30 phút/lần. | 22/07/2026 | 22/07/2026 | Tài liệu AWS |
| 5 | - Viết `Cronjob Worker Lambda` quét DynamoDB tìm task sắp quá hạn. | 23/07/2026 | 23/07/2026 | AWS Blogs |
| 6 | - Tích hợp SES vào Cronjob để tự động gửi email nhắc nhở.<br>- Điều chỉnh IAM security policies cho Lambda truy cập DynamoDB, SES, SNS. | 24/07/2026 | 24/07/2026 | Báo cáo tuần |


## 3. Các kết quả đạt được
- Tạo thành công Topic trên Amazon SNS cho kênh broadcasting cảnh báo khẩn cấp (SMS/email).
- Subscribe thành công các endpoint nhận cảnh báo hệ thống vào SNS Topic.
- Thiết lập thành công Amazon EventBridge Scheduler chạy định kỳ 30 phút/lần.
- Viết thành công Cronjob Worker Lambda quét DynamoDB tìm task sắp quá hạn.
- Tích hợp thành công SES vào Cronjob để tự động gửi email nhắc nhở.
- Điều chỉnh thành công IAM security policies cho Lambda truy cập DynamoDB, SES, SNS.
- Tích hợp SNS để phát tín khẩn cấp và tự động hóa cronjob gửi nhắc nhở công việc quá hạn.

## 4. Khó khăn & Hướng giải quyết
- **Khó khăn:** Quá trình tìm hiểu và tích hợp đôi lúc gặp lỗi không mong muốn. Cần nhiều thời gian đọc log và tài liệu kỹ thuật của AWS.
- **Giải pháp:** Phối hợp cùng các thành viên khác trong nhóm để trao đổi, đọc kỹ tài liệu hướng dẫn và tham khảo thêm ý kiến của Mentor.

## 5. Kế hoạch tuần tiếp theo
- Rà soát lại công việc của tuần này (Review).
- Bắt tay vào nghiên cứu và triển khai các nhiệm vụ của Tuần 6.
