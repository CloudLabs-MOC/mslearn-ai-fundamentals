# Module 22: Explore Content Safety in Azure AI Foundry

Azure AI services help users create AI applications with out-of-the-box and pre-built and customizable APIs and models. In this exercise you will take a look at one of the services, Azure AI Content Safety, which enables you to moderate text and image content. In the Azure AI Foundry portal, Microsoft's platform for creating intelligent applications, you will use Azure AI Content Safety to categorize text and assign it a severity score. 

> **Note**
> The goal of this exercise is to get a general sense of how Azure AI services are provisioned and used. Content Safety is used as an example, but you are not expected to gain a comprehensive knowledge of content safety in this exercise!

## Lab objectives

In this lab, you will perform:
- Task 1: Create a project in Azure AI Foundry portal
- Task 2: Try out text moderation with Content Safety in Azure AI Foundry portal 

## Task 1: Create a project in the Azure AI Foundry portal

1. Open a new tab, and navigate to [Azure AI Foundry](https://ai.azure.com?azure-portal=true).

1. On the Welcome to Azure AI Foundry page, Click on **Sign in** in the top right corner.

   ![](./media/17-18.png)

1.  Enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
       ![Enter Your Username](./media/19-4.png)
 
1. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Password](./media/19-5.png)
 
1. If prompted to stay signed in, you can click **No**.

1. On the Azure AI Foundry portal home page, select **Create a project**. In Azure AI Foundry, projects are containers that help organize your work.  

    ![Screenshot of Azure AI Foundry home page with create a project selected.](./media/azure-ai-foundry-create-project.png)

1. On the **Create a project** pane, enter project name **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)** and then select **Customize (2)**.

    ![](./media/17-3.png)

1. On the **Create a project** pane, Configure it with the following settings:

    - **Hub name**: Enter **myhub<inject key="DeploymentID" enableCopy="false" /> (1)**
    - **Subscription**: **Use existing Azure subscription (2)**
    - **Resource group**: Select **AI-900-Module-22 (3)**
    - **Location**: Select **<inject key="location" enableCopy="false"/> (4)**
    - **Connect Azure AI Services or Azure OpenAI Service**:
    Click on **Create new AI Services** and provide name **AI<inject key="DeploymentID" enableCopy="false" /> (5)** and click on **Next**
    - **Connect Azure AI Search**: Leave as default **(6)**
    - Click on **Next (7)**

        ![](./media/22-12.png)

    > **Important**: You will need an Azure AI services resource provisioned in a specific location to complete the rest of the lab.

1. On the **Review and Finish** page, click on **Create**.

    ![](./media/22-1.png)

1. Keep track of the following created resources: 
    
    - **Azure AI Project**
    - **Azure AI Hub**  
    - **Azure AI Services**    
    - **Storage Account**  
    - **Key Vault**

      ![](./media/17-4.png)

1. After the resources are created, you will be brought to your project's *Overview* page.  

1. Naivaget back to the Azure portal, search for **Resourse Group (1)**, and select **Resourse Group (2)** from the result.

   ![](./media/22-2.png)

1. On the Resource Group page, select **AI-900-Module-22** from the result.

   ![](./media/22-3.png)

1. In the Azure portal, on the left-hand pane, select **Access Control (IAM) (1)**. Then on the open pane, select **Add (2)** next to the plus sign, and select **Add role assignment (3)**. 

   ![](./media/22-4.png)

1. Search for **Cognitive Services User (1)** in the list of roles, and select **Cognitive Services User (2)**. Then select **Next (3)**. 

   ![](./media/22-5.png)

1. Use the following settings to assign yourself to the role: 
    - **Assign access to (1)**: select user, group, or service principal
    - **Members**: click on **+ Select members (2)**
        - On the open *Select members* pane, search for **<inject key="AzureAdUserEmail"></inject> (3)** . Click on **<inject key="AzureAdUserEmail"></inject> (4)**. Then click **Select (5)**.
    - **Description**: *leave blank*
    - Click on **Next (6)**

    ![](./media/22-6.png)

1. Select **Review and Assign**, then select **Review and Assign** again to add the role assignment.    

   ![](./media/2207.png)

1. In your browser, return to the [Azure AI Foundry portal](https://ai.azure.com?azure-portal=true). Select your project. 

1. On the left-hand menu on the screen, select **AI Services (1)** and select the **Content Filter (2)** tile to try out Azure AI Vision and Document capabilities.
    
    ![](./media/22-7.png)

## Task 2: Try out text moderation with Content Safety in Azure AI Foundry portal 

1. On the **Content Safety** page, under Filter text content, select **Moderate text content**.

   ![](./media/22-8.png)

1. On the **Moderate text content** page, under the **Try it out** heading, select the Azure AI services resource you just created from the drop-down menu.  

1. Under Run a Simple Test, select the **Safe Content** tile. Notice that text is displayed in the box below. 

   ![](./media/22-9.png)

1. Click **Run test**. Running a test calls the Content Safety Service's deep learning model. The deep learning model has already been trained to recognize unsafe content.

   ![](./media/22-10.png)

1. In the Results panel, inspect the results. There are four severity levels from safe to high, and four types of harmful content. Does the Content Safety AI service consider this sample to be acceptable or not? What's important to note is that the results are within a confidence interval. A well-trained model, like one of Azure AI's out-of-the-box models, can return results that have a high probability of matching what a human would label the result. Each time you run a test, you call the model again. 

   ![](./media/22-11.png)

1. Now try another sample. Select the text under Violent content with misspellings. Check that the content is displayed in the box below.

1. Click **Run test** and inspect the results in the Results panel again. 

You can run tests on all the samples provided, and then inspect the results.

### Review
In this exercise, you have completed the following tasks:
- Created a project in the Azure AI Foundry portal
- Tried out text moderation with Content Safety in the Azure AI Foundry portal.

## Learn more

This exercise demonstrated only some of the capabilities of the Content Safety service. To learn more about what you can do with this service, see the [Content Safety page](https://learn.microsoft.com/azure/ai-services/content-safety/overview).

## You have successfully completed this lab.
