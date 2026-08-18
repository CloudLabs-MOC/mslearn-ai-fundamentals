# Lab: Explore retrieval augmented generation (RAG)

### Please be aware that no Lab VM is provided for this lab. You will need to complete the lab on your personal computer.

## Lab Overview

In this lab, you'll explore retrieval augmented generation (RAG) by using a chat playground to interact with a generative AI model. You will start by testing a model's ability to answer general questions about expense policies, then you'll upload an expense policy document to provide the model with specific company knowledge. By comparing the model's responses before and after adding this knowledge source, you'll see how RAG improves the accuracy and relevance of AI-generated answers by grounding responses in real organizational data. This hands-on experience demonstrates how knowledge sources enhance generative AI models to provide more accurate, context-specific information.

## Lab Objectives

In this lab, you will complete the following task:

- Task 1: Chat with a model
- Task 2: Add a knowledge source

### Estimated timing: 15 Minutes

## Task 1: Chat with a model

In this task, you will interact with a generative AI model using the Chat Playground. You'll configure the model with system instructions that define its purpose as an advisor on business expense policies, and then submit questions about expense claims. This will allow you to observe how the model responds to questions based only on its training data, before we enhance it with a knowledge source.

> **Note**: If your browser supports WebGPU, the chat playground uses the *Microsoft Phi 3.5 Mini* model running on your computer's GPU. If not, the model runs on CPU - with reduced response-generation quality. If *that* fails, a basic mode with no model and responses retrieved from Wikipedia is activated. Performance may vary depending on the available memory in your computer and your network bandwidth to download the model. After opening the app, use the **?** (*About this app*) icon in the chat area to find out more.

1. In a web browser, open the **[Chat Playground](https://aka.ms/chat-playground)** at `https://aka.ms/chat-playground`.
1. Wait for the model to download and initialize.

    The first time you download a model, it may take a few minutes. Subsequent downloads will be faster.

    > **Tip**: If the model is taking a *very* long time to load, you can cancel and start in ***Basic*** mode. You can switch between available models at any time in the **Model** list; but on older or lower-spec computers, you may have a better experience in basic mode.

    When ready, the Chat Playground looks like this:

    ![Screenshot of the chat playground.](./media/gen-ai-01.png)

    > **Tip**: You can switch between *light* and *dark* themes using the &#x263C; / &#x263E; toggle at the top right.

1. In the pane on the left, in the **Instructions** text area, change the model's instructions to `You are an AI assistant that provides succinct answers to business expense-related questions.`

    > **Tip**: Instructions, sometimes known as a *system prompt*, are used to provide the model with an overall context for its responses. You can use the system prompt to provide guidelines about format, style, and constraints about what the model should and should not include in its responses.

1. In the chat pane, enter the prompt `Tell me about per-diem allowances.` and review the response.

    ![Screenshot of a prompt and response.](./media/expenses_prompt.png)

1. Now try a follow-up question: `How are they reimbursed?`

    > **Tip**: Generative AI chat applications often include chat history in the prompt; so the context of the conversation is retained between messages (for example, in the follow-up prompt *How are they reimbursed?*, "they" is interpreted as relating to per-diem allowances).<br><br>In *Basic* mode, the conversation history is not retained; so the follow up prompt results in a new Wikipedia query.

    So far, the model has successfully answered some general questions related to expense claims based on the data it was trained with.

1. In the chat playground, at the top of the chat pane, use the **New chat** (&#128172;) button to restart the conversation.
1. Enter the prompt `If I take a taxi to meet a customer, how much can I claim for it?` and review the response.

    ![Screenshot of a prompt and response.](./media/expenses_prompt_no_context.png)

    The model responds with a general answer (in *Basic* mode, it may be completely unrelated to expense claims).

    If we want to use the model to power an agent that advises employees in an organization about expense claims, it needs more specific knowledge of the organization's expense policies.

    Let's fix that.

## Task 2: Add a knowledge source

In this task, you will upload an expenses policy document to the chat playground, implementing a retrieval augmented generation (RAG) approach. You will then ask the model the same questions about expense claims and observe how its responses now include information grounded in the specific expense policy document. You will also see how the model provides citations to show where the information came from, demonstrating the key advantage of RAG: providing accurate, sourced answers based on organizational knowledge.

1. Open a new browser tab, and view the **[expenses guide](https://aka.ms/expenses-txt)** at `https://aka.ms/expenses-txt`. We'll use this to ground the model, so it has some context for questions about expenses.

    > **Tip**: This is a very small document for the purposes of this exercise. In a real scenario, an AI agent might have access to large volumes of data spread across multiple sources.

1. Save the **expenses.txt** file on your local computer.

1. Return to the tab containing the chat playground, and in the pane on the left, in the **Tools** section, add select **Upload files**.

1. Upload the **expenses.txt** file. After it's been been uploaded, it's listed in the **Tools** section and the chat is automatically restarted.

1. Enter the prompt `If I take a taxi to meet a customer, how much can I claim for it?` and view the response.

    This time the response should be informed by the information in the expenses data source.

    ![Screenshot of the chat playground using the file search tool.](./media/expenses_prompt_with_context.png)

    Note that the response includes a citation for the source of the information (the *expenses.txt* file you uploaded).

1. Try more expense-related prompts, such as `Can I buy the customer lunch?` or `What is a purchase order?` and verify that the uploaded file is referenced if any relevant context is found in it, but not if a search of the file returned no relevant information for the prompt.

    > **Tip**: When you uploaded the file, a simple keyword index was created. You can select the file icon to view this index. In a real-world RAG solution, the index would be more comprehensive and most likely be vector-based and support *semantic* matching in addition to *keyword* matching.

## Summary

In this exercise, you explored a generative AI model in a chat playground, and saw how a model's responses can be affected by adding a knowledge source that provides additional content in a RAG implementation.

The interface and techniques used in this exercise are similar to those in Microsoft Foundry portal; a platform for building AI apps and agents in the Microsoft Azure cloud. Additionally, Foundry includes *Foundry IQ*; a managed knowledge layer that makes it easier to build enterprise-scale RAG solutions with multiple, shared knowledge stores.
