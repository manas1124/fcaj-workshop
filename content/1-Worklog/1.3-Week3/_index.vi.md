---
title: "Tuần 3: Kiến trúc Event-Driven (EventBridge)"
date: 2026-07-06
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

## 1. Mục tiêu công việc
Triển khai mô hình Event-Driven, giảm tải xử lý đồng bộ; đồng thời củng cố kiến thức VPC và bảo mật mạng (Security Groups, NACLs, Internet Gateway, NAT Gateway).

## 2. Nhật ký công việc chi tiết

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|---|---|---|---|---|
| 2 | - Tìm hiểu VPC, Security Groups, NACLs, Internet Gateway, NAT Gateway. | 06/07/2026 | 06/07/2026 | Tài liệu AWS |
| 3 | - Khởi tạo Custom Event Bus (`smart-campus-bus`) trên Amazon EventBridge. | 07/07/2026 | 07/07/2026 | Tài liệu AWS |
| 4 | - Xây dựng JSON Event Schema chuẩn hóa (ví dụ: `AttendanceRecorded`) phối hợp với Backend. | 08/07/2026 | 08/07/2026 | API Docs |
| 5 | - Tích hợp boto3 vào Backend để emit event lên EventBridge ngay sau khi ghi nhận điểm danh. | 09/07/2026 | 09/07/2026 | AWS Blogs |
| 6 | - Định nghĩa Event Rules để lọc và định tuyến event.<br>- Kiểm tra log trên CloudWatch để xác nhận event nhận thành công. | 10/07/2026 | 10/07/2026 | Báo cáo tuần |


## 3. Các kết quả đạt được
- Đã nắm kiến thức về VPC, Security Groups, NACLs, Internet Gateway, NAT Gateway.
- Khởi tạo thành công Custom Event Bus (`smart-campus-bus`) trên Amazon EventBridge.
- Xây dựng thành công JSON Event Schema chuẩn hóa (ví dụ: `AttendanceRecorded`) phối hợp với Backend.
- Tích hợp thành công boto3 vào Backend để emit event lên EventBridge ngay sau khi ghi nhận điểm danh.
- Định nghĩa thành công Event Rules để lọc và định tuyến event.
- Xác nhận event nhận thành công qua CloudWatch Logs.
- Triển khai mô hình Event-Driven, giảm tải xử lý đồng bộ.

## 4. Khó khăn & Hướng giải quyết
- **Khó khăn:** Quá trình tìm hiểu và tích hợp đôi lúc gặp lỗi không mong muốn. Cần nhiều thời gian đọc log và tài liệu kỹ thuật của AWS.
- **Giải pháp:** Phối hợp cùng các thành viên khác trong nhóm để trao đổi, đọc kỹ tài liệu hướng dẫn và tham khảo thêm ý kiến của Mentor.

## 5. Kế hoạch tuần tiếp theo
- Rà soát lại công việc của tuần này.
- Bắt tay vào nghiên cứu và triển khai các nhiệm vụ của Tuần 4.
