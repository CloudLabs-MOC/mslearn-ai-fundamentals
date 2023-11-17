# Module 09: Explore Speech Studio

## Lab overview

In this exercise, you will try out the capabilities of Azure AI Speech using Azure AI Speech Studio. The **Azure AI Speech** service transcribes speech into text, and text into audible speech. You might use AI Speech to create an application that can transcribe meeting notes or generate text from the recording of interviews. 
 
## Lab objectives

In this lab, you will perform:

- Creating an *Azure AI Speech* resource
- Exploring speech to text in Speech Studio

## Estimated timing: 30 minutes

## Architecture Diagram

  ![](media/module09.png)


## Exercise 1: Explore Speech Studio

### Task 1: Create an **Azure AI Speech** resource

You can use the Speech service by creating either a **Speech** resource or an **Azure AI services** resource.

In this exercise, you will create an AI Speech resource, unless you already have a resource that you can use.

1. In another browser tab, open [Azure AI Speech Studio](https://speech.microsoft.com/), signing in with your following credentials:

  - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

  - **Password:** <inject key="AzureAdUserPassword"></inject>

1. Select **Settings** then **Create a resource.** Configure it with the following settings:
    - **Name of new resource (1)**: Enter **speech<inject key="DeploymentID" enableCopy="false" />**
    - **Subscription (2)**: Select your **existing azure subscription**.
    - **Region (3)**:  Select **<inject key="location" enableCopy="false"/>**
    - **Pricing tier (4)**: Select **Free FO** (if available, otherwise select **Standard S0**).
    - **Resource group (5)**: Select **ODL-AI-900-09-<inject key="DeploymentID" enableCopy="false" />-02**
    - Select **Create resource. (6)**

      ![](media/07.png)

1.  Wait until the resource has been created.

1. Select **Use resource**. The Get started with Speech page is displayed.

    ![](media/06.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Navigate to the Lab Validation Page, from the upper right corner in the lab guide section.
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

### Task 2: Explore speech to text in Speech Studio

1. Select [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) to download **speech.zip**. 

1. Open the zip file in labvm and **Extract** the zip file.

   ![Browse files](media/03.png)

1. On the Get started with Speech page, under *Speech* find *Real-time speech to text*. Select **Try out Real-time speech to text**.

    ![Getting started with Speech](media/02.png)

1. Under *Choose audio files*, select **Browse files** .

    ![Browse files](media/05.png)

1. Navigate to the folder where you saved the file. Select **WhatAICanDo.m4a** and then **Open**.

    ![Browse files](media/01.png)

1. The Speech service transcribes and displays the text in real time. If you have audio on your computer, you can listen to the recording as the text is being transcribed.

     ![](media/09.png)

1. Review the output, which should have successfully recognized and transcribed the audio into text.

    ![](media/08.png)

    > **Note**: If you get an error message, wait a few minutes before trying again. It takes a little time for the Speech resource to be available for first use.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Navigate to the Lab Validation Page, from the upper right corner in the lab guide section.
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.
  
## Learn more

This exercise demonstrated only some of the capabilities of the Speech service. To learn more about what you can do with this service, see the [Speech page](https://azure.microsoft.com/services/cognitive-services/speech-services).

### Review
In this exercise you created an AI Speech resource in Speech Studio. You then used the Real-time speech to text service to transcribe an audio recording. You were able to see the text transcription being generated as the audio file was played.
  
## You have successfully completed this lab.
