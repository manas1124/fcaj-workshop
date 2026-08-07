---
title: "Worklog Tuần 5"
date: 2026-07-20
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5

* Lựa chọn đề tài phù hợp cho dự án cuối chương trình.
* Phân tích yêu cầu và xác định phạm vi của hệ thống.
* Thiết kế kiến trúc tổng thể theo mô hình AWS Serverless.
* Xây dựng kế hoạch triển khai dự án theo từng milestone.

---

### Công việc thực hiện trong tuần

| Thứ   | Công việc                                                                                                    | Ngày       |
| ----- | ------------------------------------------------------------------------------------------------------------ | ---------- |
| Thứ 2 | Nghiên cứu yêu cầu dự án và lựa chọn đề tài **Smart Campus Platform**.                                       | 20/07/2026 |
| Thứ 3 | Phân tích yêu cầu nghiệp vụ, xác định phạm vi MVP và các chức năng chính của hệ thống.                       | 21/07/2026 |
| Thứ 4 | Thiết kế kiến trúc tổng thể theo AWS Well-Architected Framework và mô hình Serverless.                       | 22/07/2026 |
| Thứ 5 | Thiết kế các workflow nghiệp vụ, xác định các dịch vụ AWS sẽ sử dụng và mối quan hệ giữa các thành phần.     | 23/07/2026 |
| Thứ 6 | Thiết kế cấu trúc repository, lựa chọn công nghệ và lập kế hoạch triển khai theo từng milestone.             | 24/07/2026 |
| Thứ 7 | Rà soát tài liệu thiết kế, đánh giá tính khả thi và chuẩn bị môi trường phát triển cho giai đoạn triển khai. | 25/07/2026 |

---

### Nội dung đã thực hiện

Sau khi hoàn thành các nội dung nền tảng về AWS, tôi bắt đầu chuyển sang giai đoạn xây dựng dự án thực tế.

Trong tuần này, tôi lựa chọn đề tài **Smart Campus Platform**, một hệ thống quản lý điểm danh thông minh được xây dựng theo kiến trúc Serverless trên AWS. Trước khi triển khai, tôi tiến hành phân tích yêu cầu nghiệp vụ, xác định các nhóm chức năng chính và giới hạn phạm vi MVP nhằm đảm bảo phù hợp với thời gian thực hiện.

Tiếp theo, tôi thiết kế kiến trúc tổng thể của hệ thống dựa trên AWS Well-Architected Framework. Kiến trúc được xây dựng theo hướng Event-driven và Serverless, sử dụng các dịch vụ như Amazon API Gateway, AWS Lambda, Amazon Cognito, Amazon S3, Amazon DynamoDB, Amazon EventBridge, Amazon SNS, Amazon SES và Amazon CloudWatch.

Bên cạnh đó, tôi thiết kế các workflow chính của hệ thống, bao gồm quy trình đăng ký khuôn mặt, điểm danh từ camera, gửi thông báo, phân tích dữ liệu và tích hợp AI. Cuối tuần, tôi hoàn thiện cấu trúc repository, lựa chọn công nghệ và lập kế hoạch triển khai theo từng milestone để chuẩn bị cho giai đoạn phát triển.

---

### Khó khăn gặp phải

* Phạm vi của hệ thống ban đầu khá lớn, khó xác định các chức năng cần ưu tiên.
* Cần cân đối giữa yêu cầu của dự án và thời gian thực hiện.
* Việc lựa chọn dịch vụ AWS phù hợp cho từng thành phần của hệ thống cần nhiều thời gian nghiên cứu.
* Thiết kế kiến trúc đảm bảo khả năng mở rộng nhưng vẫn phù hợp với phạm vi MVP.

---

### Cách giải quyết

* Thu hẹp phạm vi dự án và tập trung vào chức năng điểm danh bằng nhận diện khuôn mặt.
* Chia dự án thành nhiều milestone để triển khai theo từng giai đoạn.
* Tham khảo AWS Well-Architected Framework và tài liệu chính thức của AWS để lựa chọn dịch vụ phù hợp.
* Thiết kế kiến trúc theo hướng module hóa nhằm thuận tiện cho việc mở rộng trong tương lai.

---

### Kiến thức đạt được

Sau tuần thứ năm, tôi đã:

* Hiểu quy trình phân tích và thiết kế một dự án Cloud trước khi triển khai.
* Biết cách xác định phạm vi MVP cho hệ thống.
* Hiểu cách áp dụng AWS Well-Architected Framework vào thiết kế kiến trúc.
* Hiểu mô hình Serverless kết hợp Event-driven Architecture.
* Biết cách lập kế hoạch triển khai dự án theo từng milestone.

---

### Kết quả đạt được

* Đề tài **Smart Campus Platform** được xác định.
* Tài liệu phân tích yêu cầu và phạm vi MVP.
* Kiến trúc tổng thể của hệ thống.
* Các sơ đồ workflow chính.
* Thiết kế cấu trúc repository.
* Kế hoạch triển khai theo từng milestone.

---

### Tài liệu tham khảo

* AWS Well-Architected Framework.
* AWS Serverless Application Model (AWS SAM) Documentation.
* AWS Architecture Center.
* AWS Documentation – Amazon API Gateway.
* AWS Documentation – AWS Lambda.
* AWS Documentation – Amazon EventBridge.
