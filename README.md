API Automation Testing with Postman & AWS CI/CD
________________________________________
📌 Overview: 
Project này xây dựng hệ thống kiểm thử tự động (Automation Testing) cho API của Tiki bằng Postman, kết hợp quy trình CI/CD trên AWS nhằm tự động hóa toàn bộ quá trình kiểm thử và báo cáo kết quả.
Mục tiêu chính: giảm thao tác thủ công, tăng tốc độ kiểm thử và đảm bảo chất lượng API ổn định.
________________________________________
🧪 Test Automation with Postman
- Viết testcase kiểm tra API response bằng JavaScript.
- Đồng bộ Postman Collection với GitHub để theo dõi thay đổi và tự động kích hoạt pipeline.
________________________________________

⚙️ AWS CI/CD Pipeline
Hệ thống CI/CD được thiết kế bằng các dịch vụ AWS:
  
  1️⃣ CodePipeline
  - Theo dõi GitHub repository.
  - Khi có commit → tự động kích hoạt pipeline.
  
  2️⃣ CodeBuild
  - Chạy Postman Collection bằng Newman theo cấu hình trong buildspec.yml.
  - Sinh báo cáo kiểm thử và tải lên S3.
 
  3️⃣ S3
  - Lưu trữ log, artifact và kết quả kiểm thử.
  
  4️⃣ SNS
  - Gửi thông báo về email sau khi pipeline hoàn tất (Success / Failed).
  
________________________________________
📊 Logging & Reporting
- Logs build và test được theo dõi trực tiếp trên CloudWatch.
- Kết quả kiểm thử được lưu trong S3 và sử dụng làm báo cáo đánh giá chất lượng API định kỳ.

________________________________________
🚀 Workflow Summary
1.	Developer cập nhật Postman Collection → Commit lên GitHub.
2.	AWS CodePipeline tự động kích hoạt.
3.	CodeBuild chạy Newman để test API.
4.	Kết quả kiểm thử được lưu S3 → Log gửi về CloudWatch.
5.	SNS gửi thông báo hoàn thành pipeline.

________________________________________
📌 Technologies Used
- Postman / Newman – API Testing
- GitHub – Version control
- AWS CodePipeline – CI/CD Orchestration
- AWS CodeBuild – Execute automated tests
- AWS S3 – Artifact & log storage
- AWS CloudWatch – Log monitoring
- AWS SNS – Notification service


