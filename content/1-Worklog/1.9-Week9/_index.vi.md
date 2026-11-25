---
title: "Worklog Tuần 9"
date: 2026-11-16
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu Tuần 9:

* Chốt đề tài Dự án cuối kỳ **Driver Drowsiness & Distraction Detection** (kết hợp Edge AI và AWS Cloud).
* Hoàn thiện thiết kế kiến trúc hệ thống từ bước xử lý Computer Vision tại Edge đến lưu trữ và hiển thị trên AWS Serverless.
* Ước tính chi phí vận hành qua AWS Pricing Calculator và thống nhất proposal với mentor Lữ Hoàn Thiện.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Chốt đề tài **Driver Drowsiness & Distraction Detection** <br> - Xác định hướng xử lý **Edge AI + AWS Cloud**: xử lý video webcam trực tiếp tại thiết bị Edge để giảm độ trễ, tiết kiệm băng thông và bảo vệ quyền riêng tư, chỉ gửi metadata sự kiện lên AWS | 16/11/2026 | 16/11/2026 | Project Proposal |
| 3 | - Thiết kế luồng xử lý tại Edge Device: <br>&emsp; + Dùng **OpenCV** + **MediaPipe Face Mesh** (478 landmarks) trích xuất **EAR**, **MAR**, **Head Pose** và thử nghiệm **Gaze Direction** <br>&emsp; + Thiết kế bước **Temporal Analysis** (rule-based + CSV analysis) và **Local Event Buffer** kèm cơ chế **Retry** | 17/11/2026 | 17/11/2026 | OpenCV & MediaPipe Docs |
| 4 | - Thiết kế kiến trúc Serverless trên AWS: <br>&emsp; + Luồng ghi sự kiện: **API Gateway (HTTP API)** -> **Lambda Event Writer** -> **DynamoDB** (Conditional `PutItem` theo `event_id` để chống ghi trùng) <br>&emsp; + Luồng xem Dashboard: **Amazon Cognito** (JWT) -> **API Gateway (JWT Authorizer)** -> **Lambda Event Reader** -> **DynamoDB** <br>&emsp; + Frontend: **Amazon S3 (private)** + **Amazon CloudFront (OAC)** | 18/11/2026 | 18/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> <br> <https://docs.aws.amazon.com/serverless/> |
| 5 | - Bổ sung lớp bảo mật, giám sát và tính chi phí: <br>&emsp; + Phân quyền bằng **IAM**, giám sát qua **CloudWatch** & **CloudTrail**, ghi nhận **AWS WAF** là thành phần bảo vệ mở rộng (optional) <br>&emsp; + Ước tính chi phí hàng tháng cho các dịch vụ serverless trên **AWS Pricing Calculator** | 19/11/2026 | 19/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> <br> <https://calculator.aws/> |
| 6 | - Trình bày proposal, sơ đồ kiến trúc <br> - Chốt các đầu việc cần hoàn thiện tiếp: Local Event Buffer/Retry, Temporal Analysis và kiểm thử điều kiện ánh sáng/góc quay | 20/11/2026 | 20/11/2026 | Project Proposal |

### Kết quả đạt được trong Tuần 9:

* Hoàn thiện proposal và sơ đồ kiến trúc 10 bước của hệ thống **Driver Drowsiness & Distraction Detection**.
* Chọn được kiến trúc Serverless phù hợp để tối ưu chi phí theo lượt request thực tế và đảm bảo quyền riêng tư hình ảnh tài xế.
