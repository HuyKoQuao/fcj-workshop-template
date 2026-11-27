---
title: "Bản đề xuất"
date: 2026-11-16
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Driver Drowsiness & Distraction Detection
## Hệ thống phát hiện tình trạng buồn ngủ và mất tập trung của tài xế kết hợp Edge AI và AWS Serverless

### 1. Tổng quan bài toán / giải pháp

**Driver Drowsiness & Distraction Detection** là hệ thống giám sát và phát hiện sớm tình trạng buồn ngủ hoặc mất tập trung của tài xế trong quá trình lái xe bằng **Computer Vision** kết hợp **AWS Cloud**, nhằm nâng cao nhận thức về an toàn giao thông và hạn chế các rủi ro tai nạn có thể xảy ra.

Thay vì đẩy luồng video liên tục lên đám mây để xử lý, hệ thống áp dụng mô hình lai **Edge AI + AWS Serverless**:
* **Tại thiết bị biên (Edge Device):** Hình ảnh khuôn mặt tài xế từ webcam được xử lý trực tiếp tại chỗ bằng **OpenCV** và **MediaPipe Face Mesh** để trích xuất các đặc trưng hành vi và phân tích trạng thái theo thời gian. Video thô hoàn toàn không được truyền ra ngoài thiết bị.
* **Trên nền tảng AWS Cloud:** Chỉ dữ liệu **metadata** của các sự kiện bất thường được gửi lên AWS thông qua **Amazon API Gateway** và **AWS Lambda** để kiểm tra, chống ghi trùng, lưu trữ trên **Amazon DynamoDB** và hiển thị lịch sử trên giao diện Dashboard (**Amazon S3 + CloudFront**) được bảo mật bởi **Amazon Cognito**.

---

### 2. Mục tiêu & phạm vi

**Mục tiêu dự án**
* Xây dựng pipeline thị giác máy tính tại thiết bị biên để trích xuất các chỉ số trạng thái khuôn mặt gồm **EAR** (*Eye Aspect Ratio*), **MAR** (*Mouth Aspect Ratio*), **Head Pose** (tư thế đầu) và thử nghiệm **Gaze Direction** (hướng nhìn).
* Áp dụng phân tích chuỗi thời gian (**Temporal Analysis**) để nhận diện chính xác các biểu hiện buồn ngủ hoặc mất tập trung, hạn chế cảnh báo giả.
* Triển khai hạ tầng backend **AWS Serverless** gọn nhẹ, bảo mật và tối ưu chi phí để tiếp nhận, lưu trữ và truy vấn lịch sử sự kiện.
* Đảm bảo hệ thống hoạt động ổn định ngay cả khi mất kết nối Internet thông qua cơ chế lưu đệm cục bộ (**Local Event Buffer**) và tự động gửi lại (**Retry**).

**Phạm vi thực hiện**
* **Xử lý AI tại Edge:** Thu thập hình ảnh qua webcam, nhận diện 478 điểm mốc khuôn mặt (*facial landmarks*), trích xuất đặc trưng và phân tích trạng thái dựa trên tập luật (*rule-based* kết hợp *CSV analysis*). Riêng thành phần phân tích hướng nhìn (**Gaze Direction**) nằm ở mức thử nghiệm và cần đánh giá thêm trước khi đưa vào làm tiêu chí nhận diện chính thức.
* **Hạ tầng AWS Cloud:** Xây dựng hoàn chỉnh các dịch vụ Serverless gồm **API Gateway (HTTP API)**, **AWS Lambda** (Event Writer & Event Reader), **Amazon DynamoDB**, **Amazon Cognito**, **Amazon S3 (private)**, **Amazon CloudFront (OAC)**, **Amazon CloudWatch**, **AWS IAM**, **AWS CloudTrail** và **AWS Budgets** (cùng **AWS WAF** ở mức thành phần bảo vệ mở rộng *optional*).
* **Kiểm thử & Đánh giá:** Đánh giá độ chính xác nhận diện trong nhiều điều kiện ánh sáng, góc quay camera khác nhau và kiểm thử khả năng đồng bộ dữ liệu khi ngắt/khôi phục kết nối mạng.

---

### 3. Vấn đề cần giải quyết

* **Khó nhận biết kịp thời dấu hiệu buồn ngủ và mất tập trung:** Các biểu hiện như nhắm mắt kéo dài, ngáp liên tục, thay đổi tư thế đầu hoặc lệch hướng nhìn diễn ra nhanh, khiến tài xế khó tự kiểm soát nếu không có công cụ hỗ trợ theo dõi liên tục.
* **Hạn chế của kiến trúc xử lý video tập trung trên Cloud:** Việc truyền luồng video thời gian thực lên đám mây đòi hỏi băng thông mạng lớn, làm tăng độ trễ phản hồi, phát sinh chi phí hạ tầng cao và tiềm ẩn rủi ro xâm phạm quyền riêng tư hình ảnh của tài xế.
* **Thất thoát hoặc trùng lặp dữ liệu khi mạng không ổn định:** Thiết bị hoạt động trên phương tiện di chuyển dễ gặp tình trạng rớt mạng tạm thời. Nếu thiếu cơ chế lưu trữ tạm tại chỗ và kiểm soát định danh sự kiện, dữ liệu cảnh báo có thể bị mất hoặc bị ghi lặp nhiều lần khi hệ thống gửi lại.

---

### 4. Kiến trúc giải pháp sơ bộ

![Driver Drowsiness & Distraction Detection Architecture](/images/2-Proposal/Architecture.png)

#### Luồng xử lý 10 giai đoạn của hệ thống

1. **Thu thập dữ liệu:** Webcam ghi nhận hình ảnh khuôn mặt tài xế và đưa trực tiếp vào bộ xử lý trên thiết bị Edge (không truyền video lên AWS).
2. **Xử lý AI tại Edge:** Sử dụng **OpenCV** kết hợp **MediaPipe Face Mesh** (478 landmarks) để trích xuất các chỉ số **EAR**, **MAR**, **Head Pose** và thử nghiệm **Gaze Direction**.
3. **Phân tích trạng thái:** Các đặc trưng trích xuất được đưa qua bước **Temporal Analysis** (sử dụng *CSV analysis* và *rule-based candidates*) để đánh giá trạng thái buồn ngủ hoặc mất tập trung theo thời gian.
4. **Lưu trữ sự kiện tại thiết bị:** Khi phát hiện sự kiện, hệ thống sinh mã `event_id` duy nhất và lưu metadata vào **Local Event Buffer**. Cơ chế **Retry** sẽ tự động gửi lại các sự kiện chưa đồng bộ nếu kết nối mạng gặp sự cố.
5. **Gửi dữ liệu lên AWS:** Thiết bị gửi bản tin metadata qua giao thức **HTTPS POST** tới **Amazon API Gateway (HTTP API)**.
6. **Kiểm tra và ghi nhận sự kiện:** Request từ API Gateway được chuyển tới hàm **AWS Lambda Event Writer** để kiểm tra tính hợp lệ (*validate*). Sau đó, Lambda thực hiện lệnh **Conditional `PutItem`** vào **Amazon DynamoDB** dựa trên khóa `event_id` nhằm ngăn chặn việc ghi trùng sự kiện.
7. **Đăng nhập và xác thực:** Dashboard sử dụng **Amazon Cognito** để quản lý đăng ký, đăng nhập và cấp phát **JWT**. **API Gateway** tích hợp **JWT Authorizer** để xác thực quyền truy cập của từng request.
8. **Truy vấn lịch sử:** Khi người dùng xem lịch sử sự kiện trên Dashboard, request đi qua API Gateway (đã xác thực JWT) tới hàm **AWS Lambda Event Reader** để truy vấn dữ liệu từ DynamoDB.
9. **Hiển thị Dashboard:** Giao diện Frontend được lưu trữ trên **Amazon S3 (private)** và phân phối thông qua **Amazon CloudFront** sử dụng **Origin Access Control (OAC)**.
10. **Giám sát hệ thống:** **Amazon CloudWatch** thu thập API access logs, Lambda logs, errors, duration và DynamoDB metrics để theo dõi vận hành và cảnh báo khi có bất thường.

#### Tổng hợp các dịch vụ AWS sử dụng

| Nhóm chức năng | Dịch vụ AWS | Vai trò trong kiến trúc |
| --- | --- | --- |
| **Tiếp nhận & Xử lý API** | Amazon API Gateway (HTTP API), AWS Lambda | Tiếp nhận event từ Edge Device, xác thực JWT và thực thi logic ghi/đọc dữ liệu (`Event Writer` & `Event Reader`). |
| **Lưu trữ dữ liệu** | Amazon DynamoDB | Lưu trữ metadata sự kiện tập trung, đảm bảo tính duy nhất bằng Conditional `PutItem` theo `event_id`. |
| **Frontend & Phân phối** | Amazon S3 (private), Amazon CloudFront (OAC) | Lưu trữ mã nguồn web tĩnh an toàn và phân phối giao diện Dashboard tới người dùng qua HTTPS. |
| **Xác thực & Bảo mật** | Amazon Cognito, AWS IAM, AWS WAF *(Optional)* | Quản lý tài khoản người dùng/JWT, phân quyền truy cập dịch vụ theo đặc quyền tối thiểu và bảo vệ lớp biên API. |
| **Giám sát & Chi phí** | Amazon CloudWatch, AWS CloudTrail, AWS Budgets | Thu thập logs/metrics, theo dõi lịch sử gọi API trên tài khoản và cảnh báo ngưỡng chi phí vận hành. |

---

### 5. Kế hoạch & Timeline thực hiện

Lộ trình triển khai dự án được phân bổ bám sát kế hoạch thực tập 11 tuần (từ **21/09/2026** đến **30/11/2026**):

* **Giai đoạn 1 – Nền tảng AWS & Xây dựng Edge Pipeline cơ bản (Tuần 1 – Tuần 8 | 21/09/2026 – 13/11/2026):**
  * Thực hành làm chủ các dịch vụ nền tảng trên AWS (VPC, EC2, S3, DynamoDB, IAM, CloudWatch) và mô hình Serverless.
  * Xây dựng bước đầu pipeline xử lý tại Edge với webcam, OpenCV, MediaPipe Face Mesh (trích xuất EAR, MAR, Head Pose, Gaze) và thuật toán phân tích luật (*rule-based Temporal Analysis*).
* **Giai đoạn 2 – Thiết kế kiến trúc & Hoàn thiện đề xuất (Tuần 9 | 16/11/2026 – 20/11/2026):**
  * Chốt phạm vi đề tài **Driver Drowsiness & Distraction Detection** theo hướng Edge AI + AWS Serverless.
  * Hoàn thiện sơ đồ kiến trúc 10 bước, thiết kế luồng xác thực/dữ liệu và ước tính chi phí trên AWS Pricing Calculator.
* **Giai đoạn 3 – Triển khai AWS Cloud, Hoàn thiện Edge & Kiểm thử (Tuần 10 | 23/11/2026 – 27/11/2026):**
  * Triển khai hoàn chỉnh các dịch vụ trên AWS: DynamoDB, Cognito, Lambda (Writer/Reader), API Gateway, S3 (private), CloudFront (OAC), CloudWatch, IAM, CloudTrail và AWS Budgets.
  * Hoàn thiện cơ chế **Local Event Buffer & Retry**, tinh chỉnh **Temporal Analysis** và đánh giá thêm độ ổn định của **Gaze Direction**.
  * Kiểm thử độ chính xác nhận diện trong nhiều điều kiện ánh sáng, góc quay khác nhau và kiểm thử đồng bộ dữ liệu khi ngắt kết nối Internet.
* **Giai đoạn 4 – Tổng hợp báo cáo & Demo bảo vệ dự án (Tuần 11 | 30/11/2026):**
  * Hoàn thiện tài liệu dự án trên trang báo cáo Hugo (GitHub Pages), chạy demo trực tiếp luồng dữ liệu từ Edge lên Cloud và dọn dẹp tài nguyên AWS sau khi hoàn thành.

---

### 6. Bảng dự toán ngân sách & chi phí (Cost Estimation)

Hệ thống ưu tiên sử dụng kiến trúc **AWS Serverless** theo cơ chế tính phí dựa trên mức sử dụng thực tế (*Pay-as-you-go*) nhằm tối ưu chi phí vận hành trong giai đoạn phát triển và thử nghiệm khi lượng người dùng còn ít, đồng thời tích hợp **AWS Budgets** để giám sát và cảnh báo ngưỡng chi tiêu.

| Thành phần / Dịch vụ | Quy mô / Cấu hình dự kiến | Cơ chế tính phí & Tối ưu chi phí |
| --- | --- | --- |
| **Edge Device (Webcam & Máy tính xử lý)** | Xử lý AI cục bộ bằng OpenCV + MediaPipe | Tận dụng phần cứng sẵn có; không tốn chi phí thuê GPU/EC2 xử lý video trên Cloud. |
| **Amazon API Gateway (HTTP API)** | Tiếp nhận các bản tin metadata sự kiện và API truy vấn Dashboard | Sử dụng HTTP API (chi phí thấp hơn REST API), tính phí theo số lượng request thực tế. |
| **AWS Lambda** | 2 hàm (`Event Writer` & `Event Reader`), bộ nhớ nhỏ gọn | Tính phí theo số lượt gọi và thời gian thực thi (ms); tận dụng mức miễn phí hàng tháng của AWS Free Tier. |
| **Amazon DynamoDB** | 1 bảng lưu trữ metadata sự kiện (kích thước bản ghi nhỏ) | Chế độ On-Demand / Free Tier, tối ưu chi phí đọc/ghi theo lưu lượng thực tế. |
| **Amazon Cognito** | Quản lý đăng ký, đăng nhập và cấp JWT cho người dùng Dashboard | Miễn phí cho nhóm người dùng quy mô nhỏ (MAU thấp) theo chính sách của Cognito. |
| **Amazon S3 & CloudFront** | Lưu trữ tĩnh giao diện Dashboard (S3 private) và phân phối qua CDN | Dung lượng tệp tĩnh nhỏ, chi phí lưu trữ và băng thông truyền tải tối thiểu. |
| **CloudWatch, CloudTrail, IAM & Budgets** | Ghi nhận logs cơ bản, kiểm soát quyền và cảnh báo ngân sách | IAM miễn phí; cấu hình lưu giữ log hợp lý trên CloudWatch và đặt cảnh báo sớm qua AWS Budgets. |

---

### 7. Rủi ro & phương án giảm thiểu

| Rủi ro tiềm ẩn | Mức độ ảnh hưởng | Xác suất xảy ra | Phương án giảm thiểu & Khắc phục |
| --- | --- | --- | --- |
| **Mất hoặc chập chờn kết nối Internet trên phương tiện** | Cao | Trung bình | Tách biệt hoàn toàn tác vụ nhận diện AI tại thiết bị biên để cảnh báo tại chỗ không phụ thuộc mạng. Tích hợp **Local Event Buffer** lưu trữ cục bộ sự kiện kèm cơ chế **Retry** tự động đồng bộ lại lên AWS khi có kết nối. |
| **Ghi trùng dữ liệu sự kiện khi thiết bị thực hiện Retry** | Trung bình | Trung bình | Sinh mã `event_id` duy nhất cho từng sự kiện tại Edge và sử dụng thao tác **Conditional `PutItem`** trên Amazon DynamoDB trong hàm Lambda Event Writer để loại bỏ các bản ghi trùng lặp. |
| **Sai lệch nhận diện do ánh sáng yếu hoặc góc quay camera** | Cao | Trung bình | Kết hợp đồng thời nhiều chỉ số (EAR, MAR, Head Pose) qua bước **Temporal Analysis** thay vì xét khung hình đơn lẻ; kiểm thử đa dạng điều kiện ánh sáng/góc quay và tách riêng **Gaze Direction** ở mức thử nghiệm để đánh giá kỹ trước khi áp dụng chính thức. |
| **Rủi ro quyền riêng tư hình ảnh và bảo mật truy cập Cloud** | Cao | Thấp | Không truyền video thô lên Cloud (chỉ gửi metadata sự kiện); phân quyền dịch vụ theo nguyên tắc đặc quyền tối thiểu bằng **IAM**, xác thực người dùng qua **Cognito JWT** và khóa truy cập trực tiếp S3 bằng **CloudFront OAC**. |
| **Phát sinh chi phí Cloud ngoài dự kiến** | Trung bình | Thấp | Sử dụng kiến trúc Serverless trả phí theo lượt dùng thực tế, thiết lập ngưỡng cảnh báo tự động qua **AWS Budgets** và kiểm tra định kỳ trên **CloudWatch / Cost Explorer**. |
