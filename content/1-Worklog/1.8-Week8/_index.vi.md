---
title: "Worklog Tuần 8"
date: 2026-11-09
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu Tuần 8:

* Hiểu Mô hình Trách nhiệm Chia sẻ và cách phân quyền bằng IAM Role, JSON Policy.
* Biết cách mã hóa dữ liệu với AWS KMS và lưu trữ mật khẩu bằng Secrets Manager.
* Thiết lập giám sát qua CloudWatch, CloudTrail và truy cập EC2 an toàn bằng SSM Session Manager.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu **AWS Shared Responsibility Model** và **AWS IAM**: <br>&emsp; + Cách đọc và viết IAM Policy định dạng JSON <br>&emsp; + Sử dụng IAM Role cho dịch vụ thay vì lưu cứng Access Key | 09/11/2026 | 09/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 3 | - Tìm hiểu **AWS KMS** và **AWS Secrets Manager**: <br>&emsp; + Mã hóa dữ liệu trên EBS/S3/RDS bằng KMS Key <br>&emsp; + Lưu trữ chuỗi kết nối DB trên Secrets Manager và Parameter Store | 10/11/2026 | 10/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 4 | - Tìm hiểu giám sát & quản trị máy chủ: <br>&emsp; + **Amazon CloudWatch** (Logs, Metrics, Alarms) và **AWS CloudTrail** (lịch sử gọi API) <br>&emsp; + **SSM Session Manager** (kết nối vào EC2 không cần mở port 22 hay dùng file `.pem`) | 11/11/2026 | 11/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 5 | - **Thực hành IAM Role & Secrets Manager:** <br>&emsp; + Gắn IAM Role cho EC2 để truy cập S3 và lấy mật khẩu DB từ Secrets Manager <br>&emsp; + Kiểm tra truy cập từ EC2 mà không cần chạy `aws configure` | 12/11/2026 | 12/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 6 | - **Thực hành CloudWatch & SSM Session Manager:** <br>&emsp; + Tạo CloudWatch Alarm gửi thông báo qua email khi CPU vượt ngưỡng <br>&emsp; + Truy cập vào EC2 trong Private Subnet bằng SSM Session Manager và xem log trên CloudTrail | 13/11/2026 | 13/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Kết quả đạt được trong Tuần 8:

* Biết cách dùng IAM Role và Secrets Manager để không phải hardcode thông tin đăng nhập trong code.
* Kết nối được vào EC2 nội bộ thông qua SSM Session Manager mà không cần mở cổng SSH công khai.
* Thiết lập được giám sát log, cảnh báo trên CloudWatch và kiểm tra lịch sử thao tác trên CloudTrail.
