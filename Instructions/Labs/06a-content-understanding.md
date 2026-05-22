# Get started with information extraction in Microsoft Foundry

### Estimated Duration: 30 Minutes

## Lab overview

In this lab, you will explore how to use Microsoft Foundry and Azure Content Understanding to extract structured information from business documents. You will create a Foundry project, test different Content Understanding analyzers such as **Read**, **Layout**, and **Document fields**, and analyze invoice documents in the Foundry portal. You will also review the extracted fields and JSON output, and learn how document analysis can be performed programmatically using REST APIs and the Python SDK. This lab demonstrates how AI-powered document analysis can automate information extraction from unstructured content.

## Lab objectives

In this exercise, you will perform:

- Task 1: Create a Microsoft Foundry project
- Task 2: Extract information from documents in the new Foundry portal
- Task 3: Understand how to extract content with the REST API
- Task 4: Understand how to extract content with the Python SDK

## Task 1: Create a Microsoft Foundry project

In this task, you'll create and configure a Microsoft Foundry project to manage resources and enable Azure Content Understanding capabilities.

1. Copy the **Microsoft Foundry** link and paste it into a new browser tab to access the portal: `https://ai.azure.com/`

1. On the **Microsoft Foundry** home page, click on **Sign in** in the top right corner.

   ![](./media/mod6-p2t1p1.png)

1. If prompted to sign in, enter your credentials:
   - **Email/Username:** Enter <inject key="AzureAdUserEmail"></inject> **(1)** and click on **Next (2)**.

     ![Enter Your Username](./media/mod6-p2t1p2.png)

   - **Password:** Enter <inject key="AzureAdUserPassword"></inject> **(1)** and click on **Sign in (2)**.

     ![Enter Your Password](<./media/mod6-p2t1p2(1).png>)

1. If prompted to **Stay signed in?**, you can click **No**.

   ![](./media/mod6-p2t1p3.png)

1. Close any tips or quick start panes that are opened the first time you sign in, and if necessary use the **Foundry** logo at the top left to navigate to the home page.

   ![](./media/mod01-p2t1p2.png)

1. If it is not already enabled, in the tool bar the top of the page, enable the **New Foundry** option.

   ![](./media/mod01-p2t1p3.png)

1. In the **Create a project** wizard, enter project name **Myproject<inject key="DeploymentID" enableCopy="false" /> (1)**, and **Expand Advanced options (2)** to specify the following settings for your project:
   - Subscription : **Leave default subscription (3)**
   - Resource Group : Select **AI-900-Module-06a (4)**
   - Microsoft Foundry resource: **MyFoundry<inject key="DeploymentID" enableCopy="false" /> (5)**
   - Region : Select **<inject key="location" enableCopy="false"/> (6)**
   - Click on **Create** **(7)**

     ![](./media/lab6a-e1t1p4.png)

     > **Note:** Model deployments are restricted by regional quotas. If you select a region in which you have insufficient available quota, you may need to select an alternative region for a new resource later. At the time of writing, Content Understanding is supported in these regions: `West US`,`Sweden Central`, and `Australia East`.

1. Wait for your project to be created. It may take a few minutes.

1. In the **Welcome to new Microsoft Foundry** window, click the **X** icon in the top-right corner to close the welcome screen.

   ![](./media/mod01-p2t1p6.png)

1. After creating a project in the new Foundry portal, it should open in a page similar to the following image:

   ![](./media/ai901-lab6a-t1p2.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:

- Hit the Validate button for the corresponding task. You will receive a success message.
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="ef1ed7b3-d177-4af2-b182-064e6945644b" />

## Task 2: Extract information from documents in the new Foundry portal

In this task, you'll use Azure Content Understanding analyzers in Microsoft Foundry to extract text, structure, and fields from documents.

1. In the new Foundry portal, navigate to the tool bar at the top of the screen and select **Build**.

   ![](./media/ai901-lab6a-t2p1.png)

1. On the **Build** page, navigate to the menu on the left-side of the screen (you may need to expand it by clicking on the expand icon at the bottom of the menu). From the left-side menu, select **Models (1)**. Then, at the top of the Models page, select **AI Services (2)**.

   ![](./media/ai901-lab6a-t2p2.png)

1. Identify the **Content Understanding** capabilities you can try out in a Foundry playground setting:
   - **Content Understanding - Read**: Raw text extraction only. Answers the question, "What text is here?"
   - **Content Understanding - Layout**: Adds structure, hierarchy, and positioning. Answers the question, "How is this content organized?"
   - **Content Understanding**: offers the full analyzer capability by extracting fields and structure and generating insights. Answers the question, "What does this content mean and what should I do with it?"

     ![](./media/ai901-lab6a-t2p3.png)

### Task 2.1: Try out Content Understanding's Read capabilities

In this task, you'll use the **Read** analyzer to extract raw text content from a sample document using Azure Content Understanding.

1. Select **Content Understanding - Read**. The **Read** capability is the first step in content understanding-it reads and extracts text, but doesn’t try to understand structure or meaning yet.

   ![](./media/ai901-lab6a-t2p4.png)

2. Select the sample **read_barcode.pdf (1)** and use the **Run analysis (2)** button to extract information from the document.

   ![](./media/ai901-lab6a-t2p5.png)

3. When analysis is complete, view the results.

   ![](./media/ai901-lab6a-t2p6.png)

4. Select the **back** button to return to the previous page to test out other capabilities.

   ![](./media/ai901-lab6a-t2p7.png)

### Task 2.2: Try out Content Understanding's Layout capabilities

In this task, you'll use the **Layout** analyzer to identify document structure, tables, and content organization within a sample document.

1. From the **Build - Models** page and **AI Services** tab, select **Content Understanding - Layout**.

   ![](./media/ai901-lab6a-t2p8.png)

2. Select the sample **layout_checklist.jpg (1)** and use the **Run analysis (2)** button to extract information from it.

   ![](./media/ai901-lab6a-t2p9.png)

3. When analysis is complete, view the results.

   ![](./media/ai901-lab6a-t2p10.png)

4. In the content output, select the **Tables** tab. Review how the **Layout** analyzer is able to capture both the text and structure of the content.

   ![](./media/ai901-lab6a-t2p11.png)

5. Select the **back** button to return to the previous page to test out other capabilities.

   ![](./media/ai901-lab6a-t2p7.png)

### Task 2.3: Try out Content Understanding's other analyzer capabilities

In this task, you'll use the **Document fields** analyzer to extract structured information, review JSON results, and analyze invoice documents in Microsoft Foundry.

1. From the **Build - Models** page and **AI Services** tab, select **Content Understanding** to test another one of Azure Content Understanding analyzers.

   ![](./media/ai901-lab6a-t2p12.png)

2. On the **Content Understanding** page, select the **Document** modality.

   ![](./media/ai901-lab6a-t2p13.png)

3. Next to the **Document** modality, select **Document fields (1)** from the dropdown menu. If asked to deploy models that aren't configured yet, select **Deploy models (2)**.

   ![](./media/ai901-lab6a-t2p14.png)

   ![](./media/ai901-lab6a-t2p15.png)

   > **Note:** _Document fields_ and other advanced extraction requirements often require deploying multiple AI models, as each deployment is associated with a specific model version or capability. Using multiple models in Azure AI Foundry enables more efficient handling of diverse processing tasks by allowing you to select the most suitable model for each scenario.

4. Select the recommended **Chat completion model (1)** and **Embedding model (2)** from the drop-down menus. Then select **Apply changes (3)**. Once the changes are applied, you can close the **Configure** panel.

   ![](./media/ai901-lab6a-t2p16.png)

5. Let's try to use the full analyzer with our own invoice. Open a new browser window. Enter the following URL: `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/content-understanding/contoso-invoice-1.pdf` to download **[contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/content-understanding/contoso-invoice-1.pdf)** .

   ![](./media/ai901-lab6a-t2p17.png)

6. Select the **Browse for files** link to upload the **contoso-invoice-1.pdf** document you just downloaded.

   ![](./media/ai901-lab6a-t2p18.png)

7. In the **Open** window, select **Downloads (1)** from the left pane, then select the **contoso-invoice-1.pdf** file **(2)** that you have downloaded in the previous step. Finally, select **Open (3)** to upload the file.

   ![](./media/ai901-lab6a-t2p19.png)

8. Select **Run analysis**.

   ![](./media/ai901-lab6a-t2p20.png)

9. Review the results and notice that not only is the text rendered, but its layout is captured, and the fields are organized into cohesive categories.

   ![](./media/ai901-lab6a-t2p21.png)

10. In the pane on the right where the extracted fields are displayed, view the **Result** tab to see the raw results in JSON. Identify the **analyzerID** field, which contains the type of analyzer used. You can find a list of prebuilt Content Understanding analyzers [here](https://learn.microsoft.com/azure/ai-services/content-understanding/concepts/prebuilt-analyzers).

    ![](./media/ai901-lab6a-t2p22.png)

    > **Note:** Consider this: the _Fields_ tab displays the information from the raw JSON in the _Results_ tab in a user-friendly way.

## Task 3: Understand how to extract content with the REST API

In this task, you'll understand how developers can use REST APIs to submit documents and retrieve analysis results programmatically.

1. Developers can use the REST API to build an app that submits a document for analysis with Content Understanding analyzers using a POST operation. For example, the following cUrl command could be used to analyze an invoice:

   ```bash
   curl -i -X POST "{endpoint}/contentunderstanding/analyzers/{analyzerId}:analyze?api-version=2025-11-01" \
     -H "Ocp-Apim-Subscription-Key: {key}" \
     -H "Content-Type: application/json" \
     -d '{
           "inputs":[
             {
               "url": "https://{url_path}/invoice.png"
             }
           ]
         }'
   ```

1. Consider what you would need to specify in the cUrl command:
   - _analzyerID_
   - _endpoint_
   - _key_
   - _url_path_ to the document

1. When you run the command, you receive a response in JSON. The analysis is performed asynchronously, so the response includes an **id** value specific to the analysis job that can be used to poll for the results:

   ```json
   {
     "id": {resultId},
     "status": "Running",
     "result": {
       "analyzerId": {analyzerId},
       "apiVersion": "2025-11-01",
       "createdAt": "YYYY-MM-DDTHH:MM:SSZ",
       "warnings": [],
       "contents": []
     }
   }
   ```

   > **Note:** Polling for results in an asynchronous call means repeatedly checking the status of a request at intervals until the operation is complete and the final result is available. The final result in this case is that the analysis is complete. After the result is returned, another call should be made to retrieve the results.

1. In order to retrieve the results using the ID, the client must submit a GET request:

   ```bash
   curl -i -X GET "{endpoint}/contentunderstanding/analyzerResults/{resultId}?api-version=2025-11-01" \
     -H "Ocp-Apim-Subscription-Key: {key}"
   ```

1. Consider what you would need to specify in the cUrl command:
   - _resultID_
   - _endpoint_
   - _key_

## Task 4: Understand how to extract content with the Python SDK

In this task, you'll review how the Python SDK can be used to analyze documents and process extracted content programmatically.

1. Alternatively, as a developer, you can also use code to submit a document for analysis to the _Document Fields_ analyzer. The Foundry playground provides code samples.

1. Select the **Code** tab to review the code you could use to process this response and utilize the extracted fields.

   ![](./media/ai901-lab6a-t2p23.png)


<question source="Questions/Module-6/question-01.md" />

<question source="Questions/Module-6/question-02.md" />


## Summary

In this lab, you explored Azure Content Understanding in Foundry and learned how it transforms unstructured content into structured, usable data. You tried out three analyzers, each building on the previous one in capability:

- **Read**: Extracts raw text from documents without interpreting structure or meaning-answering, "What text is here?"
- **Layout**: Goes a step further by capturing structure, hierarchy, and positioning-including tables-answering, "How is this content organized?"
- **Document fields**: an analyzer that uses a combination of capabilities to extract fields, organize them into cohesive categories, and generate insights-answering, "What does this content mean and what should I do with it?" Content Understanding analyzers like this one sometimes require deploying additional AI models (such as chat completion and embedding models) to handle complex extraction needs.

You also learned how developers can integrate Content Understanding into applications using the **REST API** (submitting documents via a POST request and polling for results with a GET request) or the **Python SDK**, both of which enable programmatic analysis of documents outside the Foundry playground.

### Congratulations, you’ve successfully completed the hands-on lab!
