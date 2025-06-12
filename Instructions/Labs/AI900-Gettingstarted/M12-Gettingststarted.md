
# AI-900: Microsoft Azure AI Fundamentals Workshop

Welcome to your AI-900: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn Azure Services. Let's begin by making the most of this experience.

# Module 2a: Explore generative AI in Azure AI Foundry portal

### Overall Estimated timing: 30 minutes

## Overview

This lab provides an introduction to generative AI through the Azure AI Foundry portal, Microsoft's platform for creating and deploying intelligent applications. In this exercise, you'll interact with the Chat playground in Azure AI Foundry, where you will explore the deployment of the GPT-4o model, learn how to optimize responses, and understand effective prompting techniques to refine outputs from generative AI.

## Objective

By the end of this lab, you will be able to create a project in Azure AI Foundry and analyze a receipt using Azure AI Document Intelligence to extract key information efficiently

1. Create a Project in the Azure AI Foundry portal to organize and set up AI resources.

2. Explore Generative AI in the Azure AI Foundry’s Chat playground, interact with a deployed GPT model, and experiment with response optimization techniques.

## Pre-requisites

Basic Understanding of Generative AI

## Architecture

In this hands-on lab, the architecture flow includes several essential components.

1. **Azure AI Foundry Portal**: The platform for creating, managing, and deploying AI models and resources.

2. **Azure AI Project**: A container for organizing your work within the portal.

3. **Chat Playground**: An interactive environment where you can test the deployed model by sending prompts and receiving responses.

4. **Deployment**: The process of deploying the GPT-4o model to make it available for interaction within the playground.

## Architecture Diagram

![](../media/12png.png)

## Explanation of Components

1. **Azure AI Foundry Portal**: This is the central hub where users can create and manage projects, deploy AI models, and interact with various AI capabilities. It offers a user-friendly interface to experiment with different AI models and services without requiring deep technical knowledge.

2. **Azure AI Project**: A project in the Azure AI Foundry serves as an organizational unit for grouping and managing resources. Each project is linked to a hub, which provides a workspace for various tasks related to AI models, data processing, and exploration.

3. **GPT-4o Model**: The GPT-4o model is a large language model developed by OpenAI that can understand and generate human-like text. When deployed in the Chat playground, GPT-4o is used to generate responses to user inputs (prompts), which can vary from answering factual questions to providing creative suggestions.

4. **Deployment**: To begin using GPT-4o in the Azure AI Foundry, the model must be deployed first. The deployment process makes the model accessible in the chat playground and allows it to interact with users' inputs.

5. **Chat Playground**: The Chat playground is an interactive interface where you can test the generative AI model by sending different prompts and receiving responses. It allows you to iterate on your prompts, providing insights into how well the model performs and how you can improve its outputs.

6. **Prompting Techniques**: Effective prompting is crucial for optimizing the model's responses. In this lab, you’ll experiment with various techniques to guide the model’s output, such as providing clear instructions, setting expectations, and providing context. You’ll also learn how to iterate on prompts to refine the responses.

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
 
     ![Enter Your Password](../media/sc900-image-2.png)
 
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

