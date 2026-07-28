# Lesson 3: Building an Azure-Based Anomaly Detection Notebook & Evaluating Data Storage

## Lesson Description

In this lesson, students will build a machine learning workflow in Microsoft Azure Machine Learning Studio Notebooks to detect anomalies in manufacturing sensor data. The workflow uses a custom **Isolation Forest** model, trained through Python code, to identify unusual sensor readings. Students will evaluate the model's predictions and export the results to Azure Blob Storage. The lesson simulates a real-world predictive maintenance workflow and emphasizes cloud storage strategies.

## Main Learning Goal

Students will be able to build, evaluate, and store a cloud-based anomaly detection model in Azure, while analyzing tradeoffs in data storage and integrating external data structures.

## Essential Question

**How can cloud-based machine learning systems help engineers identify equipment problems before they cause manufacturing failures?**

## Standards

- **4.4**: Create a computational model using a large data set, make inferences, and address the limitations of the model.
- **3.4**: Evaluate the data storage needs of a computing solution and explain the tradeoff between speed and data storage.
- **5.3**: Determine when external data structures are appropriate and incorporate them into programs.

## Objectives

- Train an Isolation Forest anomaly detection model.
- Analyze the tradeoffs in data storage within cloud-based workflows.
- Identify opportunities to integrate external data storage structures.

---

## Introduction to the Cloud

Think of the cloud as a very large, powerful computer that lives in a data center. Instead of running everything on your personal device, you can use this powerful remote computer through the internet.

Microsoft's cloud platform, called **Azure**, lets you:

- Store data
- Build machine learning models
- Run apps without needing your own servers

A **machine learning model** is like a decision-making tool.
For example, if you give it sensor readings from a factory, it can learn to spot signs that a machine might break soon.

In this lesson, the model isn't pre-built — you write the Python code yourself using a library called **scikit-learn**, inside a notebook that runs on an Azure cloud computer.

> Think of Isolation Forest like sorting students by height.
> Most students cluster between 5 and 6 feet tall. One student who is 7 feet tall gets separated from the group almost immediately when you keep splitting people into smaller groups. The model applies this same idea to sensor readings — values that separate from the rest of the data quickly are flagged as anomalies.

---

## Building a Workflow in Azure

### Understanding the Dataset

The dataset (`anomaly_data.csv`) we'll use comes from sensors attached to machines on a manufacturing floor.

Each row in the dataset includes:

- `timestamp`: When the sensor reading was taken
- `machine_id`: Identifies which machine the data came from
- `sensor_reading`: A numerical value showing the machine's status or behavior
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
