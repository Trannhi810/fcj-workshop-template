---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---



### Mục tiêu tuần 12:

* Khắc phục triệt để các lỗi hệ thống (Lambda, API Gateway, DynamoDB).
* Kiểm thử toàn diện hệ thống và luồng tự động.
* Cập nhật workshop template và hoàn thành báo cáo thực tập.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Rà soát log trên CloudWatch. Phát hiện và xử lý các vấn đề: Lambda thiếu bảng DynamoDB, thiếu biến môi trường. <br> - Bổ sung 2 bảng DynamoDB mới và fix các lỗi core liên quan đến xử lý dữ liệu, quyền truy cập IAM. | 06/07/2026 | 07/07/2026 | docs.aws.amazon.com (API Gateway CORS) |
| 3 | - Khắc phục các lỗi tích hợp API Gateway (CORS, thiếu route, authorizer) và lỗi đăng nhập Developer. <br> - Viết kịch bản kiểm thử (Test cases) cho các chức năng chính. <br> - Tiến hành kiểm thử (testing) toàn bộ hệ thống: <br>&emsp; + Unit Test cho các hàm xử lý logic <br>&emsp; + Integration Test giữa API Gateway, Lambda và DynamoDB <br>&emsp; + End-to-End (E2E) Testing mô phỏng người dùng thực tế | 08/07/2026 | 09/07/2026 | docs.aws.amazon.com (API Gateway CORS) |
| 4 | - Sửa dứt điểm luồng kiểm thử thủ công và tự động. <br> - Chạy thử toàn hệ thống thấy kết quả đúng và email báo cáo gửi thành công. | 10/07/2026 | 10/07/2026 | docs.aws.amazon.com (API Gateway CORS) |
| 5 | - Cập nhật lại hướng dẫn trong Workshop Template. <br> - Tổng hợp số liệu và hoàn thành viết tài liệu báo cáo triển khai thực tập. | 11/07/2026 | 11/07/2026 | |

### Kết quả đạt được tuần 12:

* Hoàn thành fix lỗi hệ thống và API Gateway, Lambda, DynamoDB.
* Hệ thống đã được kiểm thử toàn diện và vận hành ổn định.
* Cập nhật xong workshop template.
* Hoàn thành viết báo cáo thực tập và sẵn sàng bảo vệ đề tài.

