# Module 08: Use Conversational Language Understanding with Language Studio

## Lab overview
Increasingly, we expect computers to be able to use AI to understand natural language commands, either spoken or typed. For example, you might want a home automation system to control devices in your home by using voice commands such as “switch on the light” or “put the fan on.” AI-powered devices can understand these commands and take appropriate action.

In this exercise, you will use Language Studio to create and test a project that sends instructions to devices such as lights or fans. You’ll use the capabilities of the Conversational Language Understanding service to configure your project. 

## Lab objectives

In this lab, you will perform:

- Task 1: Create a *Language* resource
- Task 2: Create a Conversational Language Understanding App
- Task 3: Create intents, utterances, and entities
- Task 4: Train the model
- Task 5: Deploy and test the model

## Estimated timing: 45 minutes

## Architecture Diagram
![Select add under Intents on the Build Schema pane.](media/arch8.PNG)

## Exercise 1: Use Conversational Language Understanding with Language Studio

### Task 1: Create a *Language* resource

In this task, you will learn how to create a **Language** resource in Azure to unlock advanced natural language processing capabilities for text analysis and AI-driven insights.

You can use many Azure AI Language features with either a **Language** or **Azure AI services** resource. There are some instances where only a Language resource can be used. For the exercise below, we will use a **Language** resource. If you haven't already done so, create a **Language** resource in your Azure subscription.

1. In the azure portal, Click the **&#65291;Create a resource** button.

   ![An image of the text in the image outlined](media/lab-5(1).png)

1. In the Marketplace page search for **Language service (1)** and Select **Language service (2)**.

   ![An image of the text in the image outlined](media/lab-6(1).png)

1. You will be taken to a page to *Select additional features*. Keep the default selection and click **Continue to create your resource**. 

1. On the page **Create Language**, configure it with the following settings:
    - **Subscription (1)**: *Your Azure subscription*.
    - **Resource group (2)**: **AI-900-Module-08-<inject key="DeploymentID" enableCopy="false" />**
    - **Region (3)**: Select **East US**
    - **Name (4)**: Enter **Conversational<inject key="DeploymentID" enableCopy="false" />**
    - **Pricing tier (5)**: *Free F0* (if Free F0 is not available, select *S*)
    - **By checking this box I certify that I have reviewed and acknowledge the terms in the Responsible AI Notice. (6)**: *Selected*.

      ![An image of the text in the image outlined](media/lab-5(1)n.png)   

1. Select **Review + create (7)** then **Create** and wait for deployment to complete.

### Task 2: Create a Conversational Language Understanding App

In this task, you will learn how to create a **Conversational Language Understanding (CLU)** app to build intelligent conversational agents that can understand and process natural language input.

To implement natural language understanding with Conversational Language Understanding, you create an app; and then add entities, intents, and utterances to define the commands you want the app to execute.

1. In a new browser tab, open the Language Studio portal at [https://language.azure.com](https://language.azure.com?azure-portal=true) and sign in using the Microsoft account associated with your Azure subscription.

1. If prompted to choose a Language resource, select the following settings, and select **Done**:
   
    - **Azure directory (1)**: *The Azure directory containing your subscription*.
    - **Azure subscription (2)**: *Your Azure subscription*.
    - **Resource type (3)**: *Language*.
    - **Resource name (4)**: *select the Language service resource you just created*

    ![Creating a Language Service resource with custom question answering enabled.](media/mod7-01a.png)

   If you are ***not*** prompted to choose a language resource, it may be because you have multiple Language resources in your subscription; in which case:
    1. On the bar at the top of the page, select **Settings (&#9881;)**.
    2. On the **Settings** page, view the **Resources** tab.
    3. Select the language resource you just created, and make sure the managed identity tab is **enabled.**.
    4. At the top of the page, select **Language Studio** to return to the Language Studio home page.

1. At the top of the portal, select **Create new** menu, and select **Conversational language understanding**.

    ![Select add under Intents on the Build Schema pane.](media/lab8(1).png)
   
1. In the **Create a project** dialog box, on the **Enter basic information** page, enter the following details and select **Next**:  

   - **Name**: **Project<inject key="DeploymentID" enableCopy="false" />** **(1)**  
   - **Utterances primary language**: *English (US)* **(2)**  
   - **Enable multiple languages in project**: **Do not select** **(3)**  
   - **Description**: `Simple home automation` **(4)**  
   
      Click **Next** **(5)**  
   
      ![Select add under Intents on the Build Schema pane.](media/LAB8.png)  

   > **Tip**: Make a note of your *project name*, as you will need it later.  

   > **Note:** It may take approximately **15-20 minutes** for the **Utterances Primary Language** list to appear.  

1. On the **Review and finish** page, select **Create**. 
  
### Task 3: Create intents, utterances, and entities

In this task, you will learn how to create intents, utterances, and entities in your **Conversational Language Understanding (CLU)** app to train it to recognize user inputs and respond appropriately.

An *intent* is an action you want to perform - for example, you might want to switch on a light, or turn off a fan. In this case, you'll define two intents: one to switch on a device, and another to switch off a device. For each intent, you'll specify sample *utterances* that indicate the kind of language used to indicate the intent.

1. In the **Schema definition** pane, ensure that **Intents** is selected then select **+ Add**

    ![Select add under Intents on the Build Schema pane.](media/lab8(3).png)

1. Add an intent with the name `switch_on` (in lower-case) and select **Add intent**.

1. Select the **switch_on** intent. It will take you to the **Data labeling** page. In the **Intent** drop down, select **switch_on**.
   
    ![Select add under Intents on the Build Schema pane.](media/lab8(4).png)

1. Next to the **switch_on** intent, type the utterance `turn the light on` and press **Enter** to submit this utterance to the list.

1. The language service needs at least five different utterance examples for each intent to sufficiently train the language model. Add five more utterance examples for the **switch_on** intent:  
    - `switch on the fan`
    - `put the fan on`
    - `put the light on`
    - `switch on the light`
    - `turn the fan on`

        ![Select add under Intents on the Build Schema pane.](media/lab8(5).png)

1. On the **Activity pane** on the right-hand side of the screen, select **Labels**, then select **+ Add entity**.

    ![Select add under Intents on the Build Schema pane.](media/lab8(6).png)

1.  Type `device` (in lower-case), select **List** and select **Add entity**.

    ![Select add under Intents on the Build Schema pane.](media/lab88.png)

1. In the ***turn the fan on*** utterance, highlight the word "fan". Then in the list that appears, in the *Search for an entity* box select **device**.

    ![Select add under Intents on the Build Schema pane.](media/lab8(8).png)

1. Do the same for all the utterances. Label the rest of the *fan* or *light* utterances with the **device** entity. When you're finished, verify that you have the following utterances and make sure to select **Save changes**:

    | **intent** | **utterance** | **entity** |
    | --------------- | ------------------ | ------------------ |
    | switch_on   | put the fan on     | Device - *select fan* |
    | switch_on   | put the light on    | Device - *select light* |
    | switch_on   | switch on the light | Device - *select light* |
    | switch_on   | turn the fan on     | Device - *select fan* |
    | switch_on   | switch on the fan   | Device - *select fan* |
    | switch_on   | turn the light on   | Device - *select light* |

    ![Select add under Intents on the Build Schema pane.](media/lab8(9).png)

1. In the pane on the left, select **Schema definition** and verify that your **switch_on** intent is listed. Then select **+ Add** and add a new intent with the name `switch_off` (in lower-case).

    ![Select add under Intents on the Build Schema pane.](media/lab8(10).png)

1. Select the **switch_off** intent. It will take you to the **Data labeling** page. In the **Intent** drop down, select **switch_off**. Next to the **switch_off** intent, add the utterance `turn the light off`.

1. Add five more utterance examples to the **switch_off** intent.
    - `switch off the fan`
    - `put the fan off`
    - `put the light off`
    - `turn off the light`
    - `switch the fan off`

1. Label the words *light* or *fan* with the **device** entity. When you're finished, verify that you have the following utterances and make sure to select **Save changes**:  

    | **intent** | **utterance** | **entity** | 
    | --------------- | ------------------ | ------------------ |
    | switch_off   | put the fan off    | Device - *select fan* | 
    | switch_off   | put the light off  | Device - *select light* |
    | switch_off   | turn off the light | Device - *select light* |
    | switch_off   | switch the fan off | Device - *select fan* |
    | switch_off   | switch off the fan | Device - *select fan* |
    | switch_off   | turn the light off | Device - *select light* |

   ![Select add under Intents on the Build Schema pane.](media/lab8(11).png)
   
### Task 4: Train the model

In this task, you will learn how to train the model in your **Conversational Language Understanding (CLU)** app to improve its ability to recognize and understand user intents, utterances, and entities.

Now you're ready to use the intents and entities you have defined to train the conversational language model for your app.

1. On the left-hand side of Language Studio, select **Training jobs**, then select **+ Start a training job**.
   
   ![Select add under Intents on the Build Schema pane.](media/lab8(12).png)
   
1. Use the following settings:
    - **Train a new model**: **Train<inject key="DeploymentID" enableCopy="false" />**
    - **Training mode**: Standard training (free)
    - **Data Splitting**: *select Automatically split the testing set from the training data, keep default percentages*
    - Select **Train** at the bottom of the page.

        ![Select add under Intents on the Build Schema pane.](media/lab8(13).png)
   
1. Wait for training to complete.

### Task 5: Deploy and test the model

In this task, you will learn how to deploy and test the model in your **Conversational Language Understanding (CLU)** app to ensure it functions correctly and responds accurately to user inputs.

To use your trained model in a client application, you must deploy it as an endpoint to which the client applications can send new utterances; from which intents and entities will be predicted.

1. On the left-hand side of Language Studio, select **Deploying a model (1)**, and select **Add deployment (2)**.

    ![Select add under Intents on the Build Schema pane.](media/lab8(14).png)

1. Use these settings:
    - **Create or select an existing deployment name**: **Deploy<inject key="DeploymentID" enableCopy="false" />**
    - **Assign trained model to your deployment name**: *Select the name of the trained model*.
    - Select **Deploy**

        > **Tip**: Note your *deployment name*, you will use it later.    

        ![Select add under Intents on the Build Schema pane.](media/lab8(15).png)
   
1. When the model is deployed, select **Testing deployments** on the left-hand side of the page, and then select your deployed model under **Deployment name**.

1. Enter the following text, and then select **Run the test**:

    `switch the light on`

    Review the result that is returned, noting that it includes the predicted intent (which should be **switch_on**) and the predicted entity (**device**) with confidence scores that indicate the probability the model calculated for the predicted intent and entity. The JSON tab shows the comparative confidence for each potential intent (the one with the highest confidence score is the predicted intent)

    ![](media/results(1).png)

1. Clear the text box and test the model with the following utterances under *Enter your own text, or upload a text document*:
    
    - `turn off the fan`
    - `put the light on`
    - `put the fan off`

You have now successfully configured a conversational language project and defined entities, intents, and utterances. You have seen how to train and deploy a model in the Language Studio. And you have tried it out with both utterances you defined, and some that you did not explicitly define but the model was able to determine.

> **NOTE**: Conversational language understanding provides the intelligence to interpret the intention of the input; it doesn't perform any actions such as turning on the light or the fan. A developer would need to build an application that uses the Conversational Language Understanding model to determine the user's intent, and then automate the appropriate action.

## Validation

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. you will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="1c8ee6fe-9783-45b7-9293-38c9766a4fb2" />

## Learn more

This app shows only some of the capabilities of the Conversational Language Understanding feature of the Language service. To learn more about what you can do with this service, see the [Conversational Language Understanding page](https://docs.microsoft.com/azure/cognitive-services/language-service/conversational-language-understanding/overview).

### Review

In this lab, you have completed the following tasks:
- Created a *Language* resource
- Created a Conversational Language Understanding App
- Created intents, utterances, and entities
- Trained the model
- Deployed and tested the model
  
## You have successfully completed this lab.
