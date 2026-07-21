---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---



### Mục tiêu tuần 2:

* Tìm hiểu và thực hành triển khai máy chủ ảo Amazon EC2.
* Cấp quyền cho ứng dụng chạy trên EC2 bằng IAM Roles.
* Quản lý DNS lai với Amazon Route 53 và thực hành Networking Workshop.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Xem video hướng dẫn EC2 trên FCJ Bootcamp <br> - Tìm hiểu lý thuyết EC2: Instance types, AMI, key pair, EBS volume <br> - Thực hành: <br>&emsp; + Tạo EC2 instance (Amazon Linux 2) <br>&emsp; + Cấu hình Security Group mở port 22 (SSH) và 80 (HTTP) <br>&emsp; + Kết nối SSH vào EC2 từ máy local <br>&emsp; + Cài đặt Apache Web Server và kiểm tra trên trình duyệt | 27/04/2026 | 27/04/2026 | <https://000004.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Xem video IAM Roles for EC2 trên FCJ Bootcamp <br> - Tìm hiểu sự khác biệt giữa IAM User và IAM Role <br> - Thực hành: <br>&emsp; + Tạo IAM Role với quyền AmazonS3ReadOnlyAccess <br>&emsp; + Gắn Role vào EC2 instance <br>&emsp; + Kiểm tra quyền truy cập S3 từ EC2 bằng AWS CLI <br>&emsp; + So sánh trước và sau khi gắn Role | 28/04/2026 | 28/04/2026 | <https://000048.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Xem video Route 53 & Hybrid DNS trên FCJ Bootcamp <br> - Tìm hiểu Amazon Route 53: Hosted Zone, Record types (A, CNAME, Alias) <br> - Thực hành: <br>&emsp; + Tạo Public Hosted Zone <br>&emsp; + Tạo A Record trỏ về EC2 instance <br>&emsp; + Cấu hình Routing Policy (Simple, Weighted) | 29/04/2026 | 29/04/2026 | <https://000010.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - **Thực hành Networking on AWS Workshop:** <br>&emsp; + Cấu hình VPC Peering giữa 2 VPC <br>&emsp; + Thiết lập Transit Gateway kết nối nhiều VPC <br>&emsp; + Kiểm tra kết nối giữa các VPC sau khi cấu hình | 30/04/2026 | 02/05/2026 | <https://000092.awsstudygroup.com> |
| 7   | - Ôn tập và tổng hợp kiến thức tuần 2 | 03/05/2026 | 03/05/2026 |                                           |


### Kết quả đạt được tuần 2:

* Triển khai EC2 instance thành công, kết nối SSH và cài Web Server.
* Cấu hình IAM Role gắn vào EC2 để cấp quyền truy cập S3 an toàn.
* Hiểu và thực hành Route 53: tạo Hosted Zone và cấu hình DNS Record.
* Hoàn thành VPC Peering và Transit Gateway trong Networking Workshop.

