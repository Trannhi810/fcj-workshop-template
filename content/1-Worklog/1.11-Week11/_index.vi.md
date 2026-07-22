---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---



### Mục tiêu tuần 11:

* Tiến hành làm giao diện (Frontend) cho project.
* Thiết lập Amazon Cognito để quản lý tài khoản và xác thực người dùng.
* Khởi tạo Amazon API Gateway và kết nối các dịch vụ AWS cho project.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Khởi tạo dự án ReactJS (sử dụng Vite hoặc Create React App) <br> - Thiết kế và lập trình giao diện người dùng (UI) cho các màn hình chính: <br>&emsp; + Trang Login/Register <br>&emsp; + Dashboard tổng quan <br>&emsp; + Trang quản lý dữ liệu (Management) | 29/06/2026   | 29/06/2026      |                                           |
| 3   | - Khởi tạo Amazon Cognito User Pool cho project <br> - Cấu hình App Client, định nghĩa các thuộc tính bắt buộc (email, password policy) <br> - Tích hợp thư viện AWS Amplify vào dự án React <br> - Code chức năng đăng ký, đăng nhập và lấy JWT Token | 30/06/2026   | 30/06/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Khởi tạo Amazon API Gateway (loại HTTP API) để làm cổng giao tiếp <br> - Tạo các Lambda function (Node.js/Python) xử lý logic backend <br> - Kết nối API Gateway với Lambda (Lambda Proxy Integration) <br> - Cấu hình CORS trên API Gateway để cho phép Frontend gọi API | 01/07/2026   | 02/07/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Tích hợp gọi API từ Frontend lên API Gateway <br> - Truyền JWT Token của Cognito vào header (Authorization) để xác thực người dùng <br> - Kiểm thử luồng dữ liệu từ UI -> API -> Lambda (Phát hiện các lỗi về CORS và logic xử lý) | 03/07/2026   | 04/07/2026      |                                           |


### Kết quả đạt được tuần 11:

* Xây dựng giao diện Frontend với các màn hình chính của ứng dụng.
* Tích hợp Amazon Cognito User Pool vào Frontend để xác thực người dùng.
* Khởi tạo và cấu hình API Gateway kết nối với các dịch vụ AWS.
* Luồng đăng nhập và gọi API cơ bản hoạt động thành công.

