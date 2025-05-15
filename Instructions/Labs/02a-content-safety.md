# Lab 2a: Explore Content Safety in Azure AI Foundry

Azure AI services empower users to build intelligent applications using pre-built and customizable APIs and models. In this exercise, you'll explore Azure AI Content Safety, a service that enables moderation of text and image content. Using the Azure AI Foundry portal, Microsoft's platform for creating intelligent applications, you'll utilize Azure AI Content Safety to categorize text and assign severity scores.

> **Note**
> This exercise aims to provide a general understanding of how Azure AI services are provisioned and utilized. Content Safety is used as an example; comprehensive knowledge of content safety is not required for this exercise.

## Lab Overview

In this lab, you will create an Azure AI Foundry project, configure resources, and explore how to moderate text content using Azure AI Content Safety.


## Lab Objectives

By the end of this lab, you will be able to:

- Create and configure a project in Azure AI Foundry.
- Use Azure AI Content Safety to moderate text content.

## Exercise 1: Explore Content Safety in Azure AI Foundry

### Task 1: Create a project in the Azure AI Foundry portal

In this task, we are creating an Azure AI Foundry project and configuring necessary resources to explore AI language capabilities in the Language Playground.

1. Right-click the [Azure AI Foundry](https://ai.azure.com?azure-portal=true) **(1)** link, choose **Copy link (2)** from the context menu, then paste it into a new tab to open the Azure AI Foundry portal.

   ![](./media/3-27.png)

1. On the **Welcome to Azure AI Foundry** page, look at the top right corner and click the **Sign in** button to log in.

   ![](./media/17-18.png)

1. If prompted to sign in, enter your credentials.
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
      ![Enter Your Username](./media/19-4.png)
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Password](./media/19-5.png)
 
1. If prompted to stay signed in, you can click **No**.

   ![](./media/9-8.png)

1. If prompted with *Streamlined from the start*, click on **Got it** to proceed.

   ![](./media/3-23.png)

1. On the Azure AI Foundry portal home page, select **Create a project**. In Azure AI Foundry, projects are containers that help organize your work.  

    ![Screenshot of Azure AI Foundry home page with create a project selected.](./media/azure-ai-foundry-create-project.png)

1. On the **Create a project** pane, enter project name **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)** and then select **Customize (2)**.

    ![](./media/17-3.png)

1. On the **Create a project** pane, Configure it with the following settings:

    - **Hub name**: Enter **myhub<inject key="DeploymentID" enableCopy="false" /> (1)**
    - **Subscription**: **Use existing Azure subscription (2)**
    - **Resource group**: Select **AI-900-Module-06 (3)**
    - **Location**: Select **<inject key="location" enableCopy="false"/> (4)**
    - **Connect Azure AI Services or Azure OpenAI Service**:
    Click on **Create new AI Services** and provide name **AI<inject key="DeploymentID" enableCopy="false" /> (5)** and click on **Next**
    - **Connect Azure AI Search**: Leave as default **(6)**
    - Click on **Next (7)**

        ![](./media/18-8.png)

    > **Important**: You will need an Azure AI services resource provisioned in a specific location to complete the rest of the lab.

1. On the **Review and Finish** page, click on **Create**.

    ![](./media/17-2.png)

1. Keep track of the following created resources: 
    
    - **Azure AI Project**
    - **Azure AI Hub**  
    - **Azure AI Services**    
    - **Storage Account**  
    - **Key Vault**

      ![](./media/17-4.png)

      >**Note:** Once the deployment will succeed, close the *Project help* pane that will appear on right side.

11. After the resources are created, you will be brought to your project's *Overview* page.

12. To use Content Safety, you need to update permissions for your *Azure AI hub* resource:

    a. Open the [Azure portal](https://portal.azure.com?portal-azure=true) and log in with the same subscription used to create your AI Foundry resources.

    b. In the Azure portal, use the search bar at the top to search for **Azure AI Foundry**.

    c. Select the resource you just created with the type **Azure AI hub**.

    d. In the left-hand pane, select **Access Control (IAM)**.

    e. Click **Add** and then select **Add role assignment**.

    f. Search for **Azure AI Safety Evaluator** in the list of roles and select it.

    g. Click **Next**.

    h. Under **Assign access to**, select *User, group, or service principal*.

    i. Click on **Select members**, find your name, click the plus icon next to your name, and then click **Select**.

    j. Click **Review and Assign**, then click **Review and Assign** again to add the role assignment.

    ![Add role assignment](./media/add-role-assignment.png)

13. Return to the [Azure AI Foundry portal](https://ai.azure.com?azure-portal=true).

14. Select your project.([Microsoft Learn][1])

15. In the left-hand menu, select **AI Services**.

    ![AI Services](./media/ai-services-menu.png)

16. On the *AI Services* page, select the **Content Safety** tile.

    ![Content Safety tile](./media/content-safety-tile.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:

* Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
* If not, carefully read the error message and retry the step, following the instructions in the lab guide.
* If you need any assistance, please contact us at [cloudlabs-support@spektrasystems.com](mailto:cloudlabs-support@spektrasystems.com). We are available 24/7 to help you out.

<validation step="">

### Task 2: Try Out Text Moderation with Content Safety in Azure AI Foundry Portal

In this task, you will test text moderation using Azure AI Content Safety to categorize and assess the severity of different text samples.

1. On the *Content Safety* page, under *Filter text content*, select **Moderate text content**.

   ![Moderate text content](./media/moderate-text-content.png)

2. On the *Moderate text content* page, under the *Try it out* heading, select the Azure AI services resource you just created from the drop-down menu.

   ![Select AI service](./media/select-ai-service.png)

3. Under *Run a simple test*, select the **Safe Content** tile. Notice that text is displayed in the box below.

   ![Safe content sample](./media/safe-content-sample.png)

4. Click **Run test**. Running a test calls the Content Safety Service's deep learning model, which has been trained to recognize unsafe content.

   ![Run test](./media/run-test.png)

5. In the *Results* panel, inspect the results. There are four severity levels from safe to high, and four types of harmful content. Determine whether the Content Safety AI service considers this sample acceptable. Note that the results are within a confidence interval, indicating the probability that the content matches what a human would label. Each time you run a test, you call the model again.

   ![Results panel](./media/results-panel.png)

6. Now try another sample. Select the text under **Violent content with misspelling**. Ensure that the content is displayed in the box below.

   ![Violent content sample](./media/violent-content-sample.png)

7. Click **Run test** and inspect the results in the *Results* panel again.

   ![Run test again](./media/run-test-again.png)

You can run tests on all the samples provided and inspect the results to understand how the Content Safety service evaluates different types of content.

### Review

In this lab, you have completed the following tasks:

- Created a project in the Azure AI Foundry portal and configured necessary resources.
- Assigned the **Azure AI Safety Evaluator** role to your Azure AI hub resource.
- Explored the Content Safety service within the Azure AI Foundry portal.
- Performed text moderation tests on sample content using Azure AI Content Safety.

## Learn More

This exercise demonstrated only some of the capabilities of the Content Safety service. To learn more about what you can do with this service, see the [Azure AI Content Safety documentation](https://learn.microsoft.com/en-us/azure/ai-services/content-safety/overview).
