---
title: "Worklog Tuần 7"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Thống nhất cấu trúc các API endpoint
* Kiểm thử các chức năng cơ bản của ứng dụng
* Thiết lập AWS Cognito cho xác thực và phân quyền người dùng

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Họp nhóm thảo luận và thống nhất các API endpoint <br> - Định nghĩa cấu trúc API và quy tắc đặt tên <br> - Tài liệu hóa các API specifications                                          | 21/10/2025   | 21/10/2025      | API design best practices, REST standards |
| 3   | - Triển khai các API endpoint đã chuẩn hóa <br>&emsp; + APIs quản lý người dùng <br>&emsp; + APIs nội dung <br>&emsp; + APIs xác thực                                                      | 22/10/2025   | 22/10/2025      | <https://docs.aws.amazon.com/apigateway/> |
| 4   | - Kiểm thử các chức năng cơ bản của ứng dụng <br> - Thực hiện integration testing <br> - Debug và sửa các lỗi phát hiện được                                                               | 23/10/2025   | 23/10/2025      | Testing frameworks, Postman |
| 5   | - Tìm hiểu AWS Cognito cơ bản <br>&emsp; + User pools <br>&emsp; + Identity pools <br>&emsp; + Authentication flows <br> - Lên kế hoạch tích hợp Cognito                                   | 24/10/2025   | 24/10/2025      | <https://docs.aws.amazon.com/cognito/> |
| 6   | - **Thực hành:** <br>&emsp; + Thiết lập Cognito user pool <br>&emsp; + Cấu hình authentication flows <br>&emsp; + Tích hợp Cognito với API Gateway                                         | 25/10/2025   | 25/10/2025      | <https://docs.aws.amazon.com/cognito/> |


### Kết quả đạt được tuần 7:

* Thống nhất thành công tất cả API endpoints với quy tắc đặt tên và cấu trúc nhất quán

* Hoàn thành integration testing cho các tính năng cơ bản:
  * Luồng đăng ký và đăng nhập người dùng
  * APIs lấy nội dung
  * Xác thực dữ liệu và xử lý lỗi

* Thiết lập AWS Cognito user pool với:
  * Xác thực và phân quyền người dùng
  * Chính sách mật khẩu và tùy chọn MFA
  * Custom attributes cho user profiles

* Tích hợp Cognito với API Gateway:
  * Cấu hình authorizers
  * Triển khai JWT token validation
  * Bảo mật các API endpoints

* Sửa các lỗi nghiêm trọng và cải thiện thời gian phản hồi API

* Tài liệu hóa các API endpoints và authentication flows cho nhóm tham khảo


