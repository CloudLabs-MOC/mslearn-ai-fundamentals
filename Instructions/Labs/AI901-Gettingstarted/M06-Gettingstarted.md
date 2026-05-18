# AI-900: Microsoft Azure AI Fundamentals Workshop

Welcome to your AI-900: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn Azure Services. Let's begin by making the most of this experience.

# Analyze text in the Microsoft Foundry portal

### Overall Estimated timing: 30 Minutes

## Overview:

In this hands-on lab, you'll gain practical experience in analyzing text using the Microsoft Foundry portal, a platform for building intelligent applications with Azure AI Language services. You will learn how to create and configure a project in the Microsoft Foundry portal and explore key Natural Language Processing (NLP) capabilities. Specifically, you will extract named entities from text, identify key phrases, and generate text summaries using Azure AI Language. By the end of this lab, you’ll be proficient in leveraging Microsoft Foundry for text analysis, equipping you with the skills to extract meaningful insights from unstructured text data in various real-world scenarios.

## Objectives

By the end of this lab, you will be able to create a project in Microsoft Foundry and analyze text using Azure AI language.

1. **Create a project in Microsoft Foundry portal**: You will learn how to sign in to the Microsoft Foundry portal, create a new project, and access the Language playground to explore Azure AI Language features.

1. **Extract named entities with Azure AI Language in Microsoft Foundry portal:** You will learn how to use the Language playground to perform Named Entity Recognition (NER) on sample text and identify entities such as locations, dates, and organizations along with confidence scores.

1. **Extract key phrases with Azure AI Language in Microsoft Foundry portal:** You will learn how to use the Language playground to extract key phrases from text, helping identify the most important terms and topics within unstructured data.

1. **Summarize text with Azure AI Language in Microsoft Foundry portal:** You will learn how to generate an extractive summary using Azure AI Language in the Language playground by identifying the most relevant sentences from a given text.

## Pre-requisites

Basic knowledge of Azure AI services, Microsoft Foundry and Azure AI Language.

## Architecture

In this hands-on lab, the architecture flow includes several essential components.

1. **Create a project in Microsoft Foundry portal**: Understanding how to set up a new project in Microsoft Foundry, including configuring AI resources to support Vision and Document Intelligence capabilities. This involves selecting the appropriate AI models, setting up access permissions, and ensuring the project is properly structured for document processing workflows.

1. **Extract named entities with Azure AI Language in Microsoft Foundry portal:**
Extracting named entities using Azure AI Language in Microsoft Foundry helps businesses automate data categorization, improve text analytics, and enhance information retrieval. It identifies critical data points such as names, locations, organizations, and dates from unstructured text, making it invaluable for industries like finance, legal, and customer service.

1. **Extract key phrases with Azure AI Language in Microsoft Foundry portal:** Key phrase extraction in Azure AI Language helps automatically identify important topics and keywords from large text datasets, enabling faster insights and improved searchability. It enhances workflows like sentiment analysis, content categorization, and business intelligence by streamlining text processing. Integrating this with Microsoft Foundry allows businesses to automate data-driven decision-making efficiently.

1. **Summarize text with Azure AI Language in Microsoft Foundry portal:** Text summarization in Azure AI Language enables automatic condensation of lengthy documents into concise summaries, preserving key information while improving readability. This helps businesses quickly extract insights from reports, articles, and customer feedback. Integrated with Microsoft Foundry, it enhances efficiency in knowledge management, decision-making, and content automation.

## Architecture Diagram

![](../media/lab6-arch.png)

## Explanation of Components:

1. **Microsoft Foundry:** A centralized platform for managing AI projects, models, and experiments. It provides tools for building, testing, and deploying AI solutions.    

1. **Azure AI Language**: A cloud-based service that enables natural language processing (NLP) capabilities, including text analysis, entity recognition, sentiment analysis, and language understanding. It provides tools for extracting insights from text, building conversational AI, and enhancing search experiences.

# Getting Started with lab
 
Welcome to your AI-900: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn about machine learning and AI concepts and related Microsoft Azure services. Let's begin by making the most of this experience:
 
## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and **Guide** will be right at your fingertips within your web browser.
 
![Access Your VM and Lab Guide](../media/4-7.png)

## Virtual Machine & Lab Guide
 
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
 
Feel free to **Start, Stop, or Restart (2)** your virtual machine as needed from the **Resources (1)** tab. Your experience is in your hands!
 
![Manage Your Virtual Machine](../media/aig4.png)

## Track Your Progress

Click on the **Progress** tab to track your progress in the lab. The percentage increases as you complete each validation and reaches 100% when all validations are successfully completed.  

On the **Progress (1)** tab, you can view your overall points and validation status, **Validations 0/1 (2)**.    

![Manage Your Virtual Machine](../media/AI-l12-prg.png)

![Manage Your Virtual Machine](../media/AI-l12-prg1.png)

## Lab Duration Extension

1. To extend the duration of the lab, kindly click the **Hourglass** icon in the top right corner of the lab environment. 

    ![Manage Your Virtual Machine](../media/gext.png)

    >**Note:** You will get the **Hourglass** icon when 10 minutes are remaining in the lab.

2. Click **OK** to extend your lab duration.
 
   ![Manage Your Virtual Machine](../media/gext2.png)

3. If you have not extended the duration prior to when the lab is about to end, a pop-up will appear, giving you the option to extend. Click **OK** to proceed.

## Let's Get Started with Azure Portal
 
1. On your virtual machine, click on the **Azure Portal** icon as shown below:
 
   ![Launch Azure Portal](../media/sc900-image(1).png)

2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your **credentials (1)** and click on **Next (2)**:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
       ![Enter Your Username](../media/sign-in-page.png)
 
3. Next, provide your **password (1)** and click on **Next (2)**:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Password](../media/tap-password.png)
 
4. If you see the pop-up **Stay-Signed in?**, click **No**.

      ![](../media/Sign-in-no.png)
 
6. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **Cancel**.

    ![](../media/AI-l6-4.png)

## Support Contact
 
The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels explicitly tailored for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.
 
Learner Support Contacts:
 
- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Click on **Next** from the lower right corner to move on to the next page.

   ![Start Your Azure Journey](../media/sc900-image(3).png)

## Happy Learning !!
