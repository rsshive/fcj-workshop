---
title: "Blog 2"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

{{% notice warning %}}
 **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

# Ra mắt các nhóm phiên bản "mặc định" (default instance) dành cho AWS Batch

#### Bởi Angel Pizarro vào 18/8/2025 trong [AWS Batch](https://aws.amazon.com/blogs/hpc/category/compute/aws-batch/), [Điện toán hiệu năng cao (HPC)](https://aws.amazon.com/blogs/hpc/category/high-performance-computing/) | [Liên kết](https://aws.amazon.com/blogs/hpc/introducing-default-instance-categories-for-aws-batch/)

Hôm nay, chúng tôi ra mắt một bộ **phân loại theo họ instance** mới cho **AWS Batch**, gồm **"default_x86_64"** và **"default_arm64"**. Các danh mục mới này vừa là sự **làm rõ** vừa là **cải tiến** so với danh mục loại phiên bản **"optimal"** hiện có. Bài viết này cung cấp một số bối cảnh về tính năng mới và cách bạn có thể **cấu hình các môi trường Batch** để tận dụng những cải tiến đó.

## Lựa chọn instance types cho AWS Batch Compute Environments để khởi chạy

Bạn có thể chỉ định **tập hợp các loại phiên bản [Amazon EC2](https://aws.amazon.com/ec2/) (instance types)** mà một **môi trường tính toán (compute environment)** được phép khởi chạy để chạy các job trong **hàng đợi công việc (job queues)** của bạn. Ví dụ, nếu bạn biết các job của mình đạt **giá/hiệu năng** (price/performance) tốt nhất trên g6.16xlarge, bạn có thể đặt [tham số](https://docs.aws.amazon.com/batch/latest/APIReference/API_ComputeResource.html#Batch-Type-ComputeResource-instanceTypes) computeResources.instanceTypes của môi trường tính toán thành ["g6.16xlarge"], và môi trường đó sẽ chỉ khởi chạy **chính xác** loại và kích cỡ phiên bản này cho các job trong (các) hàng đợi liên kết.

Để tận dụng tối đa **khả năng lập lịch (scheduling) và co giãn (scaling)** của Batch, bạn nên định nghĩa **một tập hợp đa dạng** các phiên bản và để Batch quyết định sẽ khởi chạy loại nào dựa trên yêu cầu tài nguyên CPU, bộ nhớ và GPU của các job. Mặc dù bạn có thể chỉ định một **danh sách loại phiên bản** (ví dụ ["c5.24xlarge", "m6.48xlarge"]), bạn cũng có thể định nghĩa một **tập hợp các họ phiên bản (instance families)** (ví dụ ["c5","c7a","c7i","m7i"]) để Batch có thể khởi chạy thay bạn. Trước đây, bạn cũng có tùy chọn dùng danh mục **"optimal"**, mà Batch sẽ ánh xạ thành ["c4","m4","r4"] khi các phiên bản này khả dụng trong **Vùng (AWS Region)** của bạn. Nếu một Region không có các loại phiên bản đó, Batch sẽ ánh xạ *optimal* sang **thế hệ có chi phí thấp nhất** trong Region, thường là ["c5","m5","r5"].

Mặc dù *optimal* là một thiết lập viết tắt tiện lợi, chúng tôi nhận thấy nó **không khớp** với kỳ vọng của khách hàng. Batch **không** chọn các phiên bản cho **hiệu năng tốt nhất** của job hay **giá tốt nhất** cho ứng dụng của bạn. Danh mục *optimal* chỉ là **một phép ánh xạ đơn giản** và không hơn. Các thế hệ phiên bản mới hơn có khả năng mang lại **giá/hiệu năng** tốt hơn cho hầu hết workload. Trong tất cả các trường hợp tôi đã xem xét, các phiên bản **thế hệ thứ 4** vừa **chậm hơn** vừa **đắt hơn** so với **thế hệ thứ 5**, vì vậy *optimal* thực ra **không hề "tối ưu"** như cái tên của nó!

Cuối cùng, *optimal* **không bao gồm** các phiên bản dùng **bộ xử lý AWS Graviton**, vốn được thiết kế riêng để mang lại **giá/hiệu năng vượt trội** cho nhiều loại workload.

## Nâng cấp từ cấu hình "optimal"

Hôm nay, chúng tôi đã ra mắt một bộ **danh mục loại phiên bản (instance type categories)** mới để cải thiện trải nghiệm của bạn với tính năng lựa chọn instance của Batch. Giờ đây bạn có thể chọn default_x86_64 cho một tập các **họ instance** dùng CPU **x86**, và default_arm64 cho một tập các **instance** dùng CPU **AWS Graviton**. Danh sách **instance type** này sẽ **không tĩnh** và sẽ thay đổi theo thời gian khi chúng tôi giới thiệu các **họ instance** mới. Bạn có thể tìm phần ánh xạ giữa từng **danh mục** và tập **họ instance** theo từng **Region** trong trang tài liệu [**Instance type compute table**](https://docs.aws.amazon.com/batch/latest/userguide/instance-type-compute-table.html); ví dụ, phần ánh xạ của default_arm64 tại thời điểm ra mắt tính năng sẽ như sau:

| Vùng/Khu vực (Regions) | Họ phiên bản (instance families) |
| :---- | :---- |
| Tất cả các Vùng AWS hỗ trợ AWS Batch | m6g, c6g, r6g c7g |

*Bảng 1. Bản ánh xạ của **danh mục loại phiên bản*** default_arm64 *tới các **họ phiên bản cụ thể** trong các **Vùng (Regions)** có hỗ trợ **AWS Batch**.*

Các ánh xạ mặc định **không** bao gồm các phiên bản tăng tốc (accelerated instances) theo thiết kế. Chúng tôi **rất khuyến nghị** bạn chỉ định cụ thể các loại phiên bản nếu workload của bạn được hưởng lợi từ các phiên bản tăng tốc. Ngoài ra, chúng tôi khuyến nghị **định nghĩa riêng** một **job queue** và **compute environment** tách biệt với các cụm instance **không tăng tốc**. Khi tài nguyên được tách riêng, Batch có thể đưa ra các quyết định co giãn (scaling) **tốt hơn** cho workload của bạn và **ngăn** việc lập lịch các job không tăng tốc lên các instance tăng tốc, điều có thể dẫn đến **chi phí phát sinh**.

Tương tự như trước đây với *optimal*, bạn vẫn có thể **định nghĩa bổ sung** các **instance type** bên cạnh các danh mục default_*. Batch sẽ xem xét **toàn bộ danh sách** bạn đã khai báo khi lựa chọn **instance type** để chạy các job.

## Chuyển đổi từ *optimal*

Chúng tôi khuyến nghị bạn cập nhật các môi trường Batch để áp dụng các danh mục mới. Tuy nhiên, bạn **không bắt buộc** phải cập nhật. Các môi trường tính toán (compute environments) AWS Batch hiện có đang sử dụng *optimal* vẫn **hợp lệ**. Các thao tác API [**CreateComputeEnvironment**](https://docs.aws.amazon.com/batch/latest/APIReference/API_CreateComputeEnvironment.html) và [**UpdateComputeEnvironment**](https://docs.aws.amazon.com/batch/latest/APIReference/API_UpdateComputeEnvironment.html) vẫn chấp nhận *optimal* như một giá trị hợp lệ. Hành vi của *optimal* sẽ **giữ nguyên** cho đến **đầu tháng 11 năm 2025**. Sau thời điểm đó, *optimal* sẽ **hành xử giống** với danh mục loại phiên bản default_x86_64.

Một lần nữa, sau **đầu tháng 11 năm 2025**, *optimal* sẽ **không còn** là một ánh xạ tĩnh tới các phiên bản **thế hệ thứ 4** (nếu khả dụng) và sẽ **thay đổi theo thời gian** khi AWS giới thiệu các họ phiên bản mới. Nếu bạn muốn **duy trì** tập phiên bản hiện tại cho *optimal*, bạn nên cập nhật (các) môi trường tính toán của mình để **chỉ định cụ thể** các **instance type** đó.

Chúng tôi khuyến nghị mọi **môi trường tính toán mới** mà bạn tạo hãy sử dụng các danh mục default_* mới. Cá nhân tôi cũng khuyến nghị bạn kiểm tra xem ứng dụng của mình có thể hưởng lợi từ **Graviton** hay không bằng cách tạo **container cho Arm** và định nghĩa một **compute environment** cùng **job queue** dùng default_arm64. Rất có thể bạn sẽ nhận được một kết quả **như mong muốn**!

## Kết luận

Chúng tôi rất mong bạn dùng thử các danh mục loại phiên bản (instance type) mặc định default_* mới. Chúng tôi tin rằng việc dần dần áp dụng các thế hệ instance mới hơn theo thời gian sẽ giúp workload của bạn vận hành hiệu quả và tiết kiệm chi phí. Để bắt đầu sử dụng các danh mục mới, hãy đăng nhập vào **Bảng điều khiển quản trị AWS Batch (AWS Batch management console)**, hoặc tham khảo hướng dẫn tạo **môi trường tính toán EC2** **được quản lý** (**managed EC2 compute environment)** trong **Sổ tay hướng dẫn (User Guide)** của chúng tôi.

---

**Angel Pizarro** là Principal Developer Advocate về HPC (High-Performance Computing  điện toán hiệu năng cao) và khoa học tính toán. Anh có nền tảng về phát triển ứng dụng tin-sinh học và xây dựng kiến trúc hệ thống cho điện toán có khả năng mở rộng trong genomics và các lĩnh vực khoa học sự sống thông lượng cao khác.
