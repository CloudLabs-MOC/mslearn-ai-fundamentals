
# AI-901: Microsoft Azure AI Fundamentals Workshop

Welcome to your AI-901: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn Azure Services. Let's begin by making the most of this experience.

# Getting Started with lab
 
Welcome to your AI-901: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn about machine learning and AI concepts and related Microsoft Azure services. Let's begin by making the most of this experience:
 
## Overview

In these hands-on labs, you will develop the skills required to get started with **Microsoft Foundry** across a range of AI scenarios. You will begin by creating a Foundry project, exploring the portal and its Azure resources, and deploying a generative AI model, then connect a sample client application to it using the project endpoint, API key, and deployment name. You will use Azure AI Language capabilities such as sentiment analysis, key phrase extraction, named entity recognition, and summarization, and combine generative AI prompts with Azure Language analyzers to detect language and identify personally identifiable information.You will build a speech-enabled agent using Azure Speech - Voice Live for real-time speech-to-text and text-to-speech interaction.
You will apply default and custom content safety guardrails to manage harmful, offensive, or sensitive model outputs.You will build a Python application that performs translation, transliteration, language detection, and sentiment analysis using a single deployed model.
By completing these labs, you will gain practical, end-to-end experience building, customizing, and integrating AI solutions with Microsoft Foundry.

## Objectives

By the end of these labs, you will be able to:

1. **Create and explore a Microsoft Foundry project:** Create a Microsoft Foundry project, explore the Foundry portal and its connected Azure resources, deploy and test a generative AI model in the playground, and connect a sample client application using the project endpoint, API key, and model deployment name.

2. **Build generative AI agents:** Deploy a generative AI model, interact with it in the Chat Playground, customize its behavior with system instructions, extend it with Web Search and File Search tools, and create, preview, and integrate a reusable AI agent.

3. **Analyze text with the Language Playground:** Use the Language Playground to perform sentiment analysis, extract key phrases and named entities, and generate extractive summaries from text.

4. **Combine generative AI with language analyzers:** Deploy a GPT model to summarize text through natural language prompts in the Chat Playground, and use Azure Language analyzers to detect language and identify personally identifiable information (PII).

5. **Build a speech-enabled agent:** Create and configure an agent, enable Azure Speech - Voice Live, and explore real-time speech-to-text and text-to-speech interaction in the agent playground.

6. **Work with computer vision and generative models:** Analyze images with a vision-enabled generative AI model, and generate new images and videos from text prompts using image- and video-generation models.

7. **Extract information from documents and images:** Use Azure AI Content Understanding's OCR/Read, Layout, and Receipt analyzers to extract text, structure, and business-specific fields from documents and images.

8. **Configure content safety guardrails:** Test a deployed model's default content safety guardrails against harmful, offensive, and sensitive prompts, then create and apply custom guardrails with stricter filtering thresholds.

9. **Build a multilingual translation application:** Design and test translation and transliteration prompts in the Chat Playground, then build a Python application using the Azure AI Foundry SDK to perform translation, transliteration, language detection, and sentiment analysis with a single deployed model.

## Pre-requisites

- Basic familiarity with the Azure portal and navigating Azure services.
- Basic knowledge of Python programming and running commands from a terminal or command-line interface.
- General understanding of generative AI models and prompt-based, chat-based AI interactions.
- Basic awareness of AI concepts such as natural language processing, computer vision, speech recognition, and responsible AI (content safety and moderation) is helpful but not required.

## Architecture

The lab architecture demonstrates how each lab builds on a Microsoft Foundry project to deploy, customize, and integrate a specific AI capability.

1. **Project creation and model deployment:** A Foundry project is created and linked to an underlying Azure resource; a generative AI model is deployed from the model catalog and tested in the playground; a sample client application connects to the model using the project endpoint and API key.

2. **Agent configuration:** A deployed GPT model is customized with system instructions and extended with Web Search and File Search tools, then saved as a reusable agent that client applications integrate with via the Azure AI Projects SDK.

3. **Text analysis:** The Language Playground and Chat Playground analyze text using sentiment analysis, key phrase extraction, named entity recognition, summarization, language detection, and PII recognition.

4. **Speech interaction:** An agent is configured with a generative AI model and Azure Speech - Voice Live, enabling real-time speech-to-text and text-to-speech interaction in the agent playground.

5. **Computer vision and generation:** Vision-enabled and image/video-generation models are deployed and used through Foundry playgrounds to analyze images and generate new images and videos from prompts.

6. **Information extraction:** Documents and images are submitted to the Azure AI Content Understanding playground, where OCR/Read, Layout, and Receipt analyzers extract progressively richer structured information.

7. **Content safety:** Prompts and model responses are evaluated against default and custom content safety guardrail policies before being returned to the user.

8. **Translation and localization:** A deployed GPT-5 Mini model is used through the Chat Playground and a Python application to perform translation, transliteration, language detection, and sentiment analysis via prompt engineering.

## Explanation of Components

1. **Microsoft Foundry Portal:** The centralized platform used across the labs to create and manage Foundry projects, deploy models, configure agents, and access built-in playgrounds.

1. **Microsoft Foundry Project and Azure Resources:** The workspace that links to an underlying Azure resource, providing the infrastructure for model deployments, agents, and AI services used throughout the labs.

1. **Generative AI Models (GPT-5, GPT-5 Mini):** Models deployed from the Foundry model catalog to generate conversational, text, and image-based responses from prompts.

1. **Chat Playground:** The browser-based interface used to design and test prompts, system instructions, and content filter settings against a deployed model.

1. **AI Agents and Tools (Web Search, File Search):** Used to extend a deployed model with system instructions, current-information retrieval, and custom document knowledge, then saved as a reusable agent.

1. **Speech Search:** Configured on an agent to enable real-time speech-to-text and text-to-speech interaction in the agent playground's voice mode.

1. **Vision-Enabled and Generation Models:** Used to analyze uploaded images and generate new images and short videos from natural language prompts via the image and video playgrounds.

1. **Content Safety Guardrails and Content Filters:** Default and custom policies that evaluate prompts and responses for harmful content categories such as Hate, Violence, Sexual, and Self-harm.

1. **Azure AI Translator:** A service that provides text translation, transliteration, and language detection for multilingual applications.

## Accessing Your Lab Environment
 
Once you're ready to dive in, your virtual machine and **Guide** will be right at your fingertips within your web browser.
 
![Access Your VM and Lab Guide](../media/4-7.png)

## Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.

## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.
 
![Explore Lab Resources](../media/ai901-g1.png)

## Lab Guide Zoom In/Zoom Out
 
To adjust the zoom level for the environment page, click the **A↕: 100%** icon located next to the timer in the lab environment.

![](../media/zoomin.png)

## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.
 
![Use the Split Window Feature](../media/ai901-g2.png)

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
 
    ![Launch Azure Portal](../media/mod01-gs-t1p1.png)

2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your **credentials (1)** and click on **Next (2)**:
 
    - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
      ![Enter Your Username](../media/mod01-gs-t1p2.png)
 
3. Next, provide your **password (1)** and click on **Next (2)**:
 
    - **Password:** <inject key="AzureAdUserPassword"></inject>
 
      ![Enter Your Password](../media/mod01-gs-t1p3.png)
 
4. If you see the pop-up **Stay-Signed in?**, click **Yes**.

    ![](../media/mod01-gs-t1p4.png)
 
5. If a **Welcome to Microsoft Azure** pop-up window appears, simply click **Maybe later**.

    ![](../media/lab2a-g4.png)

## Support Contact
 
The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels explicitly tailored for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.
 
Learner Support Contacts:
 
- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Click on **Next** from the lower right corner to move on to the next page.

   ![Start Your Azure Journey](../media/sc900-image(3).png)

## Happy Learning !!
