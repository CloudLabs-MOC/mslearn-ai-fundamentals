# Module 02:  Explore the Content Safety Studio 

## Lab overview

In this exercise, you will set up a single-service resource in Azure AI Content Safety Studio to evaluate and moderate text and image content, providing severity scores for various categories, ranging from safe to high.

## Lab objectives
In this lab, you will perform:
- Task 1: Explore the Content Safety Studio
- Task 2: Associate a resource with the studio 
- Task 3: Try out text moderation in the Content Safety Studio
- Task 4: Check out the keys and endpoint

## Estimated timing: 30 minutes

## Architecture Diagram

![](media/Module1.1.png)

> **Note:** The goal of this exercise is to get a general sense of how Azure AI services are provisioned and used. Content Safety is used as an example, but you are not expected to gain a comprehensive knowledge of content safety in this exercise!

## Exercise 1:  Explore the Content Safety Studio 

### Task 1: Explore the Content Safety Studio 

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

1. The Content Safety Studio is set up like many other studios for Azure AI services. On the menu at the top of the screen, click on the icon on the left of **Azure AI**. You will see a drop-down list of other studios designed for development with Azure AI services. You can click on the icon again to hide the list.

     ![](media/29.png)  

### Task 2: Associate a resource with the studio 

Before using the studio, you need to associate an Azure AI services resource with the studio. Depending on the studio, you may find you need a specific single-service resource, or can use a general multi-service resource. In the case of the Content Safety Studio, you can use the service by creating a single-service *Content Safety* resource or *Azure AI services* general multi-service resource. In the steps below, we will create a single-service Content Safety resource. 

1. On the top right of the screen, click on the **Settings** icon. 

   ![](media/26.png)

2. On the **Settings** page, you will see a *Directory* tab and *Resource* tab. On the *Resource* tab, select **+ Create a new resource**. This takes you to page to create a resource in the Azure Portal.

    ![](media/27.png)

   > **Note**: The **Directory** tab allows users to select different directories from which to create resources. You do not need to change its settings unless you wish to use a different directory. 

1. On the Create Content Safety page in the [Azure Portal](https://portal.azure.com?auzre-portal=true), you need to configure several details to create your resource. Configure it with the following settings:
    - **Subscription (1)**: Use the existing Azure subscription.
    - **Resource group (2)**: Select **AI-900-Module-02**
    - **Region (3)**: Select **<inject key="location" enableCopy="false"/>**
    - **Name (4)**: Enter **contentsafety<inject key="DeploymentID" enableCopy="false"/>**
    - **Pricing tier (5)**: Select **Free F0** from the drop-down.
    - Select **Review + Create (6)**

      ![](media/25.png)

1. Review the configuration. Then select **Create**. The screen will indicate when the deployment is complete. 

   >**Congrats! You've just created, or provisioned, an Azure AI services resource. The one you provisioned, in particular, is a single-service Content Safety service resource.**

1. Return to the [Content Safety Studio](https://contentsafety.cognitive.azure.com?azure-portal=true). 

1. Select the **Settings** icon on the top right of the screen again. This time you should see that your newly created resource has been added to the list.  

1. On the Content Safety Studio's Settings page, select the checkbox of the **Azure AI service (1)** resource you just created and click **Use resource (2)** on the bottom of the screen. You will be taken back to the studio home page. Now you can begin using the studio with your newly created resource.

   ![](media/30.png)

   >**Note:** The provision of content safety resources will take approximately 30-40 minutes. During this time, please proceed with Module 3. After completing Module 3, return to Module 2 and continue the lab from Task 3.

### Task 3: Try out text moderation in the Content Safety Studio

1. Navigate back to the Content Safety Studio home page.

1. On the Content Safety Studio home page, under *Run moderation tests*

1. Select the **Moderate text content** box.

   ![](media/37.png)
 
1. Under run a simple test, click **Safe Content (1)**. Notice that text is displayed in the box below and click on **Run test (2)**. Running a test calls the Content Safety Service's deep learning model. The deep learning model has already been trained to recognize un-safe content.

   ![](media/azureai.png)

   ![](media/chopping.png)

1. In the Results panel, inspect the results. There are four severity levels from safe to high, and four types of harmful content. Does the Content Safety AI service consider this sample to be acceptable or not? What's important to note is that the results are within a confidence interval. A well-trained model, like one of Azure AI's out-of-the-box models, can return results that have a high probability of matching what a human would label the result. Each time you run a test, you call the model again.

   ![](media/results.png)

1. Now try another sample. Select the text under **Violent content with misspelling (1)**. Check that the content is displayed in the box below and click on**Run test (2)**.

    ![](media/voilent.png)

    ![](media/run-test.png)

1. Inspect the results in the Results panel again. 

   ![](media/runtest(2).png)

You can run tests on all the samples provided, then inspect the results.

### Task 4: Check out the keys and endpoint

These capabilities you tested can be programmed into all sorts of applications. The keys and endpoint used for application development can be found both in the Content Safety Studio and the Azure Portal. 

1. In the Content Safety Studio, navigate back to the **Settings** page, with the Resources tab selected. Look for the resource you used. Scroll across to see the endpoint and key for your resource. 

   ![](media/32.png)

1. In the Azure Portal, you will see that these are the **same** endpoint and **different** keys for your resource. To check it out, head to the [Azure Portal](https://portal.azure.com?auzre-portal=true). Search for Content Safety on the top search bar. Find your resource and click on it. On the left-hand menu, look under *Resource Management* for **Keys and Endpoints**. Select **Keys and Endpoints** to view the endpoint and keys for your resource. 

     ![](media/31.png)

## Validation

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="5371378e-8511-44ed-9037-3a000338132f" />

## Learn more

This simple search index only some of the capabilities of the Content Safety Studio. To learn more about what you can do with this service, see the [ Explore the Content Safety Studio ](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview).

### Review
In this lab, you have completed:
- Explored Content Safety Studio
- Associated a resource with safety studio
- Tried out text moderation in the Content Safety Studio
- Checked out the keys and endpoint

## You have successfully completed this lab.
