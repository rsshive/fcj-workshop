---
title: "Nhật ký tuần 10"
date: "`r Sys.Date()`"
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}


### Mục tiêu tuần 10:

* Tích hợp nguồn dữ liệu TMDB vào chatbot
* Phát triển các Lambda functions hỗ trợ hoạt động chatbot
* Nâng cao khả năng cung cấp thông tin phim/chương trình TV cho chatbot

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Nghiên cứu cấu trúc và khả năng của TMDB API <br> - Lên kế hoạch chiến lược tích hợp dữ liệu TMDB <br> - Định nghĩa các trường dữ liệu phim/TV cần thiết                                 | 11/11/2025   | 11/11/2025      | <https://developers.themoviedb.org/> |
| 3   | - Phát triển Lambda functions cho TMDB API calls <br>&emsp; + Tìm kiếm phim/chương trình TV <br>&emsp; + Lấy thông tin chi tiết và metadata <br>&emsp; + Xử lý API rate limits             | 12/11/2025   | 12/11/2025      | TMDB API documentation |
| 4   | - Tích hợp dữ liệu TMDB với chatbot <br>&emsp; + Kết nối TMDB Lambda với Bedrock <br>&emsp; + Nâng cao prompts với dữ liệu thực <br>&emsp; + Định dạng thông tin phim/TV                  | 13/11/2025   | 13/11/2025      | Lambda integration patterns |
| 5   | - Phát triển các Lambda functions hỗ trợ <br>&emsp; + Lớp caching dữ liệu <br>&emsp; + Xử lý lỗi và retry <br>&emsp; + Tối ưu response                                                     | 14/11/2025   | 14/11/2025      | AWS Lambda best practices |
| 6   | - **Thực hành:** <br>&emsp; + Test chatbot với dữ liệu TMDB <br>&emsp; + Xác thực độ chính xác dữ liệu <br>&emsp; + Tối ưu hiệu suất                                                      | 15/11/2025   | 15/11/2025      | Testing and optimization guides |


### Kết quả đạt được tuần 10:

* Tích hợp thành công nguồn dữ liệu TMDB:
  * Cấu hình truy cập TMDB API
  * Triển khai quản lý API key bảo mật
  * Thiết lập rate limiting và caching

* Phát triển các Lambda functions toàn diện:
  * **TMDB Search Lambda**: Tìm kiếm phim và chương trình TV
  * **TMDB Details Lambda**: Lấy thông tin chi tiết
  * **Data Processing Lambda**: Định dạng và tối ưu dữ liệu
  * **Cache Management Lambda**: Quản lý dữ liệu truy cập thường xuyên

* Nâng cao khả năng chatbot:
  * Thông tin phim/chương trình TV real-time
  * Chi tiết diễn viên và crew chính xác
  * Ngày phát hành và đánh giá
  * Gợi ý dựa trên dữ liệu TMDB
  * Xem dịch vụ EC2
  * Tạo và quản lý key pair
  * Kiểm tra thông tin dịch vụ đang chạy
  * ...

* Có khả năng kết nối giữa giao diện web và CLI để quản lý tài nguyên AWS song song.
* ...


