---
title: "Worklog Tuần 2"
date: 2026-09-28
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu Tuần 2:

* Hiểu cách thiết kế mạng ảo Amazon VPC và chia dải địa chỉ IP (CIDR).
* Cấu hình được Public/Private Subnet, Route Table, Internet Gateway và NAT Gateway.
* Phân biệt và sử dụng Security Group với Network ACL (NACL).

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu Amazon VPC: <br>&emsp; + CIDR blocks và cách chia subnet <br>&emsp; + Khác biệt giữa Public Subnet và Private Subnet <br>&emsp; + Thiết kế mạng trên nhiều AZ (Multi-AZ) | 28/09/2026 | 28/09/2026 | <https://000003.awsstudygroup.com/> |
| 3 | - Tìm hiểu định tuyến và kết nối Internet trong VPC: <br>&emsp; + Route Tables <br>&emsp; + Internet Gateway (IGW) và NAT Gateway <br>&emsp; + VPC Endpoints (Gateway & Interface) | 29/09/2026 | 29/09/2026 | <https://000003.awsstudygroup.com/> |
| 4 | - Tìm hiểu bảo mật lớp mạng: <br>&emsp; + Security Group (Stateful) vs. NACL (Stateless) <br>&emsp; + VPC Flow Logs | 30/09/2026 | 30/09/2026 | <https://000003.awsstudygroup.com/> |
| 5 | - **Thực hành (Phần 1):** <br>&emsp; + Tạo VPC mới với 2 Public Subnets và 2 Private Subnets <br>&emsp; + Gắn IGW và cấu hình Route Table cho Public Subnet | 01/10/2026 | 01/10/2026 | <https://000003.awsstudygroup.com/> |
| 6 | - **Thực hành (Phần 2):** <br>&emsp; + Tạo NAT Gateway để EC2 trong Private Subnet ra được Internet <br>&emsp; + Test các rule của Security Group, NACL và xóa NAT Gateway sau khi xong lab | 02/10/2026 | 02/10/2026 | <https://000003.awsstudygroup.com/> |

### Kết quả đạt được trong Tuần 2:

* Biết cách tính CIDR và dựng kiến trúc Multi-AZ VPC hoàn chỉnh từ đầu.
* Cấu hình đúng Route Table, IGW và NAT Gateway cho từng loại subnet.
* Hiểu rõ khi nào dùng Security Group và khi nào dùng NACL để chặn/mở traffic.
