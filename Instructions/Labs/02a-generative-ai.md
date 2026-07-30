# Get started with generative AI and agents in Microsoft Foundry

### Estimated Duration: 60 Minutes

## Lab overview

In this lab, you will learn how to build and enhance a generative AI agent using Microsoft Foundry. You'll create a Foundry project, deploy a GPT model, and interact with it through the chat playground. You'll then customize the model's behavior using system instructions, extend its capabilities with web search and custom knowledge sources, and save it as a reusable agent. Finally, you'll preview the agent and explore the client code required to integrate it into your own applications.

## Lab objectives

In this lab, you will perfomr the following tasks:

* Task 1: Create a Microsoft Foundry project.
* Task 2: Deploy a model.
* Task 3: Chat with the model.
* Task 4: Specify instructions.
* Task 5: Add a web_search tool.
* Task 6: Add knowledge.
* Task 7: Save the model configuration as an agent.
* Task 8: Preview the agent.
* Task 9: View client code to access the agent in your project.

## Task 1: Create a Microsoft Foundry project

In this task, you'll create a Microsoft Foundry project, configure the required Azure resources, and obtain the project endpoint needed for application development.

1. Copy the **Microsoft Foundry** link and paste it into a new browser tab to access the portal: `https://ai.azure.com/`

1. On the **Microsoft Foundry** home page, click on **Start building** in the top right corner.

     ![](./media/mod7-t1p1.png)

1. If prompted to sign in, enter your credentials:
 
   - **Email/Username:** Enter <inject key="AzureAdUserEmail"></inject> **(1)** and click on **Next (2)**.
 
        ![Enter Your Username](./media/mod6-p2t1p2.png)
 
   - **Password:** Enter <inject key="AzureAdUserPassword"></inject> **(1)** and click on **Sign in (2)**.
 
      ![Enter Your Password](./media/mod6-p2t1p2(1).png)

1. If prompted to **Stay signed in?**, you can click **No**.

    ![](./media/mod6-p2t1p3.png)

1. You will be redirected to the **Setting up your project** page. Wait **1-2 minutes** for the project creation process to complete before proceeding.

   ![](./media/lab8new-t1p1.png) 

1. In the **Your project is set up. What would you like to do next ?** pop-up, click **X** button to dismiss the window.

    ![](./media/mod7-t1p3.png)

1. After creating a project in the new **Foundry** portal, it should open in a page similar to the following image:

    ![](./media/mod7-t1p4.png)

    > **Note:** The Microsoft Foundry landing page may vary depending on the version of the portal, your account configuration, or recent UI updates. If your home page looks different, continue with the lab by locating the required menu options using the navigation menu. The appearance of the portal may differ, but the functionality and lab steps remain the same.

    ![](./media/ai901-l5-1(3).png)


> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="9b1d64ef-a910-4275-bc8f-078000830e02" />

## Task 2: Deploy a model

In this task, you will explore the model catalog in Microsoft Foundry and deploy a generative AI model. The deployed model will be used for interactive testing and experimentation in the playground.

1. On the **Microsoft Foundry** home page, then select **Discover (1)** and then click on **Model (2)** to view the Microsoft Foundry model catalog.

     ![](./media/ai901-l5-1(4).png)

1. On the **Models** page, search for **gpt-5-mini (1)** in the search bar, and then select the **gpt-5-mini (2)** model from the search results.

     ![](./media/lab2a-p2t1p4.png)

1. On the **gpt-5-mini** model details page, click **Deploy (1)**, and then select **Default settings (2)** to deploy the model using the standard configuration.

    ![](./media/lab2a-p2t1p5.png)

1. When the model has been deployed, view the model playground page that is opened, in which you can chat with the model.

    ![](./media/ai901-l2-02.png)


> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="6d51d370-fbe8-4b78-ac65-6daae4aea306" />

## Task 3: Chat with the model

In this task, you'll interact with the deployed model in the chat playground to understand how it responds to prompts and maintains conversational context.

You can use the playground to explore the model by chatting with it.

1. Use the button at the bottom of the left navigation pane to hide it and give yourself more room to work with.
1. In the **Chat** pane, enter a prompt such as `Who was Ada Lovelace?`, and review the response.

    ![](./media/lab2a(1)-p2t1p6.png)

1. Enter a follow-up prompt, such as `Tell me more about her work with Charles Babbage.` and review the response.

    ![](./media/lab2a(1)-p2t1p7.png)
    
    >**Tip**: Generative AI chat applications often include the conversation history in the prompt; so the context of the conversation is retained between messages. In this case, "her" is interpreted as referring to Ada Lovelace.

## Task 4: Specify instructions

In this task, you'll customize the model's behavior by defining system instructions that control its role, tone, and response boundaries.

1. In the model playground, switch back to the **Chat (1)** tab. Then, at the top-right of the chat pane, use the **New chat (2)** button to restart the conversation and removes the conversation history.

    ![](./media/ai901-l5-1(8).png)

1. In the pane on the left, in the **Instructions** text area, change the system prompt to:

    ```
    You are an expert in the history of computing and AI. You only answer questions about significant people and events in the development of computing, and about notable vintage computers. Do not engage in conversations on any topic that is unrelated to computing history.
    ```

    ![](./media/lab2a(1)-p2t1p1.png)

1. Enter a new prompt, such as `Tell me about ELIZA.` and view the response.

    ![](./media/lab2a(1)-p2t1p2.png)

1. Continue the conversation with prompts such as `How does it compare with modern LLMs?`.

    ![](./media/lab2a(1)-p2t1p3.png)

1. Try asking an "off-topic" question, such as `What's the capital of Spain?`; and view the response.

    ![](./media/lab2a(1)-p2t1p4.png)

## Task 5: Add a web_search tool

In this task, you'll enable the Web Search tool so the model can retrieve current information from the web and provide more up-to-date responses.

1. In the pane on the left, under the instructions, expand the **Tools** section if it isn't already expanded.

1. In the **Add (1)** drop-down list, enable **Web search (2)**. Then read the information about the tool.

    ![](./media/lab2a(1)-p2t1p8.png)

1. In the model playground, at the top right of the chat pane, use the **New chat** button to restart the conversation.

    ![](./media/lab2a(1)-p2t1p9.png)

1. With the *web_search* tool listed in the pane on the left, in the chat pane, enter the prompt `Find a vintage computer store near Seattle` (*or your local city!*) and review the response.

    ![](./media/lab2a(1)-p2t1p10.png)

    The model should have searched the Web for vintage computer stores near the specific city.

## Task 6: Add knowledge

In this task, you'll upload a document as a knowledge source and configure a File Search tool so the model can answer questions using your custom data.

1. Open a new browser tab, and view the **[vintage_computer_identifiers.docx](https://microsoftlearning.github.io/mslearn-ai-fundamentals/data/vintage_computer_identifiers.docx)** at `https://microsoftlearning.github.io/mslearn-ai-fundamentals/data/vintage_computer_identifiers.docx`. We'll use this to provide a knowledge source that the agent can use to identify computers based on serial numbers, product IDs, and other common printed details.

    >**Note:** If the document does not open in your browser, open the link in an InPrivate or Incognito browser window and download the file.

1. Download **vintage_computer_identifiers.docx** to the labvm.

    ![](./media/lab2a(1)-p2t1p11.png)

1.  Return to the browser tab containing the **Agent Playground**. In the **Tools** section, click **Upload files (1)**, then select **browse for files (2)**. In the file picker, open the **Downloads (3)** folder, select the **vintage_computer_identifiers.docx (4)** file, and click **Open (5)**. Wait for the file to be indexed using the default index name. When the indexing process is complete, click **Attach** to add the knowledge index to the agent.

      ![](./media/lab2a(1)-p2t1p12.png)

      ![](./media/lab2a(1)-p2t1p13.png)

1. In the model playground, at the top right of the chat pane, use the **New chat** button to restart the conversation.

1. In the **Chat** tab, enter the prompt `I have a printed circuit board with the "ASSY 250425" on it. What can you tell me about it?` and view the response.

    ![](./media/lab2a(1)-p2t1p14.png)

    This time the response should be informed by the information in the expenses data source.

1. Try a few more prompts - for example, `What kind of computer does a PCB with "820-001A" come from?` or `What about "i386"?`.

    ![](./media/lab2a(1)-p2t1p15.png)

    When there's relevant information in the file, the model will use it to answer. If no information is found, the model will use its own training knowledge or the web_search tool.

## Task 7: Save the model configuration as an agent

In this task, you'll save the configured model as a reusable AI agent that includes its instructions and connected tools.

1. In the model playground, at the top right select **Save as agent (1)**. Then, when prompted, name your new agent `computing-historian` **(2)** and then click on **Create and open playground (3)**.

    ![](./media/lab2a(1)-p2t1p16.png)

    ![](./media/lab2a(1)-p2t1p17.png)

1. In the pane on the right, view the **YAML** tab, which contains the definition for your agent. Note that its definition includes the model, its parameter settings, and the instructions you specified - similar to this:

    ```yml
    metadata:
      logo: Avatar_Default.svg
      microsoft.voice-live.enabled: "false"
    object: agent.version
    id: computing-historian:1
    name: computing-historian
    version: "1"
    description: ""
    created_at: 1784419039
    definition:
      kind: prompt
      model: gpt-5-mini
      instructions: You are an expert in the history of computing and AI. You only answer questions about significant people and events in the development of computing, and about notable vintage computers. Do not engage in conversations on any topic that is unrelated to computing history.
      tools:
        - type: web_search
        - type: file_search
          vector_store_ids:
            - vs_qpRG020jZSewWHPI7B06q2V4
    status: active
    instance_identity:
      principal_id: 0000000-0000000-000000000
      client_id: 0000000-0000000-000000000
    blueprint:
      principal_id: 0000000-0000000-000000000
      client_id: 0000000-0000000-000000000
    blueprint_reference:
      type: ManagedAgentIdentityBlueprint
      blueprint_id: computing-historian-c9996
    agent_guid: c0000000-0000000-000000000
    ```

    ![](./media/lab2a(1)-p2t1p19.png)

1. Switch back to the **Chat** tab, and enter the prompt `Who are you?`

    The response should indicate that the agent is "aware" of its role as a computing historian.

    ![](./media/lab2a(1)-p2t1p18.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="6c0bebb0-789f-4b1a-b8e2-07f5ac7982b2" />

## Task 8: Preview the agent

In this task, you'll preview the published agent in a web-based chat interface and verify that it behaves according to its configured instructions and knowledge.

1. At the top of the chat pane, in the **Preview (1)** drop-down list, select **Preview agent (2)**.

    ![](./media/lab2a(1)-p2t1p20.png)

1. A preview chat interface is opened in a new browser tab.

    ![](./media/lab2a(1)-p2t1p21.png)

1. Enter a prompt, such as `What can you tell me about the Altair 8800?` and view the response from your agent.

    ![](./media/lab2a(1)-p2t1p22.png)

## Task 9: View client code to access the agent in your project

In this task, you'll review the sample client code that connects to your Microsoft Foundry project and interacts with the deployed AI agent using the Azure AI Projects SDK.

1. In the agent playground, switch from the **Chat** tab to the **Call agent** tab, and view the sample code for consuming the agent; which should be similar to this:

    ```python
    # Before running the sample:
    # pip install azure-ai-projects>=2.1.0
    
    from azure.identity import DefaultAzureCredential
    from azure.ai.projects import AIProjectClient
    
    endpoint = "https://ai-resrce.services.ai.azure.com/api/projects/ai-project"
    
    project_client = AIProjectClient(
        endpoint=endpoint,
        credential=DefaultAzureCredential(),
    )
    
    my_agent = "computing-historian"
    my_version = "1"
    
    openai_client = project_client.get_openai_client()
    
    # Reference the agent to get a response
    
    response = openai_client.responses.create(
        input=[{"role": "user", "content": "Tell me what you can help with."}],
        extra_body={"agent_reference": {"name": my_agent, "version": my_version, "type": "agent_reference"}},
    )
    
    print(f"Response output: {response.output_text}")
    ```
    ![](./media/lab2a(1)-p2t1p23.png)

    The code to connect to your agent uses the **Azure.AI.Projects** library to create an **AIProjectClient** object connected to your Foundry project. Since this involves connecting to a project, which may contain privileged resources, key-based authentication is <u>not</u> supported, and the application must use an Entra ID identity to be authenticated.

    After connecting to the project, the code uses the project client's **get_openai_client** method to retrieve an OpenAI client object; with which it can submit prompts to the agent using the same **Responses** API we previously saw being used to chat with a model. Since a project can contain multiple agents and models, the specific agent details are specified as **extra_body** in the **responses.create** method.

## Summary

In this lab, you explored how to deploy and chat with a generative AI model in Microsoft Foundry portal. You then saved the model as an agent with instructions and tools.

The agent explored in this lab is a simple example that demonstrates how quickly and easily you can get started with generative AI app and agent development using Microsoft Foundry. From this foundation, you could build a comprehensive agentic solution in which agents use tools to find information and automate tasks, and collaborate with one another to perform complex workflows.

### Congratulations, you’ve successfully completed the hands-on lab!
