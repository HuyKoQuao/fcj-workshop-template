---
title: "Worklog Tuần 6"
date: 2026-10-26
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu Tuần 6:

* Nắm vững các tính năng cốt lõi của Amazon S3 (Storage Classes, Versioning, Lifecycle, Bucket Policy).
* Phân biệt khi nào dùng S3, EBS và EFS.
* Thực hành kết nối lưu trữ nội bộ lên S3 thông qua AWS Storage Gateway.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu **Amazon S3**: <br>&emsp; + Bucket, Object, Versioning và mã hóa (SSE-S3, SSE-KMS) <br>&emsp; + Các lớp lưu trữ (Standard, IA, Intelligent-Tiering, Glacier) và Lifecycle Rules | 26/10/2026 | 26/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 3 | - Tìm hiểu bảo mật S3 & **Amazon EFS**: <br>&emsp; + Bucket Policy, Block Public Access và Presigned URL <br>&emsp; + So sánh S3, EBS và EFS (chia sẻ file cho nhiều EC2 cùng lúc) | 27/10/2026 | 27/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 4 | - Tìm hiểu **AWS Storage Gateway**: <br>&emsp; + Phân biệt File Gateway, Volume Gateway và Tape Gateway <br>&emsp; + Cách đồng bộ file từ máy chủ nội bộ lên S3 | 28/10/2026 | 28/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 5 | - **Thực hành Amazon S3:** <br>&emsp; + Tạo bucket, bật Versioning, cài đặt Lifecycle Rule chuyển file sang Glacier <br>&emsp; + Test host static website trên S3 và tạo Presigned URL | 29/10/2026 | 29/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 6 | - **Thực hành Storage Gateway:** <br>&emsp; + Khởi tạo File Gateway, tạo SMB/NFS File Share nối với S3 bucket <br>&emsp; + Mount ổ đĩa mạng lên máy client, copy file và kiểm tra đồng bộ trên S3 | 30/10/2026 | 30/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Kết quả đạt được trong Tuần 6:

* Biết cách cấu hình S3 an toàn, quản lý phiên bản file và tự động chuyển lớp lưu trữ để giảm chi phí.
* Hoàn thành bài lab AWS Storage Gateway kết nối chia sẻ file từ client lên S3.
* Phân biệt rõ ưu nhược điểm của S3, EBS và EFS cho từng loại dữ liệu.
