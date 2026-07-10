---
title : "Kiểm thử End-to-End"
date : 2026-07-10
weight : 12
chapter : false
pre : " <b> 5.12. </b> "
---

#### Chạy kiểm thử End-to-End toàn hệ thống

Trong phần này, bạn sẽ kích hoạt một lần chạy kiểm thử đầy đủ thông qua Dashboard UI hoặc API Gateway để xác minh toàn bộ luồng hệ thống — từ tiếp nhận yêu cầu qua SQS, ECS Fargate thực thi kiểm thử, lưu báo cáo lên S3, phân tích AI cho đến gửi thông báo email qua SES — hoạt động chính xác và đồng bộ.

{{% notice note %}}
Nội dung phần này sẽ được cập nhật. Hãy đảm bảo tất cả các phần trước (5.2 đến 5.11) đã hoàn tất trước khi chạy kiểm thử end-to-end.
{{% /notice %}}

---

Tiếp theo, chúng ta sẽ chuyển sang **[5.13. Dọn dẹp tài nguyên](../5.13-cleanup/)** để xóa tất cả tài nguyên đã tạo trong workshop này.
