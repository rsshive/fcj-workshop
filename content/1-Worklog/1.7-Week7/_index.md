---
title: "Week 7 Worklog"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 7 Objectives:

* Finalize and standardize API endpoint structure
* Test basic functionality of the application
* Set up AWS Cognito for user authentication and authorization

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Team meeting to discuss and standardize API endpoints <br> - Define API structure and naming conventions <br> - Document API specifications                                                          | 21/10/2025 | 21/10/2025      | API design best practices, REST standards |
| 3   | - Implement standardized API endpoints <br>&emsp; + User management APIs <br>&emsp; + Content APIs <br>&emsp; + Authentication APIs                                                                   | 22/10/2025 | 22/10/2025      | <https://docs.aws.amazon.com/apigateway/> |
| 4   | - Test basic application functionality <br> - Perform integration testing <br> - Debug and fix identified issues                                                                                       | 23/10/2025 | 23/10/2025      | Testing frameworks, Postman |
| 5   | - Learn AWS Cognito fundamentals <br>&emsp; + User pools <br>&emsp; + Identity pools <br>&emsp; + Authentication flows <br> - Plan Cognito integration strategy                                       | 24/10/2025 | 24/10/2025      | <https://docs.aws.amazon.com/cognito/> |
| 6   | - **Practice:** <br>&emsp; + Set up Cognito user pool <br>&emsp; + Configure authentication flows <br>&emsp; + Integrate Cognito with API Gateway                                                     | 25/10/2025 | 25/10/2025      | <https://docs.aws.amazon.com/cognito/> |


### Week 7 Achievements:

* Successfully standardized all API endpoints with consistent naming conventions and structure

* Completed integration testing for basic application features:
  * User registration and login flows
  * Content retrieval APIs
  * Data validation and error handling

* Set up AWS Cognito user pool with:
  * User authentication and authorization
  * Password policies and MFA options
  * Custom attributes for user profiles

* Integrated Cognito with API Gateway:
  * Configured authorizers
  * Implemented JWT token validation
  * Secured API endpoints

* Fixed critical bugs and improved API response times

* Documented API endpoints and authentication flows for team reference
