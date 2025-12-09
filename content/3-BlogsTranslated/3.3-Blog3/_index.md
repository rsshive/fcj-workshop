---
title: "Blog 3"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
{{% notice warning %}}
 **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

# Preventing machine breakdowns: How Physical AI predicts equipment problems

By Ram Gorur, Ashish Chaurasia, and Channa Samynathan on August 15, 2025 | in [Amazon Bedrock Agents](https://aws.amazon.com/blogs/iot/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-agents/), [Amazon Bedrock Guardrails](https://aws.amazon.com/blogs/iot/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/amazon-bedrock-guardrails/), [Amazon Machine Learning](https://aws.amazon.com/blogs/iot/category/artificial-intelligence/amazon-machine-learning/), [Amazon SageMaker AI](https://aws.amazon.com/blogs/iot/category/artificial-intelligence/sagemaker/amazon-sagemaker-ai/), [Artificial Intelligence](https://aws.amazon.com/blogs/iot/category/artificial-intelligence/), [Automotive](https://aws.amazon.com/blogs/iot/category/industries/automotive/), [AWS IoT Core](https://aws.amazon.com/blogs/iot/category/internet-of-things/aws-iot-platform/), [AWS IoT FleetWise](https://aws.amazon.com/blogs/iot/category/internet-of-things/aws-iot-fleetwise/), [Generative AI](https://aws.amazon.com/blogs/iot/category/artificial-intelligence/generative-ai/), [Manufacturing](https://aws.amazon.com/blogs/iot/category/industries/manufacturing/), [Technical How-to](https://aws.amazon.com/blogs/iot/category/post-types/technical-how-to/)

## Physical AI: Intelligence that acts in the real world

Physical AI differs from traditional AI in that it directly interacts with and controls the physical world. While traditional AI processes data and generates text on screens, Physical AI enables robots, autonomous vehicles, and intelligent systems to sense, understand, and act in real multidimensional environments.

The key difference: Physical AI understands spatial relationships and physical behaviors through training on synthetic and real-world data, bridging the gap between digital intelligence and physical action.

How it works: High-fidelity computer simulations create digital twins of real spaces like factories and streets, where virtual sensors and machinery that mirror real-world physics are used to train specialized models.

## Transforming maintenance

Physical AI transforms maintenance from reactive to autonomous. These systems sense their environment, understand the relationships between components, and take preventive actions before problems occur. The [Predictive Maintenance (PdM) market](https://market.us/report/automotive-predictive-maintenance-market/) in automotive will reach  billion by 2032, a revolution in vehicle care driven by Physical AI capabilities.

Electric vehicles (EVs) are a prime example of where Physical AI can be applied. They can be designed to continuously learn from their surroundings, make instant decisions to optimize performance, and manage their own health while in motion. These systems understand how parts mesh and work together, predict how physical forces will impact different components, and adjust driving patterns to reduce wear.

The same principles behind PdM in automotive also appear in other fields. Manufacturing robots now predict and prevent equipment failures before they occur. In smart warehouses, systems schedule private maintenance for maximum efficiency. Medical robots monitor accuracy and self-calibrate when needed. Even smart infrastructure can detect its own problems and coordinate automatic repairs.

## How does it actually work?

Physical AI systems in modern electric vehicles represent an advanced approach to vehicle monitoring and maintenance through an integrated sensor network that continuously analyzes multiple vehicle systems. These systems monitor battery health, motor performance, brakes, and suspension system components while building dynamic models of component interactions. AI monitors relationships between temperature, vibration, electrical load, and mechanical stress to predict and prevent potential failures. The system takes proactive measures such as adjusting charging patterns to reduce battery stress and modifying regenerative braking to minimize wear. This predictive maintenance approach transforms traditional reactive vehicle maintenance into a proactive system that understands and responds to real-world conditions, although specific performance metrics and outcome data are needed to quantify benefits.

## Overview

In this blog, you'll learn about the different types of generative AI applications that are transforming PdM supporting Physical AI and how AWS services enable these innovations.

AWS Internet of Things (IoT), Artificial Intelligence (AI)/Machine Learning (ML), and generative AI have transformed the connected vehicle landscape, and more specifically electric vehicles, by providing innovative solutions for PdM supporting Physical AI. The integration of these advanced technologies has paved the way for a more efficient approach to electric vehicle maintenance, ensuring optimal performance and longevity through deep understanding of physical systems.

AWS IoT is used by many automotive customers to develop and manage Physical AI applications (autonomous driving, predictive maintenance, entertainment, etc.). AWS IoT enables electric vehicles to connect to the cloud and transmit real-time data about condition and performance, including spatial relationships and physical interactions between components. This data is then analyzed using AWS AI/ML services that can identify patterns, detect anomalies, and predict potential issues by understanding the physics of how different systems interact in the real world.

Generative AI in PdM supporting Physical AI operates through four main stages: Machine prioritization uses retrieval-augmented generation (RAG) systems to analyze structured and unstructured maintenance data, identifying which equipment needs priority. Failure prediction processes machine sensor data through real-time analysis and ML models to predict failures before they occur. Repair plan generation leverages large language models to create comprehensive work orders with instructions and resource allocation by integrating data from multiple sources. Maintenance guide generation combines service notes and repair plans using generative AI to provide enhanced actionable guidance for technicians.

This approach enables automotive manufacturers to collect rich data about vehicle performance under real physical conditions, improve future vehicle design by understanding how vehicles interact with the physical environment, and make informed decisions about component improvements that account for physics and actual usage patterns.

## Architecture overview

PdM in electric vehicles requires monitoring, analysis, and action based on collected information. Electric vehicles are equipped with multiple sensors that collect data about battery health, vehicle location, motor health, brakes, and more. To reduce operating costs, this model aims to enhance electric vehicle maintenance by using sensor data to create PdM models.

## 1. Data collection and processing

Connected vehicles bring opportunities for manufacturers to enhance vehicle quality, safety, and autonomy. However, these advances come with challenges, particularly managing and effectively leveraging the massive volume of data from connected vehicles. The data collection task is complex due to the diverse proprietary data formats of electronic control units (ECUs) and the significant costs associated with scaling data collection operations.

[AWS IoT FleetWise](https://aws.amazon.com/iot-fleetwise/) is a purpose-built service for the automotive industry. It enables you to easily collect, transform, and transmit vehicle data from many different formats regardless of make, model, or options. The service standardizes data formats, making cloud-based analysis easier without custom data collection systems. With AWS IoT FleetWise, you can transmit data to the cloud in near-real-time using intelligent filtering capabilities. By selecting transmitted data and defining rules, events based on parameters like weather conditions, location, or vehicle type, you can reduce the amount of data sent to the cloud.

In this section, we will use AWS IoT FleetWise to collect and store vehicle data in S3 for training machine learning models for predictive analytics.

* Set up AWS IoT FleetWise Edge Agent on vehicle  Create Edge Agent for AWS IoT FleetWise to create connection between vehicle and cloud. Edge Agent is fully functional embedded software written in C++ designed to collect vehicle data, capable of running on most embedded Linux platforms. IoT FleetWise controls what data is collected and transmitted by the Edge Agent from the vehicle.
* Create signal catalog  Signals structure vehicle data and metadata into distinct types:
  * **Sensors** record real-time measurements like temperature, storing the name, data type, and unit of each signal.
  * **Attributes** contain fixed information like manufacturer and production date. Branches create hierarchical organization  Vehicle branches into Powertrain, containing combustionEngine sub-branch. Sensor data tracks instantaneous vehicle state including fluid levels, temperatures, and vibrations.
  * **Actuator** data controls device state for components like engines and door locks. When you adjust a device  like turning on a heater  you update its actuator data.

The signal catalog simplifies vehicle modeling with predefined signals. AWS IoT FleetWise integrates Vehicle Signal Specification (VSS), defining standard signals like "vehicle_speed" in km/h. This central repository of sensors and standard signals accelerates new vehicle model creation through efficient signal reuse.

Create vehicle model  You use signals to establish standardized vehicle models that normalize vehicle formats. Vehicle models ensure uniform data across multiple vehicles of the same type, enabling efficient processing from fleets. Vehicles created from the same model inherit a consistent signal set.

* **Create decoder manifest**  Decoder manifest contains decoding information that AWS IoT FleetWise uses to translate binary vehicle data into understandable values. IoT FleetWise supports OBD II, CAN bus, and vehicle middleware like ROS2. For example, if a vehicle uses OBD network interface, the decoder manifest should include signal associations with message ID 11 and binary data like 000011 with OBDCoolantTemperature.
* **Create vehicles**  Vehicles are instances of vehicle model. Vehicles must be created from vehicle model and associated with decoder manifest. Vehicles upload one or more data streams to the cloud. For example, a vehicle might send mileage, battery voltage, and heater status to the cloud.
* **Create and deploy campaign to collect vehicle data**  After modeling vehicles and creating signal catalog, you can create data collection campaigns using signals created in the model. Campaigns are orchestrations of data collection rules. Campaigns provide Edge Agent for AWS IoT FleetWise with instructions on how to select, collect, and transmit data to the cloud. All campaigns are created on the cloud. After campaigns are marked as approved by team members, AWS IoT FleetWise automatically deploys them to vehicles. Automotive teams can choose to deploy campaigns to specific vehicles or fleets. The Edge Agent software will not begin collecting vehicle network data until running campaigns are deployed to the vehicle.
* **Store vehicle data in S3**  Edge Agent software for AWS IoT FleetWise transmits selected vehicle data to Amazon Timestream or Amazon Simple Storage Service (Amazon S3). After data reaches its destination, you can use other AWS services to visualize and share.

## 2. Training PdM model

Machine Learning (ML) algorithms are used here to perform PdM analysis to predict equipment failures and optimize maintenance operations. PdM uses real-time data to analyze factors correlated with electric vehicle failures, thereby predicting the likelihood of failure occurrence. This proactive approach can effectively minimize unplanned vehicle breakdowns, extend component lifespan, and reduce total repair costs.

When electric vehicle data is brought into the AWS environment, it is stored in Amazon S3 bucket. This data is then used to create real-time predictions from trained and deployed ML models. Predictions can be further processed and used by downstream applications to take necessary actions and initiate PdM operations. The solution includes the following parts:

* **Train and deploy model**  We use PdM dataset from Data Repository to train machine learning model with XGBoost algorithm using SageMaker. Then, deploy trained model to SageMaker asynchronous inference endpoint.
* **Train model**  To train model, we first store electric vehicle data in Amazon S3. This enables secure and efficient storage of large amounts of data. After data is stored, we begin training process using Amazon SageMaker Training. This service is designed to handle training machine learning models at scale. Its capabilities enable fast and accurate model training, even with large datasets, ensuring efficient and effective model training, leading to high-quality results.
* **Collect near-real-time electric vehicle data**  Electric vehicle data is collected from vehicles and processed in AWS environment before storage in Amazon S3. This data includes critical parameters like battery voltage, battery temperature, motor health, location, etc. Then, Amazon Lambda function is triggered to invoke Amazon SageMaker asynchronous endpoint.
* **Perform near-real-time PdM**  Amazon SageMaker asynchronous endpoint is used to generate inferences from deployed model for incoming electric vehicle data. These endpoints are particularly suitable for PdM workloads because they support larger payload sizes and can generate inferences in minutes. Inferences from the model are stored in Amazon S3. They can be applied to create dashboards, visualizations, and perform generative AI tasks.

To ensure an effective Predictive Maintenance solution at scale, implement robust training and deployment pipelines by referencing AWS Well-Architected Framework principles for machine learning.

## 3. Generative AI

* Create **AWS Glue Data Catalog** using AWS Glue crawler (or other method). Using [Titan-Text-Embeddings](https://docs.aws.amazon.com/bedrock/latest/userguide/titan-embedding-models.html) model on Amazon Bedrock, convert metadata to embeddings and store in Amazon OpenSearch Serverless vector store, serving as knowledge base in [RAG framework](https://aws.amazon.com/what-is/retrieval-augmented-generation/). At this stage, the process is ready to receive queries in natural language.
* Users enter queries in natural language. You can use any web application to provide chat interface. Therefore, we don't cover UI details in this post.
* Solution applies RAG framework through similarity search, adding context from metadata from vector database. This table is used to find correct table, database, and attributes.
* Model receives generated SQL query and connects to Athena to validate syntax.
* Finally, run SQL using Athena and generate output. Output is presented to user. For architecture simplification, we don't show this step.

## Conclusion

The convergence of Generative AI and Physical AI is reshaping condition-based and predictive maintenance across industries. As explored, generative AI's capabilities in analyzing large datasets, generating synthetic training scenarios, and providing intelligent recommendations are transforming how Physical AI systems monitor, diagnose, and self-maintain. From electric vehicles predicting battery degradation to industrial robots self-scheduling maintenance, we're witnessing a paradigm shift where intelligent systems don't just perform tasks  they proactively preserve and optimize their own operational capabilities.

## References

1. [NVIDIA: What is Physical AI?](https://www.nvidia.com/en-us/glossary/generative-physical-ai/)
2. [Predictive maintenance: When a machine knows in advance that repairs are needed](https://www.press.bmwgroup.com/global/article/detail/T0338859EN/predictive-maintenance:-when-a-machine-knows-in-advance-that-repairs-are-needed?language=en)
3. [Well-Architected machine learning](https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/well-architected-machine-learning.html)
4. [Build a robust text-to-SQL solution](https://aws.amazon.com/blogs/machine-learning/build-a-robust-text-to-sql-solution-generating-complex-queries-self-correcting-and-querying-diverse-data-sources/)
5. [Global Automotive Predictive Maintenance Market](https://market.us/report/automotive-predictive-maintenance-market/)

## About the authors

**Ram Gorur** is a Senior Solutions Architect at AWS, specializing in Agriculture and Consulting Services, with a focus on Edge AI and Connected Products. Based in Virginia, he leverages over 23 years of comprehensive IT experience to help AWS enterprise customers deploy IoT solutions spanning from edge devices to cloud infrastructure. His expertise encompasses designing and deploying connected product solutions across diverse industries, where he develops custom architectural frameworks connecting edge computing with cloud capabilities.

**Ashish Chaurasia** is a Senior Technical Account Manager at AWS, having collaborated with enterprise customers since 2020 to align cloud technologies with strategic business outcomes. With over 17 years of software development experience, he specializes in guiding organizations through cloud-native transformation journeys. Ashish is an IoT enthusiast and enjoys building DIY projects to automate daily tasks.

**Channa Samynathan** is a Senior Global Specialist Solutions Architect for AWS Edge AI & Advanced Compute. With over 29 years of experience in the technology industry, Channa has held diverse roles including design engineer, system tester, operations, business consultant, and product manager. His career spans multiple multinational telecommunications companies, where he consistently demonstrated expertise in sales, business development, and technical solution design. Channa's global experience, having worked in over 26 countries, has equipped him with deep technical knowledge and ability to rapidly adapt to new technologies.
