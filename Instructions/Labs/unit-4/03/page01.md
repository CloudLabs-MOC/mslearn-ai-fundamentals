# Lesson 3: Deploying Azure-Based Anomaly Detection Pipeline & Evaluating Data Storage

## Lesson Description
In this lesson, students will deploy a machine learning pipeline in Microsoft Azure to detect anomalies in a time-series dataset. The pipeline will use Azure’s built-in PCA-Based Anomaly Detection module. Students will compare the performance of the model and evaluate storage needs in a cloud-based environment. The lesson simulates real-world deployment of ML workflows and emphasizes cloud storage strategies.

## Main Learning Goal
Students will be able to deploy, compare, and evaluate machine learning pipelines using built-in and custom components in Azure, while analyzing tradeoffs in data storage and integrating external data structures.

## Essential Question
**How can deploying and comparing different machine learning pipelines in Azure help improve system performance and data management in an industrial setting?**

## Standards
- **4.4**: Create a computational model using a large data set, make inferences, and address the limitations of the model.  
- **3.4**: Evaluate the data storage needs of a computing solution and explain the tradeoff between speed and data storage.  
- **5.3**: Determine when external data structures are appropriate and incorporate them into programs.

## Objectives
- Deploy two anomaly detection pipelines in Azure (PCA-based).
- Analyze the tradeoffs in data storage within cloud-based pipelines.
- Identify opportunities to integrate external data storage structures.

---

## Introduction to the Cloud

Think of the cloud as a very large, powerful computer that lives in a data center. Instead of running everything on your personal device, you can use this powerful remote computer through the internet. 

Microsoft’s cloud platform, called **Azure**, lets you:
- Store data
- Build machine learning models
- Run apps without needing your own servers

A **machine learning model** is like a decision-making tool.  
For example, if you give it sensor readings from a factory, it can learn to spot signs that a machine might break soon.

Azure has several built-in machine learning models that are ready to use.  
These models are already trained, so you don’t need to write code or start from scratch.  
You just upload your data, adjust a few settings, and Azure takes care of the rest.

> Think of these like using a pre-mixed cake batter.  
> You follow the steps and get a reliable result, even if you don’t know how to bake from scratch!

---

## Building a Pipeline in Azure

### Understanding the Dataset

The dataset (`anomaly_data.csv`) we’ll use comes from sensors attached to machines on a manufacturing floor.

Each row in the dataset includes:
- `timestamp`: When the sensor reading was taken  
- `machine_id`: Identifies which machine the data came from  
- `sensor_reading`: A numerical value showing the machine’s status or behavior  
- `anomaly_flag`: A binary indicator (`0` or `1`) marking whether the data point is normal or an anomaly

### Why is this important?

In a factory, machines need to work within safe and expected ranges.  
If a sensor reading is off, it could mean something is wrong, such as:
- The machine is overheating or under too much pressure
- Parts are wearing out
- The machine is running incorrectly

If these warning signs go unnoticed, it can lead to:
- Costly breakdowns
- Delays
- Even accidents

**Detecting anomalies early helps companies keep machines running safely and efficiently.**
