---
title: "Blog 2"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# Ra m?t các nhóm phiên b?n "m?c d?nh" (default instance) dành cho AWS Batch

#### B?i Angel Pizarro vào 18/8/2025 trong [AWS Batch](https://aws.amazon.com/blogs/hpc/category/compute/aws-batch/), [Ði?n toán hi?u nang cao (HPC)](https://aws.amazon.com/blogs/hpc/category/high-performance-computing/) | [Liên k?t](https://aws.amazon.com/blogs/hpc/introducing-default-instance-categories-for-aws-batch/)

Hôm nay, chúng tôi ra m?t m?t b? **phân lo?i theo h? instance** m?i cho **AWS Batch**, g?m **"default_x86_64"** và **"default_arm64"**. Các danh m?c m?i này v?a là s? **làm rõ** v?a là **c?i ti?n** so v?i danh m?c lo?i phiên b?n **"optimal"** hi?n có. Bài vi?t này cung c?p m?t s? b?i c?nh v? tính nang m?i và cách b?n có th? **c?u hình các môi tru?ng Batch** d? t?n d?ng nh?ng c?i ti?n dó.

## L?a ch?n instance types cho AWS Batch Compute Environments d? kh?i ch?y

B?n có th? ch? d?nh **t?p h?p các lo?i phiên b?n [Amazon EC2](https://aws.amazon.com/ec2/) (instance types)** mà m?t **môi tru?ng tính toán (compute environment)** du?c phép kh?i ch?y d? ch?y các job trong **hàng d?i công vi?c (job queues)** c?a b?n. Ví d?, n?u b?n bi?t các job c?a mình d?t **giá/hi?u nang** (price/performance) t?t nh?t trên g6.16xlarge, b?n có th? d?t [tham s?](https://docs.aws.amazon.com/batch/latest/APIReference/API_ComputeResource.html#Batch-Type-ComputeResource-instanceTypes) computeResources.instanceTypes c?a môi tru?ng tính toán thành ["g6.16xlarge"], và môi tru?ng dó s? ch? kh?i ch?y **chính xác** lo?i và kích c? phiên b?n này cho các job trong (các) hàng d?i liên k?t.

Ð? t?n d?ng t?i da **kh? nang l?p l?ch (scheduling) và co giãn (scaling)** c?a Batch, b?n nên d?nh nghia **m?t t?p h?p da d?ng** các phiên b?n và d? Batch quy?t d?nh s? kh?i ch?y lo?i nào d?a trên yêu c?u tài nguyên CPU, b? nh? và GPU c?a các job. M?c dù b?n có th? ch? d?nh m?t **danh sách lo?i phiên b?n** (ví d? ["c5.24xlarge", "m6.48xlarge"]), b?n cung có th? d?nh nghia m?t **t?p h?p các h? phiên b?n (instance families)** (ví d? ["c5","c7a","c7i","m7i"]) d? Batch có th? kh?i ch?y thay b?n. Tru?c dây, b?n cung có tùy ch?n dùng danh m?c **"optimal"**, mà Batch s? ánh x? thành ["c4","m4","r4"] khi các phiên b?n này kh? d?ng trong **Vùng (AWS Region)** c?a b?n. N?u m?t Region không có các lo?i phiên b?n dó, Batch s? ánh x? *optimal* sang **th? h? có chi phí th?p nh?t** trong Region, thu?ng là ["c5","m5","r5"].

M?c dù *optimal* là m?t thi?t l?p vi?t t?t ti?n l?i, chúng tôi nh?n th?y nó **không kh?p** v?i k? v?ng c?a khách hàng. Batch **không** ch?n các phiên b?n cho **hi?u nang t?t nh?t** c?a job hay **giá t?t nh?t** cho ?ng d?ng c?a b?n. Danh m?c *optimal* ch? là **m?t phép ánh x? don gi?n** và không hon. Các th? h? phiên b?n m?i hon có kh? nang mang l?i **giá/hi?u nang** t?t hon cho h?u h?t workload. Trong t?t c? các tru?ng h?p tôi dã xem xét, các phiên b?n **th? h? th? 4** v?a **ch?m hon** v?a **d?t hon** so v?i **th? h? th? 5**, vì v?y *optimal* th?c ra **không h? "t?i uu"** nhu cái tên c?a nó!

Cu?i cùng, *optimal* **không bao g?m** các phiên b?n dùng **b? x? lý AWS Graviton**, v?n du?c thi?t k? riêng d? mang l?i **giá/hi?u nang vu?t tr?i** cho nhi?u lo?i workload.

## Nâng c?p t? c?u hình "optimal"

Hôm nay, chúng tôi dã ra m?t m?t b? **danh m?c lo?i phiên b?n (instance type categories)** m?i d? c?i thi?n tr?i nghi?m c?a b?n v?i tính nang l?a ch?n instance c?a Batch. Gi? dây b?n có th? ch?n default_x86_64 cho m?t t?p các **h? instance** dùng CPU **x86**, và default_arm64 cho m?t t?p các **instance** dùng CPU **AWS Graviton**. Danh sách **instance type** này s? **không tinh** và s? thay d?i theo th?i gian khi chúng tôi gi?i thi?u các **h? instance** m?i. B?n có th? tìm ph?n ánh x? gi?a t?ng **danh m?c** và t?p **h? instance** theo t?ng **Region** trong trang tài li?u [**Instance type compute table**](https://docs.aws.amazon.com/batch/latest/userguide/instance-type-compute-table.html); ví d?, ph?n ánh x? c?a default_arm64 t?i th?i di?m ra m?t tính nang s? nhu sau:

| Vùng/Khu v?c (Regions) | H? phiên b?n (instance families) |
| :---- | :---- |
| T?t c? các Vùng AWS h? tr? AWS Batch | m6g, c6g, r6g c7g |

*B?ng 1. B?n ánh x? c?a **danh m?c lo?i phiên b?n*** default_arm64 *t?i các **h? phiên b?n c? th?** trong các **Vùng (Regions)** có h? tr? **AWS Batch**.*

Các ánh x? m?c d?nh **không** bao g?m các phiên b?n tang t?c (accelerated instances) theo thi?t k?. Chúng tôi **r?t khuy?n ngh?** b?n ch? d?nh c? th? các lo?i phiên b?n n?u workload c?a b?n du?c hu?ng l?i t? các phiên b?n tang t?c. Ngoài ra, chúng tôi khuy?n ngh? **d?nh nghia riêng** m?t **job queue** và **compute environment** tách bi?t v?i các c?m instance **không tang t?c**. Khi tài nguyên du?c tách riêng, Batch có th? dua ra các quy?t d?nh co giãn (scaling) **t?t hon** cho workload c?a b?n và **ngan** vi?c l?p l?ch các job không tang t?c lên các instance tang t?c, di?u có th? d?n d?n **chi phí phát sinh**.

Tuong t? nhu tru?c dây v?i *optimal*, b?n v?n có th? **d?nh nghia b? sung** các **instance type** bên c?nh các danh m?c default_*. Batch s? xem xét **toàn b? danh sách** b?n dã khai báo khi l?a ch?n **instance type** d? ch?y các job.

## Chuy?n d?i t? *optimal*

Chúng tôi khuy?n ngh? b?n c?p nh?t các môi tru?ng Batch d? áp d?ng các danh m?c m?i. Tuy nhiên, b?n **không b?t bu?c** ph?i c?p nh?t. Các môi tru?ng tính toán (compute environments) AWS Batch hi?n có dang s? d?ng *optimal* v?n **h?p l?**. Các thao tác API [**CreateComputeEnvironment**](https://docs.aws.amazon.com/batch/latest/APIReference/API_CreateComputeEnvironment.html) và [**UpdateComputeEnvironment**](https://docs.aws.amazon.com/batch/latest/APIReference/API_UpdateComputeEnvironment.html) v?n ch?p nh?n *optimal* nhu m?t giá tr? h?p l?. Hành vi c?a *optimal* s? **gi? nguyên** cho d?n **d?u tháng 11 nam 2025**. Sau th?i di?m dó, *optimal* s? **hành x? gi?ng** v?i danh m?c lo?i phiên b?n default_x86_64.

M?t l?n n?a, sau **d?u tháng 11 nam 2025**, *optimal* s? **không còn** là m?t ánh x? tinh t?i các phiên b?n **th? h? th? 4** (n?u kh? d?ng) và s? **thay d?i theo th?i gian** khi AWS gi?i thi?u các h? phiên b?n m?i. N?u b?n mu?n **duy trì** t?p phiên b?n hi?n t?i cho *optimal*, b?n nên c?p nh?t (các) môi tru?ng tính toán c?a mình d? **ch? d?nh c? th?** các **instance type** dó.

Chúng tôi khuy?n ngh? m?i **môi tru?ng tính toán m?i** mà b?n t?o hãy s? d?ng các danh m?c default_* m?i. Cá nhân tôi cung khuy?n ngh? b?n ki?m tra xem ?ng d?ng c?a mình có th? hu?ng l?i t? **Graviton** hay không b?ng cách t?o **container cho Arm** và d?nh nghia m?t **compute environment** cùng **job queue** dùng default_arm64. R?t có th? b?n s? nh?n du?c m?t k?t qu? **nhu mong mu?n**!

## K?t lu?n

Chúng tôi r?t mong b?n dùng th? các danh m?c lo?i phiên b?n (instance type) m?c d?nh default_* m?i. Chúng tôi tin r?ng vi?c d?n d?n áp d?ng các th? h? instance m?i hon theo th?i gian s? giúp workload c?a b?n v?n hành hi?u qu? và ti?t ki?m chi phí. Ð? b?t d?u s? d?ng các danh m?c m?i, hãy dang nh?p vào **B?ng di?u khi?n qu?n tr? AWS Batch (AWS Batch management console)**, ho?c tham kh?o hu?ng d?n t?o **môi tru?ng tính toán EC2** **du?c qu?n lý** (**managed EC2 compute environment)** trong **S? tay hu?ng d?n (User Guide)** c?a chúng tôi.

---

**Angel Pizarro** là Principal Developer Advocate v? HPC (High-Performance Computing  di?n toán hi?u nang cao) và khoa h?c tính toán. Anh có n?n t?ng v? phát tri?n ?ng d?ng tin-sinh h?c và xây d?ng ki?n trúc h? th?ng cho di?n toán có kh? nang m? r?ng trong genomics và các linh v?c khoa h?c s? s?ng thông lu?ng cao khác.
