---
title: "Event 2"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy it verbatim** into your report, including this warning.
{{% /notice %}}

# Summary Report: "Data Science On AWS Workshop"

### Event Information

- **Event**: Data Science On AWS Workshop
- **Date**: Thursday, October 16th, 2025
- **Time**: 9:30 AM - 11:45 AM
- **Location**: Hall Academic, FPT University
- **Organizers**: AWS Community Builders

### Event Objectives

- Explore the complete journey of building a modern Data Science system on AWS
- Demonstrate practical implementation from theory to hands-on practice
- Understand the importance of Cloud in Data Science workflows
- Learn AWS services for data processing, ML training, and model deployment
- Compare Cloud vs. On-premise solutions for cost and performance

### Speakers

- **Văn Hoàng Kha** – Cloud Solutions Architect, AWS Community Builder
- **Bạch Doãn Vương** – Cloud Develops Engineer, AWS Community Builder

### Workshop Agenda

| Time | Activity | Speaker |
|------|----------|----------|
| 9:30 AM - 9:40 AM | Introduction & Importance of Cloud in Data Science | Organizers |
| 9:40 AM - 10:05 AM | Overview of Data Science Pipeline on AWS (S3, Glue, SageMaker) | Văn Hoàng Kha |
| 10:05 AM - 10:35 AM | Demo 1: Data Processing and Cleaning from IMDb Dataset with AWS Glue | Bạch Doãn Vương |
| 10:35 AM - 11:00 AM | Demo 2: Training and Deploying Sentiment Analysis Model with SageMaker | Văn Hoàng Kha |
| 11:00 AM - 11:35 AM | In-depth Discussion: Cost & Performance (Cloud vs. On-premise) | Both Speakers |
| 11:35 AM - 11:45 AM | Post-workshop Mini Project Guidance | Organizers |

### Key Highlights

#### Introduction: Cloud's Role in Data Science

**Why Cloud for Data Science?**
- **Scalability**: Easily scale compute resources based on workload demands
- **Cost Efficiency**: Pay-only-for-what-you-use model eliminates upfront infrastructure costs
- **Accessibility**: Access powerful computing resources without physical hardware
- **Collaboration**: Team members can work on the same datasets and models from anywhere
- **Faster Time-to-Market**: Quick experimentation and iteration without provisioning delays

**Traditional Challenges Addressed:**
- Limited local compute power for large datasets
- High upfront costs for GPU/TPU hardware
- Difficulty in collaboration and version control
- Complex infrastructure management

#### Data Science Pipeline on AWS

**Complete End-to-End Workflow:**

1. **Data Storage (Amazon S3)**
   - Centralized data lake for raw and processed data
   - Scalable, durable, and cost-effective storage
   - Integration with all AWS data services

2. **Data Processing (AWS Glue)**
   - Serverless ETL (Extract, Transform, Load) service
   - Automated data cataloging and schema discovery
   - Built-in data quality and validation
   - Support for various data formats (CSV, JSON, Parquet)

3. **Model Development (Amazon SageMaker)**
   - Fully managed ML platform
   - Built-in algorithms and framework support
   - Jupyter notebooks for experimentation
   - AutoML capabilities with SageMaker Autopilot

4. **Model Training**
   - Distributed training for large datasets
   - Automatic hyperparameter tuning
   - Spot instance support for cost optimization

5. **Model Deployment**
   - One-click deployment to production
   - Auto-scaling endpoints
   - A/B testing and canary deployments
   - Real-time and batch inference options

#### Demo 1: AWS Glue for Data Processing

**IMDb Dataset Processing:**

**Dataset Overview:**
- Movie reviews and ratings
- User sentiment labels (positive/negative)
- Unstructured text data requiring cleaning

**AWS Glue Operations:**
- **Data Crawlers**: Automatically discover and catalog IMDb data schema
- **ETL Jobs**: Transform raw text data into structured format
- **Data Cleaning**: Remove duplicates, handle missing values, normalize text
- **Feature Engineering**: Extract relevant features for sentiment analysis

**Key Glue Features Demonstrated:**
- Visual ETL designer for no-code transformations
- PySpark scripts for advanced processing
- Data quality rules and validation
- Job scheduling and monitoring

**Results:**
- Clean, structured dataset ready for ML training
- Reduced data preparation time by 70%
- Automated pipeline for future data ingestion

#### Demo 2: SageMaker Sentiment Analysis

**Model Development Workflow:**

**1. Data Preparation in SageMaker:**
- Load processed data from S3
- Split into training, validation, and test sets
- Feature vectorization using TF-IDF or word embeddings

**2. Model Selection:**
- Pre-built algorithm: BlazingText for text classification
- Custom model: LSTM/Transformer-based sentiment classifier
- Transfer learning: Fine-tune pre-trained BERT model

**3. Training Process:**
- Configure training instance type (ml.p3.2xlarge for GPU)
- Set hyperparameters (learning rate, batch size, epochs)
- Enable SageMaker Experiments for tracking
- Monitor training metrics in real-time

**4. Model Evaluation:**
- Accuracy: 92% on test set
- Precision/Recall analysis
- Confusion matrix visualization
- Error analysis for model improvement

**5. Deployment:**
- Create SageMaker endpoint
- Configure auto-scaling policies
- Set up monitoring and logging
- Test with sample movie reviews

**Live Demonstration Results:**
- Positive Review: "This movie was absolutely fantastic!" → Confidence: 95%
- Negative Review: "Worst movie I've ever seen" → Confidence: 93%
- Neutral Review: "It was okay, nothing special" → Confidence: 78%  

#### Cloud vs. On-Premise Comparison

**Cost Analysis:**

| Aspect | On-Premise | AWS Cloud |
|--------|------------|-----------|
| Initial Investment | $50,000+ for hardware | $0 upfront |
| GPU Servers | $10,000-$30,000 each | Pay-per-hour ($3-$30/hour) |
| Maintenance | 20% annual cost | Managed by AWS |
| Scaling | Manual hardware purchase | Instant scaling |
| Utilization | Fixed cost regardless of usage | Pay only for actual usage |

**Performance Considerations:**
- **Training Speed**: Cloud offers latest GPU instances (A100, V100)
- **Experimentation**: Quick iteration without resource constraints
- **Parallel Jobs**: Run multiple experiments simultaneously
- **Global Reach**: Deploy models closer to users worldwide

**ROI Analysis:**
- Break-even point: Typically 3-6 months for most projects
- Cost savings: 40-60% compared to maintaining on-premise infrastructure
- Time savings: 70-80% reduction in infrastructure setup time

### Key Takeaways

#### Data Science on Cloud Benefits

- **Speed to Insights**: Reduce time from data collection to model deployment by 80%
- **Scalability**: Handle datasets of any size without infrastructure worries
- **Cost Optimization**: Pay only for compute resources when actually training/inferring
- **Collaboration**: Teams can work together seamlessly with shared environments
- **Latest Tools**: Access to cutting-edge ML frameworks and services

#### AWS Services for Data Science

- **S3**: Foundation for data lake architecture
- **Glue**: Serverless ETL that eliminates data engineering overhead
- **SageMaker**: Complete ML platform from experimentation to production
- **Additional Services**: 
  - Athena for SQL queries on S3
  - QuickSight for data visualization
  - Lambda for serverless inference
  - Step Functions for ML workflow orchestration

#### Best Practices Learned

1. **Start with Data Quality**: Clean data is crucial for model performance
2. **Automate Everything**: Use Glue crawlers and SageMaker pipelines
3. **Monitor Costs**: Set budget alerts and use spot instances
4. **Version Control**: Track datasets, models, and experiments
5. **Incremental Deployment**: Test models before full production rollout

### Post-Workshop Mini Project

**Suggested Project: Movie Review Sentiment Analyzer**

**Objective:** Build end-to-end sentiment analysis system using AWS services

**Steps:**
1. Collect movie review dataset from public sources
2. Store data in S3 bucket
3. Use AWS Glue to clean and prepare data
4. Train sentiment analysis model in SageMaker
5. Deploy model as REST API endpoint
6. Create simple web interface to test predictions

**Learning Outcomes:**
- Hands-on experience with complete Data Science pipeline
- Understanding of AWS service integration
- Cost estimation and optimization skills
- Model deployment and monitoring experience

### Applying to Work

#### For Current OJT Project

- **Apply SageMaker** for movie recommendation model training
- **Use S3** for storing TMDB dataset and preprocessed data
- **Leverage Glue** for ETL operations on movie metadata
- **Deploy Models** using SageMaker endpoints for real-time recommendations

#### Future Applications

- **Chatbot Enhancement**: Train custom NLP models for better understanding
- **Recommendation Systems**: Build collaborative filtering models
- **User Behavior Analysis**: Process and analyze user interaction data
- **A/B Testing**: Deploy multiple model versions for comparison  

### Event Experience

Attending the **“GenAI-powered App-DB Modernization”** workshop was extremely valuable, giving me a comprehensive view of modernizing applications and databases using advanced methods and tools. Key experiences included:

#### Learning from highly skilled speakers
- Experts from AWS and major tech organizations shared **best practices** in modern application design.  
- Through real-world case studies, I gained a deeper understanding of applying **DDD** and **Event-Driven Architecture** to large projects.  

#### Hands-on technical exposure
- Participating in **event storming** sessions helped me visualize how to **model business processes** into domain events.  
- Learned how to **split microservices** and define **bounded contexts** to manage large-system complexity.  
- Understood trade-offs between **synchronous and asynchronous communication** and integration patterns like **pub/sub, point-to-point, streaming**.  

#### Leveraging modern tools
- Explored **Amazon Q Developer**, an AI tool for SDLC support from planning to maintenance.  
- Learned to **automate code transformation** and pilot serverless with **AWS Lambda** to improve productivity.  

#### Networking and discussions
- The workshop offered opportunities to exchange ideas with experts, peers, and business teams, enhancing the **ubiquitous language** between business and tech.  
- Real-world examples reinforced the importance of the **business-first approach** rather than focusing solely on technology.  

#### Lessons learned
- Applying DDD and event-driven patterns reduces **coupling** while improving **scalability** and **resilience**.  
- Modernization requires a **phased approach** with **ROI measurement**; rushing the process can be risky.  
- AI tools like Amazon Q Developer can significantly **boost productivity** when integrated into the current workflow.  

#### Some event photos
*Add your event photos here*  

> Overall, the event not only provided technical knowledge but also helped me reshape my thinking about application design, system modernization, and cross-team collaboration.

### Event Experience

Attending the **"Data Science On AWS"** workshop at FPT University was an incredibly enriching experience that bridged the gap between academic knowledge and industry practices. Key experiences included:

#### Learning from AWS Community Builders

- **Van Ho�ng Kha** and **B?ch Do�n Vuong** brought real-world expertise as active AWS Community Builders  
- Both speakers shared **production-ready practices** from actual enterprise Data Science projects  
- Their hands-on approach made complex AWS services accessible and practical  
- Emphasis on cost optimization showed real business awareness  

#### Comprehensive AWS Data Science Pipeline

- Gained complete understanding of **end-to-end ML workflow** on AWS  
- Learned how **S3, Glue, and SageMaker** work together seamlessly  
- Understood the **importance of data quality** before model training  
- Saw how AWS abstracts infrastructure complexity, letting data scientists focus on models  

#### Live Demonstrations

**AWS Glue Demo:**
- Witnessed real-time **ETL processing** of IMDb dataset  
- Observed automated **data cataloging and schema discovery**  
- Learned data cleaning techniques for text data  
- Understood how Glue eliminates traditional data engineering bottlenecks  

**SageMaker Demo:**
- Watched **end-to-end ML model development** from notebook to production  
- Saw **hyperparameter tuning** and experiment tracking in action  
- Observed **one-click model deployment** to scalable endpoints  
- Tested live sentiment analysis predictions with impressive accuracy  

#### Cost vs. Performance Insights

- Eye-opening comparison between **Cloud and On-premise** infrastructure  
- Learned about **spot instances** for 70% cost savings on training  
- Understood **pay-per-use model** eliminates waste from idle resources  
- Discovered Cloud provides **better ROI** for most Data Science workloads  

#### Practical Application to OJT Project

- Realized I can use **SageMaker for training recommendation models**  
- Identified opportunity to **migrate TMDB data processing to Glue**  
- Learned how to **deploy ML models as REST APIs** using SageMaker endpoints  
- Understood cost-effective strategies for running ML workloads  

#### Networking and Collaboration

- Connected with fellow students interested in Data Science and ML  
- Exchanged ideas about applying AWS services to university projects  
- Discussed internship opportunities in cloud and data science roles  
- Built relationship with AWS Community Builders for mentorship  

#### Key Realizations

- **Data Science is not just about algorithms** - infrastructure and operations matter  
- **Cloud democratizes ML** - anyone can access powerful compute without huge investments  
- **AWS provides mature ecosystem** for complete ML lifecycle  
- **Automation is key** - managed services reduce operational burden significantly  
- **Production deployment** is as important as model accuracy  

#### Immediate Actions Post-Workshop

1. Created AWS account and explored SageMaker Studio  
2. Completed the suggested mini-project using IMDb dataset  
3. Experimented with Glue crawlers on TMDB data  
4. Researched SageMaker pricing for OJT project feasibility  
5. Documented learnings for team knowledge sharing  

#### Some workshop photos
*Add your workshop photos here*  

> This workshop was a perfect example of how industry and academia should connect. The speakers demonstrated real-world applications while making sure concepts were accessible to students. It reinforced my belief that cloud computing is not optional but essential for modern Data Science work, and AWS provides a comprehensive platform to build production-grade ML systems.
