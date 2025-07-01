
# Module 06: Analyze text in the Azure AI Foundry portal

## Lab overview

Natural Language Processing (NLP) is a branch of AI that deals with written and spoken language. You can use NLP to build solutions that extract semantic meaning from text or speech, or that formulate meaningful responses in natural language.

Azure AI Language service includes Text Analytics, with capabilities such as entity recognition, key phrase extraction, summarization, and sentiment analysis. For example, suppose the fictitious travel agent Margie's Travel encourages customers to submit reviews for hotel stays. You could use the Language service to extract named entities, identify key phrases, summarize text, and more.

In this exercise, you will use Azure AI Language in Azure AI Foundry portal, Microsoft's platform for creating intelligent applications, to analyze hotel reviews. 

## Lab objectives

In this lab, you will perform:
- Task 1: Create a project in the Azure AI Foundry portal
- Task 2: Extract named entities with Azure AI Language in the Azure AI Foundry portal
- Task 3: Extract key phrases with Azure AI Language in the Azure AI Foundry portal
- Task 4: Summarize text with Azure AI Language in the Azure AI Foundry portal

## Task 1: Create a project in the Azure AI Foundry portal

In this task, we are creating an Azure AI Foundry project and configuring the necessary resources to explore AI language capabilities in the Language Playground.

1. On the Azure Portal page, in the Search resources, services, and docs (G+/) box at the top of the portal, enter **Azure AI Foundry (1)**, and then select **Azure AI Foundry (2)** under **Services**.

    ![](./media/lab6-1.png) 

1. In the left navigation pane for the AI Foundry, select **AI Hubs (2)** under **Use with AI Foundry (1)**. On the AI Hubs page, click on **+ Create** and select **Hub (3)** from the drop-down.

    ![](./media/lab6-2.png) 

1. On the **Create an AI hub resource** pane, enter the following details:

    - Subscription : **Leave default subscription** 
    - Resource Group : Select **AI-900-Module-06 (1)** 
    - Region : **<inject key="Region" enableCopy="false"></inject>** Use the same location as the resource group **(2)**
    - Name : Use the format **Myhub-<inject key="Deployment ID" enableCopy="false"></inject> (3)** 
    - Connect AI Services incl. OpenAI : Click on **Create New (7)**
    - Create new Azure AI Services: Provide a name to the AI Service,Use the format **AI<inject key="Deployment ID" enableCopy="false"></inject> (8)**  
    - Click on **Save (9)**.
    - Click on **Review + Create (10)**

       ![](./media/lab6-3(1).png) 

1. Click on the **Create** button to begin the deployment process.

1. Right-click on the [Azure AI Foundry](https://ai.azure.com?azure-portal=true) **(1)** link, select **Copy link (2)** from the context menu, then paste it into a new tab to access the Azure AI Foundry portal.

   ![](./media/3-27.png)

1. On the Welcome to Azure AI Foundry page, Click on **Sign in** in the top right corner.

   ![](./media/17-18.png)

1. If prompted to sign in, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject> **(1)** and click on **Next (2)**.
 
      ![Enter Your Username](./media/19-4(1).png)
 
   - **Password:** <inject key="AzureAdUserPassword"></inject> **(1)** and click on **Next (2)**.
 
     ![Enter Your Password](./media/19-5(1).png)

1. If prompted to stay signed in, you can click **No**.

   ![](./media/9-8(1).png)

1. If prompted with *Streamlined from the start*, click on **Got it** to proceed.

   ![](./media/3-23.png)

1. Close any tips or quick start panes that are opened the first time you sign in, and if necessary use the **Azure AI Foundry** logo at the top left to navigate to the home page, which looks similar to the following image (close the **Help** pane if it's open)

1. In the browser, navigate to `https://ai.azure.com/managementCenter/allResources` and select **Create new**.

1. Choose the option to create a **AI hub resource (1)** then select **Next (2)**.

   ![](./media/lab3-20.png)

1. In the **Create a new project** wizard, enter project name **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)**, and select newly created **Myhub<inject key="DeploymentID" enableCopy="false" /> (2)** and select **Create (3)**.

    ![](./media/lab6-5(1).png)

1. Wait for your project created.

1. When the project is created, you will be taken to an **Overview** page of the project details.

   ![](./media/lab6-6(1).png)

1. From the left-hand navigation menu, click on **AI Services**.

   ![Navigation showing AI Services in Azure AI Foundry](./media/upd-1.1.png)

1. Under the **"Infuse your solutions with AI capabilities"** section, click on the **Language + Translator** tile.

    ![Language + Translator tile under AI capabilities](./media/upd-1.2.png)

1. On the **Explore Language capabilities**, under the **Extract Information** tab, select **Extract named entities**.

    ![Extract named entities option in Language capabilities](./media/upd-1.3.png)

1. You will be prompted to create a new AI Services resource.

   - Choose the **Region** matching your Foundry project.
   - Provide a **Name** for the resource (e.g., `AI_Connection`).
   - Click **Create and connect** to link this resource to your project.
   
      ![Create and connect AI Services resource dialog](./media/upd-1.4.png)

1. Wait for the AI Services resource to be created.

1. On the left-hand menu on the screen, select **Playgrounds**.

   ![](./media/lab6-7.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="07c3e734-e32f-44b6-b8e8-7b5b85f4a45b" />

### Task 2: Extract named entities with Azure AI Language in the Azure AI Foundry portal

This task demonstrates how to use Azure AI Language Playground for Named Entity Recognition (NER). By analyzing a hotel review, Azure AI extracts key entities like locations, dates, and organizations, along with confidence scores. 

*Named entities* are words that describe people, places, and objects with proper names. Let's use the named entity extraction capability of Azure AI Language to identify types of information in a review.

1. Navigate to **Playgrounds** from the left pane, Under **Language playground** tile select **Try the Language playground**.

    ![](./media/18-1.png)

1. In the Language playground, select **Extract information (1)**. Then select the **Extract named entities (2)** tile. 

   ![](./media/3-25.png)

1. Under **Sample**, copy and paste the following review:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

   ![](./media/6-1.png)
   
1. Click **Run** to process the text.

   ![](./media/6-2.png)

2. Review the output and observe the **Details** section, where the extracted entities are accompanied by additional information such as type and confidence scores. The confidence score indicates the probability that the identified type correctly belongs to the specified category.

   ![](./media/18-3.png)

## Task 3: Extract key phrases with Azure AI Language in the Azure AI Foundry portal

This task demonstrates how to use Azure AI Language Playground for key phrase extraction. By analyzing a hotel review, Azure AI identifies important phrases that summarize the text's main points. 

*Key phrases* are the most important pieces of information in the text. Let's use the key phrase extraction capability of Azure AI Language to pull important information from a review.

1. In the Language playground, select **Extract information (1)**. Then select the **Extract key phrases (2)** tile. 

   ![](./media/6-3.png)

1. Under **Sample**, copy and paste the following review:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

   ![](./media/6-4.png)

1. Click **Run** to process the text.

   ![](./media/6-5.png)

1. Review the output and observe the different phrases extracted in the **Details** section. These phrases should represent key elements that contribute the most to the overall meaning of the text.

   ![](./media/6-6.png)

## Task 4: Summarize text with Azure AI Language in Azure AI Foundry portal

In this task, we are using Azure AI Language to generate an extractive summary by identifying key sentences from a hotel review.
 
1. Let's look at Azure AI Language's summarization capabilities. In the Language playground, select **Summarize information (1)**, then select the **Summarize text (2)** tile.

   ![](./media/6-7.png)

1. Under **Sample**, copy and paste the following review:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

   ![](./media/6-8.png)

1. Click **Run** to process the text.

   ![](./media/6-9.png)

1. Review the output and observe that the *Extractive summary* in the **Details** section provides rank scores for the most significant sentences, highlighting their relevance to the overall text.  

   ![](./media/6-10.png)

### Review
In this exercise, you have completed the following tasks:
- Created a project in the Azure AI Foundry portal
- Extracted named entities with Azure AI Language in the Azure AI Foundry portal
- Extracted key phrases with Azure AI Language in the Azure AI Foundry portal
- Summarized text with Azure AI Language in the Azure AI Foundry portal 

## Learn more

To learn more about what you can do with this service, see the [Language service page](https://learn.microsoft.com/azure/ai-services/language-service/overview).

## You have successfully completed this lab.
