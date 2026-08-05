
# AI-901: Microsoft Azure AI Fundamentals Workshop

Welcome to your AI-901: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn Azure Services. Let's begin by making the most of this experience.

# Getting Started with lab
 
Welcome to your AI-901: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn about machine learning and AI concepts and related Microsoft Azure services. Let's begin by making the most of this experience:
 
## Overview

In these hands-on labs, you will develop the skills required to build, deploy, and manage AI-powered solutions using **Microsoft Foundry** and Azure AI services. Working through a series of guided exercises, you will create Microsoft Foundry projects, deploy generative AI models such as GPT-4.1, GPT-4o, GPT-5, and GPT-5 Mini, and interact with them through chat, vision, speech, image, and video playgrounds. You will build and configure AI agents with system instructions, Web Search, File Search, and Azure Speech - Voice Live capabilities, and connect applications to deployed models using the Azure AI Foundry SDK, Azure AI Projects SDK, REST APIs, and Python sample code.

The labs also cover Azure AI Language capabilities such as sentiment analysis, key phrase extraction, named entity recognition, text summarization, language detection, and PII detection, along with Conversational Language Understanding (CLU) and Question Answering knowledge bases. You will use Azure AI Vision, Azure AI Face, and Azure AI Content Understanding to analyze images, detect faces and objects, read text with OCR, and extract structured information from documents, receipts, and invoices. Additional labs explore Azure AI Search for building intelligent, AI-enriched search indexes, Azure AI Translator for multilingual translation and transliteration, and responsible AI practices through content safety guardrails and content filters. By completing these labs, you will gain the practical experience needed to build, secure, and operate intelligent, multimodal AI applications on Azure.

## Objectives

By the end of these labs, you will be able to:

1. **Create and configure Microsoft Foundry projects:** Set up Microsoft Foundry/Azure AI Foundry projects, provision the underlying Azure resources, and explore the Foundry portal, AI hubs, and connected resources.

2. **Deploy and interact with generative AI models:** Deploy models such as GPT-4.1, GPT-4o, GPT-5, and GPT-5 Mini from the Foundry model catalog and use the Chat Playground to design, test, and refine prompts.

3. **Build and extend AI agents:** Create AI agents, configure system instructions, and extend agent capabilities with Web Search, File Search, and Azure Speech - Voice Live for real-time voice interaction.

4. **Analyze and process text with Azure AI Language:** Perform sentiment analysis, key phrase extraction, named entity recognition, text summarization, language detection, and PII detection using the Language Playground and Language Studio.

5. **Build conversational and question-answering solutions:** Create and train Conversational Language Understanding (CLU) apps with intents, utterances, and entities, and build, train, and deploy a Question Answering knowledge base.

6. **Analyze images, faces, and video with Azure AI Vision:** Generate captions, tags, and object detections, detect faces, read text with OCR, and generate new images and videos from text prompts using vision-enabled generative models.

7. **Extract structured information with Azure AI Content Understanding and Document Intelligence:** Use OCR/Read, Layout, and Receipt analyzers, and Document Intelligence, to extract fields, tables, and JSON output from documents, receipts, and invoices.

8. **Build intelligent search solutions:** Create an Azure AI Search resource, index documents stored in Azure Storage, enrich content with AI skills, and query the search index and knowledge store.

9. **Translate and localize content:** Use Azure AI Translator and generative AI prompts to translate, transliterate, and detect the language of text.

10. **Apply responsible AI practices:** Configure and test content safety guardrails and content filters to manage harmful, offensive, or sensitive model outputs.

11. **Integrate AI capabilities into applications:** Build Python applications using the Azure AI Foundry SDK, Azure AI Projects SDK, and REST APIs to connect client applications to deployed models, agents, and AI services.

## Pre-requisites

- Basic familiarity with the Azure portal and navigating Azure services.
- Basic knowledge of Python programming and running commands from a terminal or command-line interface.
- General understanding of generative AI models, prompt engineering, and chat-based AI interactions.
- Familiarity with core AI concepts such as natural language processing, computer vision, speech recognition, and responsible AI is helpful but not required.

## Architecture

The lab architecture demonstrates how Microsoft Foundry and Azure AI services work together to build, deploy, and operate intelligent, multimodal AI applications. Throughout these labs, you will provision Foundry projects, deploy and test generative AI models, build AI agents, and integrate language, vision, speech, search, and translation services into real-world scenarios.

1. **Microsoft Foundry Projects and Azure Resources:** Foundry projects are created and linked to underlying Azure resources that provide the infrastructure for model deployments, agents, and AI services used across the labs.

2. **Generative AI Models and Chat Playground:** Models such as GPT-4.1, GPT-4o, GPT-5, and GPT-5 Mini are deployed from the Foundry model catalog and tested in the Chat Playground using prompts, system instructions, and content filters.

3. **AI Agents and Tools:** Agents are configured with system instructions and extended with Web Search, File Search, and Azure Speech - Voice Live to build task-specific, voice- and knowledge-enabled assistants.

4. **Azure AI Language Services:** Language, Conversational Language Understanding, and Question Answering resources analyze and interpret text, powering sentiment analysis, entity extraction, summarization, and conversational understanding scenarios.

5. **Azure AI Vision and Content Understanding:** Vision, Face, Document Intelligence, and Content Understanding services analyze images, video, and documents to generate captions, detect objects and faces, perform OCR, and extract structured fields.

6. **Azure AI Search and Storage:** Azure AI Search indexes documents stored in Azure Storage, using AI skills to enrich content and enable intelligent querying.

7. **Azure AI Translator:** Provides text translation, transliteration, and language detection for building multilingual applications.

8. **Client Applications and Developer Tools:** Python applications, the Azure AI Foundry SDK, Azure AI Projects SDK, and REST APIs connect to deployed models, agents, and AI services, while the Azure Portal and Foundry portal are used to provision, configure, and monitor resources throughout the labs.

## Explanation of Components

1. **Microsoft Foundry Portal:** The centralized platform used to create and manage AI projects, hubs, connected resources, model deployments, agents, and playgrounds throughout the labs.

1. **Generative AI Models (GPT-4.1, GPT-4o, GPT-5, GPT-5 Mini):** Large language models deployed from the Foundry model catalog that generate conversational, text, and multimodal responses based on prompts and system instructions.

1. **AI Agents:** Reusable, task-specific assistants that combine a deployed model, system instructions, and tools such as Web Search, File Search, and Voice Live to perform specialized tasks and be integrated into applications.

1. **Azure AI Language:** A cloud-based natural language processing service used for sentiment analysis, key phrase extraction, named entity recognition, text summarization, language detection, and PII detection.

1. **Question Answering:** A feature used to build, train, and deploy a knowledge base of question-and-answer pairs for FAQ-style bots and services.

1. **Azure AI Vision:** A service used to generate image captions and tags, detect objects and faces, and extract text from images using OCR.

1. **Azure AI Speech:** A service that provides real-time speech-to-text, text-to-speech, and Voice Live capabilities for building voice-enabled applications and agents.

1. **Azure AI Content Understanding:** A multimodal analysis service that uses prebuilt analyzers such as OCR/Read, Layout, and Receipt to extract structured fields, tables, and JSON output from documents, images, audio, and video.

1. **Azure AI Document Intelligence:** A service used to analyze documents such as receipts and invoices and extract key business fields for downstream processing.

1. **Azure AI Search:** A cloud-based search service that indexes documents from Azure Storage and provides AI-enriched, queryable search indexes and knowledge stores.

1. **Azure AI Translator:** A service that provides text translation, transliteration, and language detection for multilingual applications.

1. **Content Safety Guardrails and Content Filters:** Built-in and custom filtering policies that evaluate prompts and model responses for harmful content categories such as Hate, Violence, Sexual, and Self-harm, supporting responsible AI practices.

1. **Azure AI Foundry SDK, Azure AI Projects SDK, and REST APIs:** Developer tools used to connect client applications to deployed models, agents, and AI services, enabling programmatic integration of AI capabilities.

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
