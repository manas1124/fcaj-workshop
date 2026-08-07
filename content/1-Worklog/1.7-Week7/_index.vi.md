---
title: "Worklog Tuần 7"
date: 2026-08-03
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7

- Hoàn thiện toàn bộ phạm vi dự án Smart Campus Platform theo kế hoạch.
- Triển khai hệ thống lên môi trường AWS bằng AWS SAM và CloudFormation.
- Kiểm thử các chức năng chính và tối ưu quy trình triển khai.
- Hoàn thiện tài liệu kỹ thuật, báo cáo và nộp sản phẩm cuối cùng.

---

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày |
|------|-----------|------|
| Thứ 2 | Hoàn thiện các Lambda Function, tích hợp Amazon API Gateway, Amazon Cognito, Amazon S3 và Amazon DynamoDB. | 03/08/2026 |
| Thứ 3 | Hoàn thiện các workflow nghiệp vụ, cấu hình IAM Role và EventBridge, kiểm tra luồng xử lý dữ liệu. | 04/08/2026 |
| Thứ 4 | Build và triển khai hệ thống bằng AWS SAM, CloudFormation và GitHub Actions; xử lý các lỗi phát sinh trong quá trình triển khai. | 05/08/2026 |
| Thứ 5 | Kiểm thử toàn bộ hệ thống, sửa lỗi và tối ưu cấu hình CloudWatch Logging, IAM Policy và môi trường triển khai. | 06/08/2026 |
| Thứ 6 | Hoàn thiện tài liệu kỹ thuật, sơ đồ kiến trúc, hướng dẫn triển khai và chuẩn bị báo cáo dự án. | 07/08/2026 |
| Thứ 7 | Rà soát sản phẩm, hoàn thiện hồ sơ, nộp báo cáo và bàn giao dự án. | 08/08/2026 |

---

### Nội dung thực hiện

Trong tuần thứ bảy, tôi tập trung hoàn thiện toàn bộ dự án Smart Campus Platform trước thời điểm nộp sản phẩm. Các chức năng cốt lõi của hệ thống được tích hợp hoàn chỉnh theo kiến trúc AWS Serverless đã thiết kế ở các tuần trước.

Tôi hoàn thiện các Lambda Function theo từng nhóm nghiệp vụ, bao gồm xử lý đăng ký khuôn mặt, điểm danh, thông báo và các thành phần hỗ trợ khác. Mã nguồn tiếp tục được tổ chức theo hướng Clean Architecture, tách biệt Lambda Handler, Service Layer và các thành phần dùng chung nhằm đảm bảo khả năng mở rộng và bảo trì.

Bên cạnh đó, tôi tích hợp Amazon API Gateway để cung cấp REST API, sử dụng Amazon Cognito cho cơ chế xác thực và phân quyền, đồng thời kết nối Amazon S3 và Amazon DynamoDB để lưu trữ dữ liệu của hệ thống. Các IAM Role được cấu hình theo nguyên tắc Least Privilege nhằm đảm bảo tính an toàn khi các Lambda truy cập tài nguyên AWS.

Sau khi hoàn thiện chức năng, tôi sử dụng AWS SAM và CloudFormation để build và triển khai hạ tầng lên AWS. Quy trình triển khai được tự động hóa thông qua GitHub Actions với các bước Unit Test, SAM Validate, SAM Build và SAM Deploy nhằm đảm bảo việc triển khai diễn ra nhất quán giữa các môi trường.

Trong quá trình triển khai, tôi gặp một số lỗi như cấu hình AWS Credentials, lỗi `sam validate`, cấu hình CloudFormation Stack và quyền truy cập IAM chưa phù hợp. Các lỗi này được xử lý bằng cách rà soát lại template AWS SAM, cập nhật cấu hình AWS CLI, điều chỉnh IAM Policy và kiểm tra log trên Amazon CloudWatch.

Sau khi hệ thống được triển khai thành công, tôi tiến hành kiểm thử các workflow chính như xác thực người dùng, đăng ký khuôn mặt, lưu trữ hình ảnh trên Amazon S3, ghi nhận dữ liệu điểm danh vào Amazon DynamoDB và xác minh luồng xử lý giữa các dịch vụ AWS. Kết quả kiểm thử cho thấy các chức năng chính hoạt động đúng theo thiết kế.

Cuối tuần, tôi hoàn thiện tài liệu kỹ thuật, cập nhật sơ đồ kiến trúc, hướng dẫn triển khai, tổng hợp kết quả thực hiện và hoàn thành báo cáo để nộp theo yêu cầu của chương trình.

---

### Khó khăn gặp phải

- Tích hợp đồng thời nhiều dịch vụ AWS trong cùng một workflow.
- Cấu hình IAM Role và IAM Policy để đảm bảo đúng quyền truy cập cho từng Lambda Function.
- Xử lý các lỗi phát sinh trong quá trình `sam validate`, `sam build` và `sam deploy`.
- Đồng bộ cấu hình giữa môi trường phát triển và môi trường AWS.
- Đảm bảo tài liệu kỹ thuật phản ánh đúng kiến trúc và quá trình triển khai thực tế.

---

### Cách giải quyết

- Kiểm thử từng thành phần trước khi tích hợp thành workflow hoàn chỉnh.
- Áp dụng nguyên tắc Least Privilege khi cấu hình IAM Role và IAM Policy.
- Sử dụng AWS SAM để kiểm tra và xác thực template trước khi triển khai.
- Theo dõi log trên Amazon CloudWatch để xác định và khắc phục lỗi.
- Chuẩn hóa tài liệu và sơ đồ kiến trúc trước khi hoàn thiện báo cáo.

---

### Kiến thức đạt được

Sau tuần thứ bảy, tôi đã:

- Hiểu quy trình hoàn thiện và triển khai một ứng dụng Serverless theo kiến trúc Production trên AWS.
- Thành thạo hơn trong việc sử dụng AWS SAM và CloudFormation để triển khai hạ tầng bằng Infrastructure as Code.
- Có kinh nghiệm xây dựng quy trình CI/CD với GitHub Actions cho dự án Serverless.
- Hiểu cách tích hợp Amazon API Gateway, Amazon Cognito, AWS Lambda, Amazon S3, Amazon DynamoDB và Amazon CloudWatch trong cùng một hệ thống.
- Nâng cao kỹ năng kiểm thử, xử lý lỗi và tối ưu quy trình triển khai trên môi trường Cloud.

---

### Kết quả đạt được

- Hoàn thành Smart Campus Platform theo phạm vi yêu cầu của dự án.
- Triển khai thành công hệ thống lên AWS bằng AWS SAM và CloudFormation.
- Xây dựng và vận hành thành công pipeline CI/CD bằng GitHub Actions.
- Hoàn thành tích hợp các dịch vụ Amazon API Gateway, Amazon Cognito, AWS Lambda, Amazon S3, Amazon DynamoDB và Amazon EventBridge.
- Hoàn thiện tài liệu kỹ thuật, sơ đồ kiến trúc và hướng dẫn triển khai.
- Hoàn thành báo cáo và nộp sản phẩm đúng tiến độ.

---

### Tài liệu tham khảo

- AWS Well-Architected Framework.
- AWS Serverless Application Model (AWS SAM) Documentation.
- AWS CloudFormation Documentation.
- AWS Lambda Developer Guide.
- Amazon API Gateway Developer Guide.
- Amazon Cognito Developer Guide.
- Amazon DynamoDB Developer Guide.
- Amazon S3 User Guide.
- GitHub Actions Documentation.