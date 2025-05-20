# Module 03: Analyze images in the Azure AI Foundry portal

## Lab overview

**Azure AI Vision** includes numerous capabilities for understanding image content and context and extracting information from images. In this exercise, you will use Azure AI Vision in Azure AI Foundry portal, Microsoft's platform for creating intelligent applications, to analyze images using the built-in try-it-out experiences. 

Suppose the fictitious retailer *Northwind Traders* has decided to implement a "smart store", in which AI services monitor the store to identify customers requiring assistance, and direct employees to help them. By using Azure AI Vision, images taken by cameras throughout the store can be analyzed to provide meaningful descriptions of what they depict.

## Lab Objectives

In this lab, you will perform:
- Task 1: Create a project in the Azure AI Foundry portal
- Task 2: Generate captions for an image
- Task 3: Tagging images 
- Task 4: Object detection

## Task 1: Create a project in the Azure AI Foundry portal

In this task, we are setting up a project in Azure AI Foundry by creating and configuring an AI services environment for further experimentation.

1. Right-click on the [Azure AI Foundry](https://ai.azure.com?azure-portal=true) **(1)** link, select **Copy link (2)** from the context menu, then paste it into a new tab to access the Azure AI Foundry portal.

   ![](./media/3-27.png)

1. On the Welcome to Azure AI Foundry page, Click on **Sign in** in the top right corner.

   ![](./media/17-18.png)

1. If prompted to sign in, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
      ![Enter Your Username](./media/19-4.png)
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Password](./media/19-5.png)

1. If prompted to stay signed in, you can click **No**.

   ![](./media/9-8.png)

1. If prompted with *Streamlined from the start*, click on **Got it** to proceed.

   ![](./media/3-23.png)

1. Close any tips or quick start panes that are opened the first time you sign in, and if necessary use the **Azure AI Foundry** logo at the top left to navigate to the home page, which looks similar to the following image (close the **Help** pane if it's open)

    ![Screenshot of Azure AI Foundry home page with create an agent selected.](./media/azure-ai-foundry-home-page.png)

1. In the home page, select **+ Create an agent**.

1. In the **Create an agent** wizard, enter project name **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)** and then expand **Advanced options**.

1. Select **Advanced options** and specify the following settings:
   - **Subscription**: **Use existing Azure subscription (2)**
    - **Resource group**: Select **AI-900-Module-03 (3)**
    - **Azure AI Foundry resource**: **Keep the default name (4)**
    - **Region**: Select **<inject key="location" enableCopy="false"/> (5)**
    - Select **Create (6)**

      ![](./media/lab3-13.png)

1. Review your configuration. Wait for the set up process to complete.

1. When your project is created, you will be brought by default to the Agents playfround in Azure AI Foundry portal, which should look similar to the following image:

   ![](./media/lab3-12.png)

## Task 2: Generate captions for an image

In this task, we are exploring Azure AI Vision's image captioning and dense captioning capabilities by uploading an image and observing how AI generates descriptive text for the entire image and specific objects within it.

Let's use the image captioning functionality of Azure AI Vision to analyze images taken by a camera in the *Northwind Traders* store. Image captions are available through the **Caption** and **Dense Captions** features.

1. In a new browser window, open the [Azure AI services exploration page](https://ai.azure.com/explore/aiservices).

1. On the **AI Services** page, select the **Vision + Document** tile to try out Azure AI Vision and Document capabilities.

    ![Screenshot of the Vision and Document tile selected on the AI Services page.](./media/17-6.png)

1. On the **Vision + Document** page, scroll down and select **Image (1)** under View all other vision capabilities. Then select the **Image captioning (2)** tile.

    ![](./media/17-7.png)

1. On the **Add captions to images** page, click on **Select a hub** under **Try It Out** subheading.

    ![](./media/lab3-14.png)

1. On the Select a Hub page, choose **Create a New Hub**.

   ![](./media/lab3-15.png)

1. On the Create a new hub page, enter the following details:

   - **Hub name:** Select **myhub<inject key="DeploymentID" enableCopy="false" /> (1)**
   - **Subscription:** **Use existing Azure subscription (2)**
   - **Resource group:** Select **AI-900-Module-03 (3)** 
   - **Location:** Select **<inject key="location" enableCopy="false"/> (4)**
   - **Connect Azure AI Services or Azure OpenAI Service**: Leave as default **(5)**
   - **Connect Azure AI Search**: Click on **Create new AI Services** and provide name **AI<inject key="DeploymentID" enableCopy="false" /> (6)**.
   - Click on **Next (7)**

      ![](./media/lab3-16.png)

1. On the **Review and Finish** page, click on **Create**.

   ![](./media/lab3-17.png)

1. On the **You'll need a project to keep working** enter **myproject<inject key="DeploymentID" enableCopy="false" /> (1)** and click on **Create project (2)**.

    ![](./media/lab3-18.png)

1. Go back to the **Add Captions to Images** page, click on **Select a Hub (1)**, choose **myhub<inject key="DeploymentID" enableCopy="false" /> (2)** from the drop-down menu, and then click **Select (3)**.

    ![](./media/lab3-19.png)

   >**Note:** To return to the **Add Captions to Images** page, repeat **Task 2**, from **Step 1** through **Step 4**.

1. Copy the highlighted link by right-clicking the [**https://aka.ms/mslearn-images-for-analysis**](https://aka.ms/mslearn-images-for-analysis) and selecting "Copy" from the context menu, and paste it into a new tab to download **image-analysis.zip**. 

1. Click the **download icon (1)** to view your downloads, then click the **folder icon (2)** to open the file location.

   ![](./media/3-6.png)

1. **Right-click** the **ZIP file (1)**  and select **Extract All (2)** to **unzip** its contents. 

   ![](./media/3-7.png)

1. Select the destination folder, ensure Show extracted files when complete is checked, and click **Extract** to unzip the files. 

   ![](./media/3-9.png)

1. The image-analysis folder contains **JPG files** named **store-camera-1**, **store-camera-2**, **store-camera-3**, and **store-camera-4**. 

   ![](./media/3-8.png)

1. Locate the file named **store-camera-1.jpg**; which contains the following image:

    ![](./media/analyze-images-vision/store-camera-1.jpg)

1. Go back to the Azure AI Foundry portal and upload the **store-camera-1.jpg** image by clicking **Browse for a file (1)**. Then, navigate to the **C:\Users\azureuser\Downloads\image-analysis (2)** folder, select **store-camera-1 (3)**, and click **Open (4)**.

   ![](./media/3-10.png)

1. Observe the generated caption text, visible in the **Detected attributes** panel to the right of the image.

    ![](./media/17-8.png)

    >**Note:** The **Caption** feature generates a **single** human-readable English sentence that describes the image's content.

1. Next, use the same image to perform **Dense captioning**. Return to the **Vision + Document** page by selecting the **back** arrow at the top of the page.

   ![](./media/3-11.png)

1. On the **Vision + Document** page, select the **Image (1)** tab, then select the **Dense captioning (2)** tile.

   ![](./media/ai900m3-1.png)

1. Upload the **store-camera-1.jpg** image by clicking **Browse for a file (1)**. Then, select **store-camera-1 (2)**, and click **Open (3)**.

   ![](./media/3-12.png)

1. The **Dense Captions** feature differs from the **Caption** capability in that it provides multiple human-readable captions for an image, one describing the image's content and others, each covering the essential objects detected in the picture. Each detected object includes a bounding box, which defines the pixel coordinates within the image associated with the object.

1. Hover over one of the captions in the **Detected** **attributes** list and observe what happens within the image.

    ![](./media/3-13.png)

1. Move your mouse cursor over the other captions in the list, and notice how the bounding box shifts in the image to highlight the portion of the image used to generate the caption.

   ![](./media/3-14.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="10cf8d2c-7678-441a-8ad5-7752773b3f33" />
   
## Task 3: Tagging images 

In this task, we are using Azure AI Vision's common tag extraction feature to analyze an image and generate a list of descriptive tags, including objects and actions, along with confidence scores.

The next feature you will try is the *Extract Tags* functionality. Extract tags are based on thousands of recognizable objects, including living beings, scenery, and actions.

1. Return to the **Vision + Document** page by selecting the **back** arrow at the top of the page. 

   ![](./media/3-16.png)

1. Select the **Image (1)** tab, and select the **Common tag extraction (2)** tile.

   ![](./media/3-15.png)

1. Open the folder containing the images you downloaded and locate the file named **store-camera-2.jpg**, which looks like this:

    ![](./media/analyze-images-vision/store-camera-2.jpg)

1. Upload the **store-camera-2.jpg** image by clicking **Browse for a file (1)**. Then, select **store-camera-2 (2)**, and click **Open (3)**.

    ![](./media/3-17.png)

1. Review the list of tags extracted from the image and the confidence score for each in the detected attributes panel. Here the confidence score is the likelihood that the text for the detected attribute describes what is actually in the image. Notice in the list of tags that it includes not only objects, but actions, such as **shopping**, **selling**, and **standing**.

    ![](./media/17-11.png)

## Task 4: Object detection

In this task, you use the **Object detection** feature of Image Analysis. Object detection detects and extracts bounding boxes based on thousands of recognizable objects and living beings.

1. Return to the **Vision + Document** page by selecting the **back** arrow at the top of the page. 

   ![](./media/3-18.png)

1. Select the **Image (1)** tab, and select the **Common object detection (2)** tile.

   ![](./media/17-13.png)

1. Open the folder containing the images you downloaded and locate the file named **store-camera-3.jpg**, which looks like this:

    ![](./media/analyze-images-vision/store-camera-3.jpg)

1. Upload the **store-camera-3.jpg** image by clicking **Browse for a file (1)**. Then, select **store-camera-3 (2)**, and click **Open (3)**.

   ![](./media/3-20.png)

1. In the **Detected attributes** box, observe the list of detected objects and their confidence scores.

   ![](./media/3-21.png)

1. Hover your mouse cursor over the objects in the **Detected attributes** list to highlight the object's bounding box in the image.

   ![](./media/17-16.png)

1. Move the **Threshold value** slider until a value of 70 is displayed to the right of the slider. Observe what happens to the objects in the list. The threshold slider specifies that only objects identified with a confidence score or probability greater than the threshold should be displayed.

   ![](./media/17-17.png)

### Review
In this exercise, you have completed the following tasks:
- Created a project in the Azure AI Foundry portal
- Generated captions for an image
- Tagged images 
- Detected Object 

## Learn more

To learn more about what you can do with this service, see the [Azure AI Vision page](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).

## You have successfully completed this lab.
