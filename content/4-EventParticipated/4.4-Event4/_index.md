---
title: "Event 4"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Summary Report: "DevOps on AWS - Full-Day Workshop"

### Event Information

- **Event**: DevOps on AWS Workshop
- **Date**: Monday, November 17th, 2025
- **Time**: 8:30 AM - 5:00 PM (Full Day)
- **Location**: AWS Vietnam Office, Bitexco Financial Tower, 2 Hai Trieu Street, Ben Nghe Ward, District 1, Ho Chi Minh City
- **My Role**: Attendee

---

## Event Overview

This comprehensive full-day workshop provided an in-depth exploration of DevOps practices and tools on AWS. The session covered the complete DevOps lifecycle from source control to monitoring, with hands-on demonstrations of CI/CD pipelines, Infrastructure as Code, container orchestration, and observability solutions. The workshop balanced theoretical concepts with practical implementations, featuring live demos and real-world case studies from both startups and enterprises.

---

## Morning Session (8:30 AM – 12:00 PM)

### **8:30 – 9:00 AM | Welcome & DevOps Mindset**

The workshop began with a comprehensive introduction to DevOps culture and principles:

- **Recap of Previous AI/ML Session**: Brief review connecting AI/ML workflows with DevOps automation practices

- **DevOps Culture and Principles**:
  - **Collaboration**: Breaking down silos between development and operations teams
  - **Automation**: Automating repetitive tasks to increase efficiency and reduce human error
  - **Continuous Improvement**: Iterative approach to optimizing processes and systems
  - **Fast Feedback Loops**: Rapid detection and resolution of issues
  - **Shared Responsibility**: Everyone owns the quality and reliability of the system

- **Key Benefits of DevOps**:
  - Faster time to market
  - Improved deployment frequency
  - Lower failure rate of new releases
  - Shorter lead time between fixes
  - Faster mean time to recovery (MTTR)

- **DevOps Metrics (DORA Metrics)**:
  - **Deployment Frequency**: How often code is deployed to production
  - **Lead Time for Changes**: Time from commit to production deployment
  - **Mean Time to Recovery (MTTR)**: Average time to recover from failures
  - **Change Failure Rate**: Percentage of deployments causing failures

**Key Learnings**: Understanding that DevOps is not just about tools, but fundamentally about culture, collaboration, and continuous improvement mindset.

---

### **9:00 – 10:30 AM | AWS DevOps Services – CI/CD Pipeline**

This intensive session covered the complete AWS CI/CD toolchain:

#### **Source Control**
- **AWS CodeCommit**: 
  - Fully managed Git repositories hosted on AWS
  - Encryption at rest and in transit
  - Integration with IAM for access control
  - Branch protection and merge strategies

- **Git Strategies**:
  - **GitFlow**: Feature branches, develop, release, and main branches for structured releases
  - **Trunk-Based Development**: Short-lived feature branches merged directly to main/trunk
  - Comparison of approaches and when to use each

#### **Build & Test**
- **AWS CodeBuild**:
  - Managed build service that compiles code and runs tests
  - `buildspec.yml` configuration for build phases
  - Environment variables and parameter management
  - Integration with ECR for container image builds
  - Caching strategies for faster builds

- **Testing Pipelines**:
  - Unit tests, integration tests, and security scans
  - Parallel test execution for faster feedback
  - Test result reporting and metrics

#### **Deployment**
- **AWS CodeDeploy**:
  - **Blue/Green Deployment**: Switching traffic between two identical environments
  - **Canary Deployment**: Gradually rolling out changes to a subset of users
  - **Rolling Updates**: Incremental updates to maintain availability
  - Automatic rollback on deployment failures
  - Integration with Auto Scaling Groups and Lambda functions

#### **Orchestration**
- **AWS CodePipeline**:
  - Automated workflow orchestrating all CI/CD stages
  - Visual pipeline editor and stage management
  - Integration with third-party tools (GitHub, Jenkins, etc.)
  - Approval stages for production deployments
  - Pipeline execution history and artifact management

#### **Live Demo: Full CI/CD Pipeline**
The instructor demonstrated a complete pipeline:
1. Code commit triggers CodePipeline
2. CodeBuild compiles and tests the application
3. Docker image pushed to Amazon ECR
4. CodeDeploy executes Blue/Green deployment to ECS
5. Automated rollback on failed health checks

**Key Learnings**: 
- Always implement automated testing before deployment stages
- Use Blue/Green deployments for zero-downtime releases
- Configure automatic rollbacks to minimize impact of failed deployments
- Monitor pipeline execution times and optimize build caching

---

### **10:30 – 10:45 AM | Coffee Break**

---

### **10:45 AM – 12:00 PM | Infrastructure as Code (IaC)**

This session explored AWS's Infrastructure as Code tools:

#### **AWS CloudFormation**
- **Templates**: YAML/JSON definitions of AWS resources
- **Stacks**: Deployed instances of templates as single units
- **Change Sets**: Preview infrastructure changes before applying
- **Drift Detection**: Identifying manual changes to resources
- **StackSets**: Deploying stacks across multiple accounts and regions
- **Best Practices**:
  - Parameterized templates for reusability
  - Using nested stacks for modular infrastructure
  - Implementing stack policies to prevent accidental deletions

#### **AWS CDK (Cloud Development Kit)**
- **Programming Language Support**: TypeScript, Python, Java, C#, Go
- **Constructs**: 
  - **L1 (CloudFormation Resources)**: Direct mappings to CloudFormation resources
  - **L2 (Curated Constructs)**: Higher-level abstractions with sensible defaults
  - **L3 (Patterns)**: Complete architectural patterns
- **Reusable Patterns**: Sharing infrastructure code across projects
- **CDK Advantages**:
  - Type safety and IDE autocomplete
  - Using familiar programming languages
  - Testing infrastructure code with unit tests
  - More concise than CloudFormation templates

#### **Live Demo: Deploying with CloudFormation and CDK**
Two parallel demonstrations:
1. **CloudFormation**: Deploying a VPC with subnets, NAT gateways, and route tables
2. **CDK (Python)**: Deploying the same infrastructure with significantly less code

#### **Discussion: Choosing Between IaC Tools**
- **CloudFormation**: Native AWS support, declarative, visual designer
- **CDK**: Programming languages, reusable components, better for complex logic
- **Terraform**: Multi-cloud support, large community, extensive providers
- **When to use each tool based on project requirements and team expertise**

**Key Learnings**:
- Start with CloudFormation for simple infrastructures
- Use CDK for complex, repeatable infrastructure patterns
- Always version control your IaC code
- Implement CI/CD for infrastructure deployments
- Test infrastructure changes in non-production environments first

---

## Lunch Break (12:00 – 1:00 PM)
Self-arranged lunch break

---

## Afternoon Session (1:00 – 5:00 PM)

### **1:00 – 2:30 PM | Container Services on AWS**

Comprehensive coverage of containerization and orchestration:

#### **Docker Fundamentals**
- **Microservices Architecture**: Breaking monoliths into smaller, independent services
- **Containerization Benefits**:
  - Consistent environments from development to production
  - Resource efficiency compared to VMs
  - Rapid deployment and scaling
  - Isolation and security boundaries

#### **Amazon ECR (Elastic Container Registry)**
- **Image Storage**: Private Docker container registry
- **Image Scanning**: Automated vulnerability scanning on push
- **Lifecycle Policies**: Automated cleanup of old images to reduce costs
- **Cross-Region Replication**: Disaster recovery and global deployments
- **Integration with ECS and EKS**: Seamless image pulling

#### **Amazon ECS (Elastic Container Service)**
- **Task Definitions**: Container specifications (CPU, memory, networking)
- **Services**: Maintaining desired count of running tasks
- **Launch Types**:
  - **EC2**: Running containers on managed EC2 instances
  - **Fargate**: Serverless container execution
- **Service Discovery**: DNS-based service discovery with Cloud Map
- **Load Balancing**: Integration with ALB/NLB for traffic distribution

#### **Amazon EKS (Elastic Kubernetes Service)**
- **Kubernetes on AWS**: Managed Kubernetes control plane
- **Worker Nodes**: EC2 or Fargate for pod execution
- **kubectl**: Command-line tool for cluster management
- **Helm Charts**: Package manager for Kubernetes applications
- **Add-ons**: CoreDNS, kube-proxy, VPC CNI plugin
- **IRSA (IAM Roles for Service Accounts)**: Fine-grained IAM permissions for pods

#### **AWS App Runner**
- **Simplified Deployment**: Deploy containers from source code or images
- **Automatic Scaling**: Based on traffic patterns
- **Built-in Load Balancing**: No configuration required
- **Use Cases**: Simple web applications and APIs without infrastructure management

#### **Live Demo & Case Study: Microservices Deployment Comparison**
The instructor demonstrated deploying the same microservices application on:
1. **ECS Fargate**: Quick setup, serverless, pay-per-use
2. **EKS**: More control, Kubernetes ecosystem, complex workloads
3. **App Runner**: Fastest deployment, limited customization

**Comparison Discussion**:
- **ECS**: Best for AWS-native deployments, simpler than Kubernetes
- **EKS**: Best for Kubernetes expertise, multi-cloud strategies, complex orchestration
- **App Runner**: Best for simple applications, minimal infrastructure management

**Key Learnings**:
- Choose ECS for AWS-centric microservices without Kubernetes complexity
- Choose EKS when you need Kubernetes features or multi-cloud portability
- Use Fargate to eliminate infrastructure management
- Implement health checks and proper logging for all containers
- Use ECR lifecycle policies to manage storage costs

---

### **2:30 – 2:45 PM | Coffee Break**

---

### **2:45 – 4:00 PM | Monitoring & Observability**

Critical session on observability and operational excellence:

#### **Amazon CloudWatch**
- **Metrics**:
  - Built-in metrics for AWS services (CPU, network, disk)
  - Custom metrics from applications
  - High-resolution metrics (1-second granularity)
  - Metric math for complex calculations

- **Logs**:
  - **CloudWatch Logs**: Centralized log aggregation
  - **Log Groups and Streams**: Organization structure
  - **Insights**: SQL-like queries for log analysis
  - **Log Retention**: Cost optimization through retention policies
  - **Subscription Filters**: Real-time log processing with Lambda

- **Alarms**:
  - Threshold-based alarms on metrics
  - Composite alarms combining multiple conditions
  - Actions: SNS notifications, Auto Scaling, EC2 actions

- **Dashboards**:
  - Custom visualization of metrics and logs
  - Cross-region dashboards for global visibility
  - Sharing dashboards with stakeholders

#### **AWS X-Ray**
- **Distributed Tracing**: Following requests through microservices
- **Service Map**: Visual representation of application architecture
- **Trace Analysis**: Identifying performance bottlenecks
- **Annotations and Metadata**: Adding context to traces
- **Integration**: Works with Lambda, ECS, EKS, API Gateway, and more
- **Sampling Rules**: Controlling trace data volume and costs

#### **Live Demo: Full-Stack Observability Setup**
Complete implementation of observability for a microservices application:
1. **Application Instrumentation**: Adding X-Ray SDK to code
2. **Log Aggregation**: Shipping container logs to CloudWatch
3. **Custom Metrics**: Publishing business metrics
4. **Dashboard Creation**: Building operational dashboards
5. **Alarm Configuration**: Setting up critical alerts
6. **Trace Analysis**: Using X-Ray to debug latency issues

#### **Best Practices**
- **Alerting Strategy**:
  - Alert on symptoms, not causes
  - Reduce alert fatigue with proper thresholds
  - Use composite alarms to reduce false positives
  - Implement escalation policies

- **Dashboard Design**:
  - Separate operational and business dashboards
  - Include SLIs (Service Level Indicators) and error rates
  - Use consistent time ranges across widgets
  - Display dashboards on team monitors

- **On-Call Processes**:
  - Clear runbooks for common alerts
  - Incident response playbooks
  - Postmortem processes for learning
  - Rotation schedules to prevent burnout

**Key Learnings**:
- Implement the three pillars of observability: metrics, logs, and traces
- Use CloudWatch for infrastructure and application monitoring
- Enable X-Ray for microservices to understand request flows
- Set meaningful alerts that require action
- Build dashboards that tell the story of system health

---

### **4:00 – 4:45 PM | DevOps Best Practices & Case Studies**

Practical implementation strategies and real-world examples:

#### **Deployment Strategies**
- **Feature Flags**:
  - Decoupling deployment from release
  - Gradual feature rollout to user segments
  - A/B testing and experimentation
  - Emergency kill switches
  - AWS AppConfig for feature flag management

- **A/B Testing**:
  - Testing variations to optimize user experience
  - Statistical significance in experiments
  - Integration with CloudWatch for metrics

#### **Automated Testing**
- **Testing Pyramid**:
  - Unit tests (fast, isolated)
  - Integration tests (component interactions)
  - End-to-end tests (full user workflows)
- **CI/CD Integration**:
  - Fail fast with early testing
  - Parallel test execution
  - Test coverage metrics
  - Security scanning in pipeline

#### **Incident Management**
- **Incident Response Process**:
  1. Detection (monitoring and alerting)
  2. Triage (severity assessment)
  3. Investigation (root cause analysis)
  4. Resolution (fix and verify)
  5. Communication (stakeholder updates)
  6. Postmortem (learning and prevention)

- **Postmortem Best Practices**:
  - Blameless culture
  - Timeline of events
  - Root cause analysis (5 Whys)
  - Action items with owners
  - Sharing learnings across teams

#### **Case Studies**

**Case Study 1: Startup DevOps Transformation**
- **Challenge**: Manual deployments, frequent production issues, slow feature delivery
- **Solution**: 
  - Implemented CI/CD with CodePipeline
  - Containerized applications with ECS Fargate
  - Infrastructure as Code with CDK
  - Comprehensive monitoring with CloudWatch
- **Results**: 
  - Deployment frequency increased from weekly to multiple times per day
  - MTTR reduced from hours to minutes
  - Developer productivity improved significantly
  - Zero-downtime deployments achieved

**Case Study 2: Enterprise Multi-Account DevOps**
- **Challenge**: Complex multi-account structure, compliance requirements, coordinated releases
- **Solution**:
  - AWS Organizations with SCPs
  - Cross-account CI/CD pipelines
  - Centralized logging and monitoring
  - Automated compliance checks in pipeline
- **Results**:
  - Consistent deployments across 50+ AWS accounts
  - Reduced compliance audit time by 70%
  - Improved security posture with automated scanning

**Key Learnings**:
- Start small and iterate on DevOps practices
- Automate everything that can be automated
- Measure everything and use data to drive improvements
- Foster a culture of continuous learning and improvement
- Invest in developer experience to improve productivity

---

### **4:45 – 5:00 PM | Q&A & Wrap-up**

Final session for questions and career guidance:

#### **DevOps Career Pathways**
- **Entry Level**: Focus on scripting, CI/CD tools, and cloud fundamentals
- **Mid Level**: Infrastructure as Code, container orchestration, observability
- **Senior Level**: Architecture design, multi-region deployments, platform engineering
- **Specializations**: SRE, Platform Engineering, Cloud Architecture, Security Engineering

#### **AWS Certification Roadmap for DevOps**
Recommended certification path:
1. **AWS Certified Cloud Practitioner**: Foundation knowledge (optional for experienced developers)
2. **AWS Certified Developer – Associate**: Application development on AWS
3. **AWS Certified DevOps Engineer – Professional**: Comprehensive DevOps practices
4. **AWS Certified Solutions Architect – Professional**: Advanced architecture skills (recommended for senior roles)

#### **Learning Resources**
- AWS Skill Builder for hands-on labs
- AWS Workshops for guided projects
- AWS re:Post for community Q&A
- AWS Whitepapers for best practices
- Local AWS User Groups and events

---

## Personal Reflections & Value Gained

This full-day DevOps workshop was incredibly comprehensive and valuable for my professional development:

1. **Complete DevOps Lifecycle Understanding**: Gained end-to-end knowledge from source control to production monitoring, understanding how all pieces fit together

2. **Hands-On Tool Proficiency**: Live demonstrations of CodePipeline, CloudFormation, CDK, ECS, and CloudWatch provided practical skills I can immediately apply

3. **Real-World Context**: Case studies from startups and enterprises showed how DevOps practices scale and adapt to different organizational needs

4. **Infrastructure as Code Mastery**: Deep dive into CloudFormation and CDK clarified when to use each tool and how to structure infrastructure code

5. **Container Orchestration Clarity**: Understanding the differences between ECS, EKS, and App Runner helps me choose the right tool for different use cases

6. **Observability Best Practices**: Learning to implement comprehensive monitoring with metrics, logs, and traces is critical for production operations

7. **DevOps Culture**: Understanding that DevOps is about culture and collaboration, not just tools, changes how I approach software delivery

8. **Career Development**: Clear roadmap for DevOps certifications and career progression provides direction for my learning journey

---

## Application to Current Work

The knowledge gained directly applies to my internship and projects:

- **Workshop Development**: Can now add CI/CD deployment instructions to my S3 VPC endpoint workshop
- **Infrastructure as Code**: Implementing CloudFormation/CDK templates for repeatable deployments
- **Containerization**: Understanding when to recommend ECS vs. EKS for different scenarios
- **Monitoring**: Setting up proper CloudWatch dashboards and alarms for production workloads
- **Documentation**: Creating better runbooks and deployment guides based on DevOps best practices

---

## Key Takeaways

1. **Automation is Key**: Automate repetitive tasks to reduce errors and increase velocity
2. **Measure Everything**: Use metrics to drive continuous improvement
3. **Start Small**: Begin with simple CI/CD pipelines and gradually add sophistication
4. **Infrastructure as Code**: Version control all infrastructure for reproducibility
5. **Observability is Critical**: Can't improve what you can't measure
6. **Culture Matters**: DevOps transformation requires organizational buy-in
7. **Security from the Start**: Integrate security scanning into CI/CD pipelines
8. **Learn from Failures**: Blameless postmortems turn incidents into learning opportunities

---

## Conclusion

The DevOps on AWS workshop was an exceptional full-day learning experience that provided both breadth and depth across the entire DevOps landscape. From CI/CD pipelines to container orchestration to observability, every session built upon previous knowledge while providing practical, hands-on examples.

The combination of theoretical principles, live demonstrations, and real-world case studies made complex concepts accessible and immediately applicable. The workshop reinforced that successful DevOps is about culture, automation, measurement, and continuous improvement.

I highly recommend this workshop to anyone looking to implement DevOps practices on AWS or advance their career in cloud operations and site reliability engineering. The skills learned here are foundational to modern software delivery and will be invaluable throughout my career in cloud computing.

Moving forward, I plan to pursue the AWS Certified DevOps Engineer - Professional certification and continue implementing these practices in my projects, contributing to faster, more reliable software delivery.
