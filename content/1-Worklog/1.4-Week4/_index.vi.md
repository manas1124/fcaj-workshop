---
title: "Worklog Tuần 4"
date: 2026-07-13
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4

* Tìm hiểu cơ chế quản lý danh tính và phân quyền trên AWS.
* Hiểu nguyên tắc bảo mật theo mô hình Least Privilege.
* Thực hành sử dụng IAM User, Group, Role và Policy.
* Làm quen với AWS Lambda và Amazon API Gateway để chuẩn bị cho giai đoạn phát triển dự án Serverless.

---

### Công việc thực hiện trong tuần

| Thứ   | Công việc                                                                                                 | Ngày       |
| ----- | --------------------------------------------------------------------------------------------------------- | ---------- |
| Thứ 2 | Tìm hiểu AWS Identity and Access Management (IAM), bao gồm User, Group và Role.                           | 13/07/2026 |
| Thứ 3 | Nghiên cứu IAM Policy, Permission và nguyên tắc Least Privilege.                                          | 14/07/2026 |
| Thứ 4 | Thiết lập xác thực đa yếu tố (MFA), thực hành phân quyền cho nhiều người dùng và dịch vụ AWS.             | 15/07/2026 |
| Thứ 5 | Tìm hiểu AWS Lambda, mô hình Function as a Service (FaaS) và các trường hợp sử dụng.                      | 16/07/2026 |
| Thứ 6 | Tìm hiểu Amazon API Gateway và xây dựng API Serverless đơn giản kết hợp với AWS Lambda.                   | 17/07/2026 |
| Thứ 7 | Tổng hợp kiến thức đã học, đánh giá các dịch vụ nền tảng và lập kế hoạch cho dự án Smart Campus Platform. | 18/07/2026 |

---

### Nội dung đã thực hiện

Trong tuần thứ tư, tôi tập trung nghiên cứu các dịch vụ liên quan đến quản lý danh tính, phân quyền và bảo mật trên AWS.

Đầu tiên, tôi tìm hiểu AWS Identity and Access Management (IAM), bao gồm IAM User, IAM Group, IAM Role và IAM Policy. Tôi thực hành tạo người dùng, phân quyền truy cập và áp dụng nguyên tắc Least Privilege nhằm đảm bảo mỗi tài khoản hoặc dịch vụ chỉ được cấp các quyền cần thiết.

Tiếp theo, tôi nghiên cứu cơ chế xác thực đa yếu tố (MFA) và cách sử dụng IAM Role để cấp quyền tạm thời cho các dịch vụ AWS mà không cần lưu trữ Access Key.

Ở phần thực hành Serverless, tôi làm quen với AWS Lambda và Amazon API Gateway. Tôi tìm hiểu cách xây dựng một API đơn giản sử dụng Lambda làm backend, từ đó hiểu được mô hình Function as a Service (FaaS) và quy trình xử lý yêu cầu trong kiến trúc Serverless.

Cuối tuần, tôi tổng hợp toàn bộ kiến thức đã học trong bốn tuần đầu và xây dựng kế hoạch phát triển dự án Smart Campus Platform theo kiến trúc AWS Serverless.

---

### Khó khăn gặp phải

* Ban đầu khó phân biệt vai trò của IAM User và IAM Role trong các tình huống khác nhau.
* Việc viết IAM Policy theo định dạng JSON khá phức tạp đối với người mới.
* Cần thời gian để hiểu cách API Gateway chuyển tiếp yêu cầu đến AWS Lambda.
* Chưa quen với mô hình Serverless và vòng đời thực thi của Lambda Function.

---

### Cách giải quyết

* Tham khảo AWS IAM Best Practices và các ví dụ Policy từ tài liệu chính thức.
* Thực hành tạo nhiều IAM User, Role và Policy để hiểu rõ từng trường hợp sử dụng.
* Xây dựng API Serverless đơn giản nhằm quan sát luồng xử lý giữa API Gateway và Lambda.
* Ghi chú lại các nguyên tắc bảo mật để áp dụng cho dự án ở các tuần tiếp theo.

---

### Kiến thức đạt được

Sau tuần thứ tư, tôi đã:

* Hiểu cơ chế quản lý danh tính và phân quyền trên AWS.
* Biết cách tạo và quản lý IAM User, Group, Role và Policy.
* Áp dụng nguyên tắc Least Privilege trong việc cấp quyền.
* Hiểu vai trò của MFA trong việc tăng cường bảo mật.
* Hiểu mô hình Serverless và Function as a Service.
* Biết cách tích hợp Amazon API Gateway với AWS Lambda.
* Có nền tảng để bắt đầu phát triển dự án Smart Campus Platform theo kiến trúc Serverless.

---

### Kết quả đạt được

* Cấu hình thành công IAM User, Group, Role và Policy.
* Thiết lập xác thực đa yếu tố (MFA).
* Xây dựng API Serverless đơn giản bằng Amazon API Gateway và AWS Lambda.
* Hoàn thành ghi chú về IAM Security Best Practices.
* Xây dựng kế hoạch triển khai dự án Smart Campus Platform.

---

### Tài liệu tham khảo

* AWS First Cloud Journey Learning Path.
* AWS Documentation – AWS Identity and Access Management (IAM).
* AWS Documentation – AWS Lambda.
* AWS Documentation – Amazon API Gateway.
* AWS Well-Architected Framework – Security Pillar.
