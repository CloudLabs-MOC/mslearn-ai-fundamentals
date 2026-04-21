# Get started with generative AI and agents in Microsoft Foundry

## Lab overview

In this exercise, you'll use Microsoft Foundry to deploy and explore a generative AI model. You'll then use the model in an agent that includes knowledge tools to answer user questions.

## Lab objectives

In this exercise, you will perform:

- Task 1: Create a Microsoft Foundry project
- Task 2: Deploy a model
- Task 3: Chat with the model
- Task 4: Experiment with system prompts
- Task 5: View client code to chat with a model
- Task 6: Save the model configuration as an agent
- Task 7: Add a knowledge tool to the agent
- Task 8: Explore options to use the agent

## Task 1: Create a Microsoft Foundry project

In this task, you will access the Microsoft Foundry portal and create a new project.
This project acts as a workspace to organize and manage resources required for building generative AI solutions.

1. Copy the **Microsoft Foundry** link and paste it into a new browser tab to access the portal: `https://ai.azure.com?azure-portal=true`

1. On the **Microsoft Foundry** home page, click on **Sign in** in the top right corner.

   ![](./media/mod6-p2t1p1.png)

1. If prompted to sign in, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject> **(1)** and click on **Next (2)**.
 
      ![Enter Your Username](./media/mod6-p2t1p2.png)
 
   - **Password:** <inject key="AzureAdUserPassword"></inject> **(1)** and click on **Sign in (2)**.
 
     ![Enter Your Password](./media/mod6-p2t1p2(1).png)

1. If prompted to **Stay signed in?**, you can click **No**.

   ![](./media/mod6-p2t1p3.png)

   > **Note:** Close any tips or quick start panes that are opened the first time you sign in, and if necessary use the **Foundry** logo at the top left to navigate to the home page.

1. At the top of the **Microsoft Foundry** portal, enable the **New Foundry toggle (1)** to switch to the latest Foundry user interface.

1. From the **Select a project to continue** dialog, click the drop-down under **Select or search for a project**, and then select **Create a new project (2)**.

    ![](./media/lab2a-l1.png)

1. In the **Create a project** wizard, enter project name **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)**, and **Expand Advanced options (2)** to specify the following settings for your project: 

    - Subscription : **Leave default subscription (3)** 
    - Resource Group : Select **AI-900-Module-02a (4)** 
    - Microsoft Foundry resource: **MyFoundry<inject key="DeploymentID" enableCopy="false" /> (5)**
    - Region : Select **<inject key="location" enableCopy="false"/> (6)**
    - Click on **Create** **(7)**

      ![](./media/lab2a-l2.png)
      
      >**Note:** Model deployments are restricted by regional quotas. If you select a region in which you have insufficient available quota, you may need to select an alternative region for a new resource later.

1. Wait for your project created. It may take a few minutes, once the setup is complete, you are automatically redirected to the **Microsoft Foundry home page** for the newly created project.

   ![](./media/lab2a-l3.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="41ca39eb-3ddc-4498-89e5-e45e1c9c9239" />

## Task 2: Deploy a model

In this task, you will explore the model catalog in Microsoft Foundry and deploy a generative AI model. The deployed model will be used for interactive testing and experimentation in the playground.

1. On the **Microsoft Foundry** home page, click **Start building (1)**, and then select **Browse models (2)** from the drop-down menu.

     ![](./media/lab2a-l4.png)

1. Microsoft Foundry provides a large collection of models from Microsoft, OpenAI, and other providers, that you can use in your AI apps and agents.

    ![](./media/lab2a-l5.png)

1. On the **Models** page, search for **gpt-4.1-mini (1)** in the search bar, and then select the **gpt-4.1-mini (2)** model from the search results.

     ![](./media/lab2a-l6.png)

1. On the **gpt-4.1-mini** model details page, click **Deploy (1)**, and then select **Default settings (2)** to deploy the model using the standard configuration.

    ![](./media/lab2a-l7.png)

1. When the model has been deployed, view the model playground page that is opened, in which you can chat with the model.

    ![](./media/lab2a-l8.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="53a76f5b-037d-4dff-a723-3e67a901b5f5" />

## Task 3: Chat with the model

In this task, you will interact with the deployed model using the chat playground.
You will ask questions, observe responses, and understand how conversation context is maintained during interactions.

1. Use the button at the bottom of the left navigation pane to hide it and give yourself more room to work with.

1. In the **Chat** pane, enter a prompt such as `Who was Ada Lovelace?`, and review the response.

    ![](./media/lab2a-l9.png)

1. Enter a follow-up prompt, such as `Tell me more about her work with Charles Babbage.` and review the response.

    ![](./media/lab2a-l10.png)

    > **Note:** Generative AI chat applications often include the conversation history in the prompt; so the context of the conversation is retained between messages. In this case, "her" is interpreted as referring to Ada Lovelace.

1. At the top-right of the chat pane, use the **New chat** button to restart the conversation. This removes all conversation history.

     ![](./media/lab2a-l11.png)

1. Enter a new prompt, such as `Who was Alan Turing?` and view the response.

     ![](./media/lab2a-l12.png)

1. Continue the conversation with prompts such as `What is the Turing test?` or `What is a Turing machine?`.

## Task 4: Experiment with system prompts

In this task, you will explore how system prompts and model parameters influence the responses generated by the model. This helps you understand how to control response style, length, and creativity.

1. At the top of the chat pane, use the **New chat (1)** button to restart the conversation. Then enter a new prompt, such as `What was ENIAC?` **(2)** and view the response.

     ![](./media/lab2a-l13.png)

     ![](./media/lab2a-l14.png)

1. In the pane on the left, in the **Instructions** text area, change the system prompt to `You are an AI assistant that provides short and concise answers using simple language. Limit responses to a single sentence.` **(1)**, then enter **What was ENIAC? (2)** in the chat box..

     ![](./media/lab2a-l15.png)

1. Review the updated response generated for the prompt **What was ENIAC?**.

     ![](./media/lab2a-l16.png)

1. Continue to experiment with different 
system prompts to try to influence the kinds of response returned by the model.

1. When you have finished experimenting, change the system prompt back to `You are an AI assistant that helps people find information.`

     ![](./media/lab2a-l17.png)

### Task 4.1:  Experiment with model parameters

Model parameters control how the model works, and can be useful for restricting the size of its responses (measured in *tokens*) and controlling how "creative" its responses can be.

1. Use the **New chat (1)** button to restart the conversation.

1. In the pane on the left, next to the model name, select **Parameters (2)**.

     ![](./media/lab2a-l18.png)

1. Review the parameter settings, using the *(i)* links to view their description. Then, without changing them, enter a prompt like `What is Moore's law?` and review the response

     ![](./media/lab2a-l19.png)

1. Experiment by changing the parameter values and repeating the same prompt. You may see some differences in behavior from the model. For example, changing the **Temperature** modifies the randomness of the model's "next word" selection, with lower temperatures resulting in less "creative" response construction.

1. Select the **Parameters (1)** icon to open the parameter settings panel, drag the **Temperature (2)** slider to modify the model’s response behavior, enter the prompt **What is Moore’s law? (3)**, and then run the query.

     ![](./media/lab2a-l20.png)

     >**Tip:** You can use the **Stop generation** button in the chat pane to stop long-running responses.

1. When you've finished experimenting, reset the parameters to their original values.

## Task 5: View client code to chat with a model

In this task, you will review sample client code in the Code tab to understand how to connect to and chat with a deployed model using the Microsoft Foundry APIs and SDKs.

1. In the **Chat** pane, view the **Code** tab. This tab shows sample code that a client application can use to chat with the model. Above the sample code, you can choose preferences for:

    ![](./media/lab2a-l22.png)

    - **API:** The OpenAI API is a common standard for implementing conversations with generative AI models. There are two variants of the OpenAI API that you can use:
        - **Completions:** A broadly used programmatic syntax for submitting prompts to a model.
        - **Responses:** A newer syntax that offers greater flexibility for building apps that converse with both standalone models and with *agents*.
    - **Language:** You can write code to consume a model in a wide range of programming languages, including Python. Microsoft C#, JavaScript, and others.
    - **SDK:** You can use a language-specific SDK, which encapsulates the low-level communication details between the client and model; or you can work directly with the REST API, enabling you to have full control over the HTTP request messages that your client sends to the model.
    - **Authentication:** To use a model deployed in Microsoft Foundry, the client application must be authenticated. You can implement authentication using:
        - **Key-based authentication:** The client app must present a security key (which you can find by selecting the key icon above the code sample)
        - **Microsoft Entra ID authentication:** The client app presents an authentication token based on an identify that is assigned to it (or to the current user).

1. Select the following code options:
    - **API**: Responses API
    - **Language**: Python
    - **SDK**: OpenAI SDK
    - **Authentication**: Key authentication

      ![](./media/lab2a-l23.png)

    - The resulting sample should be similar to the following code:

    ```python
    from openai import OpenAI
    
    endpoint = "https://your-project-resource.openai.azure.com/openai/v1/"
    deployment_name = "gpt-4.1-mini"
    api_key = "<your-api-key>"
    
    client = OpenAI(
        base_url=endpoint,
        api_key=api_key
    )
    
    response = client.responses.create(
        model=deployment_name,
        input="What is the capital of France?",
    )
    
    print(f"answer: {response.output[0]}")
    ```

    - The code connects to the resource endpoint for your Microsoft Foundry project, using its secret authentication key (which you would need to copy into the code to set the **api_key** variable). It then uses your deployed model to generate a response from an input prompt (in this case, the hard-coded question "What is the capital of France?") and prints the response to the output console.

      > **Tip:** If you are using a work or school account to sign into Azure, and you have sufficient permissions in the Azure subscription, you can open the sample code in VS Code for Web to run it, and experiment with editing it.

1. When you have finished reviewing the code, switch back to the **Chat** tab.

## Task 6: Save the model configuration as an agent

In this task, you will encapsulate the model, its instructions, and tool configuration into an agent to create a fully agentic AI experience. The agent will be configured to help employees with expense claims.

1. In the model playground, at the top right select **Save as agent (1)**. Then, when prompted, name your new agent `expenses-agent` **(2)** and then select **Create (3)**. When the agent is created, it opens in a new playground specifically for working with agents.

    ![](./media/lab2a-l24.png)

1. Change the **Instructions** to `You are a helpful AI assistant who supports employees with expense claims.` **(1)**

1. At the top of the agent playground, select **Save (2)**.

     ![](./media/lab2a-l26.png)

1. In the pane on the right, view the **YAML** tab, which contains the definition for your agent. Note that its definition includes the model, its parameter settings, and the instructions you specified - similar to this:

    ```yml
    metadata:
      logo: Avatar_Default.svg
      description: ""
      modified_at: "1767997310"
    object: agent.version
    id: expenses-agent:2
    name: expenses-agent
    version: "2"
    description: ""
    created_at: 1767997284
    definition:
      kind: prompt
      model: gpt-4.1-mini
      instructions: You are a helpful AI assistant who supports employees with expense claims.
      temperature: 0.98
      top_p: 1
      tools: []
    ```

     ![](./media/lab2a-l27.png)

1. Switch back to the **Chat** tab, and enter the prompt `What can you do?`. The response should indicate that the agent is "aware" of its role as an expense claims advisor.

    ![](./media/lab2a-l28.png)

1. Enter an expenses-related prompt, such as `How much can I claim for a taxi?`. The response is likely to be generic. Accurate; but not particularly helpful to the employee. We need to give the agent some knowledge about the company's expense policies and procedures.

     ![](./media/lab2a-l29.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="26a02172-cb11-4e43-9aae-fb763d33b068" />

## Task 7: Add a knowledge tool to the agent

In this task, you will add a file-based knowledge tool to the agent so it can use company expense policy documents to provide more accurate and helpful responses.

1. Open a new **InPrivate/Incognito** browser window, navigate to `https://microsoftlearning.github.io/mslearn-ai-fundamentals/data/expenses_policy.docx`, and download the **expenses_policy.docx** file to your local computer.

1. Return to the tab containing the agent playground, and in the pane on the left, expand the **Tools (1)** section if it's not already expanded and select **Upload files (2)**.

     ![](./media/lab2a-l31.png)

1. In the **Attach files** pane, keep **Create a new index** selected, then select **Browse for files** to upload the required documents.

    ![](./media/lab2a-l32.png)

1. In the **Open** dialog box, select **Downloads** (1), choose the **expenses_policy** file (2), and then select **Open** (3) to upload the file.

     ![](./media/lab2a-l33.png)

1. Verify that the **expenses_policy.docx** file shows a **Success** status, and then select **Attach** to complete uploading the file to the agent.

     ![](./media/lab2a-l34.png)

1. At the top of the agent playground, use the **Save** button to update the agent definition.

     ![](./media/lab2a-l35.png)

1. In the pane on the right, view the **YAML** tab, which contains the definition for your agent. Note that its definition now includes the file search tool you added:

    ```yml
    metadata:
      logo: Avatar_Default.svg
      description: ""
      modified_at: "1767999261"
    object: agent.version
    id: expenses-agent:3
    name: expenses-agent
    version: "3"
    description: ""
    created_at: 1767999232
    definition:
      kind: prompt
      model: gpt-4.1-mini
      instructions: You are a helpful AI assistant who supports employees with expense claims.
      temperature: 0.98
      top_p: 1
      tools:
        - type: file_search
          vector_store_ids:
            - vs_sYs3SP17fUcc3E7eJqWfgxBW
    ```

     ![](./media/lab2a-l36.png)

1. Switch back to the **Chat** tab, and enter the same expenses-related prompt as before (for example, `How much can I claim for a taxi?`) and view the response.

    ![](./media/lab2a-l37.png)

     - This time the response should be informed by the information in the expenses data source.

1. Try a few more expenses-related prompts, like `What about a hotel?` or `Can I claim the cost of my dinner?`

## Task 8: Explore options to use the agent

In this task, you will preview the agent, test its responses, and review sample code that shows how the agent can be consumed by client applications or published for enterprise use.

1. At the top of the agent playground, in the **Preview (1)** drop-down list, select **Preview agent (2)**.

    ![](./media/lab2a-l38.png)

1. In the preview web page that opens in a new tab, enter a prompt such as `How do I submit an expense claim?` in the message box **(1)**, then select the **Send (2)** and review the response.

    ![](./media/lab2a-l39.png)

    ![](./media/lab2a-l40.png)

1. Explore the agent preview by submitting some more prompts. When you're finished, close the browser tab containing the preview app and return to the agent playground.

1. In the agent playground, note that the **Publish** button can be used to publish your agent as an enterprise application in Azure so it can be consumed within Microsoft 365 and Teams.

    - In many cases, publishing an expense claim support agent for use in the enterprise application ecosystem would be an ideal way to implement an agentic solution. However, in other cases you may want to consume the agent from a custom application. 

1. Switch from the **Chat** tab to the **Code** tab, and view the sample code for consuming the agent. The code uses the OpenAI Responses API; but has some agent-specific differences from the code you previously examined to chat with the model.

    ```python
    # Before running the sample:
    #    pip install --pre azure-ai-projects>=2.0.0b1
    #    pip install azure-identity
    
    from azure.identity import DefaultAzureCredential
    from azure.ai.projects import AIProjectClient
    
    myEndpoint = "https://your-project-resource.services.ai.azure.com/api/projects/ai-project-123"
    
    project_client = AIProjectClient(
        endpoint=myEndpoint,
        credential=DefaultAzureCredential(),
    )
    
    myAgent = "expenses-agent"
    # Get an existing agent
    agent = project_client.agents.get(agent_name=myAgent)
    print(f"Retrieved agent: {agent.name}")
    
    openai_client = project_client.get_openai_client()
    
    # Reference the agent to get a response
    response = openai_client.responses.create(
        input=[{"role": "user", "content": "Tell me what you can help with."}],
        extra_body={"agent": {"name": agent.name, "type": "agent_reference"}},
    )
    
    print(f"Response output: {response.output_text}")
    ```

    ![](./media/lab2a-l41.png)

    > **Tip:** If you are using a work or school account to sign into Azure, and you have sufficient permissions in the Azure subscription, you can open the sample code in VS Code for Web to run it, and experiment with editing it.

## Summary

In this exercise, you explored how to deploy an chat with a generative AI model in Microsoft Foundry portal. You then saved the model as an agent, and configured the agent with instructions and tools before exploring options for deploying and using the agent.

The agent explored in this exercise is a simple example that demonstrates how quickly and easily you can get started with generative AI app and agent development using Microsoft Foundry. From this foundation, you could build a comprehensive agentic solution in which agents use tools to find information and automate tasks, and collaborate with one another to perform complex workflows.

### Congratulations, you’ve successfully completed the hands-on lab!
