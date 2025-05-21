# Module 12: Explore generative AI in Azure AI Foundry portal

Generative AI describes a category of capabilities within AI that create content. People typically interact with generative AI that has been built into chat applications. In this exercise, you try out generative AI in Azure AI Foundry portal, Microsoft's platform for creating intelligent applications.

## Lab objectives

In this lab, you will perform:
- Task 1: Create a project in Azure AI Foundry portal
- Task 2: Explore generative AI in Azure AI Foundry's chat playground

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

1. In the home page, select **Create an agent**.

   ![](./media/ai900l12f.png)

1. In the **Create a new project** wizard, enter **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)** for your project. 

   ![](./media/ai900l12e.png)

1. Select **Advanced options (2)** and specify the following settings:
    - **Azure AI Foundry resource**: **Myproject<inject key="DeploymentID" enableCopy="false" />**
    - **Subscription**: *Use existing Azure subscription*
    - **Resource group**: **AI-900-Module-12 (3)**
    - **Region**: Select **<inject key="location" enableCopy="false"/> (4)**

1. Select **Create (5)** and review your configuration. Wait for the set up process to complete.

    >**Note**: If you receive a permissions error, select the **Fix it** button to add the appropriate permissions to continue.

1. When your project is created, you will be brought by default to the Agents playfround in Azure AI Foundry portal, which should look similar to the following image:

    ![Screenshot of a Azure AI project details in Azure AI Foundry portal.](./media/ai900l12h.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="41170453-b806-4a87-8243-fd736e4bfab5" />
   
## Task 2: Explore generative AI in Azure AI Foundry's chat playground

In this task, you will learn how to interact with the Chat playground in Azure AI Foundry, deploy a generative AI model, and optimize responses using effective prompting techniques.

1. In Azure AI Foundry's Portal page, Click **Playgrounds (1)** in the left menu, then select **Try the Chat playground (2)** to start.

   ![](./media/ai900l12g.png)

1. Consider the following ways you can improve responses from a generative AI assistant:
    - Start with a specific goal for what you want the assistant to do
    - Iterate based on previous prompts and responses to refine the result
    - Provide a source to ground the response in a specific scope of information
    - Add context to maximize response appropriateness and relevance
    - Set clear expectations for the response

1. Let's try generating a resonse using a prompt with a specific goal. In the chat box, enter the following prompt **(1)** and click on the **Send (2)** button.

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

    ![](./media/ai900m12-6.png)

1. Review the response. **Note**: Keep in mind that the specific response you receive may vary due to the nature of generative AI.

   ![](./media/ai900m12-7.png)
 
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

1. When you are done, you can close the browser window.

### Review

In this Module, you have completed the following tasks:
- Created a project in the Azure AI Foundry portal
- Explored generative AI in Azure AI Foundry's chat playground

## Learn more

This lab demonstrated only some of the capabilities of the AI Generative AI service. To learn more about what you can do with this service, see the [Generative AI](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/evaluate-generative-ai-app) page.

## You have successfully completed this lab.
