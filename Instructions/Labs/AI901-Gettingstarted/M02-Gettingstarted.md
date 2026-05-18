
# AI-900: Microsoft Azure AI Fundamentals Workshop

Welcome to your AI-900: Microsoft Azure AI Fundamentals workshop! We've prepared a seamless environment for you to explore and learn Azure Services. Let's begin by making the most of this experience.

# Module 02: Explore the Content Safety Studio

### Overall Estimated timing: 30 minutes

## Overview

In this hands-on lab, you'll explore the Azure AI Content Safety Studio to evaluate and moderate text and image content. By creating a Content Safety service, associating it with the studio, and running moderation tests, you’ll gain insights into the severity levels of different types of content. The lab will guide you through exploring text moderation, analyzing results, and checking the necessary keys and endpoints for integrating the service with your applications.

## Objectives

By the end of this lab, you will be able to use Azure AI services effectively. You will learn to:

1. **Create an *Azure AI services* resource in the Azure portal**: Learn how to provision a multi-service AI resource using the Azure portal.

2. **Check out the keys and endpoint**: Locate the authentication credentials required to access Azure AI services via APIs.

3. **See Azure AI services in action**: Explore AI capabilities like face detection using interactive demos in the Azure AI Foundry portal.

## Pre-requisites

Basic knowledge of Azure and Azure Portal and familiarity with AI concepts related to content moderation.

## Architecture

In this hands-on lab, the architecture flow includes several key components that showcase how Azure AI services are provisioned and utilized.

1. **Provision an Azure AI multi-service resource**: Learn how to create a centralized Azure AI service resource that provides access to multiple AI capabilities, such as Vision, Language, and Decision services. This involves configuring resource settings like region, pricing tier, and deployment details within the Azure portal.

2. **Explore and test AI capabilities using Azure AI Foundry**: Use the Azure AI Foundry portal to interact with AI services such as Face Detection. This includes accessing demos, analyzing images with AI models, and viewing sample code that integrates the service's keys and endpoints—demonstrating how developers can connect their applications to Azure AI services..

## Architecture Diagram

   ![](../media/Module1.1.png)

## Explanation of Components

1. **Azure AI Content Safety Studio**: A platform within Azure AI designed to manage and moderate text and image content by evaluating it for harmful or inappropriate categories. It provides easy-to-use tools to test and analyze content using AI-based moderation models.

2. **Azure Content Safety Resource**: A service that analyzes content (text and images) and assigns severity scores based on categories like violence, hate speech, or explicit content. This resource is configured within the Azure portal and linked to the Content Safety Studio for testing and integration.

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
