---
title: "Tuần 6: Bảo mật Hệ thống với AWS WAF"
date: 2026-07-27
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

## 1. Mục tiêu công việc
Bảo vệ API Gateway và CloudFront trước các tấn công phổ biến, giới hạn request và chặn truy cập ngoài phạm vi.

## 2. Nhật ký công việc chi tiết

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | - Khởi tạo AWS WAF WebACL.<br>- Attach WAF vào API Gateway (Backend) và CloudFront (Frontend). | 27/07/2026 | 27/07/2026 | Tài liệu AWS |
| 3 | - Bật AWS Managed Rules chặn SQL Injection và XSS. | 28/07/2026 | 28/07/2026 | Tài liệu AWS |
| 4 | - Tạo Rate-Based Rule chặn IP vượt quá 1000 requests / 5 phút. | 29/07/2026 | 29/07/2026 | Tài liệu AWS |
| 5 | - Tạo Geo-Match rule chặn kết nối từ ngoài lãnh thổ Việt Nam. | 30/07/2026 | 30/07/2026 | AWS Blogs |
| 6 | - Mô phỏng tấn công và kiểm tra WAF logs để xác nhận auto-block hoạt động.<br>- Tìm hiểu thêm AWS Shield và Certificate Manager (bổ sung trên roadmap). | 31/07/2026 | 31/07/2026 | Báo cáo tuần |


## 3. Các kết quả đạt được
- Khởi tạo thành công AWS WAF WebACL và attach vào API Gateway (Backend) và CloudFront (Frontend).
- Bật thành công AWS Managed Rules chặn SQL Injection và XSS.
- Tạo thành công Rate-Based Rule chặn IP vượt quá 1000 requests / 5 phút.
- Tạo thành công Geo-Match rule chặn kết nối từ ngoài lãnh thổ Việt Nam.
- Mô phỏng tấn công thành công và xác nhận auto-block hoạt động qua WAF logs.
- Đã tìm hiểu thêm AWS Shield và Certificate Manager.
- Bảo vệ thành công API Gateway và CloudFront trước các tấn công phổ biến, giới hạn request và chặn truy cập ngoài phạm vi.

## 4. Khó khăn & Hướng giải quyết
- **Khó khăn:** Quá trình tìm hiểu và tích hợp đôi lúc gặp lỗi không mong muốn. Cần nhiều thời gian đọc log và tài liệu kỹ thuật của AWS.
- **Giải pháp:** Phối hợp cùng các thành viên khác trong nhóm để trao đổi, đọc kỹ tài liệu hướng dẫn và tham khảo thêm ý kiến của Mentor.

## 5. Kế hoạch tuần tiếp theo
- Rà soát lại công việc của tuần này (Review).
- Bắt tay vào nghiên cứu và triển khai các nhiệm vụ của Tuần 7.
