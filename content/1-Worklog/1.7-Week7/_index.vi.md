---
title: "Worklog Tuần 7"
date: 2026-11-02
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu Tuần 7:

* Hiểu cách vận hành cơ sở dữ liệu quan hệ trên AWS với Amazon RDS và Amazon Aurora.
* Phân biệt RDS Multi-AZ và Read Replicas.
* Nắm cơ bản về cơ sở dữ liệu NoSQL Amazon DynamoDB và thực hành RDS Failover.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu **Amazon RDS**: <br>&emsp; + Các engine hỗ trợ (MySQL, PostgreSQL) và DB Subnet Group <br>&emsp; + Automated Backups, Snapshots và Point-in-Time Recovery | 02/11/2026 | 02/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 3 | - Tìm hiểu kiến trúc mở rộng CSDL: <br>&emsp; + So sánh **RDS Multi-AZ** (dự phòng HA) và **Read Replicas** (tăng tải đọc) <br>&emsp; + Tổng quan về kiến trúc **Amazon Aurora** | 03/11/2026 | 03/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 4 | - Tìm hiểu **Amazon DynamoDB** & **ElastiCache**: <br>&emsp; + Khái niệm Table, Item, Partition Key, Sort Key và chế độ On-Demand <br>&emsp; + Tổng quan ElastiCache (Redis/Memcached) | 04/11/2026 | 04/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 5 | - **Thực hành Amazon RDS:** <br>&emsp; + Tạo DB Subnet Group và khởi tạo RDS MySQL chế độ Multi-AZ trong Private Subnet <br>&emsp; + Cấu hình Security Group chỉ mở cổng 3306 cho EC2 app server | 05/11/2026 | 05/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 6 | - **Thực hành Kết nối & Failover:** <br>&emsp; + Kết nối ứng dụng từ EC2 vào RDS và tạo bảng/dữ liệu thử nghiệm <br>&emsp; + Chạy thử tính năng "Reboot with Failover" trên RDS để kiểm tra chuyển đổi sang máy dự phòng | 06/11/2026 | 06/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Kết quả đạt được trong Tuần 7:

* Triển khai được RDS MySQL Multi-AZ nằm cô lập trong Private Subnet và kết nối thành công từ EC2.
* Kiểm chứng trực tiếp cơ chế tự động failover của RDS khi máy chủ chính gặp sự cố.
* Nắm được cấu trúc lưu trữ key-value/document của DynamoDB để áp dụng cho các hệ thống serverless.
