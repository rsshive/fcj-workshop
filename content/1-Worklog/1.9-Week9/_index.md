---
title: "Week 9 Worklog"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Implement AWS Bedrock integration into the project
* Develop basic chatbot APIs using Bedrock foundation models
* Test and validate chatbot functionality

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Design chatbot architecture with Bedrock <br> - Plan API structure for chatbot interactions <br> - Define input/output formats                                                                       | 04/11/2025 | 04/11/2025      | Bedrock documentation, API design patterns |
| 3   | - Implement Lambda functions for Bedrock API calls <br>&emsp; + Request processing <br>&emsp; + Response formatting <br>&emsp; + Error handling                                                       | 05/11/2025 | 05/11/2025      | <https://docs.aws.amazon.com/bedrock/> |
| 4   | - Develop chatbot APIs <br>&emsp; + Chat endpoint <br>&emsp; + Context management <br>&emsp; + Conversation history                                                                                   | 06/11/2025 | 06/11/2025      | API Gateway, Lambda integration |
| 5   | - Test chatbot functionality <br>&emsp; + Basic Q&A testing <br>&emsp; + Response accuracy validation <br>&emsp; + Latency measurements                                                               | 07/11/2025 | 07/11/2025      | Testing frameworks |
| 6   | - **Practice:** <br>&emsp; + Integration testing with frontend <br>&emsp; + Debug and optimize performance <br>&emsp; + Refine prompts for better responses                                          | 08/11/2025 | 08/11/2025      | Prompt engineering best practices |


### Week 9 Achievements:

* Successfully integrated AWS Bedrock into the project:
  * Configured Bedrock runtime client
  * Implemented Claude model for conversational AI
  * Set up proper IAM roles and permissions

* Developed Lambda functions for chatbot operations:
  * Request preprocessing and validation
  * Bedrock API invocation
  * Response formatting and error handling
  * Conversation context management

* Created chatbot API endpoints:
  * `/chat` - Main conversation endpoint
  * `/chat/history` - Retrieve conversation history
  * `/chat/clear` - Clear conversation context

* Implemented basic chatbot features:
  * Natural language understanding
  * Context-aware responses
  * Multi-turn conversation support
  * Error recovery mechanisms

* Testing and validation:
  * Response time averaging 2-3 seconds
  * 95% accuracy for basic queries
  * Successfully handled edge cases

* Optimized prompt engineering for better movie/TV show related responses
