---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---



### Mục tiêu tuần 8:

* Học và thực hành Container Services: Docker, Amazon ECS với Fargate và Amazon EKS.
* Chốt kiến trúc và phân chia công việc cho project thực tập.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Xem video Docker & Container trên FCJ Bootcamp <br> - Tìm hiểu Docker: Image, Container, Dockerfile, Docker Hub, Docker Compose <br> - **Thực hành:** <br>&emsp; + Viết Dockerfile cho ứng dụng Node.js/Python <br>&emsp; + Build Docker image và chạy container local <br>&emsp; + Push image lên Amazon ECR (Elastic Container Registry) | 08/06/2026 | 08/06/2026 | <https://000015.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Xem video Amazon ECS trên FCJ Bootcamp <br> - Tìm hiểu Amazon ECS: Task Definition, Service, Cluster, Fargate vs EC2 Launch Type <br> - **Thực hành:** <br>&emsp; + Tạo ECS Cluster (Fargate) <br>&emsp; + Viết Task Definition với container image từ ECR <br>&emsp; + Tạo ECS Service và chạy Task <br>&emsp; + Cấu hình ALB để route traffic vào ECS Service | 09/06/2026 | 09/06/2026 | [Container Orchestration with Amazon ECS](https://000016.awsstudygroup.com) <br> [Containerization with Amazon ECS and AWS Fargate](https://000067.awsstudygroup.com) <br> [FCJ Bootcamp Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i) |
| 4   | - Xem video Amazon EKS trên FCJ Bootcamp <br> - Tìm hiểu Amazon EKS: Node Group, Pod, Deployment, Service, Ingress <br> - **Thực hành:** <br>&emsp; + Tạo EKS Cluster bằng eksctl <br>&emsp; + Deploy ứng dụng bằng kubectl apply <br>&emsp; + Tạo Kubernetes Service (LoadBalancer) <br>&emsp; + Kiểm tra Pod logs và scaling | 10/06/2026 | 11/06/2026 | <https://000016.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 5   | - Chốt ý tưởng, thiết kế kiến trúc AWS chi tiết cho project thực tập <br> - Phân chia module và lên kế hoạch triển khai | 12/06/2026 | 13/06/2026 | <https://cloudjourney.awsstudygroup.com/> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |


### Kết quả đạt được tuần 8:

* Đóng gói ứng dụng bằng Docker, push image lên ECR thành công.
* Deploy ứng dụng lên ECS Fargate với ALB, chạy ổn định.
* Hiểu cơ bản về EKS và triển khai ứng dụng bằng kubectl.
* Đã chốt kiến trúc AWS và phân chia module cho project thực tập.

