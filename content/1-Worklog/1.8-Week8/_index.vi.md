---
title: "Worklog Tuần 8"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Nghiên cứu và thảo luận về chiến lược tích hợp AI vào dự án
* Tìm hiểu các dịch vụ AWS AI/ML: Bedrock, SageMaker, và Personalize
* Đánh giá dịch vụ AI nào phù hợp nhất với yêu cầu dự án

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Thảo luận nhóm về các use case AI cho dự án <br> - Brainstorm các tính năng có thể hưởng lợi từ AI <br> - Định nghĩa yêu cầu tích hợp AI                                                  | 28/10/2025   | 28/10/2025      | AI/ML best practices |
| 3   | - Tìm hiểu AWS Bedrock cơ bản <br>&emsp; + Foundation models <br>&emsp; + Model customization <br>&emsp; + API usage và pricing <br> - Khám phá các use case của Bedrock                    | 29/10/2025   | 29/10/2025      | <https://docs.aws.amazon.com/bedrock/> |
| 4   | - Tìm hiểu AWS SageMaker cơ bản <br>&emsp; + Model training và deployment <br>&emsp; + Endpoints và inference <br> - Tìm hiểu AWS Personalize <br>&emsp; + Recommendation systems <br>&emsp; + Real-time personalization | 30/10/2025   | 30/10/2025      | <https://docs.aws.amazon.com/sagemaker/>, <https://docs.aws.amazon.com/personalize/> |
| 5   | - So sánh các dịch vụ AWS AI cho nhu cầu dự án <br> - Tạo phân tích ưu/nhược điểm cho từng dịch vụ <br> - Quyết định dịch vụ nào sẽ triển khai                                             | 31/10/2025   | 31/10/2025      | AWS AI service comparison guides |
| 6   | - **Thực hành:** <br>&emsp; + Thiết lập quyền truy cập Bedrock <br>&emsp; + Test Bedrock API calls <br>&emsp; + Thử nghiệm với các foundation models khác nhau                           | 01/11/2025   | 01/11/2025      | <https://docs.aws.amazon.com/bedrock/> |


### Kết quả đạt được tuần 8:

* Xác định được các use case AI chính cho dự án:
  * Chatbot hỗ trợ tìm kiếm phim/chương trình TV
  * Gợi ý nội dung cá nhân hóa
  * Xử lý ngôn ngữ tự nhiên cho truy vấn người dùng

* Nghiên cứu sâu về các dịch vụ AWS AI/ML:
  * **AWS Bedrock**: Foundation models, Claude, Llama
  * **AWS SageMaker**: Custom model training và deployment
  * **AWS Personalize**: Recommendation engines

* So sánh và đánh giá:
  * Bedrock phù hợp nhất cho chatbot conversational
  * Chi phí và độ phức tạp triển khai
  * Khả năng mở rộng và bảo trì

* Thiết lập thành công Bedrock:
  * Cấu hình IAM permissions
  * Test API calls với Claude model
  * Đánh giá response quality và latency

* Tạo proof of concept cho chatbot integration

* Lập kế hoạch chi tiết cho việc tích hợp Bedrock vào tuần tới


