---
title: "Event 3"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Summary Report: "AWS Well-Architected Security Pillar Workshop"

### Event Information

- **Event**: AWS Well-Architected Security Pillar Workshop
- **Date**: Friday, November 29th, 2025
- **Time**: 8:30 AM - 12:00 PM (Morning Session)
- **Location**: AWS Vietnam Office, Bitexco Financial Tower, 2 Hai Trieu Street, Ben Nghe Ward, District 1, Ho Chi Minh City
- **My Role**: Attendee

---

## Event Overview

This intensive half-day workshop provided a comprehensive deep dive into the Security Pillar of the AWS Well-Architected Framework. The session was specifically tailored to address security challenges and best practices relevant to Vietnamese enterprises adopting cloud technologies. The workshop covered all five fundamental pillars of AWS security through structured presentations, live demonstrations, and real-world incident response scenarios.

---

## Detailed Agenda & Key Takeaways

### **8:30 – 8:50 AM | Opening & Security Foundation**

The workshop began with an introduction to the critical role of the Security Pillar within the AWS Well-Architected Framework. Key topics covered included:

- **Core Security Principles**:
  - **Least Privilege**: Granting only the minimum permissions necessary for users and services to perform their tasks
  - **Zero Trust Architecture**: Never trust, always verify - assuming no implicit trust regardless of network location
  - **Defense in Depth**: Implementing multiple layers of security controls throughout the IT infrastructure

- **Shared Responsibility Model**: Understanding the division of security responsibilities between AWS (security OF the cloud) and customers (security IN the cloud)

- **Top Cloud Security Threats in Vietnam**: Discussion of the most prevalent security challenges facing Vietnamese organizations, including data breaches, misconfigured resources, and credential compromises

---

### **Pillar 1: Identity & Access Management (8:50 – 9:30 AM)**

This session focused on modern IAM architecture and best practices:

- **IAM Fundamentals**:
  - Understanding Users, Roles, and Policies
  - Avoiding long-term credentials and embracing temporary security credentials
  - Implementing role-based access control (RBAC)

- **IAM Identity Center**:
  - Implementing Single Sign-On (SSO) across AWS accounts
  - Managing permission sets for centralized access control
  - Streamlining user management in multi-account environments

- **Advanced IAM Concepts**:
  - Service Control Policies (SCPs) for organizational boundaries
  - Permission boundaries to limit maximum permissions
  - Multi-Factor Authentication (MFA) enforcement
  - Credential rotation policies and automation
  - IAM Access Analyzer for identifying overly permissive policies

- **Mini Demo**: The instructor demonstrated how to validate IAM policies using the IAM Policy Simulator and simulate user access to identify potential security gaps.

**Key Learnings**: 
- Always use IAM roles instead of IAM users for applications
- Implement MFA for all privileged accounts
- Regularly audit permissions using Access Analyzer
- Use permission boundaries to prevent privilege escalation

---

### **Pillar 2: Detection (9:30 – 9:55 AM)**

This segment covered continuous monitoring and threat detection capabilities:

- **Logging Services**:
  - **AWS CloudTrail**: Organization-level API activity logging and governance
  - **Amazon GuardDuty**: Intelligent threat detection using machine learning
  - **AWS Security Hub**: Centralized security findings and compliance status

- **Comprehensive Logging Strategy**:
  - VPC Flow Logs for network traffic analysis
  - Application Load Balancer (ALB) access logs
  - S3 access logs for data access patterns
  - CloudWatch Logs for application and system monitoring

- **Alerting & Automation**:
  - Using Amazon EventBridge to create event-driven security responses
  - Automated remediation workflows
  - Integration with incident management systems

- **Detection-as-Code**: Implementing security detection rules as infrastructure code for versioning and reproducibility

**Key Learnings**:
- Enable CloudTrail at the organization level for comprehensive visibility
- Configure GuardDuty findings to trigger automated responses
- Centralize security findings in Security Hub for unified visibility
- Implement log retention policies based on compliance requirements

---

### **Coffee Break (9:55 – 10:10 AM)**

---

### **Pillar 3: Infrastructure Protection (10:10 – 10:40 AM)**

This session addressed network and workload security:

- **VPC Segmentation**:
  - Designing multi-tier architectures with public and private subnets
  - Strategic placement of resources (public vs. private)
  - Network isolation best practices

- **Network Security Controls**:
  - **Security Groups**: Stateful firewall rules at the instance level
  - **Network ACLs (NACLs)**: Stateless firewall rules at the subnet level
  - Understanding when to use each control and how they complement each other

- **Advanced Network Protection**:
  - **AWS WAF (Web Application Firewall)**: Protecting web applications from common exploits
  - **AWS Shield**: DDoS protection (Standard and Advanced tiers)
  - **AWS Network Firewall**: Managed network firewall service for VPC-level protection

- **Workload Security**:
  - EC2 instance hardening and patch management
  - Container security for ECS and EKS
  - Secure configuration baselines

**Key Learnings**:
- Use private subnets for application and database tiers
- Implement Security Groups with minimal required ports
- Deploy WAF with managed rule groups for common threats
- Consider AWS Network Firewall for advanced traffic inspection

---

### **Pillar 4: Data Protection (10:40 – 11:10 AM)**

This critical section covered encryption and data security:

- **AWS Key Management Service (KMS)**:
  - Key policies and grants management
  - Automatic key rotation strategies
  - Customer-managed keys vs. AWS-managed keys

- **Encryption Best Practices**:
  - **At-Rest Encryption**: S3, EBS volumes, RDS databases, DynamoDB tables
  - **In-Transit Encryption**: TLS/SSL for all data transmission
  - End-to-end encryption patterns

- **Secrets Management**:
  - **AWS Secrets Manager**: Automatic rotation of database credentials and API keys
  - **Systems Manager Parameter Store**: Secure storage for configuration data
  - Comparison and use cases for each service

- **Data Governance**:
  - Data classification strategies
  - Implementing access guardrails based on data sensitivity
  - Compliance considerations (GDPR, PDP, etc.)

**Key Learnings**:
- Enable encryption by default for all data stores
- Use KMS customer-managed keys for sensitive data requiring audit trails
- Implement automatic secret rotation for database credentials
- Apply data classification tags for access control policies

---

### **Pillar 5: Incident Response (11:10 – 11:40 AM)**

The final technical session focused on incident response preparedness:

- **IR Lifecycle According to AWS**:
  - Preparation
  - Detection and Analysis
  - Containment, Eradication, and Recovery
  - Post-Incident Activity

- **Practical Incident Response Playbooks**:
  
  **Scenario 1: Compromised IAM Access Key**
  - Detection through GuardDuty or CloudTrail anomalies
  - Immediate steps: Disable the key, review CloudTrail logs
  - Investigation: Identify scope of unauthorized access
  - Remediation: Rotate keys, review IAM policies, implement additional controls
  
  **Scenario 2: S3 Bucket Public Exposure**
  - Detection through S3 access logs or Security Hub findings
  - Immediate containment: Block public access
  - Assessment: Identify exposed data and potential data exfiltration
  - Remediation: Enable S3 Block Public Access, implement bucket policies
  
  **Scenario 3: EC2 Instance Malware Detection**
  - Detection through GuardDuty malware findings
  - Isolation: Modify security groups to prevent lateral movement
  - Evidence collection: Create EBS snapshots and memory dumps
  - Analysis: Investigate malware type and entry vector
  - Recovery: Terminate instance, deploy clean replacement

- **Forensic Best Practices**:
  - Creating snapshots for forensic analysis without disrupting production
  - Network isolation techniques
  - Evidence collection and chain of custody
  - Compliance with legal requirements

- **Automated Incident Response**:
  - Using AWS Lambda functions for immediate response actions
  - AWS Step Functions for complex IR workflows
  - Integration with ticketing and communication systems
  - Automated notification to security teams

**Key Learnings**:
- Prepare IR playbooks before incidents occur
- Automate common response actions to reduce response time
- Always preserve evidence through snapshots before remediation
- Practice IR scenarios regularly through tabletop exercises

---

### **11:40 – 12:00 PM | Wrap-Up & Q&A**

The workshop concluded with a comprehensive review and practical discussion:

- **Five Pillars Summary**: Recap of Identity & Access Management, Detection, Infrastructure Protection, Data Protection, and Incident Response

- **Common Pitfalls in Vietnamese Enterprises**:
  - Over-reliance on root account credentials
  - Insufficient logging and monitoring
  - Lack of encryption for sensitive data
  - Inadequate incident response preparedness
  - Complex IAM policies leading to security gaps

- **Security Learning Roadmap**:
  - Recommended AWS Security specialty certification path
  - AWS Solutions Architect Professional (SA Pro) for advanced architecture
  - Hands-on practice with AWS Security services
  - Participation in AWS security workshops and events

---

## Personal Reflections & Value Gained

This workshop was exceptionally valuable for deepening my understanding of AWS security best practices. Key benefits included:

1. **Practical Security Knowledge**: Moving beyond theoretical concepts to understand real-world implementation of security controls in production environments

2. **Incident Response Skills**: Learning structured approaches to handling security incidents with concrete playbooks that can be applied immediately

3. **Holistic Security Perspective**: Understanding how different security services work together to create a comprehensive security posture

4. **Vietnamese Context**: Appreciated the discussion of security challenges specific to Vietnamese enterprises, making the content highly relevant

5. **Career Development**: Gained clarity on the AWS Security Specialty certification path and how to structure my security learning journey

6. **Hands-on Demonstrations**: The live demos, particularly the IAM Policy Simulator, provided practical skills I can apply in real projects

7. **Networking Opportunity**: Connected with AWS security experts and fellow attendees, expanding my professional network in the cloud security domain

---

## Application to Current Work

The knowledge gained from this workshop directly applies to my internship work:

- **Workshop Security Enhancement**: I can now implement better security controls in the S3 VPC endpoint workshop I'm developing
- **IAM Best Practices**: Applied least privilege principles to the IAM roles and policies in my projects
- **Monitoring Implementation**: Better understanding of how to implement comprehensive logging and monitoring
- **Security Documentation**: Improved ability to document security considerations and best practices in technical content

---

## Conclusion

The AWS Well-Architected Security Pillar Workshop was an excellent investment of time, providing both breadth and depth in AWS security practices. The structured approach covering all five security pillars, combined with practical playbooks and Vietnamese market insights, made this an invaluable learning experience. I highly recommend this workshop to anyone looking to strengthen their AWS security knowledge and implement production-grade security controls.

The emphasis on automation, monitoring, and incident response preparedness has fundamentally changed how I approach security in cloud architectures. Moving forward, I will incorporate these security best practices into all my AWS projects and continue pursuing the AWS Security Specialty certification.
