---
title: "Sự kiện 2"
date: 2026-08-15
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Báo cáo: AWS AgentForge Deepdive Day 3 – AgentCore DevOps & Best Practices

**Sự kiện:** Workshop offline + Hands-on Lab, 15/08/2026  
**Vai trò:** Người tham dự

---

## 1. Thông tin chung

- **Thời gian:** 3 ngày (tập trung vào use cases, best practices và thực hành trong ngày thứ 3)
- **Nội dung trọng tâm:**
  - Tổng quan 12 tính năng của Amazon Bedrock Agent Core (6 tính năng chính + 6 tính năng phụ)
  - Cập nhật thị trường: DeepSeek Harness & DeepSeek V4 Pro Max
  - Use cases thực tế: DevOps (QA Testing & Bug Fixing), Visa Intelligent Commerce
  - Best practices triển khai hệ thống Agentic trên production
  - Hands-on Labs: Xây dựng AI Agent cho e-commerce bằng Agent Core CLI và Kiro IDE

---

## 2. Tổng quan kiến thức nền tảng

Trong hai ngày đầu, chương trình đã trang bị kiến thức nền về **Amazon Bedrock Agent Core** với 12 tính năng chia làm hai nhóm:

- **Nhóm tính năng chính (Agent Core):** Bao gồm Runtime, Memory, Evaluation, Observability, Browser, Code Interpreter.
- **Nhóm tính năng phụ:** Bao gồm Skill, Gateway, Identity, Harness, Payment, Sandbox/File System.

Các khái niệm then chốt đã được làm rõ:
- **Memory:** Gồm 4 loại – Reference Memory (trích xuất sở thích người dùng), Summary Memory (tóm tắt cuộc trò chuyện), Semantic Memory (lưu trữ dạng vector để retrieve), Episodic Memory (cải thiện hiệu suất agent qua các phiên).
- **Evaluation:** Đánh giá 3 lớp – (1) Scope/Goal: kết quả cuối có đúng nhu cầu; (2) Correctness & Fairness: câu trả lời đúng, không thiên lệch; (3) Tool Usage: có sử dụng đúng công cụ không.
- **Observability:** Tracing, logging, metrics qua Agent Core Observability và CloudWatch, giúp giám sát hiệu năng và phát hiện lỗi.

---

## 3. Cập nhật thị trường: DeepSeek Harness & V4 Pro Max

### 3.1. DeepSeek Harness
Ngày 13/08, DeepSeek công bố **Harness** – một framework vận hành bao quanh lớp model ("bộ não"), đi kèm với mô hình **V4 Pro Max**.

- **Triết lý thiết kế:** *"Everything is a plugin"* – mọi thành phần ngoài model chính (tool, skill, session, sandbox, file system, browser, payment gateway) đều có thể kết nối, thay thế và mở rộng như các khối Lego.
- **Kiến trúc:** Giảm tính đơn khối (monolithic), phân mảnh thành microservices nhằm dễ dàng scale và debug.
- **Mô hình kinh doanh:** Chỉ bán token qua API với chi phí rất thấp (demo xây dựng ứng dụng 3D theo dõi trạm vũ trụ ISS chỉ tốn **~5 cent** cho ~1 triệu token và 23 API requests).
- **Ý nghĩa:** Các doanh nghiệp có thể tự host model trên phần cứng on-premise (ví dụ: GPU RTX 5090) kết hợp với Harness để xây dựng hệ thống agent độc lập, giảm phụ thuộc vào các nền tảng đóng.

### 3.2. So sánh & Bài học
- Cloud IDE (Cursor, v.v.) đang đi theo hướng closed-source, đóng gói tính năng cao cấp vào gói trả phí.
- DeepSeek đi ngược lại bằng cách open-source cả model lẫn framework vận hành, tạo lợi thế cạnh tranh về chi phí và tùy biến.

---

## 4. Use Cases Thực Tế

### 4.1. DevOps: Hệ thống QA Testing & Bug Fixing tự động
**Bối cảnh:** DevOps Engineer tại AWS Singapore triển khai giải pháp thay thế manual QA và bug fixing trong pipeline CI/CD.

**Kiến trúc hệ thống:**
- **Agent 1 – QA Testing:** Sử dụng Browser (mô phỏng người dùng nhấn nút, điền form, upload file), Code Interpreter, Memory (Semantic + Episodic), Skill và Observability.
- **Agent 2 – Bug Fixing:** Nhận báo cáo lỗi từ QA Agent, sửa code, deploy lên branch mới và tạo pull request.
- **Vòng lặp:** Developer push code → GitHub Actions trigger → QA Agent test → Report theo severity → Bug Fix Agent sửa → Deploy lại → Test lại.

**Kết quả thực tế:**
- Phát hiện **15 lỗi** trong lần chạy đầu, bao gồm lỗi nghiêm trọng như "Data Discrepancy" (chi phí hiển thị không đồng nhất giữa các trang).
- **Human-in-the-loop:** Agent không tự merge vào production. Senior DevOps vẫn giữ vai trò review cuối cùng, đảm bảo chất lượng và tính đúng đắn của bản sửa lỗi.

**Bài học:** Agent không thay thế hoàn toàn con người mà đóng vai trò "junior" thực hiện công việc lặp lại, giúp senior tập trung vào đánh giá và ra quyết định.

### 4.2. Visa Intelligent Commerce – Agentic Commerce
**Bối cảnh:** Visa hợp tác với AWS triển khai nền tảng thương mại giữa các agent (agent-to-agent, agent-to-web).

**Luồng hoạt động:**
1. Agent của người dùng (ví dụ: chatbot) lập kế hoạch mua sắm/chuyến đi dựa trên dữ liệu cá nhân được chia sẻ qua **Data Tokens API**.
2. Khi thanh toán, agent không trực tiếp xử lý thông tin thẻ. Thay vào đó, người dùng nhập thông tin vào **secure popup** của Visa.
3. **Tokenization API:** Thay thế số thẻ thật bằng token 16 chữ số bảo mật.
4. **Authentication API & Passkey:** Xác thực sinh trắc học (vân tay/khuôn mặt) để xác nhận giao dịch.
5. **Signals API:** Kiểm tra từng lệnh của agent (merchant, số tiền, mục đích) trước khi giao dịch được thực hiện.

**Ý nghĩa kiến trúc:**
- Agent **không bao giờ nắm giữ** thông tin thanh toán thật.
- Lớp bảo mật đa tầng (token, cryptogram, biometric) đảm bảo tuân thủ regulatory nghiêm ngặt của ngành tài chính.
- AWS Bedrock Agent Core cung cấp hạ tầng an toàn, reliable để xử lý quy mô hàng trăm tỷ giao dịch/năm của Visa.

---

## 5. Best Practices Triển Khai Agentic System

Dựa trên kinh nghiệm từ các case study và khuyến nghị của AWS, các best practices quan trọng bao gồm:

### 5.1. Ground Truth & Evaluation
- Thiết lập **benchmark đầu vào/đầu ra** (input/output ground truth) để đo lường độ chính xác.
- Sử dụng 13 metrics có sẵn của Agent Core (faithfulness, relevance, v.v.) để đánh giá kết quả.
- Tạo nhiều biến thể câu hỏi (variations) để kiểm tra tính ổn định của agent.

### 5.2. Observability ngay từ đầu
- Tích hợp telemetry, logging và metrics ngay từ giai đoạn thiết kế.
- Sử dụng CloudWatch để theo dõi không chỉ agent mà cả hệ thống nền tảng (GPU, latency).
- Đặt alert khi có dấu hiệu bất thường (ví dụ: GPU usage > 80%).

### 5.3. Kiến trúc không đơn khối (Break down monolithic agent)
- Chia nhỏ thành nhiều agent chuyên biệt (supervisor, shopping assistant, cart manager, v.v.) thay vì một agent "làm tất cả".
- Dễ dàng scale, debug và bảo trì từng thành phần độc lập.

### 5.4. Prompt Engineering & Loop Engineering
- Không chỉ tối ưu prompt mà còn phải chọn đúng **mode** (plan mode → execute mode/agent mode).
- Plan mode thường dùng model lớn hơn để lập kế hoạch; execute mode dùng model nhẹ hơn để thực thi.

### 5.5. Human-in-the-loop
- Luôn giữ con người ở bước review cuối cùng, đặc biệt với các hệ thống production có ảnh hưởng lớn (tài chính, y tế).

### 5.6. UX & Latency
- Người dùng cuối không quan tâm kiến trúc bên trong mà quan tâm **thời gian phản hồi**.
- Xử lý inference time bằng cách: trả lời câu hỏi đơn giản trước, đẩy tác vụ phức tạp vào background xử lý bất đồng bộ.
- Thay chữ "Loading" bằng "Thinking" để cải thiện trải nghiệm người dùng với AI.

### 5.7. Deterministic vs. Autonomous
- Cân bằng giữa luồng xác định (workflow cố định cho vấn đề có quy trình rõ ràng) và tự chủ (agent tự quyết định cho vấn đề mở).

---

## 6. Hands-on Labs: Xây dựng E-commerce Agent với Kiro & Agent Core

Phần thực hành được hướng dẫn qua **10 labs**, sử dụng:
- **Kiro IDE:** Trình AI IDE hỗ trợ viết code, tạo steering documents (tài liệu định hướng AI).
- **Stratosphr:** Framework AI để định nghĩa và gọi API của LLM.
- **Agent Core CLI:** Công cụ dòng lệnh để tạo, deploy và quản lý agent.
- **Công nghệ AWS:** Bedrock Agent Core, DynamoDB, S3 Vector Store, Lambda, API Gateway, CloudWatch.

### Tóm tắt các Labs:

| Lab | Nội dung | Kiến thức đạt được |
|-----|----------|-------------------|
| **Lab 1** | Starter Kit & Local Web Chat | Tạo agent runtime đầu tiên, gọi Bedrock LLM API, chạy local bằng `agent-core dev` |
| **Lab 2** | System Prompt & Tools | Tùy chỉnh system prompt cho ngữ cảnh e-commerce (đổi trả hàng); định nghĩa tool (lookup order, user, product) |
| **Lab 3** | Persistent Memory | Tạo memory với các strategy (reference, summary, semantic); tích hợp vào runtime qua environment variable |
| **Lab 4** | CloudFormation Template | Triển khai DynamoDB, S3 Vector Store, Bedrock Knowledge Base bằng infrastructure-as-code |
| **Lab 5** | Streamlit Web UI | Xây dựng giao diện web để tương tác với agent, quản lý user bằng Cognito |
| **Lab 6** | Observability & Tracing | Theo dõi token usage, latency, query logs trên CloudWatch; phân tích chi phí theo thời gian thực |
| **Lab 7** | Custom Features | Mở rộng agent bằng cách thêm tool mới qua Kiro, cập nhật tool spec |
| **Lab 8** | Harness | Khai báo tập trung system prompt, tool, memory, gateway trong một bộ cấu hình (harness) |
| **Lab 9** | Evaluation | Đánh giá kết quả agent bằng metrics; so sánh với ground truth qua session ID |
| **Lab 10** | Guardrails | Thiết lập policy để kiểm soát nội dung đầu ra của agent |

### Các điểm lưu ý quan trọng từ thực hành:

1. **Token Inbox cao hơn Outbox:**
   - Khi người dùng chỉ gửi 1-2 chữ (ví dụ: "hi"), token inbox vẫn có thể lên đến ~1.8k.
   - **Nguyên nhân:** Inbox bao gồm không chỉ input của user mà còn có **system prompt**, **định nghĩa tool**, **memory context** và lịch sử chat. Điều này không hiển thị trong giao diện chat nhưng vẫn được gửi đến model.

2. **Phân quyền IAM (Machine-to-Machine):**
   - Trên local, user chạy bằng quyền admin nên không cần cấu hình thêm.
   - Khi deploy lên AWS, **runtime** cần được cấp quyền IAM để truy cập **memory** (và ngược lại). Đây là phân quyền service-to-service (machine-to-machine), bắt buộc phải vá IAM policy.

3. **Tối ưu chi phí model:**
   - Mặc định Agent Core CLI gọi Claude Sonnet (khá đắt).
   - Có thể chuyển sang **Amazon Nova Lite** hoặc **Nova Pro** qua file `model.py` để giảm chi phí đáng kể (demo chỉ tốn ~$0.2 sau nhiều giờ thực hành).

4. **API Gateway & Semantic Search:**
   - Agent Core Gateway không chỉ là proxy mà còn hỗ trợ **semantic search** để tự động tìm tool phù hợp với request của người dùng.
   - Cần định nghĩa `tool spec` đầy đủ để gateway hiểu và điều phối đúng Lambda function.

---

## 7. Bài học rút ra & Định hướng cá nhân

### 7.1. Kiến thức chuyên môn
- Hiểu rõ kiến trúc **Agent Core** không chỉ là "chatbot thông minh" mà là cả một hệ sinh thái gồm memory, tool, evaluation, observability và security.
- Nắm được cách thiết kế **multi-agent system** thay vì monolithic agent, giúp hệ thống dễ scale và bảo trì.
- Hiểu sâu về **bảo mật trong agentic commerce**: tokenization, passkey, biometric authentication là bắt buộc, không phải tùy chọn.

### 7.2. Tư duy thị trường & Công nghệ
- Công nghệ AI đang thay đổi cực nhanh (DeepSeek Harness release chỉ trong 1 ngày trước workshop).
- **Nhiệm vụ của engineer:** Không chỉ hiểu công cụ mà còn phải liên tục cập nhật xu hướng, đọc paper (nếu theo hướng nghiên cứu) hoặc áp dụng tool mới (nếu theo hướng application).
- Chi phí triển khai AI đang giảm mạnh: từ hàng trăm USD/tháng cho closed-source xuống chỉ vài cent cho open-source model + self-host.

### 7.3. Kỹ năng triển khai
- Sử dụng thành thạo **Agent Core CLI** để tạo resource, deploy runtime, add memory/knowledge base.
- Tích hợp **Kiro IDE** vào quy trình phát triển để tăng tốc độ viết code, tạo steering documents và debug.
- Biết cách đọc logs, trace requests và tối ưu chi phí dựa trên dashboard.

### 7.4. Định hướng phát triển
- **Song song domain knowledge + technical knowledge:** Không thể chỉ giỏi code mà phải hiểu industry (tài chính, y tế, thương mại điện tử) để thiết kế đúng giải pháp.
- **Tập trung theo dõi thị trường:** Subscribe các trang công nghệ, tham gia cộng đồng để nắm bắt feature mới nhất của AWS, DeepSeek và các nền tảng AI khác.
- **Thực hành liên tục:** Chỉ qua 10 labs đã có thể hình dung toàn bộ pipeline từ local development đến AWS production. Cần tiếp tục áp dụng vào dự án thực tế để củng cố.

---

## 8. Kết luận

Workshop đã cung cấp cái nhìn toàn diện từ **lý thuyết → use case thực tế → thực hành hands-on** về Amazon Bedrock Agent Core. Ba điểm mấu chốt được khắc sâu:

1. **Agent = Brain + Body:** Model chỉ là bộ não; để agent thực sự làm việc cần harness, tool, memory và môi trường thực thi (browser, code interpreter).
2. **Trust but Verify:** Luôn có con người ở vòng lặp cuối (human-in-the-loop), đặc biệt trong các hệ thống ảnh hưởng đến tiền bạc và dữ liệu nhạy cảm.
3. **Cost & Speed matter:** Kiến trúc tốt không đủ nếu latency cao hoặc chi phí vượt ngân sách. Lựa chọn model phù hợp (Nova Lite/Pro thay vì Claude Sonnet khi có thể) và thiết kế luồng bất đồng bộ là yếu tố sống còn.

Với kiến thức và kinh nghiệm từ buổi event, người học hoàn toàn có thể tự triển khai một hệ thống agent cơ bản trên AWS, đồng thời có tầm nhìn đúng đắn về hướng phát triển của công nghệ Agentic AI trong tương lai gần.

## Hình ảnh chứng minh tham gia
![minh chứng tham gia](/images/4-EventParticipated/event-2/event2-1.jpg)
![minh chứng tham gia](/images/4-EventParticipated/event-2/event2-2.jpg)