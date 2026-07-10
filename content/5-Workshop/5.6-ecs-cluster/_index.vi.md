---
title : "ECS Cluster & Task Definition"
date : 2026-07-10
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

#### Tạo ECS Cluster và Task Definition cho Playwright Runner

Trong phần này, bạn sẽ tạo một Amazon ECS Cluster và cấu hình Task Definition — nơi xác định Docker image nào được sử dụng, tài nguyên cấp phát bao nhiêu và IAM role nào được áp dụng khi ECS Fargate chạy các tác vụ kiểm thử Playwright.

{{% notice note %}}
Nội dung phần này sẽ được cập nhật. Hãy đảm bảo Docker image đã được push lên ECR (phần 5.5) và các IAM role `playwright-ecs-execution-role`, `playwright-ecs-task-role` đã được tạo (phần 5.2.3) trước khi tiếp tục.
{{% /notice %}}

---

Tiếp theo, chúng ta sẽ chuyển sang **[5.7. Lambda Functions](../5.7-lambda-functions/)** để triển khai lớp điều phối.
