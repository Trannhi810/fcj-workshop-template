---
title: "Sự kiện: 3"
date: 2026-06-06
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Bài Thu Hoạch: "Meetup Cộng Đồng AWS Study Group – Tháng 6/2026"

### Mục Đích Của Sự Kiện

Buổi **Meetup AWS Study Group** (ngày 06/06/2026) được tổ chức với các mục tiêu:

- **Chia sẻ kiến thức thực chiến** từ các thành viên cộng đồng về các công nghệ Cloud, DevOps và bảo mật đang được ứng dụng thực tế.
- **Giới thiệu Docker** như một công nghệ container hóa nền tảng cho các kỹ sư Cloud và DevOps.
- **Trình bày giải pháp bảo mật** kết hợp AWS WAF với Machine Learning để phát hiện tấn công mạng.
- **Khám phá khả năng multiplayer gaming** trên nền tảng AWS thông qua WebSocket và Godot Engine.
- **Chia sẻ định hướng nghề nghiệp** từ IT Helpdesk lên Senior Sysadmin và lộ trình chuyển dịch sang Cloud/DevOps.
- **Giới thiệu AWS Neptune** cho bài toán xây dựng Knowledge Graph phục vụ GraphRAG.
- **Thảo luận phương pháp làm việc nhóm** hiệu quả trong môi trường kỹ thuật.

---

### Danh Sách Diễn Giả

Buổi meetup có **6 diễn giả** chia sẻ về các chủ đề khác nhau:

1. **Bảo Huỳnh** — Docker – Công nghệ Container Hóa
2. **Lê Hoàng Gia Đại** — Kết hợp AWS WAF với Machine Learning để phát hiện tấn công mạng trên AWS
3. **Nguyễn Quốc Bảo** — Multiplayer trong Cloud: Kết nối Godot Client với AWS WebSocket
4. **Trương Phước (Huy Phước)** — Cách làm việc nhóm hiệu quả
5. **Việt Phát** — AWS Neptune cho bài toán xây dựng Graph Knowledge Base phục vụ GraphRAG
6. **Vinh Trần** — Từ IT Helpdesk lên Senior Sysadmin: Hành trình tự học và lộ trình chuyển sang Cloud/DevOps

---

### Nội Dung Nổi Bật

#### Bài 1 – Docker: Công Nghệ Container Hóa

*Diễn giả: Bảo Huỳnh*

Docker là nền tảng container hóa giúp đóng gói ứng dụng và toàn bộ môi trường phụ thuộc của nó vào một đơn vị thống nhất (container), đảm bảo ứng dụng chạy nhất quán trên mọi môi trường:

- **Container vs. Virtual Machine:** Container chia sẻ kernel của hệ điều hành host, tiêu tốn ít tài nguyên hơn VM truyền thống trong khi vẫn đảm bảo tính cô lập (isolation).
- **Dockerfile & Image:** Quy trình xây dựng image từ Dockerfile — mỗi lệnh tạo ra một layer, giúp tái sử dụng và cache hiệu quả khi build.
- **Docker Compose:** Quản lý nhiều container cùng lúc (ứng dụng multi-service) bằng file cấu hình YAML đơn giản.
- **Ứng dụng thực tế trong DevOps:** Docker là nền tảng không thể thiếu trong các pipeline CI/CD hiện đại và là bước đệm trước khi tiến lên Kubernetes (K8s) cho môi trường production quy mô lớn.

---

#### Bài 2 – Kết Hợp AWS WAF với Machine Learning để Phát Hiện Tấn Công Mạng

*Diễn giả: Lê Hoàng Gia Đại*

Bài trình bày giới thiệu kiến trúc hệ thống phát hiện xâm nhập mạng (NIDS) thông minh trên nền tảng AWS:

- **Thách thức của WAF truyền thống:** AWS WAF dựa trên rule-based (dựa trên quy tắc cố định) hiệu quả nhưng dễ bỏ sót các tấn công mới (zero-day) chưa có trong danh sách rule.
- **Giải pháp ML-NIDS:** Tích hợp mô hình Machine Learning để phân tích traffic theo thời gian thực, nhận diện các mẫu hành vi bất thường mà rule tĩnh không thể phát hiện.
- **Luồng dữ liệu:** Traffic → AWS WAF → Log → ML Model (phân loại bình thường / tấn công) → Alert tự động.
- **Lợi ích:** Kết hợp sức mạnh của rule-based (nhanh, rõ ràng) với khả năng học của ML (linh hoạt, phát hiện mẫu mới), tạo lớp bảo vệ kép cho hạ tầng AWS.

---

#### Bài 3 – Multiplayer trong Cloud: Kết Nối Godot Client với AWS WebSocket

*Diễn giả: Nguyễn Quốc Bảo*

Bài trình bày khám phá cách xây dựng tính năng multiplayer cho game sử dụng hạ tầng AWS serverless:

- **Godot Engine:** Game engine mã nguồn mở, nhẹ và linh hoạt, phù hợp để xây dựng game 2D/3D.
- **AWS API Gateway WebSocket:** Cho phép thiết lập kết nối hai chiều (bi-directional) liên tục giữa client và server, khác với HTTP truyền thống chỉ theo một chiều request-response.
- **Kiến trúc serverless:** API Gateway WebSocket → AWS Lambda → DynamoDB (lưu trạng thái kết nối) — không cần quản lý server game riêng biệt, tự động mở rộng theo số lượng người chơi.
- **Demo thực tế:** Minh họa nhiều Godot client kết nối và đồng bộ trạng thái game theo thời gian thực qua WebSocket trên AWS.

---

#### Bài 4 – Cách Làm Việc Nhóm Hiệu Quả

*Diễn giả: Trương Phước (Huy Phước)*

Bài chia sẻ tập trung vào các nguyên tắc và công cụ giúp team kỹ thuật làm việc hiệu quả hơn:

- **Giao tiếp rõ ràng:** Tầm quan trọng của việc định nghĩa rõ trách nhiệm (ownership), deadline và kỳ vọng trước khi bắt đầu bất kỳ tác vụ nào.
- **Công cụ hỗ trợ:** Sử dụng các nền tảng như Jira, Confluence, Slack và GitHub để đồng bộ thông tin và theo dõi tiến độ.
- **Phương pháp Agile/Scrum:** Áp dụng sprint ngắn, daily standup và retrospective để phát hiện sớm vấn đề và liên tục cải tiến.
- **Văn hóa feedback:** Xây dựng môi trường tâm lý an toàn (psychological safety) để các thành viên dám nêu vấn đề và góp ý mang tính xây dựng.

---

#### Bài 5 – AWS Neptune cho Bài Toán Xây Dựng Graph Knowledge Base phục vụ GraphRAG

*Diễn giả: Việt Phát*

Bài trình bày chuyên sâu về việc ứng dụng Graph Database vào bài toán RAG (Retrieval-Augmented Generation) nâng cao:

- **Hạn chế của RAG truyền thống (Vector RAG):** Tìm kiếm theo độ tương đồng ngữ nghĩa (semantic similarity) không nắm bắt được mối quan hệ có cấu trúc giữa các thực thể (entity relationships).
- **GraphRAG là gì:** Thay vì lưu tài liệu dưới dạng vector, GraphRAG lưu kiến thức dưới dạng đồ thị (graph) với các node (thực thể) và edge (mối quan hệ), cho phép truy xuất thông tin theo ngữ cảnh quan hệ phức tạp.
- **AWS Neptune:** Cơ sở dữ liệu đồ thị được quản lý hoàn toàn (fully managed), hỗ trợ cả Gremlin và SPARQL, phù hợp cho Knowledge Graph quy mô lớn.
- **Ứng dụng thực tế:** Kết hợp Neptune với AWS Bedrock để xây dựng hệ thống Q&A thông minh có khả năng trả lời các câu hỏi đòi hỏi lý luận qua nhiều bước (multi-hop reasoning).

---

#### Bài 6 – Từ IT Helpdesk lên Senior Sysadmin: Hành Trình Tự Học và Lộ Trình Chuyển Sang Cloud/DevOps

*Diễn giả: Vinh Trần*

Bài chia sẻ truyền cảm hứng về hành trình phát triển nghề nghiệp trong ngành IT:

- **Xuất phát điểm:** Bắt đầu từ vị trí IT Helpdesk (hỗ trợ kỹ thuật cơ bản) và tự học để tiến lên Senior Sysadmin trong vòng vài năm.
- **Lộ trình tự học:** Kết hợp tài liệu miễn phí (AWS Free Tier, YouTube, documentation chính thức), thực hành lab và thi chứng chỉ (AWS Certifications) để xây dựng nền tảng vững chắc.
- **Chuyển dịch sang Cloud/DevOps:** Các kỹ năng Linux, networking và scripting từ thời Sysadmin là nền tảng cực kỳ có giá trị khi bước sang Cloud — không cần bắt đầu lại từ đầu.
- **Lời khuyên thực tế:** Đừng chờ "sẵn sàng hoàn toàn" mới bắt đầu — hãy xây dựng dự án thực tế (portfolio), tham gia cộng đồng (như AWS Study Group) và liên tục apply kiến thức vào thực tiễn.

---

### Những Gì Học Được

#### Kỹ Thuật và Công Nghệ

- **Container hóa là kỹ năng nền tảng:** Docker không chỉ là công cụ mà là tư duy đóng gói, tái sử dụng và cô lập môi trường — kỹ năng thiết yếu cho bất kỳ kỹ sư Cloud/DevOps nào.
- **Bảo mật cần đa lớp:** Không có giải pháp bảo mật nào hoàn hảo đơn lẻ — kết hợp rule-based (WAF) với AI/ML tạo ra hệ thống phòng thủ linh hoạt và bền vững hơn trước các mối đe dọa mới.
- **Serverless thực sự có thể thay thế game server truyền thống:** WebSocket trên AWS API Gateway + Lambda mở ra hướng tiếp cận mới, tiết kiệm chi phí cho các ứng dụng real-time quy mô nhỏ đến vừa.
- **GraphRAG vượt trội RAG truyền thống** trong các bài toán đòi hỏi lý luận quan hệ phức tạp — không phải lúc nào vector search cũng là câu trả lời tốt nhất.

#### Tư Duy Nghề Nghiệp

- **Hành trình không tuyến tính:** Không cần xuất phát từ vị trí "cao" mới có thể trở thành kỹ sư Cloud giỏi — quan trọng hơn là tư duy học hỏi liên tục và thực hành kiên định.
- **Cộng đồng là tài sản vô giá:** Tham gia các buổi meetup, chia sẻ kiến thức và học từ kinh nghiệm thực tế của người khác đẩy nhanh tốc độ phát triển nhanh hơn tự học đơn độc.
- **Làm việc nhóm là kỹ năng kỹ thuật:** Giao tiếp rõ ràng và quy trình làm việc có cấu trúc không kém phần quan trọng so với kỹ năng lập trình hay hạ tầng.

---

### Ứng Dụng Vào Công Việc

- **Thực hành Docker ngay:** Containerize một ứng dụng cá nhân hoặc dự án học tập, viết Dockerfile và thử chạy với Docker Compose để hiểu quy trình từ đầu đến cuối.
- **Lab bảo mật với AWS WAF:** Thiết lập một web app thử nghiệm trên AWS, cấu hình WAF rule cơ bản và tìm hiểu cách đọc log để phát hiện các request bất thường.
- **Khám phá WebSocket:** Xây dựng một ứng dụng chat đơn giản hoặc real-time dashboard dùng AWS API Gateway WebSocket để hiểu cơ chế kết nối hai chiều.
- **Chuẩn bị lộ trình chứng chỉ AWS:** Dựa trên chia sẻ của Vinh Trần, lập kế hoạch thi chứng chỉ AWS Cloud Practitioner hoặc AWS Solutions Architect Associate như bước khởi đầu rõ ràng và có giá trị.
- **Tìm hiểu Graph Database:** Thử nghiệm AWS Neptune hoặc Neo4j (Community Edition miễn phí) với một tập dữ liệu nhỏ để cảm nhận sự khác biệt so với database quan hệ (RDBMS) truyền thống.

---

### Trải Nghiệm Trong Event

#### Một Số Hình Ảnh Khi Tham Gia Sự Kiện

*Thêm các hình ảnh của bạn tại đây*
