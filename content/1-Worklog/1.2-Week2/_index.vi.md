---
title: "Worklog Tuần 2"
date: 2026-06-29
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2

* Tìm hiểu các dịch vụ lưu trữ và cơ sở dữ liệu trên AWS.
* Hiểu sự khác nhau giữa Object Storage, Block Storage và Relational Database.
* Thực hành sử dụng Amazon S3, Amazon EBS và Amazon RDS.
* Xây dựng hệ thống upload file đơn giản sử dụng Amazon S3.

---

### Công việc thực hiện trong tuần

| Thứ   | Công việc                                                                    | Ngày       |
| ----- | ---------------------------------------------------------------------------- | ---------- |
| Thứ 2 | Tìm hiểu Amazon S3, Bucket, Object, Storage Class và các trường hợp sử dụng. | 29/06/2026 |
| Thứ 3 | Thực hành tạo Bucket, quản lý Object và cấu hình Lifecycle Policy.           | 30/06/2026 |
| Thứ 4 | Nghiên cứu Amazon EBS, Snapshot và cách quản lý Block Storage cho EC2.       | 01/07/2026 |
| Thứ 5 | Tìm hiểu Amazon RDS, khởi tạo cơ sở dữ liệu và kết nối từ ứng dụng.          | 02/07/2026 |
| Thứ 6 | Xây dựng hệ thống upload file sử dụng Amazon S3 làm nơi lưu trữ.             | 03/07/2026 |
| Thứ 7 | Kiểm thử chức năng upload, quản lý dữ liệu và tổng hợp kiến thức đã học.     | 04/07/2026 |

---

### Nội dung đã thực hiện

Trong tuần thứ hai, tôi tập trung nghiên cứu các dịch vụ lưu trữ và cơ sở dữ liệu phổ biến trên AWS.

Đầu tiên, tôi tìm hiểu Amazon S3, bao gồm cách tổ chức dữ liệu theo Bucket và Object, các lớp lưu trữ (Storage Classes) cũng như cơ chế Lifecycle Policy nhằm tự động quản lý vòng đời dữ liệu và tối ưu chi phí lưu trữ.

Tiếp theo, tôi nghiên cứu Amazon EBS để hiểu cách cung cấp Block Storage cho EC2 Instance, đồng thời thực hành tạo Snapshot nhằm phục vụ sao lưu và khôi phục dữ liệu.

Sau đó, tôi tìm hiểu Amazon RDS, bao gồm quy trình khởi tạo cơ sở dữ liệu, cấu hình kết nối và các thao tác quản lý cơ bản.

Cuối tuần, tôi thực hiện bài thực hành xây dựng hệ thống upload file đơn giản, trong đó Amazon S3 được sử dụng để lưu trữ tập tin và kiểm thử quá trình tải lên, truy cập cũng như quản lý dữ liệu.

---

### Khó khăn gặp phải

* Ban đầu chưa phân biệt rõ sự khác nhau giữa Amazon S3 và Amazon EBS.
* Gặp khó khăn trong việc lựa chọn Storage Class phù hợp với từng trường hợp sử dụng.
* Việc cấu hình quyền truy cập Bucket cần được tìm hiểu kỹ để tránh cấp quyền quá mức.
* Quá trình kết nối tới Amazon RDS cần cấu hình đúng Security Group và Endpoint.

---

### Cách giải quyết

* Đọc tài liệu AWS Documentation và so sánh đặc điểm của từng dịch vụ lưu trữ.
* Thực hành tạo nhiều Bucket và thử nghiệm các Storage Class khác nhau.
* Tìm hiểu nguyên tắc Least Privilege khi cấu hình quyền truy cập S3.
* Kiểm tra từng bước cấu hình mạng và Security Group khi kết nối RDS.

---

### Kiến thức đạt được

Sau tuần thứ hai, tôi đã:

* Hiểu sự khác nhau giữa Object Storage, Block Storage và Relational Database.
* Biết cách tạo và quản lý Amazon S3 Bucket.
* Hiểu cơ chế hoạt động của Lifecycle Policy.
* Biết cách tạo Snapshot cho Amazon EBS.
* Hiểu quy trình triển khai và quản lý Amazon RDS.
* Có khả năng xây dựng hệ thống upload file đơn giản sử dụng Amazon S3.

---

### Kết quả đạt được

* Tạo và quản lý thành công Amazon S3 Bucket.
* Cấu hình Lifecycle Policy cho Bucket.
* Thực hiện Snapshot cho Amazon EBS.
* Khởi tạo và kết nối thành công Amazon RDS.
* Hoàn thành hệ thống upload file sử dụng Amazon S3.
* Tổng hợp tài liệu và ghi chú về các dịch vụ lưu trữ trên AWS.

---

### Tài liệu tham khảo

* AWS First Cloud Journey Learning Path.
* AWS Documentation – Amazon S3.
* AWS Documentation – Amazon EBS.
* AWS Documentation – Amazon RDS.
