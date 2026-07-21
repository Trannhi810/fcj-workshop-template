---
title: "Sự kiện: 4"
date: 2026-06-27
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Bài Thu Hoạch: "Hội Thảo Ứng Dụng AI Agent và Bảo Mật Hạ Tầng Cloud tại FCAJ Community Day"

### Mục Đích Của Sự Kiện

Hội thảo **FCAJ Community Day** (ngày 27/06/2026) được tổ chức với các mục tiêu chính:

- **Chia sẻ định hướng và kinh nghiệm thực chiến** về vận hành hạ tầng đám mây (Cloud Infrastructure) và xử lý bài toán nợ công nghệ trong kỷ nguyên AI.
- **Giới thiệu kiến trúc Voice AI** ứng dụng cho ngôn ngữ tiếng Việt trong môi trường doanh nghiệp (tài chính, ngân hàng).
- **Cung cấp giải pháp tự động hóa** giám sát, phân tích và cô lập sự cố hệ thống thông qua trợ lý ảo DevOps AI Agent.
- **Hướng dẫn tối ưu quy trình** sàng lọc hồ sơ, quản trị nhân sự (HR) an toàn bằng Amazon Q.
- **Trình bày giải pháp kỹ thuật chuyên sâu** về thiết lập kênh kết nối Private khép kín, an toàn bảo mật cho các Agent AI qua giao thức MCP Server.

---

### Danh Sách Diễn Giả

Hội thảo gồm **5 session** độc lập với sự tham gia của **9 diễn giả**:

1. **Steve Trần** (Founder, Cloud Thinker) — Ứng dụng AI trong Vận hành & Giám sát Hạ tầng Cloud
2. **Hiếu Nghị** (Renova Cloud), **Kiệt** (AWS Study Group), **Trung** (Founder & CEO, R AI) — Giải pháp Giọng nói AI (Voice Agent) cho Doanh nghiệp
3. **Nguyên Nguyễn** & **Bảo** (Cloud Kinetic) — Trợ lý ảo DevOps (DevOps AI Agent) trên AWS
4. **Minh Anh** & **Trường / Wynn** (Noventic) — Trợ lý Tuyển dụng & Quản trị Nhân sự với Amazon Q
5. **Hiếu Nghị** (Renova Cloud) & **Toàn Nguyễn** (AWS Security Builder) — Thiết lập An toàn Bảo mật Kết nối Private cho Amazon Q qua MCP Server

---

### Nội Dung Nổi Bật

#### Session 1 – Ứng Dụng AI trong Vận Hành và Giám Sát Hạ Tầng Cloud

*Diễn giả: Steve Trần*

- **Thách thức nợ công nghệ:** Chuyển đổi sang Microservices mang lại khả năng mở rộng lớn nhưng gia tăng độ phức tạp hệ thống và nợ kỹ thuật qua nhiều năm.
- **Tự động hóa với AI Agent:** Ứng dụng AI vào kiểm soát chất lượng mã nguồn (Code Review) và tự động hóa chu kỳ đánh giá trước khi release.
- **Tối ưu chi phí & FinOps:** AI chạy FinOps tự động quản lý dashboard, đo lường mức độ sử dụng tài nguyên thay thế công việc thủ công.
- **Single Agent vs. Multi-Agent:** Đánh đổi giữa Single Agent (xử lý tốt tác vụ tổng hợp) và Multi-Agent (tối ưu context window, chi phí và phân quyền RBAC).

---

#### Session 2 – Giải Pháp Giọng Nói AI (Voice Agent) cho Doanh Nghiệp

*Diễn giả: Hiếu Nghị | Kiệt | Trung*

- **Thách thức ngôn ngữ:** Tiếng Việt là ngôn ngữ ít tài nguyên (low-resource), mô hình Speech-to-Speech trực tiếp chưa đạt hiệu quả cao.
- **Kiến trúc 3 thành phần:** Kết hợp Speech-to-Text → LLM → Text-to-Speech giúp kiểm soát chặt chẽ nội dung văn bản output trước khi phát giọng nói.
- **Tối ưu thời gian thực:** Stream dữ liệu giọng nói liên tục vào LLM kết hợp bộ lọc nhận diện giới tính và khoảng ngắt nghỉ thông minh.
- **Minh họa thực tế:** Thử nghiệm Voice Agent trên AWS Bedrock kết hợp Knowledge Base để tư vấn thông số kỹ thuật sản phẩm tự động.

---

#### Session 3 – Trợ Lý Ảo DevOps (DevOps AI Agent) trên AWS

*Diễn giả: Nguyên Nguyễn | Bảo*

- **Giảm MTTD & MTTR:** Giải quyết bài toán dữ liệu giám sát bị phân mảnh, tự động bóc tách log và tìm nguyên nhân gốc rễ (Root Cause).
- **Sáu trụ cột vận hành:** Tự động hóa qua sơ đồ Topology, quản lý quyền bằng Tag, tích hợp Slack/ServiceNow và kết nối qua giao thức MCP.
- **Quy trình 4 bước:** Trích xuất log → Điều tra nguyên nhân gốc rễ → Đề xuất phương án khắc phục → Đề xuất cải tiến hệ thống lâu dài.
- **Live Demo:** Giả lập tấn công DDoS trên ECS, AI Agent tự động chia 5 sub-tasks, phát hiện 10 tasks bị spam traffic và xuất lệnh khôi phục.

---

#### Session 4 – Trợ Lý Tuyển Dụng & Quản Trị Nhân Sự với Amazon Q

*Diễn giả: Minh Anh | Trường / Wynn*

- **Tối ưu quy trình HR:** Giải quyết hạn chế của sàng lọc CV thủ công, tiết kiệm chi phí time-to-hire và bảo mật dữ liệu nhân sự nội bộ.
- **Bảo mật Enterprise với Amazon Q:** Trợ lý AI kết nối an toàn với SharePoint, S3, Google Drive qua MCP, tiết kiệm token nhờ Memory Graph.
- **Tự động hóa tuyển dụng:** Cấu hình luật qua file Markdown → Tự động biên soạn JD → Quét CV, chấm điểm đối chiếu → Phân loại và xuất báo cáo HTML.

---

#### Session 5 – Thiết Lập An Toàn Bảo Mật Kết Nối Private cho Amazon Q qua MCP Server

*Diễn giả: Hiếu Nghị | Toàn Nguyễn*

- **Rủi ro mạng Public:** Kết nối API đến bên thứ ba qua Internet công cộng dễ đối mặt nguy cơ tấn công DDoS và Man-in-the-middle.
- **Kiến trúc Private Zero-Trust:** Đặt toàn bộ MCP Server trong Private Subnet, cô lập hoàn toàn bề mặt tấn công khỏi Internet.
- **Luồng dữ liệu khép kín:** Amazon Q → VPC Interface Endpoint → Route 53 Resolver → ALB → MCP Server, mã hóa TLS đầu cuối với ACM.
- **Đánh đổi chi phí:** Hạ tầng bảo mật nâng cao (ALB, Route 53 Resolver) phát sinh chi phí cố định ~250–350 USD/tháng, cần cân nhắc cán cân ROI.

---

### Những Gì Học Được

#### Tư Duy Thiết Kế Hệ Thống & Bảo Mật

- **Lấy bài toán thực tế làm trọng tâm:** Ứng dụng AI phải bắt đầu từ việc giải quyết các rủi ro bảo mật, nợ công nghệ và tối ưu chi phí thực tế.
- **Mô hình Human-in-the-loop:** Trợ lý AI tự động hóa các tác vụ lặp lại nhưng con người luôn giữ quyền ra quyết định và phê duyệt chiến lược.
- **Bảo mật Private là ưu tiên hàng đầu:** Đối với dữ liệu nhạy cảm cấp Enterprise, việc triển khai Zero Trust và kết nối Private cô lập là bắt buộc.

#### Kiến Trúc Kỹ Thuật & Vận Hành

- **Tầm quan trọng của Observability:** AI Agent chỉ suy luận chính xác khi hệ thống nền tảng có đầy đủ log, metrics, traces và alarm chất lượng.
- **Cân bằng chi phí và hiệu năng:** Đánh giá kỹ lưỡng giữa bài toán chi phí cố định cho hạ tầng bảo mật nâng cao và giá trị ROI mang lại.

---

### Ứng Dụng Vào Công Việc

- **Tự động hóa giám sát:** Tích hợp AWS CloudWatch với AI Agent đơn giản để làm quen quy trình phân tích log tự động.
- **Thực hành mạng Private:** Thiết lập môi trường lab cấu hình MCP Server trong Private Subnet và kết nối qua VPC Endpoint.
- **Khám phá Amazon Q & MCP:** Xây dựng knowledge base, cấu hình file instruction cho AI Agent và tích hợp custom action nội bộ.
- **Xây dựng custom AI skill:** Tận dụng công cụ AI để thử nghiệm tạo skill tự động hóa tóm tắt báo cáo và rà soát tài liệu.

---

### Trải Nghiệm Trong Event

Hội thảo FCAJ Community Day đem đến nhiều góc nhìn ứng dụng thực tế — từ việc dùng DevOps AI Agent để tự động phát hiện và xử lý sự cố, Amazon Q tự động hóa quy trình tuyển dụng, cho đến kiến trúc Private Zero-Trust bảo mật kết nối cho MCP Server. Những nội dung này giúp em hiểu rõ hơn mức độ phức tạp của các hệ thống AI thực tế và những đánh đổi doanh nghiệp phải cân nhắc khi triển khai.

#### Một Số Hình Ảnh Khi Tham Gia Sự Kiện

![Session 1 – AgenticOps for your Cloud (Steve Trần – Cloud Thinker)](/images/4-Event/Event4/session1-agenticops-cloud-thinker.jpg?featherlight=false&width=60pc)

![Session 2 – Building Voice Agent at Scale](/images/4-Event/Event4/session2-voice-agent-at-scale.jpg?featherlight=false&width=60pc)
