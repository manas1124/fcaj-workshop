---
title: "Worklog Tuần 3"
date: 2026-07-06
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3

* Tìm hiểu các khái niệm mạng trong AWS.
* Hiểu vai trò của Amazon VPC trong việc xây dựng hạ tầng Cloud.
* Phân biệt Security Group và Network ACL.
* Thực hành xây dựng mô hình mạng nhiều tầng (Multi-tier Network Architecture).

---

### Công việc thực hiện trong tuần

| Thứ   | Công việc                                                                            | Ngày       |
| ----- | ------------------------------------------------------------------------------------ | ---------- |
| Thứ 2 | Tìm hiểu Amazon VPC, CIDR Block, Subnet và Route Table.                              | 06/07/2026 |
| Thứ 3 | Nghiên cứu Internet Gateway, Public Subnet và Private Subnet.                        | 07/07/2026 |
| Thứ 4 | Tìm hiểu NAT Gateway và cơ chế truy cập Internet từ Private Subnet.                  | 08/07/2026 |
| Thứ 5 | So sánh Security Group và Network ACL, thực hành cấu hình các quy tắc truy cập mạng. | 09/07/2026 |
| Thứ 6 | Thiết kế và triển khai mô hình Multi-tier Network Architecture trên AWS.             | 10/07/2026 |
| Thứ 7 | Kiểm thử kết nối giữa các thành phần trong VPC và tổng hợp kiến thức đã học.         | 11/07/2026 |

---

### Nội dung đã thực hiện

Trong tuần thứ ba, tôi tập trung nghiên cứu kiến trúc mạng trên nền tảng AWS, bắt đầu với Amazon Virtual Private Cloud (VPC). Tôi tìm hiểu cách thiết kế không gian địa chỉ IP bằng CIDR Block, phân chia Subnet và cấu hình Route Table để định tuyến lưu lượng mạng.

Tiếp theo, tôi nghiên cứu Internet Gateway và cách triển khai Public Subnet và Private Subnet nhằm xây dựng mô hình mạng an toàn. Tôi cũng tìm hiểu vai trò của NAT Gateway trong việc cho phép các tài nguyên trong Private Subnet truy cập Internet mà không cần gán Public IP.

Bên cạnh đó, tôi thực hành cấu hình Security Group và Network ACL để hiểu sự khác nhau giữa cơ chế bảo mật ở cấp tài nguyên và cấp mạng.

Cuối tuần, tôi triển khai mô hình Multi-tier Network Architecture với các lớp mạng tách biệt, đồng thời kiểm thử khả năng kết nối giữa các thành phần trong hệ thống.

---

### Khó khăn gặp phải

* Ban đầu chưa hiểu rõ mối quan hệ giữa VPC, Subnet và Route Table.
* Dễ nhầm lẫn giữa Security Group và Network ACL do đều kiểm soát lưu lượng mạng.
* Việc thiết kế CIDR Block phù hợp cần được tính toán để tránh chồng lấn địa chỉ IP.
* Mất thời gian để hiểu cơ chế hoạt động của NAT Gateway và luồng định tuyến.

---

### Cách giải quyết

* Vẽ sơ đồ mạng để mô phỏng luồng lưu lượng giữa các thành phần.
* Thực hành tạo nhiều VPC và Subnet với các cấu hình khác nhau.
* So sánh Security Group và Network ACL thông qua các tình huống thực tế.
* Tham khảo AWS Documentation và AWS Well-Architected Framework về thiết kế mạng.

---

### Kiến thức đạt được

Sau tuần thứ ba, tôi đã:

* Hiểu vai trò của Amazon VPC trong kiến trúc AWS.
* Biết cách thiết kế CIDR Block và Subnet.
* Hiểu cơ chế định tuyến thông qua Route Table.
* Phân biệt Internet Gateway và NAT Gateway.
* Phân biệt Security Group và Network ACL.
* Có khả năng xây dựng mô hình mạng nhiều tầng theo kiến trúc AWS.

---

### Kết quả đạt được

* Mô hình Amazon VPC hoàn chỉnh.
* Public Subnet và Private Subnet được cấu hình thành công.
* Internet Gateway và NAT Gateway được triển khai.
* Security Group và Network ACL được cấu hình theo yêu cầu.
* Hoàn thành mô hình Multi-tier Network Architecture.
* Tài liệu ghi chú về các thành phần mạng trên AWS.

---

### Tài liệu tham khảo

* AWS First Cloud Journey Learning Path.
* AWS Documentation – Amazon VPC.
* AWS Documentation – Security Groups.
* AWS Documentation – Network ACLs.
* AWS Documentation – NAT Gateway.
* AWS Well-Architected Framework.
