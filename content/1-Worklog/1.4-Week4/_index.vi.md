---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---



### Mục tiêu tuần 4:

* Học và thực hành tự động mở rộng hệ thống với EC2 Auto Scaling và Elastic Load Balancer.
* Cấu hình phân phối nội dung toàn cầu với Amazon CloudFront.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Xem video hướng dẫn Auto Scaling & ELB trên FCJ Bootcamp <br> - Tìm hiểu EC2 Auto Scaling: Launch Template, Scaling Policy (Target Tracking, Step Scaling) <br> - Tìm hiểu Elastic Load Balancer: ALB vs NLB, Target Group, Health Check | 11/05/2026 | 11/05/2026 | <https://000006.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - **Thực hành Auto Scaling:** <br>&emsp; + Tạo Launch Template với AMI và Security Group <br>&emsp; + Tạo Auto Scaling Group với Min=1, Max=3, Desired=1 <br>&emsp; + Cấu hình Target Tracking Policy dựa trên CPU Utilization (70%) <br>&emsp; + Gắn Application Load Balancer vào Auto Scaling Group <br>&emsp; + Mô phỏng tải cao để kiểm tra tự động mở rộng | 12/05/2026 | 12/05/2026 | <https://000006.awsstudygroup.com> |
| 4   | - Xem video hướng dẫn CloudFront trên FCJ Bootcamp <br> - Tìm hiểu Amazon CloudFront: Distribution, Origin, Cache Behavior, TTL, Invalidation <br> - Tìm hiểu tích hợp CloudFront với S3 và WAF | 13/05/2026 | 13/05/2026 | <https://000094.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - **Thực hành CloudFront:** <br>&emsp; + Tạo CloudFront Distribution với Origin là S3 Bucket <br>&emsp; + Cấu hình Origin Access Control (OAC) để bảo mật S3 <br>&emsp; + Bật HTTPS và cấu hình SSL Certificate <br>&emsp; + Tạo Cache Invalidation để làm mới nội dung <br>&emsp; + Kiểm tra tốc độ truy cập qua CloudFront so với trực tiếp S3 | 14/05/2026 | 15/05/2026 | <https://000094.awsstudygroup.com> |
| 6   | - Ôn tập và tổng hợp kiến thức tuần 4 | 16/05/2026 | 16/05/2026 |                                           |


### Kết quả đạt được tuần 4:

* Triển khai Auto Scaling Group với ALB, hệ thống tự động mở rộng khi tải tăng.
* Cấu hình CloudFront Distribution kết nối với S3, phân phối nội dung toàn cầu với HTTPS.
* Hiểu cơ chế Cache và Invalidation trong CloudFront.
* So sánh được hiệu năng trước/sau khi dùng CloudFront.

