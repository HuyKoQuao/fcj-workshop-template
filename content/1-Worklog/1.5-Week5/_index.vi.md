---
title: "Worklog Tuần 5"
date: 2026-10-19
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu Tuần 5:

* Hiểu cách thiết kế hệ thống chịu lỗi và tự động mở rộng với ELB và Auto Scaling.
* Cấu hình được Application Load Balancer (ALB), Target Group và Auto Scaling Group.
* Nắm cơ bản về định tuyến tên miền Route 53 và CDN CloudFront.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu **Elastic Load Balancing (ELB)**: <br>&emsp; + So sánh Application Load Balancer (ALB) và Network Load Balancer (NLB) <br>&emsp; + Target Groups, Listener Rules và Health Checks | 19/10/2026 | 19/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 3 | - Tìm hiểu **EC2 Auto Scaling**: <br>&emsp; + Launch Template <br>&emsp; + Cấu hình Min / Desired / Max capacity và Scaling Policies (Target Tracking) | 20/10/2026 | 20/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 4 | - Tìm hiểu **Route 53 & CloudFront**: <br>&emsp; + Các kiểu routing DNS trên Route 53 (Simple, Weighted, Failover) <br>&emsp; + Cơ chế cache tại Edge Location và Origin Access Control (OAC) của CloudFront | 21/10/2026 | 21/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 5 | - **Thực hành ELB & Auto Scaling (Phần 1):** <br>&emsp; + Tạo Launch Template từ custom AMI <br>&emsp; + Tạo ALB chạy trên 2 AZ và gắn Auto Scaling Group vào Target Group | 22/10/2026 | 22/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 6 | - **Thực hành ELB & Auto Scaling (Phần 2):** <br>&emsp; + Chạy stress test tăng tải CPU để xem Auto Scaling tự tạo thêm EC2 <br>&emsp; + Terminate thử 1 instance đang chạy để kiểm tra cơ chế tự phục hồi | 23/10/2026 | 23/10/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |

### Kết quả đạt được trong Tuần 5:

* Dựng được cụm web server chạy Multi-AZ phía sau Application Load Balancer.
* Cấu hình và test thành công Auto Scaling tự tăng/giảm số lượng máy chủ theo mức tải CPU.
* Nắm được vai trò của Route 53 và CloudFront trong việc điều hướng và tăng tốc truy cập web.
