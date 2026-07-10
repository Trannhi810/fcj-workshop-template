---
title : "Docker Image"
date : 2026-07-10
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

#### Build và Push Docker Image Playwright lên Amazon ECR

Trong phần này, bạn sẽ build một Docker image chứa môi trường kiểm thử Playwright và push lên repository Amazon ECR (`playwright-runner`) đã tạo ở phần 5.2.5.

{{% notice note %}}
Nội dung phần này sẽ được cập nhật. Vui lòng tham khảo phần thiết lập ECR repository tại **[5.2.5. Tạo ECR](../5.2-Prerequisite/5.2.5-create-ecr/)** để xem các lệnh push image cần thiết.
{{% /notice %}}

---

Tiếp theo, chúng ta sẽ chuyển sang **[5.6. ECS Cluster & Task Definition](../5.6-ecs-cluster/)** để cấu hình môi trường chạy container cho Playwright.
