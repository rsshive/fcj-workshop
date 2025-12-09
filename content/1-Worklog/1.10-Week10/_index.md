---
title: "Week 10 Worklog"
date: "`r Sys.Date()`"
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Integrate TMDB data source into the chatbot
* Develop Lambda functions to support chatbot operations
* Enhance chatbot with movie/TV show information capabilities

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Research TMDB API structure and capabilities <br> - Plan TMDB data integration strategy <br> - Define required movie/TV data fields                                                                  | 11/11/2025 | 11/11/2025      | <https://developers.themoviedb.org/> |
| 3   | - Develop Lambda functions for TMDB API calls <br>&emsp; + Search movies/TV shows <br>&emsp; + Get details and metadata <br>&emsp; + Handle API rate limits                                          | 12/11/2025 | 12/11/2025      | TMDB API documentation |
| 4   | - Integrate TMDB data with chatbot <br>&emsp; + Connect TMDB Lambda to Bedrock <br>&emsp; + Enhance chatbot prompts with real data <br>&emsp; + Format movie/TV information                          | 13/11/2025 | 13/11/2025      | Lambda integration patterns |
| 5   | - Develop supporting Lambda functions <br>&emsp; + Data caching layer <br>&emsp; + Error handling and retries <br>&emsp; + Response optimization                                                      | 14/11/2025 | 14/11/2025      | AWS Lambda best practices |
| 6   | - **Practice:** <br>&emsp; + Test chatbot with TMDB data <br>&emsp; + Validate data accuracy <br>&emsp; + Optimize performance                                                                        | 15/11/2025 | 15/11/2025      | Testing and optimization guides |


### Week 10 Achievements:

* Successfully integrated TMDB data source:
  * Configured TMDB API access
  * Implemented secure API key management
  * Set up rate limiting and caching

* Developed comprehensive Lambda functions:
  * **TMDB Search Lambda**: Search movies and TV shows
  * **TMDB Details Lambda**: Fetch detailed information
  * **Data Processing Lambda**: Format and optimize data
  * **Cache Management Lambda**: Manage frequently accessed data

* Enhanced chatbot capabilities:
  * Real-time movie/TV show information
  * Accurate cast and crew details
  * Release dates and ratings
  * Recommendations based on TMDB data
  * View EC2 service
  * Create and manage key pairs
  * Check information about running services
  * ...

* Acquired the ability to connect between the web interface and CLI to manage AWS resources in parallel.
* ...
