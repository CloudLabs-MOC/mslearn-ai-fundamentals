# Lab: Explore computer vision

### Please be aware that no Lab VM is provided for this lab. You will need to complete the lab on your personal computer.

## Lab Overview

In this lab, you'll use a chat playground to interact with a generative AI solution that can analyze and interpret images. The goal of this lab is to explore a common pattern for combining text and visual input in a prompt for a generative AI model.

## Lab Objectives

In this lab, you will complete the following task:

+ Task 1: Prepare for image-based chat

### Estimated timing: 15 Minutes

## Task 1: Prepare for image-based chat

In this task, you use a generative AI model in a chat playground to respond to prompts that include image data.

> **Note**: The chat application uses a small language model to interpret and respond to prompts. If WebGPU is supported in your browser, the *Microsoft Phi 3 mini* model is run on your computer's GPU; if not, the *Microsoft Phi 2* model is run on the CPU. On older or low-spec devices, you may get more reliable behavior by switching to the *None* model even if CPU or GPU is available. Many modern large language models are *multimodal* - in other words, they support multiple formats of input, including text and images. However, the Microsoft Phi 3 mini and Phi 2 models are text-based only, so we'll also use the the **MobileNetV3** CNN-based computer vision model for image classification and include the predicted image class in the prompt.

1. In a web browser, open the **[Chat Playground](https://aka.ms/chat-playground)** at `https://aka.ms/chat-playground`.

    The app intiializes by downloading a language model.

    > **Tip**: The first time you download a model, it may take a few minutes. Subsequent downloads will be faster. If your browser or operating system does not support WebGPU models, the fallback CPU-based model will be selected (which provides slower performance and reduced quality of response generations). If *that* fails, a basic mode with no model and responses retrieved from Wikipedia is used.

1. While waiting for the model to download, open a new browser tab, and download **[images.zip](https://aka.ms/ai-images)** from `https://aka.ms/ai-images` to your local computer.
1. Extract the downloaded archive in a local folder to see the files it contains. These files are the images you will use AI to analyze.
1. Return to the browser tab containing the chat playground and ensure a language model has downloaded. Then, in the configuration pane on the left pane, in the **Vision** section, enable **Image analysis** and wait for the computer vision model to be downloaded and initialized.

   ![Screenshot of the Image analysis option.](./media/lab5-t1.png)

    In the chat interface, an **Upload image** (**&#x1F4CE;**) button is enabled.

1. Click the **Upload image** button, and browse to select one of the images you extracted on your computer.

    A thumbnail of the image is added to the prompt input area.

1. Enter a prompt like `Suggest a recipe for this.`. The image is included in the message.

   ![Screenshot of the chat app with an image in a prompt.](./media/lab5-t2.png)

    The MobileNetV3 model is used to determine the likely subject of the image, and the results of that analysis is included in the prompt to the Phi language model. The result should be a reponse that uses the image information to answer the question.

1. Submit prompts that include the other images, such as `What desserts could I make with this?` or `How should I cook this?`

    > **Note**: Responses will vary in quality depending on the selected language model; but the image classificaton model should correctly identify the images.

1. If you want to explore further, you can upload your own images and enter appropriate prompts. The combination of a small language model and a limited computer vision model means that the quality of the responses may be highly variable compared to a true multimodal large language model!

## Summary

In this exercise, you explored the use of computer vision with a generative AI model in a chat playground.

The app used in this exercise is based on a simplified version of the chat playground in the Microsoft Foundry portal. Microsoft Foundry supports a range of multimodal models that can accept combined image and text input, enabling significantly more complex image interpretation than this simple example. Additionally, you can use the Azure Content Understanding tool to analyze images.
