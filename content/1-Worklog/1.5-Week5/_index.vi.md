---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---



### Mục tiêu tuần 5:

* Học và thực hành cơ sở dữ liệu quan hệ với Amazon RDS và NoSQL với Amazon DynamoDB.
* Cấu hình bộ nhớ đệm với Amazon ElastiCache để tăng hiệu năng ứng dụng.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Xem video hướng dẫn RDS trên FCJ Bootcamp <br> - Tìm hiểu Amazon RDS: Engine types (MySQL, PostgreSQL, Aurora), Multi-AZ, Read Replica, Automated Backup <br> - **Thực hành:** <br>&emsp; + Tạo RDS MySQL instance trong Private Subnet <br>&emsp; + Cấu hình Security Group chỉ cho phép EC2 kết nối vào RDS <br>&emsp; + Kết nối MySQL Workbench từ EC2 vào RDS <br>&emsp; + Tạo database, table và thực hiện các câu lệnh SQL cơ bản | 18/05/2026 | 18/05/2026 | <https://000005.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - Xem video hướng dẫn DynamoDB trên FCJ Bootcamp <br> - Tìm hiểu DynamoDB: Table, Item, Partition Key, Sort Key, GSI, LSI <br> - **Thực hành:** <br>&emsp; + Tạo DynamoDB Table với Partition Key và Sort Key <br>&emsp; + Thực hiện CRUD: PutItem, GetItem, UpdateItem, DeleteItem <br>&emsp; + Tạo GSI và truy vấn dữ liệu qua Index <br>&emsp; + So sánh scan vs query về hiệu năng | 19/05/2026 | 19/05/2026 | <https://000005.awsstudygroup.com> <br> <https://000060.awsstudygroup.com> <br> <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 4   | - Tìm hiểu Amazon ElastiCache: Redis vs Memcached, use cases <br> - **Thực hành ElastiCache:** <br>&emsp; + Tạo ElastiCache Redis cluster <br>&emsp; + Kết nối ứng dụng đến Redis <br>&emsp; + Cache kết quả truy vấn database và đo thời gian phản hồi | 20/05/2026 | 21/05/2026 | <https://000060.awsstudygroup.com> |
| 6   | - Ôn tập và so sánh các loại database trên AWS: RDS vs DynamoDB vs ElastiCache | 22/05/2026 | 22/05/2026 | <https://000061.awsstudygroup.com> |


### Kết quả đạt được tuần 5:

* Triển khai RDS MySQL trong Private Subnet, kết nối và thao tác SQL thành công.
* Thực hành đầy đủ CRUD trên DynamoDB với GSI và hiểu hiệu năng scan vs query.
* Cấu hình ElastiCache Redis để cache kết quả database, giảm thời gian phản hồi.
* Hiểu rõ khi nào dùng RDS, DynamoDB hay ElastiCache.

