---
title: "Sự kiện 4"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Báo Cáo Tóm Tắt: "DevOps on AWS - Workshop Cả Ngày"

### Thông Tin Sự Kiện

- **Sự kiện**: Workshop DevOps on AWS
- **Ngày**: Thứ Hai, 17 tháng 11 năm 2025
- **Thời gian**: 8:30 AM - 5:00 PM (Cả ngày)
- **Địa điểm**: Văn phòng AWS Việt Nam, Tòa nhà Bitexco Financial Tower, số 2 đường Hải Triều, phường Bến Nghé, Quận 1, TP. Hồ Chí Minh
- **Vai trò**: Người tham dự

---

## Tổng Quan Sự Kiện

Workshop cả ngày toàn diện này cung cấp khám phá sâu về các thực hành và công cụ DevOps trên AWS. Buổi học bao gồm toàn bộ vòng đời DevOps từ source control đến monitoring, với các demo thực hành về CI/CD pipelines, Infrastructure as Code, container orchestration và các giải pháp observability. Workshop cân bằng giữa khái niệm lý thuyết với triển khai thực tế, có các demo trực tiếp và case studies thực tế từ cả startups và enterprises.

---

## Buổi Sáng (8:30 AM – 12:00 PM)

### **8:30 – 9:00 AM | Chào Mừng & Tư Duy DevOps**

Workshop bắt đầu với giới thiệu toàn diện về văn hóa và nguyên tắc DevOps:

- **Ôn tập buổi AI/ML trước**: Tóm tắt kết nối giữa AI/ML workflows với các thực hành tự động hóa DevOps

- **Văn Hóa và Nguyên Tắc DevOps**:
  - **Collaboration (Cộng tác)**: Phá bỏ rào cản giữa đội development và operations
  - **Automation (Tự động hóa)**: Tự động hóa các tác vụ lặp đi lặp lại để tăng hiệu quả và giảm lỗi con người
  - **Continuous Improvement (Cải tiến liên tục)**: Phương pháp lặp để tối ưu hóa quy trình và hệ thống
  - **Fast Feedback Loops**: Phát hiện và giải quyết vấn đề nhanh chóng
  - **Shared Responsibility (Trách nhiệm chung)**: Mọi người đều sở hữu chất lượng và độ tin cậy của hệ thống

- **Lợi Ích Chính của DevOps**:
  - Rút ngắn thời gian đưa sản phẩm ra thị trường
  - Cải thiện tần suất deployment
  - Giảm tỷ lệ thất bại của releases mới
  - Rút ngắn thời gian giữa các fixes
  - MTTR (Mean Time to Recovery) nhanh hơn

- **Các Chỉ Số DevOps (DORA Metrics)**:
  - **Deployment Frequency**: Tần suất code được deploy lên production
  - **Lead Time for Changes**: Thời gian từ commit đến production deployment
  - **Mean Time to Recovery (MTTR)**: Thời gian trung bình để phục hồi sau lỗi
  - **Change Failure Rate**: Phần trăm deployments gây ra lỗi

**Bài Học Chính**: Hiểu rằng DevOps không chỉ về công cụ, mà về văn hóa, cộng tác và tư duy cải tiến liên tục.

---

### **9:00 – 10:30 AM | Các Dịch Vụ AWS DevOps – CI/CD Pipeline**

Phần chuyên sâu này bao gồm toàn bộ chuỗi công cụ AWS CI/CD:

#### **Source Control**
- **AWS CodeCommit**: 
  - Git repositories được quản lý hoàn toàn trên AWS
  - Mã hóa at rest và in transit
  - Tích hợp với IAM để kiểm soát truy cập
  - Bảo vệ branch và chiến lược merge

- **Chiến Lược Git**:
  - **GitFlow**: Feature branches, develop, release và main branches cho structured releases
  - **Trunk-Based Development**: Short-lived feature branches merge trực tiếp vào main/trunk
  - So sánh các cách tiếp cận và khi nào dùng mỗi cách

#### **Build & Test**
- **AWS CodeBuild**:
  - Dịch vụ build được quản lý để compile code và chạy tests
  - Cấu hình `buildspec.yml` cho các build phases
  - Environment variables và parameter management
  - Tích hợp với ECR cho container image builds
  - Caching strategies để builds nhanh hơn

- **Testing Pipelines**:
  - Unit tests, integration tests và security scans
  - Parallel test execution để feedback nhanh hơn
  - Test result reporting và metrics

#### **Deployment**
- **AWS CodeDeploy**:
  - **Blue/Green Deployment**: Chuyển traffic giữa hai môi trường giống hệt nhau
  - **Canary Deployment**: Từ từ roll out changes cho một nhóm users
  - **Rolling Updates**: Cập nhật tăng dần để duy trì availability
  - Automatic rollback khi deployment thất bại
  - Tích hợp với Auto Scaling Groups và Lambda functions

#### **Orchestration**
- **AWS CodePipeline**:
  - Automated workflow điều phối tất cả các giai đoạn CI/CD
  - Visual pipeline editor và stage management
  - Tích hợp với third-party tools (GitHub, Jenkins, v.v.)
  - Approval stages cho production deployments
  - Pipeline execution history và artifact management

#### **Demo Trực Tiếp: Full CI/CD Pipeline**
Giảng viên demo một pipeline hoàn chỉnh:
1. Code commit triggers CodePipeline
2. CodeBuild compiles và tests ứng dụng
3. Docker image pushed lên Amazon ECR
4. CodeDeploy thực hiện Blue/Green deployment lên ECS
5. Automatic rollback khi health checks thất bại

**Bài Học Chính**: 
- Luôn triển khai automated testing trước deployment stages
- Sử dụng Blue/Green deployments cho zero-downtime releases
- Cấu hình automatic rollbacks để giảm thiểu tác động của failed deployments
- Monitor pipeline execution times và tối ưu build caching

---

### **10:30 – 10:45 AM | Giải Lao**

---

### **10:45 AM – 12:00 PM | Infrastructure as Code (IaC)**

Phần này khám phá các công cụ Infrastructure as Code của AWS:

#### **AWS CloudFormation**
- **Templates**: Định nghĩa YAML/JSON của AWS resources
- **Stacks**: Các instances được deploy của templates như các đơn vị đơn
- **Change Sets**: Preview thay đổi infrastructure trước khi apply
- **Drift Detection**: Xác định thay đổi thủ công đối với resources
- **StackSets**: Deploy stacks trên nhiều accounts và regions
- **Best Practices**:
  - Templates có tham số để tái sử dụng
  - Sử dụng nested stacks cho infrastructure modular
  - Triển khai stack policies để ngăn xóa nhầm

#### **AWS CDK (Cloud Development Kit)**
- **Hỗ Trợ Ngôn Ngữ Lập Trình**: TypeScript, Python, Java, C#, Go
- **Constructs**: 
  - **L1 (CloudFormation Resources)**: Ánh xạ trực tiếp đến CloudFormation resources
  - **L2 (Curated Constructs)**: Abstractions cấp cao hơn với defaults hợp lý
  - **L3 (Patterns)**: Các mẫu kiến trúc hoàn chỉnh
- **Reusable Patterns**: Chia sẻ infrastructure code giữa các projects
- **Ưu Điểm CDK**:
  - Type safety và IDE autocomplete
  - Sử dụng ngôn ngữ lập trình quen thuộc
  - Testing infrastructure code với unit tests
  - Ngắn gọn hơn CloudFormation templates

#### **Demo Trực Tiếp: Deploying với CloudFormation và CDK**
Hai demo song song:
1. **CloudFormation**: Deploy VPC với subnets, NAT gateways và route tables
2. **CDK (Python)**: Deploy cùng infrastructure với code ngắn hơn đáng kể

#### **Thảo Luận: Chọn Giữa Các Công Cụ IaC**
- **CloudFormation**: Hỗ trợ AWS native, declarative, visual designer
- **CDK**: Ngôn ngữ lập trình, reusable components, tốt cho logic phức tạp
- **Terraform**: Hỗ trợ multi-cloud, cộng đồng lớn, extensive providers
- **Khi nào dùng mỗi tool dựa trên yêu cầu project và chuyên môn team**

**Bài Học Chính**:
- Bắt đầu với CloudFormation cho infrastructures đơn giản
- Sử dụng CDK cho các mẫu infrastructure phức tạp, có thể tái sử dụng
- Luôn version control IaC code của bạn
- Triển khai CI/CD cho infrastructure deployments
- Test thay đổi infrastructure trong môi trường non-production trước

---

## Giải Lao Trưa (12:00 – 1:00 PM)
Tự sắp xếp ăn trưa

---

## Buổi Chiều (1:00 – 5:00 PM)

### **1:00 – 2:30 PM | Container Services trên AWS**

Phạm vi toàn diện về containerization và orchestration:

#### **Docker Fundamentals**
- **Microservices Architecture**: Chia monoliths thành các services nhỏ, độc lập
- **Lợi Ích Containerization**:
  - Môi trường nhất quán từ development đến production
  - Hiệu quả tài nguyên so với VMs
  - Deployment và scaling nhanh
  - Isolation và security boundaries

#### **Amazon ECR (Elastic Container Registry)**
- **Image Storage**: Private Docker container registry
- **Image Scanning**: Automated vulnerability scanning khi push
- **Lifecycle Policies**: Tự động cleanup old images để giảm chi phí
- **Cross-Region Replication**: Disaster recovery và global deployments
- **Tích Hợp với ECS và EKS**: Image pulling liền mạch

#### **Amazon ECS (Elastic Container Service)**
- **Task Definitions**: Các đặc tả container (CPU, memory, networking)
- **Services**: Duy trì số lượng mong muốn của running tasks
- **Launch Types**:
  - **EC2**: Chạy containers trên managed EC2 instances
  - **Fargate**: Serverless container execution
- **Service Discovery**: DNS-based service discovery với Cloud Map
- **Load Balancing**: Tích hợp với ALB/NLB cho phân phối traffic

#### **Amazon EKS (Elastic Kubernetes Service)**
- **Kubernetes trên AWS**: Managed Kubernetes control plane
- **Worker Nodes**: EC2 hoặc Fargate cho pod execution
- **kubectl**: Command-line tool cho cluster management
- **Helm Charts**: Package manager cho Kubernetes applications
- **Add-ons**: CoreDNS, kube-proxy, VPC CNI plugin
- **IRSA (IAM Roles for Service Accounts)**: IAM permissions chi tiết cho pods

#### **AWS App Runner**
- **Simplified Deployment**: Deploy containers từ source code hoặc images
- **Automatic Scaling**: Dựa trên traffic patterns
- **Built-in Load Balancing**: Không cần cấu hình
- **Use Cases**: Web applications và APIs đơn giản không cần quản lý infrastructure

#### **Demo Trực Tiếp & Case Study: So Sánh Microservices Deployment**
Giảng viên demo deploy cùng một microservices application trên:
1. **ECS Fargate**: Setup nhanh, serverless, pay-per-use
2. **EKS**: Kiểm soát nhiều hơn, Kubernetes ecosystem, complex workloads
3. **App Runner**: Deployment nhanh nhất, limited customization

**Thảo Luận So Sánh**:
- **ECS**: Tốt nhất cho AWS-native deployments, đơn giản hơn Kubernetes
- **EKS**: Tốt nhất cho chuyên môn Kubernetes, chiến lược multi-cloud, orchestration phức tạp
- **App Runner**: Tốt nhất cho ứng dụng đơn giản, quản lý infrastructure tối thiểu

**Bài Học Chính**:
- Chọn ECS cho microservices AWS-centric không có độ phức tạp Kubernetes
- Chọn EKS khi cần Kubernetes features hoặc multi-cloud portability
- Sử dụng Fargate để loại bỏ quản lý infrastructure
- Triển khai health checks và logging đúng cho tất cả containers
- Sử dụng ECR lifecycle policies để quản lý storage costs

---

### **2:30 – 2:45 PM | Giải Lao**

---

### **2:45 – 4:00 PM | Monitoring & Observability**

Phần quan trọng về observability và operational excellence:

#### **Amazon CloudWatch**
- **Metrics**:
  - Built-in metrics cho AWS services (CPU, network, disk)
  - Custom metrics từ applications
  - High-resolution metrics (1-second granularity)
  - Metric math cho tính toán phức tạp

- **Logs**:
  - **CloudWatch Logs**: Tập trung log aggregation
  - **Log Groups và Streams**: Cấu trúc tổ chức
  - **Insights**: SQL-like queries cho log analysis
  - **Log Retention**: Tối ưu chi phí qua retention policies
  - **Subscription Filters**: Xử lý log real-time với Lambda

- **Alarms**:
  - Threshold-based alarms trên metrics
  - Composite alarms kết hợp nhiều điều kiện
  - Actions: SNS notifications, Auto Scaling, EC2 actions

- **Dashboards**:
  - Custom visualization của metrics và logs
  - Cross-region dashboards cho global visibility
  - Chia sẻ dashboards với stakeholders

#### **AWS X-Ray**
- **Distributed Tracing**: Theo dõi requests qua microservices
- **Service Map**: Biểu diễn trực quan của application architecture
- **Trace Analysis**: Xác định performance bottlenecks
- **Annotations và Metadata**: Thêm context vào traces
- **Tích Hợp**: Làm việc với Lambda, ECS, EKS, API Gateway và nhiều hơn
- **Sampling Rules**: Kiểm soát trace data volume và costs

#### **Demo Trực Tiếp: Full-Stack Observability Setup**
Triển khai hoàn chỉnh observability cho microservices application:
1. **Application Instrumentation**: Thêm X-Ray SDK vào code
2. **Log Aggregation**: Shipping container logs đến CloudWatch
3. **Custom Metrics**: Publishing business metrics
4. **Dashboard Creation**: Xây dựng operational dashboards
5. **Alarm Configuration**: Thiết lập critical alerts
6. **Trace Analysis**: Sử dụng X-Ray để debug latency issues

#### **Best Practices**
- **Chiến Lược Alerting**:
  - Alert về symptoms, không phải causes
  - Giảm alert fatigue với thresholds đúng
  - Sử dụng composite alarms để giảm false positives
  - Triển khai escalation policies

- **Dashboard Design**:
  - Tách operational và business dashboards
  - Bao gồm SLIs (Service Level Indicators) và error rates
  - Sử dụng time ranges nhất quán giữa các widgets
  - Hiển thị dashboards trên monitors của team

- **On-Call Processes**:
  - Runbooks rõ ràng cho common alerts
  - Incident response playbooks
  - Postmortem processes để học hỏi
  - Rotation schedules để ngăn burnout

**Bài Học Chính**:
- Triển khai ba trụ cột của observability: metrics, logs và traces
- Sử dụng CloudWatch cho infrastructure và application monitoring
- Enable X-Ray cho microservices để hiểu request flows
- Thiết lập meaningful alerts cần hành động
- Xây dựng dashboards kể câu chuyện về system health

---

### **4:00 – 4:45 PM | DevOps Best Practices & Case Studies**

Chiến lược triển khai thực tế và ví dụ thực tế:

#### **Deployment Strategies**
- **Feature Flags**:
  - Tách deployment khỏi release
  - Gradual feature rollout cho user segments
  - A/B testing và experimentation
  - Emergency kill switches
  - AWS AppConfig cho feature flag management

- **A/B Testing**:
  - Testing variations để tối ưu user experience
  - Statistical significance trong experiments
  - Tích hợp với CloudWatch cho metrics

#### **Automated Testing**
- **Testing Pyramid**:
  - Unit tests (nhanh, isolated)
  - Integration tests (component interactions)
  - End-to-end tests (full user workflows)
- **Tích Hợp CI/CD**:
  - Fail fast với early testing
  - Parallel test execution
  - Test coverage metrics
  - Security scanning trong pipeline

#### **Incident Management**
- **Quy Trình Incident Response**:
  1. Detection (monitoring và alerting)
  2. Triage (severity assessment)
  3. Investigation (root cause analysis)
  4. Resolution (fix và verify)
  5. Communication (stakeholder updates)
  6. Postmortem (learning và prevention)

- **Postmortem Best Practices**:
  - Blameless culture
  - Timeline of events
  - Root cause analysis (5 Whys)
  - Action items có owners
  - Chia sẻ learnings giữa các teams

#### **Case Studies**

**Case Study 1: Startup DevOps Transformation**
- **Thách Thức**: Manual deployments, frequent production issues, slow feature delivery
- **Giải Pháp**: 
  - Triển khai CI/CD với CodePipeline
  - Containerized applications với ECS Fargate
  - Infrastructure as Code với CDK
  - Comprehensive monitoring với CloudWatch
- **Kết Quả**: 
  - Deployment frequency tăng từ hàng tuần lên nhiều lần mỗi ngày
  - MTTR giảm từ hours xuống minutes
  - Developer productivity cải thiện đáng kể
  - Đạt được zero-downtime deployments

**Case Study 2: Enterprise Multi-Account DevOps**
- **Thách Thức**: Cấu trúc multi-account phức tạp, yêu cầu compliance, coordinated releases
- **Giải Pháp**:
  - AWS Organizations với SCPs
  - Cross-account CI/CD pipelines
  - Centralized logging và monitoring
  - Automated compliance checks trong pipeline
- **Kết Quả**:
  - Consistent deployments trên 50+ AWS accounts
  - Giảm compliance audit time 70%
  - Cải thiện security posture với automated scanning

**Bài Học Chính**:
- Bắt đầu nhỏ và lặp lại các DevOps practices
- Tự động hóa mọi thứ có thể tự động hóa
- Đo lường mọi thứ và dùng data để cải tiến
- Nuôi dưỡng văn hóa học tập và cải tiến liên tục
- Đầu tư vào developer experience để cải thiện productivity

---

### **4:45 – 5:00 PM | Q&A & Tổng Kết**

Phần cuối cho câu hỏi và hướng dẫn nghề nghiệp:

#### **Lộ Trình Nghề Nghiệp DevOps**
- **Entry Level**: Tập trung vào scripting, CI/CD tools và cloud fundamentals
- **Mid Level**: Infrastructure as Code, container orchestration, observability
- **Senior Level**: Architecture design, multi-region deployments, platform engineering
- **Chuyên Môn Hóa**: SRE, Platform Engineering, Cloud Architecture, Security Engineering

#### **Lộ Trình AWS Certification cho DevOps**
Lộ trình certification được đề xuất:
1. **AWS Certified Cloud Practitioner**: Foundation knowledge (tùy chọn cho developers có kinh nghiệm)
2. **AWS Certified Developer – Associate**: Application development trên AWS
3. **AWS Certified DevOps Engineer – Professional**: Comprehensive DevOps practices
4. **AWS Certified Solutions Architect – Professional**: Advanced architecture skills (khuyến nghị cho senior roles)

#### **Tài Nguyên Học Tập**
- AWS Skill Builder cho hands-on labs
- AWS Workshops cho guided projects
- AWS re:Post cho community Q&A
- AWS Whitepapers cho best practices
- Local AWS User Groups và events

---

## Suy Nghĩ Cá Nhân & Giá Trị Thu Được

Workshop DevOps cả ngày này cực kỳ toàn diện và quý giá cho sự phát triển chuyên môn của tôi:

1. **Hiểu Biết Toàn Diện Vòng Đời DevOps**: Đạt được kiến thức end-to-end từ source control đến production monitoring, hiểu cách tất cả các phần kết hợp với nhau

2. **Thành Thạo Công Cụ Thực Hành**: Demo trực tiếp của CodePipeline, CloudFormation, CDK, ECS và CloudWatch cung cấp kỹ năng thực tế tôi có thể áp dụng ngay lập tức

3. **Bối Cảnh Thực Tế**: Case studies từ startups và enterprises cho thấy cách DevOps practices scale và thích nghi với các nhu cầu tổ chức khác nhau

4. **Thành Thạo Infrastructure as Code**: Deep dive vào CloudFormation và CDK làm rõ khi nào dùng mỗi tool và cách cấu trúc infrastructure code

5. **Rõ Ràng Container Orchestration**: Hiểu sự khác biệt giữa ECS, EKS và App Runner giúp tôi chọn công cụ đúng cho các use cases khác nhau

6. **Observability Best Practices**: Học triển khai comprehensive monitoring với metrics, logs và traces là quan trọng cho production operations

7. **Văn Hóa DevOps**: Hiểu rằng DevOps là về văn hóa và collaboration, không chỉ tools, thay đổi cách tôi tiếp cận software delivery

8. **Phát Triển Nghề Nghiệp**: Lộ trình rõ ràng cho DevOps certifications và career progression cung cấp hướng đi cho hành trình học tập của tôi

---

## Ứng Dụng vào Công Việc Hiện Tại

Kiến thức thu được áp dụng trực tiếp vào thực tập và projects của tôi:

- **Workshop Development**: Hiện có thể thêm CI/CD deployment instructions vào S3 VPC endpoint workshop của tôi
- **Infrastructure as Code**: Triển khai CloudFormation/CDK templates cho repeatable deployments
- **Containerization**: Hiểu khi nào recommend ECS vs. EKS cho các scenarios khác nhau
- **Monitoring**: Thiết lập proper CloudWatch dashboards và alarms cho production workloads
- **Documentation**: Tạo runbooks và deployment guides tốt hơn dựa trên DevOps best practices

---

## Kết Luận

Workshop DevOps on AWS là trải nghiệm học tập cả ngày đặc biệt cung cấp cả chiều rộng và chiều sâu trên toàn bộ DevOps landscape. Từ CI/CD pipelines đến container orchestration đến observability, mọi phần đều xây dựng trên kiến thức trước đó đồng thời cung cấp các ví dụ thực tế, hands-on.

Sự kết hợp của nguyên tắc lý thuyết, demo trực tiếp và case studies thực tế làm cho các khái niệm phức tạp trở nên dễ tiếp cận và có thể áp dụng ngay lập tức. Workshop củng cố rằng DevOps thành công là về văn hóa, tự động hóa, đo lường và cải tiến liên tục.

Tôi rất khuyến nghị workshop này cho bất kỳ ai muốn triển khai DevOps practices trên AWS hoặc thăng tiến nghề nghiệp trong cloud operations và site reliability engineering. Các kỹ năng học được ở đây là nền tảng cho software delivery hiện đại và sẽ vô giá trong suốt sự nghiệp của tôi trong cloud computing.

Từ giờ trở đi, tôi dự định theo đuổi chứng chỉ AWS Certified DevOps Engineer - Professional và tiếp tục triển khai các practices này trong projects của mình, đóng góp vào software delivery nhanh hơn, đáng tin cậy hơn.
