
# AI-900: Microsoft Azure AI Fundamentals Workshop

Welcome to your AI-900: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn Azure Services. Let's begin by making the most of this experience.

# Module 13: Azure AI Studio

### Overall Estimated timing: 45 minutes

## Overview

In this hands-on lab, you'll gain practical experience in leveraging Azure AI Foundry to build and manage AI solutions. You will learn how to navigate the Azure AI Foundry portal, create an Azure AI hub and project, and integrate connected resources to enhance your AI capabilities. Additionally, you'll explore various AI services available in Azure AI Foundry and deploy a generative AI model, testing its functionality in real-world scenarios. By the end of this lab, you'll be proficient in setting up AI projects, integrating resources, and deploying generative AI models, equipping you with essential skills to develop and manage AI-powered solutions in Azure.

## Objectives

By the end of this lab, you will be able to create a project in Azure AI Foundry and analyze a receipt using Azure AI Document Intelligence to extract key information efficiently

- **Open Azure AI Foundry portal**
- **Create an Azure AI hub and project**
- **Add a connected resource**
- **Explore AI Services**
- **Deploy and test a generative AI model**

## Pre-requisites Required

The solution you'll create for Fourth Coffee requires the following resources in your Azure subscription:

- An **Azure AI Search** resource, which will manage indexing and querying.

- An **Azure AI services** resource, which provides AI services for skills that your search solution can use to enrich the data in the data source with AI-generated insights.

    > **Note**
    > Your Azure AI Search and Azure AI services resources must be in the same location!

- A **Storage account** with blob containers, which will store raw documents and other collections of tables, objects, or files.

## Architecture

In this hands-on lab, the architecture flow includes several essential components.

1. **Create a project in Azure AI Foundry portal**: Understanding how to set up a new project in Azure AI Foundry, including configuring AI resources to support Vision and Document Intelligence capabilities. This involves selecting the appropriate AI models, setting up access permissions, and ensuring the project is properly structured for document processing workflows.

1. **Analyze a receipt with Azure AI Document Intelligence in Azure AI Foundry**:  Learning how to upload and analyze a receipt using Azure AI Document Intelligence. This includes extracting key details such as the merchant name, transaction date, and total amount, and understanding how to interpret the extracted data for further processing or integration into business applications.

## Architecture Diagram

![](../media/new-ai900-lab13-archdiagram.JPG)

## Explanation of Components

1. **Azure AI Search**: A cloud-based search service that enables intelligent search and data exploration capabilities. It provides tools for indexing, querying, and analyzing structured and unstructured data, incorporating AI-powered features like semantic search, natural language processing, and document understanding.  

1. **Azure AI Services**: A comprehensive suite of pre-built and customizable AI capabilities, including vision, speech, language, and decision-making models. It provides tools for building intelligent applications with features like image recognition, natural language understanding, real-time transcription, and anomaly detection. 

1. **Azure Storage Account**: A cloud-based storage solution that provides scalable, secure, and highly available storage for various data types, including blobs, files, queues, tables, and disks. It offers redundancy options, encryption, and seamless integration with Azure services for data management and analytics.

# Getting Started with lab
 
Welcome to your AI-900: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn about machine learning and AI concepts and related Microsoft Azure services. Let's begin by making the most of this experience:
 
## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and **lab guide** will be right at your fingertips within your web browser.
 
![Access Your VM and Lab Guide](../media/4-7.png)

### Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.

## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.
 
![Explore Lab Resources](../media/aig2.png)

## Lab Guide Zoom In/Zoom Out
 
To adjust the zoom level for the environment page, click the **A↕: 100%** icon located next to the timer in the lab environment.

![](../media/zoomin.png)

## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
![Use the Split Window Feature](../media/aig3.png)

## Managing Your Virtual Machine
 
Feel free to **start, stop, or restart (2)** your virtual machine as needed from the **Resources (1)** tab. Your experience is in your hands!
 
![Manage Your Virtual Machine](../media/aig4.png)

## Lab Duration Extension

1. To extend the duration of the lab, kindly click the **Hourglass** icon in the top right corner of the lab environment. 

    ![Manage Your Virtual Machine](../media/gext.png)

    >**Note:** You will get the **Hourglass** icon when 10 minutes are remaining in the lab.

2. Click **OK** to extend your lab duration.
 
   ![Manage Your Virtual Machine](../media/gext2.png)

3. If you have not extended the duration prior to when the lab is about to end, a pop-up will appear, giving you the option to extend. Click **OK** to proceed.

## Let's Get Started with Azure Portal
 
1. On your virtual machine, click on the Azure Portal icon as shown below:
 
   ![Launch Azure Portal](../media/sc900-image(1).png)

2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
       ![Enter Your Username](../media/sc900-image-1.png)
 
3. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Password](../media/pwd.png)
 
4. If prompted to stay signed in, you can click **No**.

5. If **Action required** pop-up window appears, click on **Ask later**.
   
    ![](../media/asklater.png)
 
6. If prompted to stay signed in, you can click "No."

    ![](../media/staysigned2.png)
 
7. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **Cancel**.

## Steps to Proceed with MFA Setup if the "Ask Later" Option is Not Visible

1. If you see the pop-up **Stay Signed in?**, click **No**.

1. If **Action required** pop-up window appears, click on **Next**.

   
   ![](../media/mfa1.png)

1. On **Start by getting the app** page, click on **Next**.
1. Click on **Next** twice.
1. In **android**, go to the play store and Search for **Microsoft Authenticator** and Tap on **Install**.

   ![Install](../media/mfa2.png)

   > Note: For Ios, Open the app store and repeat the steps.

   > Note: Skip if already installed.

1. Open the app and tap on **Scan a QR code**.

1. Scan the QR code visible on the screen and click on **Next**.

   ![QR code](../media/mfa3.png)

1. Enter the digit displayed on the Screen in the Authenticator app on mobile and tap on **Yes**.

1. Once the notification is approved, click on **Next**.

   ![Approved](../media/mfa4.png)

1. Click on **Done**.

1. If prompted to stay signed in, you can click **"No"**.

1. Tap on **Finish** in the Mobile Device.

   > NOTE: While logging in again, enter the digits displayed on the screen in the **Authenticator app** and click on Yes.

1. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **"Cancel"** to skip the tour.

1. If you see the pop-up **You have free Azure Advisor recommendations!**, close the window to continue the lab.


## Support Contact
 
The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels explicitly tailored for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.
 
Learner Support Contacts:
 
- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Click on **Next** from the lower right corner to move on to the next page.

   ![Start Your Azure Journey](../media/sc900-image(3).png)

## Happy Learning !!
