---
title: "Worklog Tuần 9"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 9:

* Áp dụng AWS Bedrock vào dự án
* Phát triển các API chatbot cơ bản sử dụng Bedrock foundation models
* Kiểm thử và xác thực chức năng chatbot

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Thiết kế kiến trúc chatbot với Bedrock <br> - Lên kế hoạch cấu trúc API cho tương tác chatbot <br> - Định nghĩa định dạng input/output                                                | 04/11/2025   | 04/11/2025      | Bedrock documentation, API design patterns |
| 3   | - Triển khai Lambda functions cho Bedrock API calls <br>&emsp; + Xử lý request <br>&emsp; + Định dạng response <br>&emsp; + Xử lý lỗi                                                       | 05/11/2025   | 05/11/2025      | <https://docs.aws.amazon.com/bedrock/> |
| 4   | - Phát triển các chatbot APIs <br>&emsp; + Chat endpoint <br>&emsp; + Quản lý context <br>&emsp; + Lịch sử hội thoại                                                                            | 06/11/2025   | 06/11/2025      | API Gateway, Lambda integration |
| 5   | - Kiểm thử chức năng chatbot <br>&emsp; + Test Q&A cơ bản <br>&emsp; + Xác thực độ chính xác response <br>&emsp; + Đo latency                                                              | 07/11/2025   | 07/11/2025      | Testing frameworks |
| 6   | - **Thực hành:** <br>&emsp; + Integration testing với frontend <br>&emsp; + Debug và tối ưu hiệu suất <br>&emsp; + Tinh chỉnh prompts cho response tốt hơn                         | 08/11/2025   | 08/11/2025      | Prompt engineering best practices |


### Kết quả đạt được tuần 9:

* Tích hợp thành công AWS Bedrock vào dự án:
  * Cấu hình Bedrock runtime client
  * Triển khai Claude model cho conversational AI
  * Thiết lập IAM roles và permissions phù hợp

* Phát triển Lambda functions cho chatbot:
  * Tiền xử lý và xác thực request
  * Gọi Bedrock API
  * Định dạng response và xử lý lỗi
  * Quản lý context hội thoại

* Tạo các chatbot API endpoints:
  * `/chat` - Endpoint hội thoại chính
  * `/chat/history` - Lấy lịch sử hội thoại
  * `/chat/clear` - Xóa context hội thoại

* Triển khai các tính năng chatbot cơ bản:
  * Hiểu ngôn ngữ tự nhiên
  * Phản hồi nhận biết ngữ cảnh
  * Hỗ trợ hội thoại nhiều lượt
  * Cơ chế khắc phục lỗi

* Kiểm thử và xác thực:
  * Thời gian phản hồi trung bình 2-3 giây
  * Độ chính xác 95% cho các truy vấn cơ bản
  * Xử lý thành công các edge cases

* Tối ưu prompt engineering cho phản hồi liên quan phim/chương trình TV tốt hơn


