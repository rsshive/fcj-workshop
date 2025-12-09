---
title: "Event 5"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---

# Summary Report: "AI/ML/GenAI on AWS Workshop"

### Event Information

- **Event**: AI/ML/GenAI on AWS Workshop
- **Date**: Saturday, November 15th, 2025
- **Time**: 8:30 AM - 12:00 PM (Morning Session)
- **Location**: AWS Vietnam Office, Bitexco Financial Tower, 2 Hai Trieu Street, Ben Nghe Ward, District 1, Ho Chi Minh City
- **My Role**: Attendee

---

## Event Overview

This half-day workshop provided a comprehensive introduction to Artificial Intelligence, Machine Learning, and Generative AI services available on AWS. The session was specifically designed for the Vietnamese market, covering both traditional ML workflows with Amazon SageMaker and cutting-edge Generative AI capabilities with Amazon Bedrock. Through live demonstrations, hands-on guidance, and practical examples, participants gained insights into building and deploying AI/ML solutions on AWS.

---

## Detailed Session Breakdown

### **8:30 – 9:00 AM | Welcome & Introduction**

The workshop began with a welcoming atmosphere focused on building community connections:

- **Participant Registration and Networking**: 
  - Meet and greet with fellow AI/ML enthusiasts
  - Exchange of contact information and professional backgrounds
  - Diverse attendee mix: developers, data scientists, solution architects, and business leaders

- **Workshop Overview and Learning Objectives**:
  - Understanding the AWS AI/ML service portfolio
  - Learning when to use SageMaker vs. Bedrock
  - Gaining practical skills in building AI applications
  - Exploring real-world use cases and success stories

- **Ice-Breaker Activity**:
  - Participants shared their AI/ML experience levels
  - Discussion of current challenges in implementing AI solutions
  - Expectations and specific use cases participants wanted to explore

- **AI/ML Landscape in Vietnam**:
  - Growing adoption of AI across industries (e-commerce, fintech, healthcare)
  - Talent pool development and university partnerships
  - Government initiatives supporting digital transformation
  - Challenges: Data availability, infrastructure costs, skill gaps
  - Success stories from Vietnamese companies using AWS AI/ML services

**Key Insights**: 
- Vietnam is rapidly embracing AI/ML with strong government and private sector support
- Major barriers are being addressed through cloud platforms and education initiatives
- AWS provides accessible tools that democratize AI/ML for organizations of all sizes

---

### **9:00 – 10:30 AM | AWS AI/ML Services Overview**

This intensive session explored Amazon SageMaker as the comprehensive ML platform:

#### **Amazon SageMaker - End-to-End ML Platform**

A complete overview of SageMaker's capabilities as a unified platform for the entire machine learning lifecycle:

- **Platform Philosophy**:
  - Removing heavy lifting from ML workflows
  - Providing tools for data scientists, ML engineers, and developers
  - Enabling collaboration across teams
  - Integrating with the broader AWS ecosystem

#### **Data Preparation and Labeling**

- **SageMaker Data Wrangler**:
  - Visual interface for data preparation
  - 300+ built-in data transformations
  - Data quality and insights reports
  - Export to feature store or training

- **SageMaker Ground Truth**:
  - Human labeling workforce (public, private, vendor)
  - Automated data labeling using active learning
  - Built-in labeling workflows (text, image, video)
  - Quality control and consensus mechanisms
  - Cost reduction through machine learning-assisted labeling

- **SageMaker Feature Store**:
  - Centralized repository for ML features
  - Online and offline feature serving
  - Feature versioning and lineage tracking
  - Reducing feature engineering duplication

#### **Model Training, Tuning, and Deployment**

- **Training Options**:
  - **Built-in Algorithms**: Pre-built algorithms for common tasks (XGBoost, Linear Learner, etc.)
  - **Custom Training**: Bring your own training scripts (PyTorch, TensorFlow, scikit-learn)
  - **SageMaker Training Jobs**: Managed training infrastructure
  - **Distributed Training**: Multi-GPU and multi-node training
  - **Spot Instance Training**: Cost savings up to 90%

- **Hyperparameter Tuning**:
  - Automatic model tuning with Bayesian optimization
  - Parallel training jobs for faster experimentation
  - Early stopping to save resources
  - Warm start from previous tuning jobs

- **Model Deployment**:
  - **Real-time Endpoints**: Low-latency predictions
  - **Batch Transform**: Processing large datasets
  - **Serverless Inference**: Auto-scaling without managing infrastructure
  - **Multi-Model Endpoints**: Deploy multiple models to a single endpoint
  - **Model Monitoring**: Drift detection and data quality monitoring

#### **Integrated MLOps Capabilities**

- **SageMaker Pipelines**:
  - CI/CD for machine learning
  - Orchestrating ML workflows
  - Versioning and lineage tracking
  - Integration with CI/CD tools

- **SageMaker Model Registry**:
  - Centralized model catalog
  - Model versioning and approval workflows
  - Integration with deployment pipelines
  - Model cards for documentation

- **SageMaker Experiments**:
  - Tracking training runs and parameters
  - Comparing model performance
  - Organizing experiments into trials
  - Visualizing metrics and artifacts

- **SageMaker Clarify**:
  - Detecting bias in ML models
  - Explainability and interpretability
  - Feature importance analysis
  - Model transparency for compliance

#### **Live Demo: SageMaker Studio Walkthrough**

The instructor provided a comprehensive demonstration of SageMaker Studio, the IDE for ML:

1. **Data Exploration**: 
   - Loading and visualizing a sample dataset (customer churn prediction)
   - Using Data Wrangler for feature engineering
   - Creating data quality reports

2. **Model Training**:
   - Writing a training script with TensorFlow
   - Configuring training job parameters
   - Launching distributed training
   - Monitoring training progress with CloudWatch metrics

3. **Hyperparameter Tuning**:
   - Setting up tuning job with multiple hyperparameters
   - Reviewing tuning results and best model selection

4. **Model Deployment**:
   - Deploying model to a real-time endpoint
   - Testing predictions with sample data
   - Setting up CloudWatch alarms for monitoring

5. **MLOps Pipeline**:
   - Creating a SageMaker Pipeline
   - Automating data preprocessing, training, and deployment
   - Version control and model registry integration

**Key Learnings from Demo**:
- SageMaker Studio provides a unified environment for all ML tasks
- Built-in integrations significantly reduce boilerplate code
- Managed infrastructure allows focusing on model development
- MLOps capabilities enable production-grade ML systems

---

### **10:30 – 10:45 AM | Coffee Break**

Networking opportunity with fellow participants and AWS team members

---

### **10:45 AM – 12:00 PM | Generative AI with Amazon Bedrock**

This exciting session focused on the latest Generative AI capabilities:

#### **Foundation Models: Claude, Llama, Titan**

Comprehensive overview of available foundation models on Bedrock:

- **Model Comparison**:

  | Model | Provider | Strengths | Use Cases |
  |-------|----------|-----------|-----------|
  | **Claude (2 & 3)** | Anthropic | Long context, safety, reasoning | Document analysis, coding assistance, complex conversations |
  | **Llama 2 & 3** | Meta | Open source, multilingual | General purpose, cost-sensitive applications |
  | **Amazon Titan** | AWS | Cost-effective, integration | Text generation, summarization, embeddings |
  | **Jurassic-2** | AI21 Labs | Language understanding | Content generation, text improvement |
  | **Stable Diffusion** | Stability AI | Image generation | Creative assets, product visualization |

- **Selection Guide**:
  - **Task Complexity**: More complex reasoning → Claude
  - **Context Length**: Long documents → Claude 3 (200K tokens)
  - **Cost Optimization**: High volume → Titan or Llama
  - **Multilingual**: Global applications → Llama or Claude
  - **Image Generation**: Creative needs → Stable Diffusion

#### **Prompt Engineering: Techniques and Best Practices**

Deep dive into crafting effective prompts:

- **Fundamental Principles**:
  - Be specific and clear in instructions
  - Provide context and background
  - Define expected output format
  - Use examples when needed
  - Iterate and refine prompts

- **Chain-of-Thought (CoT) Reasoning**:
  - Encouraging step-by-step thinking
  - Improving accuracy on complex problems
  - Example: "Let's solve this step by step:"
  - Breaking down multi-step reasoning tasks

- **Few-Shot Learning**:
  - Providing examples in the prompt
  - Demonstrating desired behavior
  - Pattern recognition from examples
  - Balancing examples vs. token usage

- **Advanced Techniques**:
  - **Role Playing**: "You are an expert financial analyst..."
  - **System Prompts**: Setting consistent behavior
  - **Temperature Control**: Creativity vs. consistency
  - **Token Management**: Optimizing for cost and latency

#### **Retrieval-Augmented Generation (RAG)**

Comprehensive architecture for grounding LLMs with enterprise data:

- **RAG Architecture Components**:
  1. **Document Ingestion**: Loading and chunking documents
  2. **Embedding Generation**: Converting text to vectors
  3. **Vector Storage**: Storing embeddings (OpenSearch, pgvector, FAISS)
  4. **Semantic Search**: Finding relevant context
  5. **Prompt Augmentation**: Injecting context into prompts
  6. **LLM Generation**: Producing grounded responses

- **Amazon Bedrock Knowledge Bases**:
  - Fully managed RAG solution
  - Automatic document ingestion from S3
  - Built-in embedding generation (Titan Embeddings)
  - Integration with vector databases
  - Source attribution in responses
  - Support for various document formats (PDF, Word, HTML)

- **Benefits of RAG**:
  - Reducing hallucinations with factual grounding
  - Incorporating proprietary/private data
  - Keeping information up-to-date without retraining
  - Providing source citations for transparency

#### **Bedrock Agents: Multi-Step Workflows**

Building autonomous agents that can take actions:

- **Agent Capabilities**:
  - Natural language understanding of user intent
  - Breaking down complex tasks into steps
  - Calling APIs and Lambda functions
  - Maintaining conversation context
  - Handling multi-turn interactions

- **Tool Integration**:
  - Function calling for external systems
  - Database queries
  - API invocations
  - Custom business logic execution

- **Use Cases**:
  - Customer service automation
  - IT helpdesk agents
  - Data analysis assistants
  - Booking and scheduling systems

#### **Guardrails: Safety and Content Filtering**

Implementing responsible AI practices:

- **Amazon Bedrock Guardrails**:
  - Content filtering (hate speech, violence, profanity)
  - PII detection and redaction
  - Topic restrictions (denied topics)
  - Word filters (custom blocked terms)
  - Response quality controls

- **Safety Mechanisms**:
  - Input validation before LLM processing
  - Output validation before returning to users
  - Contextual grounding verification
  - Toxicity scoring

- **Compliance and Privacy**:
  - GDPR compliance through PII redaction
  - Audit logging for all interactions
  - Regional data residency options

#### **Live Demo: Building a Generative AI Chatbot**

End-to-end demonstration of creating a customer support chatbot:

**Step 1: Knowledge Base Setup**
- Uploaded company FAQ documents to S3
- Created Bedrock Knowledge Base
- Configured embeddings with Titan Embeddings
- Tested semantic search queries

**Step 2: Agent Configuration**
- Defined agent instructions and personality
- Connected Knowledge Base for RAG
- Added Lambda function for order lookup
- Configured conversation flow

**Step 3: Guardrails Implementation**
- Set up content filters
- Enabled PII redaction for customer data
- Configured topic restrictions
- Tested with various inputs

**Step 4: Testing and Iteration**
- Demo conversations showing:
  - FAQ answering from Knowledge Base
  - Order status lookup via Lambda
  - Multi-turn conversations
  - Guardrails blocking inappropriate content
  - Source attribution for answers

**Step 5: Deployment Considerations**
- Integration options (API, SDK, web UI)
- Monitoring with CloudWatch
- Cost optimization strategies
- Scaling considerations

**Key Learnings from Demo**:
- Bedrock significantly simplifies GenAI application development
- RAG is essential for enterprise applications requiring current, accurate information
- Guardrails are critical for production deployments
- Agents enable complex, multi-step workflows without extensive code
- Source attribution builds trust with end users

---

### **12:00 PM | Workshop Conclusion & Lunch**

The workshop concluded with:

- **Q&A Session**: Participants asked questions about specific use cases and implementation challenges
- **Resource Sharing**: Links to AWS documentation, workshops, and learning resources
- **Next Steps**: Recommendations for hands-on practice and certification paths
- **Networking**: Continued discussions over self-arranged lunch

---

## Personal Reflections & Value Gained

This workshop was incredibly valuable for understanding the AI/ML landscape on AWS:

1. **Comprehensive AI/ML Understanding**: Gained clarity on the full spectrum from traditional ML (SageMaker) to Generative AI (Bedrock)

2. **Practical Implementation Skills**: Live demos provided hands-on understanding of building real-world AI applications

3. **Bedrock Knowledge**: Deep dive into foundation models, prompt engineering, and RAG architectures filled critical knowledge gaps

4. **MLOps Awareness**: Understanding SageMaker's MLOps capabilities highlighted the importance of production-grade ML systems

5. **Vietnam Context**: Learning about AI/ML adoption in Vietnam provided local market insights valuable for career planning

6. **Responsible AI**: Emphasis on guardrails and safety mechanisms reinforced the importance of ethical AI implementation

7. **Decision Framework**: Clear guidance on choosing between different models and services helps with architectural decisions

8. **Networking Opportunity**: Connected with data scientists, ML engineers, and AWS experts, expanding professional network

---

## Application to Current Work and Future Projects

The knowledge gained has immediate and future applications:

**Immediate Applications**:
- Can now recommend appropriate AWS AI/ML services for different use cases
- Understanding RAG architecture enables better documentation and knowledge management solutions
- Prompt engineering techniques improve interactions with AI tools

**Future Project Ideas**:
- Building a documentation chatbot using Bedrock Knowledge Bases for the FCJ community
- Implementing intelligent search using embeddings and semantic similarity
- Creating ML pipelines with SageMaker for predictive analytics projects
- Developing content generation tools for technical writing

**Career Development**:
- AWS Certified Machine Learning - Specialty certification path
- Hands-on projects with SageMaker and Bedrock
- Contributing to AI/ML community in Vietnam
- Exploring AI/ML engineering roles

---

## Key Takeaways

1. **SageMaker for Traditional ML**: Complete platform for end-to-end ML workflows from data prep to deployment

2. **Bedrock for GenAI**: Fastest path to building GenAI applications with foundation models and managed services

3. **RAG is Essential**: Retrieval-Augmented Generation is critical for enterprise GenAI applications requiring accuracy and current information

4. **Prompt Engineering Matters**: Quality of prompts directly impacts quality of outputs; invest time in prompt development

5. **MLOps is Necessary**: Production ML requires pipelines, monitoring, and governance - not just model training

6. **Guardrails are Non-Negotiable**: Safety and content filtering must be implemented before production deployment

7. **Choose the Right Tool**: SageMaker for custom ML models, Bedrock for leveraging pre-trained foundation models

8. **Cost Optimization**: Use spot instances, serverless inference, and efficient prompting to control costs

9. **Iterative Approach**: Start small, test thoroughly, and iterate based on real-world feedback

10. **Community and Learning**: Active learning community in Vietnam; opportunities for collaboration and knowledge sharing

---

## Industry Applications Discussed

The workshop highlighted several real-world use cases relevant to Vietnamese enterprises:

**E-commerce**:
- Product recommendation systems (SageMaker)
- Chatbots for customer support (Bedrock Agents)
- Automated product descriptions (Bedrock)
- Demand forecasting (SageMaker)

**Financial Services**:
- Fraud detection (SageMaker)
- Document processing and analysis (Bedrock with RAG)
- Risk assessment models (SageMaker)
- Financial advisory chatbots (Bedrock Agents)

**Healthcare**:
- Medical image analysis (SageMaker)
- Clinical documentation assistance (Bedrock)
- Patient triage systems (Bedrock Agents)
- Predictive analytics for patient outcomes (SageMaker)

**Education**:
- Personalized learning assistants (Bedrock)
- Automated grading and feedback (SageMaker + Bedrock)
- Content generation for educational materials (Bedrock)

---

## Resources and Next Steps

**Recommended Learning Path**:
1. AWS Skill Builder: Machine Learning Learning Plan
2. SageMaker Immersion Day workshops
3. Bedrock Workshop (hands-on labs)
4. AWS Certified Machine Learning - Specialty exam preparation

**Hands-on Practice**:
- AWS Free Tier: Experiment with SageMaker notebooks
- Bedrock Playground: Test foundation models
- Sample datasets: Kaggle, AWS Open Data
- Community projects: Contribute to open-source AI/ML projects

**Community Engagement**:
- AWS User Group Vietnam
- AI/ML Meetups in Ho Chi Minh City
- AWS re:Post for Q&A
- LinkedIn groups for Vietnamese AI/ML professionals

---

## Conclusion

The AI/ML/GenAI on AWS workshop was an excellent introduction to the rapidly evolving field of artificial intelligence on cloud platforms. The balanced approach covering both traditional machine learning with SageMaker and cutting-edge generative AI with Bedrock provided comprehensive understanding of the AWS AI/ML portfolio.

The live demonstrations were particularly valuable, showing practical implementations rather than just theoretical concepts. Seeing RAG in action and building a functioning chatbot demystified Generative AI and made it feel accessible for real-world projects.

The workshop reinforced that AI/ML is no longer the domain of only large enterprises with massive resources. AWS services democratize AI, making it accessible to startups and individual developers. The key is starting with clear use cases, leveraging managed services, and focusing on delivering value rather than building infrastructure.

Most importantly, the emphasis on responsible AI through guardrails and the discussion of MLOps practices showed that production AI is about much more than just training models - it requires thoughtful architecture, monitoring, and governance.

I highly recommend this workshop to anyone interested in AI/ML on AWS, whether you're a developer looking to add AI capabilities to applications, a data scientist exploring cloud ML platforms, or a business leader evaluating AI opportunities. The knowledge gained provides a solid foundation for building intelligent applications on AWS.

Moving forward, I plan to pursue hands-on projects with both SageMaker and Bedrock, work toward the AWS Machine Learning Specialty certification, and explore opportunities to apply AI/ML in my internship projects and future career.
