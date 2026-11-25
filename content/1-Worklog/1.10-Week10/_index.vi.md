---
title: "Worklog Tuần 10"
date: 2026-11-23
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu Tuần 10:

* Triển khai hoàn chỉnh các dịch vụ AWS Cloud của dự án (**DynamoDB, Cognito, Lambda, API Gateway, S3, CloudFront, CloudWatch, IAM, CloudTrail, Budgets**).
* Hoàn thiện cơ chế **Local Event Buffer & Retry**, tinh chỉnh **Temporal Analysis** và đánh giá thêm phần **Gaze Direction** tại Edge.
* Kiểm thử toàn bộ hệ thống trong nhiều điều kiện ánh sáng/góc quay và kiểm thử khi mất kết nối mạng.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - Tạo bảng **Amazon DynamoDB** lưu metadata sự kiện với khóa `event_id` <br> - Cấu hình **Amazon Cognito** User Pool cho đăng ký, đăng nhập và cấp JWT <br> - Tạo **IAM Roles/Policies** cấp quyền tối thiểu cho các hàm Lambda | 23/11/2026 | 23/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> <br> <https://docs.aws.amazon.com/cognito/> |
| 3 | - Viết **Lambda Event Writer** để validate dữ liệu và ghi vào DynamoDB bằng Conditional `PutItem` (tránh trùng `event_id`) <br> - Viết **Lambda Event Reader** để truy vấn lịch sử sự kiện <br> - Cấu hình **API Gateway (HTTP API)** và gắn **JWT Authorizer** | 24/11/2026 | 24/11/2026 | <https://docs.aws.amazon.com/apigateway/> |
| 4 | - Upload giao diện Dashboard lên **S3 (private)** và cấu hình **CloudFront** sử dụng **Origin Access Control (OAC)** <br> - Bật **CloudWatch** (API access logs, Lambda logs, errors, duration, DynamoDB metrics), **CloudTrail** và đặt ngưỡng cảnh báo trên **AWS Budgets** | 25/11/2026 | 25/11/2026 | <https://youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&si=z_oemJYZVgAPlx1x> |
| 5 | - Hoàn thiện **Local Event Buffer** và cơ chế **Retry** tại thiết bị Edge (lưu cục bộ khi rớt mạng và tự gửi lại qua HTTPS POST khi có mạng) <br> - Tinh chỉnh thuật toán **Temporal Analysis** và đánh giá thêm độ ổn định của **Gaze Direction** | 26/11/2026 | 26/11/2026 | OpenCV & MediaPipe Docs |
| 6 | - Kiểm thử nhận diện EAR, MAR, Head Pose trong nhiều điều kiện ánh sáng và góc quay khác nhau <br> - Ngắt mạng để test lưu đệm trên Local Event Buffer, sau đó mở lại mạng để xác nhận dữ liệu đồng bộ đủ lên DynamoDB và hiển thị trên Dashboard | 27/11/2026 | 27/11/2026 | Project GitHub Repository |

### Kết quả đạt được trong Tuần 10:

* Dựng xong toàn bộ backend Serverless và frontend Dashboard trên AWS, luồng xác thực JWT và ghi/đọc dữ liệu hoạt động ổn định.
* Hoàn thiện cơ chế **Local Event Buffer & Retry** giúp không bị mất sự kiện khi kết nối Internet bị gián đoạn.
* Hoàn tất kiểm thử thực tế với nhiều điều kiện ánh sáng, góc quay và khả năng chịu lỗi mạng trước ngày nộp bài.
