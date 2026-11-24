---
title: "Worklog Tuần 3"
date: 2026-10-05
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu Tuần 3:

* Nắm các mô hình kết nối liên mạng trên AWS: Bastion Host, VPC Peering và Transit Gateway.
* Hiểu tổng quan về kết nối mạng Hybrid (Site-to-Site VPN, Direct Connect).
* Hoàn thành bài lab định tuyến nhiều VPC với Transit Gateway.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu mô hình Bastion Host để truy cập máy chủ trong Private Subnet <br> - Tìm hiểu **VPC Peering** và hạn chế không bắc cầu (non-transitive) | 05/10/2026 | 05/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Tìm hiểu **AWS Transit Gateway** (mô hình Hub-and-Spoke) <br> - Đọc tổng quan về Site-to-Site VPN và AWS Direct Connect | 06/10/2026 | 06/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - **Thực hành:** <br>&emsp; + Dựng Bastion Host ở Public Subnet để SSH vào EC2 ở Private Subnet <br>&emsp; + Thiết lập VPC Peering giữa 2 VPC khác dải IP và cập nhật Route Table | 07/10/2026 | 07/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - **Thực hành Transit Gateway (Lab 20):** <br>&emsp; + Tạo Transit Gateway và attach 3 VPC vào <br>&emsp; + Cấu hình Transit Gateway Route Table để các VPC thông nhau | 08/10/2026 | 08/10/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - Test ping giữa các EC2 thuộc các VPC khác nhau qua Transit Gateway <br> - Dọn dẹp toàn bộ Transit Gateway Attachments và EC2 của bài lab | 09/10/2026 | 09/10/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được trong Tuần 3:

* Biết cách sử dụng Bastion Host và cấu hình VPC Peering kết nối hai mạng nội bộ.
* Hoàn thành bài lab AWS Transit Gateway và hiểu cách quản lý định tuyến tập trung khi có nhiều VPC.
* Nắm được khái niệm cơ bản về kết nối VPN từ hệ thống On-premises lên AWS.
