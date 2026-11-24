---
title: "Worklog Tuần 4"
date: 2026-10-12
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu Tuần 4:

* Nắm vững các tùy chọn cấu hình của Amazon EC2 và ổ đĩa Amazon EBS.
* Biết cách dùng User Data, tạo Snapshot và đóng gói custom AMI.
* Triển khai được một ứng dụng web hoàn chỉnh chạy trên EC2.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu chi tiết về EC2: <br>&emsp; + Các nhóm Instance (t2/t3, m5, c5, r5) và cơ chế tính phí (On-Demand, Spot, Reserved) <br>&emsp; + Elastic IP và script tự động hóa khi khởi động (User Data) | 12/10/2026 | 12/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 3 | - Tìm hiểu lưu trữ gắn kèm EC2 (**Amazon EBS**): <br>&emsp; + Các loại volume (gp3, io2, st1) <br>&emsp; + Tạo EBS Snapshot và tạo custom AMI từ EC2 có sẵn | 13/10/2026 | 13/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 4 | - **Thực hành EC2 & EBS:** <br>&emsp; + Khởi tạo EC2 Linux và Windows, kết nối qua SSH và RDP <br>&emsp; + Tạo thêm volume EBS, attach, format và mount vào máy chủ Linux | 14/10/2026 | 14/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 5 | - **Thực hành triển khai Web Server:** <br>&emsp; + Dựng môi trường mạng và Security Group cho web server <br>&emsp; + Cài đặt web server và chạy thử ứng dụng web trên EC2 | 15/10/2026 | 15/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 6 | - **Thực hành custom AMI:** <br>&emsp; + Đóng gói ứng dụng thành custom AMI và khởi tạo lại instance mới từ AMI đó <br>&emsp; + Xóa toàn bộ tài nguyên thực hành trong tuần | 16/10/2026 | 16/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Kết quả đạt được trong Tuần 4:

* Thành thạo các thao tác quản trị EC2 (Linux/Windows), gắn thêm ổ đĩa EBS và tạo bản sao lưu Snapshot.
* Biết viết User Data để tự động cài đặt phần mềm khi khởi chạy instance.
* Triển khai chạy được ứng dụng web thực tế trên EC2 và đóng gói thành custom AMI.
