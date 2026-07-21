---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---



### Mục tiêu tuần 3:

* Tìm hiểu và thực hành lưu trữ đối tượng với Amazon S3 và lưu trữ khối với Amazon EBS.
* Triển khai Static Website Hosting trên S3 và quản lý phiên bản dữ liệu với S3 Versioning.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2   | - Xem video hướng dẫn S3 & EBS trên FCJ Bootcamp <br> - Tìm hiểu Amazon S3: Bucket, Object, Storage Class, Lifecycle Policy <br> - Tìm hiểu Amazon EBS: Volume types (gp2, gp3, io1), Snapshot, Lifecycle Manager | 04/05/2026 | 04/05/2026 | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - **Thực hành S3 cơ bản:** <br>&emsp; + Tạo S3 Bucket với tên bucket duy nhất toàn cầu <br>&emsp; + Upload file và thư mục lên S3 <br>&emsp; + Cấu hình Bucket Policy cho phép public read <br>&emsp; + Thiết lập Object-level permissions qua ACL | 05/05/2026 | 05/05/2026 | <https://000057.awsstudygroup.com> |
| 4   | - **Thực hành S3 nâng cao:** <br>&emsp; + Cấu hình Static Website Hosting: chọn index.html và error.html <br>&emsp; + Bật S3 Versioning và kiểm tra lịch sử phiên bản <br>&emsp; + Cấu hình S3 Lifecycle Rule tự động chuyển sang Glacier sau 30 ngày <br>&emsp; + Kiểm tra truy cập website qua endpoint S3 | 06/05/2026 | 06/05/2026 | <https://000057.awsstudygroup.com> |
| 5   | - **Thực hành EBS:** <br>&emsp; + Tạo EBS Volume (gp3, 10GB) trong cùng AZ với EC2 <br>&emsp; + Gắn (attach) EBS Volume vào EC2 instance <br>&emsp; + Format và mount Volume vào hệ thống file Linux <br>&emsp; + Tạo Snapshot từ EBS và khôi phục Volume từ Snapshot | 07/05/2026 | 07/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tham gia sự kiện Event (Ngày 09/05) | 09/05/2026 | 09/05/2026 |                                           |


### Kết quả đạt được tuần 3:

* Hiểu rõ sự khác biệt giữa S3 (object storage) và EBS (block storage).
* Triển khai thành công Static Website Hosting trên S3.
* Cấu hình S3 Versioning và Lifecycle Policy quản lý vòng đời dữ liệu.
* Tạo và gắn EBS Volume vào EC2, thực hành tạo và khôi phục từ Snapshot.
* Tham gia sự kiện Event ngày 09/05.

