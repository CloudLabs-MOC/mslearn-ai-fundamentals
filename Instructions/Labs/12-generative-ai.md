# Module 12: Explore generative AI in Azure AI Foundry portal

Generative AI describes a category of capabilities within AI that create content. People typically interact with generative AI that has been built into chat applications. In this exercise, you try out generative AI in Azure AI Foundry portal, Microsoft's platform for creating intelligent applications.

## Lab objectives

In this lab, you will perform:
- Task 1: Create a project in Azure AI Foundry portal
- Task 2: Explore generative AI in Azure AI Foundry's chat playground

## Estimated timing: 30 minutes

## Architecture Diagram

 ![](media/12png.png)

## Task 1: Create a project in the Azure AI Foundry portal

In this task, we are creating an Azure AI Foundry project and setting up AI resources to explore Vision and Document capabilities.

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

1. On the Azure AI Foundry portal home page, select **Create a project**. In Azure AI Foundry, projects are containers that help organize your work.  

    ![Screenshot of Azure AI Foundry home page with create a project selected.](./media/azure-ai-foundry-create-project.png)

1. On the **Create a project** pane, enter project name **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)** and then select **Customize (2)**.

    ![](./media/17-3.png)

1. On the **Create a project** pane, Configure it with the following settings:

    - **Hub name**: Enter **myhub<inject key="DeploymentID" enableCopy="false" /> (1)**
    - **Subscription**: **Use existing Azure subscription (2)**
    - **Resource group**: Select **AI-900-Module-12 (3)**
    - **Location**: Select **<inject key="location" enableCopy="false"/> (4)**
    - **Connect Azure AI Services or Azure OpenAI Service**:
    Click on **Create new AI Services (5)** and provide name **AI<inject key="DeploymentID" enableCopy="false" /> (6)** and click on **Next**
    - **Connect Azure AI Search**: Leave as default **(7)**
    - Click on **Next (8)**

        ![](./media/12-1.png)

    > **Important**: You will need an Azure AI services resource provisioned in a specific location to complete the rest of the lab.

1. On the **Review and Finish** page, click on **Create**.

    ![](./media/12-2.png)

1. Keep track of the following created resources: 
    
    - **Azure AI Project**
    - **Azure AI Hub**  
    - **Azure AI Services**    
    - **Storage Account**  
    - **Key Vault**

      ![](./media/17-4.png)

      >**Note:** Once the deployment will succeed, close the *Project help* pane that will appear on right side.

1. If prompted with *Explore and experiment*, click on **Close** to dismiss it.

    ![](./media/3-24.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="41170453-b806-4a87-8243-fd736e4bfab5" />

## Task 2: Explore generative AI in Azure AI Foundry's chat playground

In this task, you will learn how to interact with the Chat playground in Azure AI Foundry, deploy a generative AI model, and optimize responses using effective prompting techniques.

1. In Azure AI Foundry's Portal page, Click **Playgrounds (1)** in the left menu, then select **Try the Chat playground (2)** to start.

   ![](./media/12-3.png)

1. In Azure AI Foundry's Playgrounds page, select **Try the Chat playground**. The Chat playground is a user interface that enables you to try out building a chat application with different generative AI mdoels. 

   ![](./media/12-3.png)

1. In order to use Chat playground, you need to associate it with a deployed model. In the Chat playground, select **Create a deployment**.

   ![](./media/12-4.png)

1. Select **gpt-4 (1)** and then click **Confirm (2)**.

    ![](./media/1205.png)

1. In the *Deploy model* window, keep the default naming and selection and select **Deploy**. It may take a moment for the model to deploy. 

   ![](./media/12-5.png)

   >**Note**: To check the status of your deployment, go to the left-hand menu and select *Models and endpoints* under *My assets*.

1. From the left-hand menu, select **Playgrounds**.

   ![](./media/12-6.png)

1. Click **Playgrounds (1)** in the left menu, then select **Try the Chat playground (2)**.

   ![](./media/12-3.png)


1. Under **Set-up**, select the **gpt-4** deployment from the drop-down menu.

    ![](./media/12-7.png)

1. Importantly, you need to select **Apply changes** after you make any changes to the *Setup*. 

   ![](./media/12-8.png)

1. Click **Continue** to update the system message and start a new chat session.

   ![](./media/12-21.png)

1. Consider the following ways you can improve responses from a generative AI assistant:
    - Start with a specific goal for what you want the assistant to do
    - Iterate based on previous prompts and responses to refine the result
    - Provide a source to ground the response in a specific scope of information
    - Add context to maximize response appropriateness and relevance
    - Set clear expectations for the response

1. Let's try generating a resonse using a prompt with a specific goal. In the chat box, enter the following prompt:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

    ![](./media/12-9.png)

1. Review the response. **Note**: Keep in mind that the specific response you receive may vary due to the nature of generative AI.

   ![](./media/12-10.png)
 
1. Let's try another prompt. Enter the following:

    ```prompt
    Where's a good location in Paris to stay? 
    ```

   ![](./media/12-12.png)

1. Review the response, which should provide some places to stay in Paris.

    ![](./media/12-11.png)

1. Let's iterate based on previous prompts and responses to refine the result. Enter the following prompt:
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

     ![](./media/12-13.png)

1. Review the response, which should provide dining options near a location from the previous response. 

   ![](./media/12-14.png)

1. Now, let's provide a source to ground the response in a specific scope of information. Enter the following: 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```
    ![](./media/12-18.png)

1. Review the response, which should provide information based on the provided website. 

   ![](./media/12-17.png)   

1. Let's try to add context to maximize the relevance of the response. Enter the following prompt: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

   ![](./media/12-15.png)

1. Review the response and reasoning for the response.

   ![](./media/12-16.png)

1. Now try setting clear expectations for the response. Enter the following prompt:
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

    ![](./media/12-20.png)

1. Review the response, which should provide a numbered list of sights to see in Paris.

   ![](./media/12-19.png)

1. When you are done, you can close the browser window.

### Review

In this Module, you have completed the following tasks:
- Created a project in the Azure AI Foundry portal
- Explored generative AI in Azure AI Foundry's chat playground

## Learn more

This lab demonstrated only some of the capabilities of the AI Generative AI service. To learn more about what you can do with this service, see the [Generative AI](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/evaluate-generative-ai-app) page.

## You have successfully completed this lab.
