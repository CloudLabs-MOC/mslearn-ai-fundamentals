# Language Translation with Microsoft Foundry

### Estimated Duration: 60 Minutes

## Lab Overview

In this lab, you will use Microsoft Foundry to create a project, deploy a GPT-5 Mini model, and explore its multilingual text-processing capabilities. You will begin by testing translation and transliteration prompts in the Chat Playground to understand how the model can translate text between languages and convert text between writing systems without changing its meaning.

You will then build a Python application using the Azure AI Foundry SDK and connect it to your deployed model. The application will perform translation, transliteration, and language detection tasks. Finally, you will extend the application by adding sentiment analysis, enabling the same deployed model to classify text as Positive, Negative, or Neutral. Through these activities, you will gain hands-on experience using a single generative AI model to perform multiple natural language processing tasks in Microsoft Foundry.

## Lab Objectives

In this exercise, you will perform the following tasks:

- Task 1: Create a Microsoft Foundry project
- Task 2: Deploy a model
- Task 3: Design Translation & Transliteration Prompts in Chat Playground
- Task 4: Build a Translation and Transliteration Application with Foundry SDK
- Task 5: Add Sentiment Analysis to the Application

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

1. After the project is created, the Microsoft Foundry portal will open to a page similar to the one shown below. Locate and copy the **Project Endpoint**, then save it in a text file or Notepad, as it will be required later when configuring the Python application in this lab.

    ![](./media/lab8new-t1p2.png)

    > **Note:** The Microsoft Foundry landing page may vary depending on the version of the portal, your account configuration, or recent UI updates. If your home page looks different, continue with the lab by locating the required menu options using the navigation menu. The appearance of the portal may differ, but the functionality and lab steps remain the same.

    ![](./media/ai901-l5-1(3).png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="e5dc05c2-1c74-47d8-a112-1956348a759a" />

## Task 2: Deploy a model

In this task, you'll deploy the GPT-5 Mini model in Microsoft Foundry and obtain the deployment name required for testing and application integration.

1. Now you're ready to explore models. On the **Discover (1)** page, select the **Models (2)** tab to view the Microsoft Foundry model catalog.

    ![](./media/mod7-t1p5.png)

    >**Note:** Depending on the version of Microsoft Foundry and your portal experience, the **Deployments** menu may appear as **Models**. Both options provide access to model deployments and related management capabilities. If you do not see **Deployments**, select **Models** and continue with the lab instructions.

1. In the **Models** page, enter **`gpt-5-mini`** in the search box **(1)** and select the **gpt-5-mini (2)** model from the search results.

    ![](./media/lab8new-t1p3.png)

1. On the Details Page, select **Custom Deploy** to deploy the model using the recommended default configuration.

    ![](./media/lab8new-t1p4.png)

1. On the **Deploy gpt-5-mini** pane, 

    - Rename the Deployment name to **gpt-5-mini (1)**
    - Set token limit to **100000** **(2)**
    - Click on **Deploy (3)**

    ![](./media/lab8new-t1p4-bd.png)

    > **Note:** Ensure that the model deployment name exactly matches the deployment created in your Azure AI Foundry resource. If the deployment name is incorrect or does not match the lab instructions, the validation will fail.

1. When the model has been deployed, it will open in the model playground.

    ![](./media/lab8new-t1p5.png)

1. Make a note of the **Deployment Name**, as it will be used later in the lab when configuring the Python application.
   
     ![](./media/lab8new-t1p6(1).png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. You will receive a success message. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="a4ce357b-cbb8-44f4-9dba-f135bc47b071" />

## Task 3: Design Translation & Transliteration Prompts in Chat Playground

In this task, you'll use the Chat Playground to create and test translation and transliteration prompts, exploring the model's multilingual text-processing capabilities.

1. Make sure you are on the **Playground** tab of gpt-5-mini.

1. In Chat Playground of **gpt-5-mini**, in the **Instructions** section, copy and paste the following:

    ```
    You are a professional language assistant. You can perform translation (converting text to a different language) and transliteration (converting text to a different script without changing the language). When the user specifies the task and target, respond ONLY with the result - no explanation, no preamble.
    ```

    ![](./media/lab8new-t1p8.png)

1. In the model playground, paste the following prompt **(1)** and click on the **blue arrow (2)** to submit.

    ```text
    Translate to French: The conference begins at 9am tomorrow.
    ```

    ![](./media/lab8new-t1p9.png)

1. Now review the response.

    ![](./media/lab8new-t1p10.png)

1. Similarly you can try the following prompts as well:

    - `Translate to Japanese: Please submit your report by Friday.`
    - `Translate to Portuguese: Welcome to our AI training program.`

1. Click the **New Chat** icon in the upper-right corner of the chat pane to start a new conversation.

    ![](./media/lab8new-t1p11.png)

1. Now test transliteration prompts and observe that only the script changes while the language and meaning remain unchanged:

    ```
    Transliterate to Latin script: مرحبا  
    ```

    Arabic for "Hello" - expected output: Marhaba

    ![](./media/lab8new-t1p12.png)

1. Similarly, test the following transliteration prompts:

    - `Transliterate to Latin script: Привет`

       Russian for "Hello" - expected output: Privet

    - `Transliterate to Latin script: こんにちは`

       Japanese for "Hello" - expected output: Konnichiwa

       ![](./media/lab8new-t1p13.png)

## Task 4: Build a Translation and Transliteration Application with Foundry SDK

In this task, you'll build a Python application using the Azure AI Foundry SDK to perform translation, transliteration, and language detection tasks.

1. Click the **Call model** tab next to the **Chat** tab to view the endpoint details and sample code for calling the deployed model programmatically.

    ![](./media/lab8new-t1p14.png)

1. Scroll down and click **Skip setup with VS Code for the Web** to launch an online VS Code environment in a new tab.

    ![](./media/lab8new-t1p15.png)
 
1. When prompted, leave the default workspace folder name unchanged and press **Enter** to create the workspace.

    ![](./media/lab8new-t1p16.png)

1. Please wait while the environment is being set up. This process may take a few minutes to complete.

    ![](./media/lab8new-t1p17.png)

1. The integrated terminal should open automatically after the environment setup is complete. If it does not appear, open it manually by selecting **Hamburger Menu (1) → View (2) → Terminal (3)**, or press **Ctrl + `** on your keyboard. The terminal will be used to run commands throughout this lab.

    ![](./media/lab8new-t1p18.png)

1. Run the following command in the terminal to install the Azure AI Foundry SDK and authentication libraries required to connect to your Foundry project and interact with the deployed **gpt-5-mini** model from Python:

    ```bash
    pip install --user azure-ai-projects azure-identity
    ```

    >**Note:** Note: If you receive a warning such as `ansible-core requires packaging, which is not installed`, you can safely ignore it for this lab.

1. Now in the **Explorer** pane click on **New File... (1)** icon to create a new file **(2)** named:

    ```text
    translate_foundry.py
    ```

    ![](./media/lab8new-t1p19.png)

1. Copy and paste the following code into **translate_foundry.py**:

      ```python
      import os
      from azure.ai.projects import AIProjectClient
      from azure.identity import DefaultAzureCredential

      # Foundry Connection
      PROJECT_ENDPOINT = "YOUR_TARGET_URI_HERE"
      DEPLOYMENT_NAME = "gpt-5-mini"

      client = AIProjectClient(
         endpoint=PROJECT_ENDPOINT,
         credential=DefaultAzureCredential()
      )

      # Helper Function
      def call_model(system, user, max_tokens=500, temperature=0.1):
         openai_client = client.get_openai_client()

         response = openai_client.chat.completions.create(
            model=DEPLOYMENT_NAME,
            messages=[
                  {"role": "system", "content": system},
                  {"role": "user", "content": user}
            ],
            max_completion_tokens=max_tokens
         )

         return response.choices[0].message.content.strip()

      # Translation
      def translate(text, target_lang):
         return call_model(
            system="You are a translation assistant. Respond ONLY with the translated text.",
            user=f"Translate to {target_lang}: {text}"
         )

      # Transliteration
      def transliterate(text, target_script="Latin"):
         return call_model(
            system=(
                  "You are a transliteration assistant. "
                  "Transliteration changes only the writing script. "
                  "Do not translate the text."
            ),
            user=f"Transliterate to {target_script} script: {text}"
         )

      # Language Detection
      def detect_and_translate(text):
         return call_model(
            system="You are a language detection and translation assistant.",
            user=(
                  f"Identify the language of this text and translate it to English.\n\n"
                  f"Text: {text}"
            )
         )

      print("=" * 60)
      print("Lab 3C - Translation and Transliteration")
      print("=" * 60)

      # Translation Tests
      translations = [
         ("Good morning, how are you today?", "Spanish"),
         ("The meeting has been rescheduled.", "French"),
         ("Azure AI Foundry is the future of AI.", "Japanese")
      ]

      print("\n--- Translation Tests ---")

      for text, lang in translations:
         result = translate(text, lang)
         print(f"\nOriginal: {text}")
         print(f"Translated: {result}")

      # Transliteration Tests
      translit_tests = [
         ("مرحبا", "Latin"),
         ("Привет", "Latin"),
         ("こんにちは", "Latin")
      ]

      print("\n--- Transliteration Tests ---")

      for text, script in translit_tests:
         result = transliterate(text, script)
         print(f"\nOriginal: {text}")
         print(f"Transliterated: {result}")

      # Language Detection
      unknowns = [
         "Bonjour, comment allez-vous?",
         "Guten Morgen, wie geht es Ihnen?",
         "Buenos dias, me llamo Juan."
      ]

      print("\n--- Language Detection ---")

      for text in unknowns:
         result = detect_and_translate(text)
         print(f"\nInput: {text}")
         print(result)
      ```

      ![](./media/lab8new-t1p20.png)

1. Update the following placeholders with the values you noted earlier from Microsoft Foundry:

    - **PROJECT_ENDPOINT** = `"YOUR_TARGET_URI_HERE"`
    - **DEPLOYMENT_NAME** = `"gpt-5-mini"`

       ![](./media/lab8new-t1p21.png)

       >**Note:** Replace `YOUR_TARGET_URI_HERE` with your copied Project Endpoint. If your deployed model uses a different Deployment Name, replace `gpt-5-mini` with that exact deployment name. Using an incorrect endpoint or deployment name will prevent the application from connecting to the model successfully.

1. Run the application by using the following command in the terminal:

    ```bash
    python translate_foundry.py
    ```

1. Verify the translation results.

    ![](./media/lab8new-t1p22.png)

## Task 5: Add Sentiment Analysis to the Application

In this task, you'll extend the application by adding sentiment analysis functionality, enabling the model to classify text as Positive, Negative, or Neutral

1. Open the **translate_foundry.py** file created in the previous task.

1. Add the following function below the existing code. This function uses the deployed gpt-5-mini model to perform sentiment analysis and classify the input text as Positive, Negative, or Neutral.

      ```python
      def analyze_sentiment(text):
         """Classify sentiment as Positive, Negative, or Neutral."""
         return call_model(
            system="Respond only with: Positive, Negative, or Neutral.",
            user=text,
            max_tokens=200
         )
      ```

     ![](./media/lab8new-t1p23.png)

1. Add the following test code below the existing application. This code demonstrates a simple translation and sentiment analysis pipeline by translating each input sentence into Spanish and then analyzing its sentiment using the gpt-5-mini model.

      ```python
      # Translation + Sentiment Analysis Pipeline

      pipeline_tests = [
         "I love this product, it works perfectly!",
         "The service was terrible and very slow.",
         "The package arrived on Tuesday."
      ]

      print("\n--- Translation + Sentiment Pipeline ---")

      for text in pipeline_tests:
         translated = translate(text, "Spanish")
         sentiment = analyze_sentiment(text)

         print(f"\nOriginal  : {text}")
         print(f"Spanish   : {translated}")
         print(f"Sentiment : {sentiment}")
      ```

      ![](./media/lab8new-t1p24.png)

1. Run the application again using the following commnad:

    ```bash
    python translate_foundry.py
    ```

1. Review the output generated by the sentiment analysis function.

    ![](./media/lab8new-t1p25.png)

## Summary

In this lab, you created a Microsoft Foundry project and deployed a GPT-5 Mini model for text-processing tasks. You used the Chat Playground to design and test prompts for translation and transliteration, observing how the model can both translate text into different languages and convert text between writing systems while preserving meaning.

You then built a Python application using the Azure AI Foundry SDK and connected it to your deployed model. The application was used to perform translation, transliteration, and language detection tasks. Finally, you enhanced the application by adding sentiment analysis, allowing the model to classify text as Positive, Negative, or Neutral. This lab demonstrated how a single deployed generative AI model can support multiple natural language processing scenarios through effective prompt engineering and application integration

### You've successfully completed the hands-on lab!