# Face Analysis with Azure Vision in Microsoft Foundry

### Estimated Duration: 50 Minutes

## Lab Overview

In this exercise, you'll use Azure Vision in Microsoft Foundry to explore face detection and face analysis capabilities. You will connect an Azure Vision resource to your Foundry project, detect faces in images, analyze face attributes such as head pose, blur, exposure, and occlusion, and interpret the JSON responses returned by the Face API. You will also use GPT-4o multimodal vision to describe face images in natural language and build a Python application that calls the Azure Vision Face API. Through these activities, you'll gain practical experience with face analysis and understand Responsible AI considerations related to facial recognition technologies.

## Lab Objectives

In this exercise, you will perform the following tasks:

* Task 1: Connect Azure Vision to your Foundry project
* Task 2: Detect faces using Azure Vision Face API
* Task 3: Analyze face attributes and JSON responses
* Task 4: Use GPT-4o multimodal vision to describe face images
* Task 5: Build a Python face detection client
* Task 6: Explore Responsible AI considerations for face recognition

---

## Task 1: Connect Azure Vision to your Foundry project

In this task, you will connect Azure Vision to your Microsoft Foundry project.

1. Copy the **Microsoft Foundry** link and paste it into a new browser tab:

   ```
   https://ai.azure.com
   ```

2. Navigate to your existing project **Myproject<inject key="DeploymentID" enableCopy="false" />**.

3. Click the **Microsoft Foundry** logo and scroll down to **Explore Foundry Tools**.

4. Select **Vision + Document (1)**.

5. Locate **Azure AI Vision (2)** and select it.

6. Click **Add to project (3)**.

7. Select **Use existing resource** and choose the Azure Vision resource in the **AI-901** resource group.

8. Click **Connect**.

   > **Note:** If an Azure Vision resource is unavailable, create a new resource using the Free (F0) tier and continue after deployment completes.

9. Verify that the Azure AI Vision resource shows **Connected** status.

10. Confirm that Face, Image Analysis, and OCR capabilities are available.

---

## Task 2: Detect faces using Azure Vision Face API

In this task, you will upload images and detect faces using the Azure Vision Face API.

### Prepare Test Images

You may use the following sample images:

* Single face:

  ```
  https://aka.ms/aifundamentals/face1
  ```

* Multiple faces:

  ```
  https://aka.ms/aifundamentals/face2
  ```

Or use your own JPEG or PNG image.

> **Note:** Use only images you own or publicly available images with appropriate permissions.

### Run Face Detection

1. In Azure AI Vision, select **Face (1)**.

2. Select **Detect faces (2)**.

3. Click **Browse for a file (3)** and upload a test image.

4. Ensure **Return face attributes (4)** is enabled.

5. Click **Run (5)**.

6. Wait for the analysis to complete.

7. Observe:

   * Face bounding boxes
   * Face attributes
   * JSON response

### Review Detection Results

Locate the following values in the JSON response:

* Face ID
* Bounding box coordinates
* Head pose
* Blur level
* Exposure
* Occlusion
* Quality for recognition

1. Repeat the test using the multiple-face image.

2. Observe that a separate result is returned for each detected face.

---

## Task 3: Analyze face attributes and JSON responses

In this task, you will interpret the Face API JSON response.

1. Review the Face API response generated in Task 2.

2. Identify the following properties:

   * Face ID
   * Face rectangle
   * Head pose
   * Blur
   * Exposure
   * Noise
   * Occlusion
   * Quality for recognition

3. Determine:

   * The top-left coordinates of the detected face
   * Whether the face is turned
   * Whether the image quality is sufficient for recognition
   * Whether any facial features are occluded

### Multiple Face Responses

1. Review the response generated from the multi-face image.

2. Observe:

   * Number of detected faces
   * Individual bounding boxes
   * Recognition quality for each face

### Access Control Scenario

Review how face detection may be used in an access control system:

1. Capture an image.

2. Detect faces using Face API.

3. Verify quality for recognition.

4. Check for occlusion.

5. Send the face image for identification if required.

> **Note:** Face identification requires Microsoft Limited Access approval and is not covered in this lab.

---

## Task 4: Use GPT-4o multimodal vision to describe face images

In this task, you will use GPT-4o vision capabilities to analyze face images.

1. In Microsoft Foundry, navigate to:

   ```
   Playgrounds → Chat Playground
   ```

2. Select the deployed **gpt-4o-mini** or **gpt-4o** model.

3. Enter the following system prompt:

   ```
   You are a Vision AI assistant that analyzes images of faces.

   When shown an image, describe:

   1. How many faces you can see
   2. The approximate position of each face in the image
   3. Whether faces appear to be looking at the camera
   4. Any visible accessories
   5. The overall image quality for face recognition purposes

   Be objective and factual.
   Do not speculate about emotions, identity, race, or gender.
   Do not make assumptions about age beyond broad categories.
   ```

4. Select **New chat**.

5. Upload a face image.

6. Submit the following prompt:

   ```
   Please analyze this image following your instructions.
   ```

7. Review the response.

8. Submit the follow-up prompt:

   ```
   Would this image be suitable for use in a touchless access control system? What concerns, if any, do you have?
   ```

9. Review the generated analysis.

### Compare Face API and GPT-4o

Compare the two approaches:

| Criterion      | Azure Vision Face API                    | GPT-4o Multimodal                        |
| -------------- | ---------------------------------------- | ---------------------------------------- |
| Output         | Structured JSON                          | Natural language                         |
| Bounding boxes | Precise coordinates                      | Approximate descriptions                 |
| Attributes     | Head pose, blur, exposure, occlusion     | Contextual image descriptions            |
| Integration    | REST API / SDK                           | OpenAI Responses API                     |
| Accessibility  | No                                       | Yes                                      |
| Best for       | Face detection and recognition workflows | Descriptions and conversational analysis |

---

## Task 5: Build a Python face detection client

In this task, you will create a Python application that calls the Azure Vision Face API.

### Get Face API Credentials

1. In Microsoft Foundry, navigate to:

   ```
   Settings → Connected resources
   ```

2. Locate the Azure AI Vision resource.

3. Copy:

   * Endpoint URL
   * Key 1

### Open VS Code

1. Open:

   ```
   https://vscode.dev
   ```

2. Open a terminal.

3. Install the Face SDK:

   ```bash
   pip install azure-ai-vision-face
   ```

4. Create a file named:

   ```
   face_detect.py
   ```

5. Paste the sample Face SDK code provided in the lab.

6. Replace:

   ```python
   ENDPOINT = "https://your-resource.cognitiveservices.azure.com/"
   KEY = "your-api-key-here"
   ```

   with your actual values.

7. Run the script:

   ```bash
   python face_detect.py
   ```

8. Verify that the output displays:

   * Face count
   * Face location
   * Head pose
   * Blur
   * Exposure
   * Occlusion
   * Quality for recognition

### Additional Testing

1. Modify the image URL.

2. Test with:

   * Sunglasses
   * Side-angle face images
   * Blurry images

3. Observe how the Face API results change.

---

## Task 6: Explore Responsible AI considerations for face recognition

In this task, you will review Microsoft's Responsible AI decisions regarding facial recognition.

### Review Responsible AI Decisions

Study the following topics:

* Emotion detection retirement
* Gender detection retirement
* Limited Access requirements for face identification
* Limited Access requirements for age estimation
* Liveness detection support

### Reflection Questions

Consider the following questions:

1. Which Responsible AI principles support retiring emotion detection?

2. Is automated attendance using facial recognition an appropriate use case?

3. Why should GPT-4o avoid speculation about identity, race, gender, or emotions?

4. Why is image quality important before performing face identification?

5. Under what safeguards could emotion detection be used responsibly?

6. How does Limited Access balance innovation and protection?

### Face Detection vs Face Recognition

| Face Detection                 | Face Recognition               |
| ------------------------------ | ------------------------------ |
| Finds faces in images          | Matches faces to identities    |
| Freely available               | Limited Access required        |
| Lower Responsible AI risk      | Higher Responsible AI risk     |
| Used for counting and analysis | Used for identity verification |

> **Note:** This lab covers face detection only. Face recognition and identification require Microsoft approval.

---

## Summary

In this lab, you connected Azure Vision to a Microsoft Foundry project and explored face analysis capabilities using the Azure Vision Face API. You detected faces, reviewed bounding boxes and attributes, and interpreted structured JSON responses containing information such as head pose, blur, exposure, occlusion, and recognition quality. You also used GPT-4o multimodal vision to generate natural language descriptions of face images and built a Python application that called the Face API programmatically. Finally, you reviewed Microsoft's Responsible AI decisions regarding facial recognition technologies and learned the distinction between face detection and face identification.

### You've successfully completed the hands-on lab!
