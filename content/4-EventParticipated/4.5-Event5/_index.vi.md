---
title: "Sự kiện 5"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

# Báo Cáo Tóm Tắt: "Workshop AI/ML/GenAI trên AWS"

### Thông Tin Sự Kiện

- **Sự kiện**: Workshop AI/ML/GenAI trên AWS
- **Ngày**: Thứ Bảy, 15 tháng 11 năm 2025
- **Thời gian**: 8:30 AM - 12:00 PM (Buổi Sáng)
- **Địa điểm**: Văn phòng AWS Việt Nam, Tòa nhà Bitexco Financial Tower, số 2 đường Hải Triều, phường Bến Nghé, Quận 1, TP. Hồ Chí Minh
- **Vai trò**: Người tham dự

---

## Tổng Quan Sự Kiện

Workshop nửa ngày này cung cấp giới thiệu toàn diện về các dịch vụ Trí tuệ Nhân tạo, Machine Learning và Generative AI có sẵn trên AWS. Buổi học được thiết kế riêng cho thị trường Việt Nam, bao gồm cả quy trình ML truyền thống với Amazon SageMaker và khả năng Generative AI tiên tiến với Amazon Bedrock. Thông qua các demo trực tiếp, hướng dẫn thực hành và ví dụ thực tế, người tham gia có được hiểu biết về việc xây dựng và triển khai các giải pháp AI/ML trên AWS.

---

## Chi Tiết Các Phần

### **8:30 – 9:00 AM | Chào Mừng & Giới Thiệu**

Workshop bắt đầu với không khí chào đón tập trung vào xây dựng kết nối cộng đồng:

- **Đăng Ký và Networking**: 
  - Gặp gỡ và chào hỏi với những người đam mê AI/ML
  - Trao đổi thông tin liên lạc và lý lịch chuyên môn
  - Hỗn hợp người tham dự đa dạng: developers, data scientists, solution architects và business leaders

- **Tổng Quan Workshop và Mục Tiêu Học Tập**:
  - Hiểu danh mục dịch vụ AWS AI/ML
  - Học khi nào sử dụng SageMaker vs. Bedrock
  - Có được kỹ năng thực tế trong xây dựng ứng dụng AI
  - Khám phá use cases thực tế và success stories

- **Hoạt Động Ice-Breaker**:
  - Người tham gia chia sẻ mức độ kinh nghiệm AI/ML của họ
  - Thảo luận về các thách thức hiện tại trong triển khai giải pháp AI
  - Kỳ vọng và use cases cụ thể người tham gia muốn khám phá

- **Bối Cảnh AI/ML tại Việt Nam**:
  - Sự áp dụng AI ngày càng tăng trên các ngành (e-commerce, fintech, healthcare)
  - Phát triển nguồn nhân lực và đối tác với các trường đại học
  - Sáng kiến của chính phủ hỗ trợ chuyển đổi số
  - Thách thức: Tính sẵn có của dữ liệu, chi phí hạ tầng, khoảng cách kỹ năng
  - Success stories từ các công ty Việt Nam sử dụng dịch vụ AWS AI/ML

**Insights Chính**: 
- Việt Nam đang nhanh chóng chấp nhận AI/ML với sự hỗ trợ mạnh mẽ từ chính phủ và khu vực tư nhân
- Các rào cản chính đang được giải quyết thông qua cloud platforms và các sáng kiến giáo dục
- AWS cung cấp các công cụ dễ tiếp cận để dân chủ hóa AI/ML cho các tổ chức mọi quy mô

---

### **9:00 – 10:30 AM | Tổng Quan Dịch Vụ AWS AI/ML**

Phần chuyên sâu này khám phá Amazon SageMaker như một nền tảng ML toàn diện:

#### **Amazon SageMaker - Nền Tảng ML End-to-End**

Tổng quan hoàn chỉnh về khả năng của SageMaker như một nền tảng thống nhất cho toàn bộ vòng đời machine learning:

- **Triết Lý Nền Tảng**:
  - Loại bỏ công việc nặng nhọc khỏi ML workflows
  - Cung cấp công cụ cho data scientists, ML engineers và developers
  - Cho phép cộng tác giữa các teams
  - Tích hợp với hệ sinh thái AWS rộng lớn hơn

#### **Chuẩn Bị và Gắn Nhãn Dữ Liệu**

- **SageMaker Data Wrangler**:
  - Giao diện trực quan cho data preparation
  - 300+ data transformations có sẵn
  - Báo cáo data quality và insights
  - Xuất sang feature store hoặc training

- **SageMaker Ground Truth**:
  - Lực lượng human labeling (công khai, riêng tư, vendor)
  - Automated data labeling sử dụng active learning
  - Quy trình labeling có sẵn (text, image, video)
  - Cơ chế quality control và consensus
  - Giảm chi phí thông qua machine learning-assisted labeling

- **SageMaker Feature Store**:
  - Repository tập trung cho ML features
  - Online và offline feature serving
  - Feature versioning và lineage tracking
  - Giảm feature engineering trùng lặp

#### **Training, Tuning và Deployment Mô Hình**

- **Training Options**:
  - **Built-in Algorithms**: Thuật toán sẵn có cho các tác vụ phổ biến (XGBoost, Linear Learner, v.v.)
  - **Custom Training**: Mang training scripts của riêng bạn (PyTorch, TensorFlow, scikit-learn)
  - **SageMaker Training Jobs**: Managed training infrastructure
  - **Distributed Training**: Multi-GPU và multi-node training
  - **Spot Instance Training**: Tiết kiệm chi phí lên đến 90%

- **Hyperparameter Tuning**:
  - Automatic model tuning với Bayesian optimization
  - Parallel training jobs cho thử nghiệm nhanh hơn
  - Early stopping để tiết kiệm resources
  - Warm start từ tuning jobs trước

- **Model Deployment**:
  - **Real-time Endpoints**: Predictions độ trễ thấp
  - **Batch Transform**: Xử lý large datasets
  - **Serverless Inference**: Auto-scaling không cần quản lý infrastructure
  - **Multi-Model Endpoints**: Deploy nhiều models lên một endpoint
  - **Model Monitoring**: Drift detection và data quality monitoring

#### **Khả Năng MLOps Tích Hợp**

- **SageMaker Pipelines**:
  - CI/CD cho machine learning
  - Điều phối ML workflows
  - Versioning và lineage tracking
  - Tích hợp với CI/CD tools

- **SageMaker Model Registry**:
  - Catalog model tập trung
  - Model versioning và approval workflows
  - Tích hợp với deployment pipelines
  - Model cards cho documentation

- **SageMaker Experiments**:
  - Tracking training runs và parameters
  - So sánh model performance
  - Tổ chức experiments thành trials
  - Visualizing metrics và artifacts

- **SageMaker Clarify**:
  - Phát hiện bias trong ML models
  - Explainability và interpretability
  - Feature importance analysis
  - Model transparency cho compliance

#### **Demo Trực Tiếp: SageMaker Studio Walkthrough**

Giảng viên demo toàn diện SageMaker Studio, IDE cho ML:

1. **Data Exploration**: 
   - Load và visualize sample dataset (dự đoán customer churn)
   - Sử dụng Data Wrangler cho feature engineering
   - Tạo data quality reports

2. **Model Training**:
   - Viết training script với TensorFlow
   - Cấu hình training job parameters
   - Launch distributed training
   - Monitor training progress với CloudWatch metrics

3. **Hyperparameter Tuning**:
   - Thiết lập tuning job với nhiều hyperparameters
   - Xem xét tuning results và best model selection

4. **Model Deployment**:
   - Deploy model lên real-time endpoint
   - Test predictions với sample data
   - Thiết lập CloudWatch alarms cho monitoring

5. **MLOps Pipeline**:
   - Tạo SageMaker Pipeline
   - Tự động hóa data preprocessing, training và deployment
   - Version control và model registry integration

**Bài Học Chính từ Demo**:
- SageMaker Studio cung cấp môi trường thống nhất cho tất cả ML tasks
- Built-in integrations giảm đáng kể boilerplate code
- Managed infrastructure cho phép tập trung vào model development
- MLOps capabilities cho phép production-grade ML systems

---

### **10:30 – 10:45 AM | Giải Lao**

Cơ hội networking với người tham gia và thành viên team AWS

---

### **10:45 AM – 12:00 PM | Generative AI với Amazon Bedrock**

Phần thú vị này tập trung vào khả năng Generative AI mới nhất:

#### **Foundation Models: Claude, Llama, Titan**

Tổng quan toàn diện về các foundation models có sẵn trên Bedrock:

- **So Sánh Models**:

  | Model | Provider | Điểm Mạnh | Use Cases |
  |-------|----------|-----------|-----------|
  | **Claude (2 & 3)** | Anthropic | Long context, safety, reasoning | Document analysis, coding assistance, complex conversations |
  | **Llama 2 & 3** | Meta | Open source, multilingual | General purpose, cost-sensitive applications |
  | **Amazon Titan** | AWS | Cost-effective, integration | Text generation, summarization, embeddings |
  | **Jurassic-2** | AI21 Labs | Language understanding | Content generation, text improvement |
  | **Stable Diffusion** | Stability AI | Image generation | Creative assets, product visualization |

- **Hướng Dẫn Lựa Chọn**:
  - **Task Complexity**: Reasoning phức tạp hơn → Claude
  - **Context Length**: Tài liệu dài → Claude 3 (200K tokens)
  - **Cost Optimization**: Khối lượng lớn → Titan hoặc Llama
  - **Multilingual**: Ứng dụng toàn cầu → Llama hoặc Claude
  - **Image Generation**: Nhu cầu sáng tạo → Stable Diffusion

#### **Prompt Engineering: Kỹ Thuật và Best Practices**

Deep dive vào crafting effective prompts:

- **Nguyên Tắc Cơ Bản**:
  - Cụ thể và rõ ràng trong instructions
  - Cung cấp context và background
  - Định nghĩa expected output format
  - Sử dụng examples khi cần
  - Iterate và refine prompts

- **Chain-of-Thought (CoT) Reasoning**:
  - Khuyến khích step-by-step thinking
  - Cải thiện accuracy trên complex problems
  - Ví dụ: "Let's solve this step by step:"
  - Breaking down multi-step reasoning tasks

- **Few-Shot Learning**:
  - Cung cấp examples trong prompt
  - Demonstrating desired behavior
  - Pattern recognition từ examples
  - Cân bằng examples vs. token usage

- **Kỹ Thuật Nâng Cao**:
  - **Role Playing**: "You are an expert financial analyst..."
  - **System Prompts**: Setting consistent behavior
  - **Temperature Control**: Creativity vs. consistency
  - **Token Management**: Tối ưu cho cost và latency

#### **Retrieval-Augmented Generation (RAG)**

Kiến trúc toàn diện để grounding LLMs với dữ liệu enterprise:

- **RAG Architecture Components**:
  1. **Document Ingestion**: Loading và chunking documents
  2. **Embedding Generation**: Converting text sang vectors
  3. **Vector Storage**: Storing embeddings (OpenSearch, pgvector, FAISS)
  4. **Semantic Search**: Finding relevant context
  5. **Prompt Augmentation**: Injecting context vào prompts
  6. **LLM Generation**: Producing grounded responses

- **Amazon Bedrock Knowledge Bases**:
  - Fully managed RAG solution
  - Automatic document ingestion từ S3
  - Built-in embedding generation (Titan Embeddings)
  - Tích hợp với vector databases
  - Source attribution trong responses
  - Hỗ trợ nhiều document formats (PDF, Word, HTML)

- **Lợi Ích của RAG**:
  - Giảm hallucinations với factual grounding
  - Incorporating proprietary/private data
  - Keeping information up-to-date không cần retraining
  - Providing source citations cho transparency

#### **Bedrock Agents: Multi-Step Workflows**

Xây dựng autonomous agents có thể take actions:

- **Agent Capabilities**:
  - Natural language understanding của user intent
  - Breaking down complex tasks thành steps
  - Calling APIs và Lambda functions
  - Maintaining conversation context
  - Handling multi-turn interactions

- **Tool Integration**:
  - Function calling cho external systems
  - Database queries
  - API invocations
  - Custom business logic execution

- **Use Cases**:
  - Customer service automation
  - IT helpdesk agents
  - Data analysis assistants
  - Booking và scheduling systems

#### **Guardrails: Safety và Content Filtering**

Implementing responsible AI practices:

- **Amazon Bedrock Guardrails**:
  - Content filtering (hate speech, violence, profanity)
  - PII detection và redaction
  - Topic restrictions (denied topics)
  - Word filters (custom blocked terms)
  - Response quality controls

- **Safety Mechanisms**:
  - Input validation trước LLM processing
  - Output validation trước khi returning to users
  - Contextual grounding verification
  - Toxicity scoring

- **Compliance và Privacy**:
  - GDPR compliance thông qua PII redaction
  - Audit logging cho tất cả interactions
  - Regional data residency options

#### **Demo Trực Tiếp: Xây Dựng Generative AI Chatbot**

End-to-end demonstration của việc tạo customer support chatbot:

**Bước 1: Knowledge Base Setup**
- Upload company FAQ documents lên S3
- Tạo Bedrock Knowledge Base
- Cấu hình embeddings với Titan Embeddings
- Test semantic search queries

**Bước 2: Agent Configuration**
- Định nghĩa agent instructions và personality
- Kết nối Knowledge Base cho RAG
- Thêm Lambda function cho order lookup
- Cấu hình conversation flow

**Bước 3: Guardrails Implementation**
- Thiết lập content filters
- Enable PII redaction cho customer data
- Cấu hình topic restrictions
- Test với various inputs

**Bước 4: Testing và Iteration**
- Demo conversations showing:
  - FAQ answering từ Knowledge Base
  - Order status lookup qua Lambda
  - Multi-turn conversations
  - Guardrails blocking inappropriate content
  - Source attribution cho answers

**Bước 5: Deployment Considerations**
- Integration options (API, SDK, web UI)
- Monitoring với CloudWatch
- Cost optimization strategies
- Scaling considerations

**Bài Học Chính từ Demo**:
- Bedrock đơn giản hóa đáng kể GenAI application development
- RAG là thiết yếu cho enterprise applications yêu cầu thông tin hiện tại, chính xác
- Guardrails là quan trọng cho production deployments
- Agents cho phép complex, multi-step workflows không cần extensive code
- Source attribution xây dựng trust với end users

---

### **12:00 PM | Kết Thúc Workshop & Trưa**

Workshop kết thúc với:

- **Q&A Session**: Người tham gia hỏi về specific use cases và implementation challenges
- **Resource Sharing**: Links đến AWS documentation, workshops và learning resources
- **Next Steps**: Recommendations cho hands-on practice và certification paths
- **Networking**: Tiếp tục thảo luận trong bữa trưa tự sắp xếp

---

## Suy Nghĩ Cá Nhân & Giá Trị Thu Được

Workshop này cực kỳ quý giá cho việc hiểu AI/ML landscape trên AWS:

1. **Hiểu Biết AI/ML Toàn Diện**: Có được sự rõ ràng về full spectrum từ traditional ML (SageMaker) đến Generative AI (Bedrock)

2. **Kỹ Năng Triển Khai Thực Tế**: Live demos cung cấp hiểu biết hands-on về xây dựng ứng dụng AI thực tế

3. **Bedrock Knowledge**: Deep dive vào foundation models, prompt engineering và RAG architectures lấp đầy các khoảng trống kiến thức quan trọng

4. **MLOps Awareness**: Hiểu MLOps capabilities của SageMaker nhấn mạnh tầm quan trọng của production-grade ML systems

5. **Vietnam Context**: Học về AI/ML adoption tại Việt Nam cung cấp local market insights quý giá cho career planning

6. **Responsible AI**: Nhấn mạnh guardrails và safety mechanisms củng cố tầm quan trọng của ethical AI implementation

7. **Decision Framework**: Hướng dẫn rõ ràng về chọn giữa các models và services khác nhau giúp với architectural decisions

8. **Networking Opportunity**: Kết nối với data scientists, ML engineers và AWS experts, mở rộng professional network

---

## Ứng Dụng vào Công Việc Hiện Tại và Projects Tương Lai

Kiến thức thu được có ứng dụng ngay lập tức và tương lai:

**Ứng Dụng Ngay**:
- Giờ có thể recommend appropriate AWS AI/ML services cho different use cases
- Hiểu RAG architecture cho phép better documentation và knowledge management solutions
- Prompt engineering techniques cải thiện interactions với AI tools

**Ý Tưởng Projects Tương Lai**:
- Xây dựng documentation chatbot sử dụng Bedrock Knowledge Bases cho FCJ community
- Implementing intelligent search sử dụng embeddings và semantic similarity
- Tạo ML pipelines với SageMaker cho predictive analytics projects
- Developing content generation tools cho technical writing

**Phát Triển Nghề Nghiệp**:
- AWS Certified Machine Learning - Specialty certification path
- Hands-on projects với SageMaker và Bedrock
- Contributing to AI/ML community tại Việt Nam
- Exploring AI/ML engineering roles

---

## Kết Luận

Workshop AI/ML/GenAI trên AWS là giới thiệu tuyệt vời về lĩnh vực artificial intelligence đang phát triển nhanh chóng trên cloud platforms. Cách tiếp cận cân bằng bao gồm cả traditional machine learning với SageMaker và cutting-edge generative AI với Bedrock cung cấp hiểu biết toàn diện về AWS AI/ML portfolio.

Live demonstrations đặc biệt quý giá, showing practical implementations thay vì chỉ theoretical concepts. Seeing RAG in action và building functioning chatbot demystified Generative AI và làm cho nó cảm thấy accessible cho real-world projects.

Workshop củng cố rằng AI/ML không còn là domain của chỉ large enterprises với massive resources. AWS services democratize AI, làm cho nó accessible cho startups và individual developers. The key là bắt đầu với clear use cases, leveraging managed services và focusing on delivering value thay vì building infrastructure.

Quan trọng nhất, nhấn mạnh về responsible AI thông qua guardrails và thảo luận về MLOps practices cho thấy rằng production AI là về nhiều hơn chỉ training models - nó yêu cầu thoughtful architecture, monitoring và governance.

Tôi rất khuyến nghị workshop này cho bất kỳ ai quan tâm đến AI/ML trên AWS, whether you're a developer looking to add AI capabilities to applications, a data scientist exploring cloud ML platforms, or a business leader evaluating AI opportunities. Kiến thức thu được cung cấp nền tảng vững chắc cho building intelligent applications trên AWS.

Từ giờ trở đi, tôi dự định theo đuổi hands-on projects với cả SageMaker và Bedrock, work toward AWS Machine Learning Specialty certification và explore opportunities to apply AI/ML in my internship projects và future career.
