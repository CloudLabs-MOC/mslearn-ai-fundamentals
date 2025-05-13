# Module 02: Explore Azure AI Services

## Lab overview

In this exercise, you will set up

## Lab Objectives

In this lab, you will perform:

- Task 1: Create an *Azure AI services* resource in the Azure portal
- Task 2: Check out the keys and endpoint
- Task 3: See Azure AI services in action

## Exercise 1: Create an *Azure AI services* resource in the Azure portal
### Task 1: Create an *Azure AI services* resource in the Azure portal

In this task, you will learn how to explore

1. Open the [Content Safety Studio](https://contentsafety.cognitive.azure.com?azure-portal=true). If you are not logged in, you will need to sign in. Select **Sign In** on the top right of the screen.  

    ![](media/28.png)

1. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:

    - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
      ![Enter Your Username](media/sc900-image-1.png)
 
1. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
      ![Enter Your Password](media/sc900-image-2.png)
 
1. If prompted to stay signed in, you can click "No."

    ![](media/15.png)

1. Click the **&#65291;Create a resource** button and search for *Azure AI services*. Select **create** an **Azure AI services** plan. You will be taken to a page to create an Azure AI services resource. Configure it with the following settings:
    - **Subscription (1)**: Use the existing Azure subscription.
    - **Resource group (2)**: Select **AI-900-Module-02**
    - **Region (3)**: Select **<inject key="location" enableCopy="false"/>**
    - **Name (4)**: Enter **contentsafety<inject key="DeploymentID" enableCopy="false"/>**
    - **Pricing tier (5)**: Select **Standard S0** from the drop-down.
    - - **By checking this box, I acknowledge that I have read and understood all the terms below**: *Selected*.
    - Select **Review + Create (6)**

      ![](media/25.png)

1. Select **Review + create** then **Create** and wait for deployment to complete.
 
   >***Congrats! You've just created or provisioned an Azure AI services resource. The one you provisioned in particular is a multi-service resource.***

1. Once the deployment is complete, select *Go to resource*. 

### Task 2: Check out the keys and endpoint

In order to incorporate Azure AI services into applications, developers need a service key and endpoint. The keys and endpoint used for application development can be found in the Azure Portal. 

1. In the Azure Portal, select your resource. On the left-hand menu, look under *Resource Management* for *Keys and Endpoints*. Select **Keys and Endpoints** to view the endpoint and keys for your resource. 

### Task 3: See Azure AI services in action

1. In a browser tab, navigate to [Azure AI Foundry](https://ai.azure.com?azure-portal=true).

1. Sign in with your account. 

1. Under *Work outside a project*, select the **View AI Services** tile.
 
    ![Screenshot of the left-hand menu on the project screen with AI Services selected.](./media/view-ai-foundry-outside-project.png)  

1. On the *AI Services* page, select the *Vision + Document* tile to try out Azure AI Vision and Document capabilities.

    ![Screenshot of the Vision and Document tile selected on the AI Services page.](./media/vision-document-tile.png)

1. Under *View all Vision capabilities* select the **Face** tab. 

1. Select the *Detect faces in an image* demo tile. 

1. Try out the Face service, which is one of many Azure AI services. Click on an image and check out the detected attributes. 

    ![Screenshot of the detect faces demo in Azure AI Foundry portal.](./media/detect-faces-demo.png)

1. Scroll down to the **Run the code** section. Select **View Code**. Sroll down to the section that starts with *import os*. In the sample code provided, you'll see placeholders where you could put a key and endpoint.

    ![Screenshot of the view code screen with a view of the code placeholders for key and endpoint.](./media/view-code-example.png) 

1. If you were to build an application that used Azure AI services, you could start with the provided code. By replacing the placeholders with your own service's key and endpoint, your application would be able to send requests and receive responses that utilize Azure AI services. In the case of the Face service, the *request* is for the Face service to analyze the image. The *response* is the detected attributes. 

    >**Note**
    >You do not need to know programming to complete any of the exercises in this course. We will continue to take a look at Azure AI services in action through the Azure AI Foundry portal.  

## Validation

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="5371378e-8511-44ed-9037-3a000338132f" />

## Learn more

This simple search index only some of the capabilities of the Content Safety Studio. To learn more about what you can do with this service, see the [ Explore the Content Safety Studio ](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview).

### Review
In this lab, you have completed the following tasks:
- Explored Content Safety Studio
- Associated a resource with safety studio
- Tried out text moderation in the Content Safety Studio
- Checked out the keys and endpoint

## You have successfully completed this lab.
