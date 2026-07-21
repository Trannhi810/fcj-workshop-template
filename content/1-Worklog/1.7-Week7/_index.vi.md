---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---



### Mục tiêu tuần 7:

* Thực hành quản lý mã hóa dữ liệu với AWS KMS và lưu trữ thông tin nhạy cảm với AWS Secrets Manager.
* Triển khai cổng API với Amazon API Gateway kết nối AWS Lambda.
* Lên ý tưởng cho project thực tập.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Xem video KMS trên FCJ Bootcamp <br> - Tìm hiểu AWS KMS: Customer Managed Key (CMK), Key Policy, Key Rotation <br> - **Thực hành:** <br>&emsp; + Tạo CMK symmetric key <br>&emsp; + Mã hóa/giải mã dữ liệu bằng KMS CLI (encrypt/decrypt) <br>&emsp; + Bật mã hóa Server-Side Encryption cho S3 Bucket bằng KMS | 01/06/2026 | 01/06/2026 | <https://000033.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Xem video Secrets Manager trên FCJ Bootcamp <br> - Tìm hiểu AWS Secrets Manager: Secret types, Automatic Rotation, Version <br> - **Thực hành:** <br>&emsp; + Tạo Secret lưu trữ thông tin kết nối RDS (username, password) <br>&emsp; + Cấu hình Automatic Rotation 30 ngày <br>&emsp; + Truy xuất Secret trong Lambda function bằng SDK <br>&emsp; + So sánh Secrets Manager vs Parameter Store | 02/06/2026 | 02/06/2026 | <https://000096.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Xem video API Gateway & Lambda trên FCJ Bootcamp <br> - Tìm hiểu Amazon API Gateway: REST API, HTTP API, WebSocket, Stage, Deployment <br> - **Thực hành:** <br>&emsp; + Tạo Lambda function (Python/Node.js) xử lý request <br>&emsp; + Tạo HTTP API trên API Gateway kết nối với Lambda <br>&emsp; + Cấu hình CORS cho phép Frontend gọi API <br>&emsp; + Deploy API lên Stage và test bằng Postman | 03/06/2026 | 04/06/2026 | <https://cloudjourney.awsstudygroup.com/> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | - Tham gia sự kiện Event (Ngày 06/06) <br> - Thảo luận và lên ý tưởng cho project thực tập với nhóm | 05/06/2026 | 06/06/2026 |                                           |


### Kết quả đạt được tuần 7:

* Tạo KMS Key và mã hóa dữ liệu S3 với SSE-KMS thành công.
* Lưu trữ và truy xuất thông tin nhạy cảm an toàn qua Secrets Manager trong Lambda.
* Triển khai HTTP API Gateway kết nối Lambda, test API thành công bằng Postman.
* Tham gia sự kiện Event ngày 06/06 và đề xuất được ý tưởng project.

