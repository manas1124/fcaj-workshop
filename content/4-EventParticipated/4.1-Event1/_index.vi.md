---
title: "Sự kiện 1"
date: 2026-08-08
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Báo cáo: AWS AgentForge Deepdive Day 2 – Advanced Amazon Bedrock AgentCore

**Sự kiện:** Workshop offline + Hands-on Lab, 08/08/2026  
**Vai trò:** Người tham dự

---

## 1. Định hướng nghề nghiệp Cloud/AI

Mô hình **T-Shaped Skills**:
- **Năm 1 – Depth:** Đào sâu một chuyên môn cốt lõi (serverless, data pipeline, model deployment).
- **Năm 2–3 – Breadth:** Mở rộng sang production và tích lũy **domain knowledge** (EdTech, HealthTech, FinTech).

Chứng chỉ AWS là điều kiện *cần*, nhưng khả năng giải quyết bài toán thực tế mới là điều kiện *đủ*.  
Kỹ năng giao tiếp với người non-technical là kỹ năng sống còn.  
Tham gia **Hackathon** để biến lý thuyết thành sản phẩm chạy được.

---

## 2. Kiến trúc Agent Core

| | Chatbot | AI Agent |
|---|---|---|
| Đầu ra | Văn bản | Thực thi hành động |
| Khả năng | Hỏi–đáp | Tự chủ lập kế hoạch |
| Công cụ | Không | Gọi Tools bên ngoài |
| Trạng thái | Không nhớ | Có Memory ngắn và dài hạn |

**Vòng lặp nhận thức:** `Reasoning` → `Thinking` → `Tool Use`. Agent tự quyết định gọi tool nào, thay vì lập trình viên hard-code từng bước.

---

## 3. Memory

- **Short-term Memory:** Lưu raw text trong phiên làm việc, xử lý **đồng bộ** → phản hồi tức thì nhưng tốn context window.
- **Long-term Memory:** Module **Memory Extraction** chạy **bất đồng bộ** ở background, tự động trích xuất insight từ chat rồi lưu dài hạn.

**Trade-off:** Chiến lược lưu chi tiết → nhớ tốt nhưng tốn token. Chiến lược tóm tắt → rẻ hơn nhưng có thể mất thông tin.

---

## 4. Observability

Giải quyết bài toán "hộp đen" của Agent:
- **Logging:** Ghi lại nội dung tương tác và tham số tool.
- **Tracing:** Theo dõi toàn bộ vòng đời request để trả lời "tại sao Agent trả lời như vậy?".
- **Metrics & Alerting:** Theo dõi latency, tài nguyên, traffic; kết nối auto-scaling khi tải tăng đột biến.

---

## 5. Evaluation

So sánh **Predicted Response** (AI sinh ra) với **Ground Truth** (câu trả lời chuẩn do người soạn) để có metrics định lượng.

Không thể tự động hóa 100%. Cần **SME** thẩm định tính chính xác nghiệp vụ, đặc biệt trong y tế, tài chính.

---

## 6. Policy & Security

- **Cedar Language:** Ngôn ngữ khai báo tập trung để định nghĩa quyền hạn Agent.
- **Permissive Mode:** Chỉ dùng khi dev.
- **Strict Mode:** Bắt buộc trên production — đảm bảo **Least Privilege**, tránh rò rỉ dữ liệu và hành động phá hoại do prompt injection.

---

## 7. Mở rộng năng lực với Tools

| Tool | Chức năng |
|---|---|
| **Browser** | Truy cập Internet lấy dữ liệu thời gian thực |
| **Code Interpreter** | Chạy code trong sandbox để tính toán, vẽ biểu đồ |
| **Payment Integration** | Gọi API thanh toán, biến Agent thành trợ lý bán hàng tự động |

---

## 8. Hands-on Lab: Refund Assistant

**Stack:** Agent CLI + Node.js + AWS CDK (triển khai serverless qua CloudFormation).  
Chỉ tính tiền khi invoke, không traffic thì không mất phí.

Agent nhận yêu cầu hoàn tiền → gọi tool tra cứu đơn hàng → kiểm tra điều kiện → phản hồi.  
Dùng **Mock Data trong System Prompt** để test logic nhanh, tránh dựng DB thật ngay từ đầu.  
**Log** lưu local (debug dev), **Trace** đẩy lên cloud observability (giám sát production).

---

## Key Takeaways

1. **Agent production ≠ Agent demo.** 30% là build, 70% còn lại là Memory, Observability, Evaluation, Security và auto-scaling.
2. **Memory hai tầng:** Ngắn hạn đồng bộ (tốc độ), dài hạn bất đồng bộ (không chậm UX).
3. **Log ≠ Trace:** Log biết *cái gì*, Trace biết *trình tự và thời gian*.
4. Không **Ground Truth** = đánh cược mù mỗi lần sửa prompt.
5. **Permissive** để dev, **Strict** để sống. Kiểm tra Strict Mode là bắt buộc trước mỗi release.
6. **Memory Strategy** ảnh hưởng trực tiếp hóa đơn token. Serverless rẻ cho PoC và traffic thấp.
7. **Nghề nghiệp:** Đào sâu trước, mở rộng sau. Chứng chỉ là cần, sản phẩm là đủ.

## Hình ảnh chứng minh tham gia
![minh chứng tham gia](/images/4-EventParticipated/event-1/event1-1.jpg)
![minh chứng tham gia](/images/4-EventParticipated/event-1/event1-2.jpg)
![minh chứng tham gia](/images/4-EventParticipated/event-1/event1-3.jpg)
![minh chứng tham gia](/images/4-EventParticipated/event-1/event1-4.jpg)