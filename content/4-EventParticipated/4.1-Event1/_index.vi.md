---
title: "Event: 1"
date: 2026-05-09
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài Thu Hoạch: "AWS First Cloud AI Journey – FCAJ Community Day"

### Mục Đích Của Sự Kiện

- **Khám phá phương pháp "trò chơi hóa" (gamification)** để tạo động lực và duy trì thói quen học tập công nghệ một cách bền bỉ.
- **Nắm bắt các kỹ thuật Prompt Engineering** từ nền tảng đến nâng cao nhằm khai thác tối đa sức mạnh của các mô hình ngôn ngữ lớn (LLM).
- **Nghiên cứu mô hình kiến trúc serverless** trên nền tảng AWS thông qua dự án thực tế và bài toán tối ưu chi phí hạ tầng.
- **Tiếp cận phương pháp BMAD** – đưa quy trình phát triển Agile và đội ngũ AI Agents vào trực tiếp môi trường IDE để chuẩn hóa việc làm phần mềm.

---

### Danh Sách Diễn Giả

- Diễn giả: **Huynh Hoang Long** – Admin of FCAJ
- Diễn giả: **Nguyen Tuan Thinh** – DevOps/Cloud Engineer, First Cloud AI Journey
- Diễn giả: **Khang**
- Diễn giả: **Thao Nguyen** – GenAI Engineer, VIB

---

### Nội Dung Nổi Bật

#### 1. Gamification: Xây Dựng Hệ Thống Học Tập Tự Động

*Diễn giả: Huynh Hoang Long – Admin of FCAJ*

Cốt lõi: Áp dụng cơ chế tiết sinh Dopamine của mạng xã hội vào việc học. Thay vì nhồi nhét, hãy tạo ra một "vòng lặp phần thưởng" để đánh lừa bộ não.

Kỹ thuật áp dụng:

- **Kích hoạt tâm lý "sợ mất mát"** bằng cách duy trì chuỗi ngày hoạt động liên tục (Streak).
- **Vượt qua sự trì hoãn ban đầu** bằng Quy tắc 2 phút (chia thật nhỏ mục tiêu để dễ bắt đầu).
- **Thiết lập phần thưởng ngay lập tức** sau những mốc hoàn thành nhỏ để tạo sự thỏa mãn tức thì.

---

#### 2. Làm Chủ Chất Lượng LLM với Kỹ Thuật Prompt Tự Động

*Diễn giả: Nguyen Tuan Thinh – DevOps/Cloud Engineer, First Cloud AI Journey*

Cốt lõi: Viết prompt có cấu trúc chặt chẽ không chỉ tăng độ chính xác của đầu ra mà còn giải quyết bài toán kinh tế (Token Economics).

- **Kỹ năng nâng cao:** Sử dụng các luồng suy luận phức tạp như Chain-of-Thought (CoT) hay phân nhánh Tree of Thoughts (ToT).
- **Kiến trúc thực tiễn:** Giới thiệu cấu trúc hệ thống của tiện ích mở rộng **Promtimizer**, hoạt động hoàn toàn dựa trên các dịch vụ AWS:
  - Amazon S3 & CloudFront cho frontend.
  - Xác thực qua Cognito.
  - API Gateway & AWS Lambda để xử lý logic serverless.
  - Tương tác AI qua Amazon Bedrock và lưu trữ dữ liệu tại DynamoDB.

---

#### 3. Định Hình Tư Duy Cốt Lõi trong Kỷ Nguyên AI

*Diễn giả: Khang*

Cốt lõi: Nhìn nhận AI như một công cụ khuếch đại năng lực (hệ số nhân), chứ không phải vật thay thế cho sự hiểu biết sâu sắc của con người.

- **Mindset thiết yếu:** Đề cao sự chính trực (Integrity) và tinh thần học hỏi không ngừng. Luôn đào sâu tìm hiểu bản chất ("Tại sao?") thay vì lạm dụng AI để đi đường tắt.
- **Phát triển sự nghiệp:** Hướng tới một công việc cân bằng giữa đam mê, quyền lợi và trách nhiệm. Bắt đầu từ những mục tiêu nhỏ gọn nhưng phải mang một tầm nhìn dài hạn, đồng thời luôn trân trọng sức mạnh của việc làm việc nhóm.

---

#### 4. BMAD Method: Cuộc Cách Mạng Context Engineering trong IDE

*Diễn giả: Thao Nguyen – GenAI Engineer, VIB*

Cốt lõi: Thay thế thói quen "Vibe Coding" (nhồi nhét mọi thứ vào một khung chat gây quá tải ngữ cảnh) bằng tư duy **Context Engineering** có thiết kế hệ thống rõ ràng.

Quy trình vận hành:

- **Sharding:** Cắt nhỏ tài liệu PRD và kiến trúc thành các "Index Chunks" siêu gọn. AI chỉ load đúng ngữ cảnh cần thiết để làm việc, giúp tránh hiện tượng ảo giác.
- **Chuyển đổi sang mô hình Agile** với các AI Agent chuyên biệt (PM, PO, Dev, Reviewer) thực thi từng Story nhỏ, chạy vòng lặp kiểm thử liên tục ngay trong IDE.

---

### Những Gì Học Được

Buổi sự kiện mang lại hai bài học lớn. Thứ nhất là cách vượt qua sức ỳ của bản thân bằng thủ thuật tự thưởng và chia nhỏ mục tiêu, giúp việc thu nạp kiến thức trở nên hấp dẫn như khi chơi game thay vì cảm thấy áp lực. Thứ hai là sự mở mang về quy trình làm việc chuyên nghiệp với AI thông qua phương pháp BMAD, giúp hiểu rằng việc dùng AI hiệu quả đòi hỏi một chiến lược phân mảnh và quản lý ngữ cảnh hệ thống một cách có kỷ luật.

---

### Ứng Dụng Vào Công Việc

Về mặt thực tiễn, sẽ áp dụng ngay cơ chế "trò chơi hóa" của anh Long để duy trì nhịp độ làm việc mỗi ngày. Riêng với phương pháp BMAD, đây là chìa khóa cực kỳ phù hợp cho quá trình xây dựng các ứng dụng web. Thay vì ném toàn bộ mã nguồn vào khung chat AI, sẽ chia nhỏ các module như xử lý logic với Node.js, Express hay định nghĩa schema cho MongoDB thành những ngữ cảnh hoàn toàn độc lập. Ngay cả khi thiết kế các dịch vụ backend phức tạp bằng Spring Boot và tiến hành viết kịch bản kiểm thử tự động với Postman hay Playwright, việc quản lý tài liệu theo cấu trúc sharding sẽ giúp AI sinh ra đoạn code hoặc test case chính xác hơn, rút ngắn đáng kể thời gian phát triển dự án.

---

### Trải Nghiệm Trong Event

#### Một Số Hình Ảnh Khi Tham Gia Sự Kiện

*Thêm các hình ảnh của bạn tại đây*

Ban đầu bước vào một sự kiện cộng đồng đông đúc khiến khá rụt rè và e ngại. Tuy nhiên, bầu không khí cởi mở và những chia sẻ tâm huyết, thực tế từ các anh chị diễn giả đã hoàn toàn gạt bỏ sự lo lắng đó. Việc đến tận nơi, lắng nghe trực tiếp mang lại cảm hứng và giá trị lớn hơn rất nhiều so với việc chỉ đọc tài liệu ở nhà. Đây chắc chắn là động lực để tự tin tham gia, học hỏi và tương tác nhiều hơn trong các sự kiện công nghệ sắp tới.
