# Module 12: Explore generative AI with Copilot

## Lab overview

In this exercise, you will explore generative AI with Bing Copilot. 

## Lab objectives
In this lab, you will perform:
- Using AI with Bing Copilot prompts to generate responses
- Trying image generation using AI with Bing Copilot
- Trying code generation using AI with Bing Copilot
  
## Estimated timing: 30 minutes

## Architecture Diagram

  ![](media/module05new.png)

## Exercise 1: Explore generative AI with Copilot

1. In  another browser tab,open [copilot.microsoft.com](https://copilot.microsoft.com?azure-portal=true)

   - **Username:** odl_user_<inject key="DeploymentID" enableCopy="false" />@outlook.com

   - **Password**: <inject key="AzureAdUserPassword"></inject>

   >**Note**: While you can sign in with your work or school account, you will see a slightly different user experience compared to signing in with your personal account. Using your work or school account, you will see Bing Enterprise chat. 

1. Select **Chat** . Chat brings you to Bing Copilot, which uses generative AI to power search results. What this means is that unlike search alone, which returns existing content, Bing Copilot can put together new responses based on natural language modeling and the web's information.  

      ![](media/lab12-01.png)

1. If asking for accepting **Terms of Use** then click on **Continue**.

      ![](media/co.png)
    
1. Towards the bottom of the screen, you will see a window **Ask me anything...**. As you enter prompts into the window, Bing Copilot uses the entire conversation thread to return responses. For example, let's try asking a series of questions about traveling. 

     ![](media/lab12-02.png)

### Task 1: Use prompts to generate responses

1. Type in a prompt: `What are 3 pros and cons of traveling in the winter?`. You will see a **Searching for:...** and **Generating...** appear before the response. The model uses the searched for responses as grounding information to generate original responses. Notice that the end of the response contains links to its sources. 

   ![A screenshot of Bing copilot's response to a traveling prompt with three bullets for pros and three bullets for cons.](./media/lab12-03.png) 

   > **Note**: If you do not see a **Generating...** message or a bullet list response, you have not gotten to see Bing Copilot in action yet. You need to return to the sign-in menu and connect the current account you are using with a personal account. 

1. Type in a prompt: `Find me 3 more pros`. What you mean with this prompt is that you would like to see 3 more positive reasons for traveling in the winter that have not already been listed. Notice that with this prompt, you are asking Bing Copilot to do two things that search alone does not do: use the previous chat response to exclude what's returned in the new response, and use the previous chat's topic without explicitly stating it. 

1. Type in a prompt: `Where are 3 places I can go to find fewer crowds?`. 

   >**Note**: Notice that while Bing Copilot is able to give a related response, it can drop earlier **memories** of the conversation thread as it continues. As a result, the responses you get may not be directly related to traveling in the winter. This is largely to do with token input limitations. When chat **remembers** earlier parts of a conversation, it is because it has saved a certain amount of tokens from the conversation. As new tokens are introduced via your new prompts and responses, chat will let go of older tokens. 

1. The **New Topic** button next to the chat window is useful Bing Copilot to clear the previous conversation thread so your new topic responses are not based on the previous topic. Use the **New Topic** icon next to the chat window to clear your message history. 

     ![](media/ai900img12.1.png)

### Task 2: Try image generation

1. Now let's see an example of image generation. Type in a prompt: `Create an image of an elephant eating a hamburger`. Notice that a message **I'll try to create that...** appears before Bing Copilot returns a response. 

    ![](media/lab12-05.png)

   > Importantly, notice that the response may look similar but not the same. This is because responses are varied.  

1. In the response, there is text at the bottom that reads **Powered by DALL-E**. Consider how DALL-E is based on large language models as your natural language input generates images. 

1. Return to **Bing Copilot's chat** by clicking on the Microsoft Bing icon on the top right corner of the screen. 

### Task 3: Try code generation

1. Now's let's see an example of code generation and translation. Type in a prompt: `Use Python to create a list`. 

    ![A screenshot of elephants eating hamgburgers.](./media/lab12-06.png)

    > Importantly, notice that the response may look similar but not the same. This is because responses are varied.  

1. Type in the prompt: `Translate that into C#`. Notice how you did not need to specify what "that" is as Bing Copilot knows to refer to the conversation history. 

   ![](media/lab12-09.png)

    > Importantly, notice that the response may look similar but not the same. This is because responses are varied.  

### Task 4: Bonus 

1. Type in a prompt: `What are 3 examples of generative AI helping people?`. You can use this as a way to brainstorm your own copilot ideas!  

   ![](media/lab12-08.png)

    > Importantly, notice that the response may look similar but not the same. This is because responses are varied.  
   
## Learn more

This simple search index only some of the capabilities of the AI with Bing. To learn more about what you can do with this service, see the [Explore generative AI with Copilot](https://learn.microsoft.com/en-us/training/modules/explore-generative-ai-copilot-bing/).

### Review
In this lab, you have completed:
- Created outlook account.
- Used AI with Bing Copilot prompts to generate responses
- Tried image generation and code generation AI with Bing Copilot.

## You have successfully completed this lab.
