# Module 11: Explore an Azure AI Search index (UI)

## Lab overview

Let's imagine you work for Fourth Coffee, a national coffee chain. You're asked to help build a knowledge-mining solution that makes it easy to search for insights about customer experiences. You decide to build an Azure AI Search index using data extracted from customer reviews.  

In this lab, you will:

- Create Azure resources
- Extract data from a data source
- Enrich data with AI skills
- Use Azure's indexer in the Azure portal
- Query your search index
- Review results saved to a Knowledge Store

## Estimated timing: 2 hours

## Architecture Diagram

  ![](media/Module0005.png)

## Pre-requisites Required

The solution you'll create for Fourth Coffee requires the following resources in your Azure subscription:

- An **Azure AI Search** resource, which will manage indexing and querying.

- An **Azure AI services** resource, which provides AI services for skills that your search solution can use to enrich the data in the data source with AI-generated insights.

    > **Note**
    > Your Azure AI Search and Azure AI services resources must be in the same location!

- A **Storage account** with blob containers, which will store raw documents and other collections of tables, objects, or files.

### Task 1: Create an Azure AI Search resource

1. On the **Azure Portal** homepage, select **+ Create a resource**.

     ![Picture1](media/lab11-01.png)

1. In the Marketplace page search for **Azure AI Search** and select **Azure AI Search**.
 
    ![Picture1](media/lab11-02.png)

1. On  the **Azure AI Search** page, click on **Create**.

    ![Picture1](media/lab11-03.png)

1. Create a new **AI Search** resource with an AI Search plan. Use the following settings:

    - **Subscription (1)**: Select your **existing azure subscription**.
    - **Resource group (2)**: Select **AI-900-Module-11-<inject key="DeploymentID" enableCopy="false" />**
    - **Service name (3)**: **aisearch<inject key="DeploymentID" enableCopy="false" />**
    - **Location (4)**: Select **<inject key="location" enableCopy="false"/>** 
    - **Pricing tier (5)**: Basic
    - Select **Review + create (6)**

      ![Picture1](media/lab11-04.png)
    
1. You see the response **Validation Success**, select **Create**.

   ![Picture1](media/lab11-05.png)

1. After deployment completes, select **Go to resource**.

   ![Picture1](media/lab11-06.png)

1. On the Azure AI Search overview page, you can add indexes, import data, and search created indexes.

### Task 2: Create an AI Services resource

You'll need to provision an **Azure AI services** resource that's in the same location as your Azure AI Search resource. Your search solution will use this resource to enrich the data in the datastore with AI-generated insights.

1. Return to the home page of the Azure portal. Select **+ Create a resource**.

     ![Picture1](media/lab11-01.png)

1. In the Marketplace page search for **Azure AI services** and select **Azure AI services**.
 
    ![Picture1](media/lab11-07.png)

1. On the **Azure AI services** Page, click on **Create**.

    ![Picture1](media/lab11-08.png)
    
1. You will be taken to a page to create an Azure AI services resource. Configure it with the following settings:

    - **Subscription (1)**: Select your **existing azure subscription**.
    - **Resource group (2)**: Select **AI-900-Module-11-<inject key="DeploymentID" enableCopy="false" />**
    - **Region (3)**: Select **<inject key="location" enableCopy="false"/>** 
    - **Name (4)**: Enter **aiservice<inject key="DeploymentID" enableCopy="false" />**
    - **Pricing tier (5)**: Standard S0
    - **By checking this box I acknowledge that I have read and understood all the terms below (6)**: Selected
   - Select **Review + create (7)**.

     ![Picture1](media/lab11-09.png) 
   
1. After you see the response **Validation Passed**, select **Create**.

    ![Picture1](media/lab11-10.png) 

1. Wait for deployment to complete, then view the deployment details.

### Task 3: Create a storage account

1. Return to the home page of the Azure portal. Select **+ Create a resource**.

     ![Picture1](media/lab11-01.png)

1. In the Marketplace page search for **Storage account** and select **Storage account**.
 
    ![Picture1](media/lab11-11.png)

1. On the **Storage account** Page, Click on **Create**.

    ![Picture1](media/lab11-12.png)
    
1. Create a **Storage account** resource with the following settings:

    - **Subscription (1)**: Select your **existing azure subscription**.
    - **Resource group (2)**: Select **AI-900-Module-11-<inject key="DeploymentID" enableCopy="false" />**
    - **Storage account name (3)**: Enter **aistorage<inject key="DeploymentID" enableCopy="false" />**
    - **Location (4)**: Select **<inject key="location" enableCopy="false"/>** 
    - **Performance (5)**: Standard
    - **Redundancy (6)**: Locally redundant storage (LRS)
   - Click **Review (7)**.

      ![Picture1](media/storageaccount.png)
   
1. On the **Review** page, Click **Create**. 

    ![Picture1](media/saccount.png)

1. Wait for deployment to complete, and then go to the deployed resource.

    ![Picture1](media/deployment.png)

1. In the Azure Storage account you created, in the left-hand menu pane, select **Configuration (1)** (under **Settings**), Change the setting for **Allow Blob anonymous access** to **Enabled (2)** and then select **Save (3)**.

    ![Picture1](media/storageaccount(1).png)

## Exercise 1: Upload Documents to Azure Storage

1. In the left-hand menu pane, select **Containers (1)**.

1. Select **+ Container (2)**. A pane on your right-hand side opens.

1. Enter the following settings:

    - **Name (3)**: coffee-reviews  
    - **Public access level (4)**: Container (anonymous read access for containers and blobs)
    - **Advanced (5)**: *no changes*.
    - click **Create (6)**

      ![Picture1](media/storage.png)

1. In the lab-VM,  open a  new browser tab, download the [zipped coffee reviews](https://aka.ms/mslearn-coffee-reviews) from `https://aka.ms/mslearn-coffee-reviews`, and extract the files to the *reviews* folder. 

1. In the Azure portal, select your *coffee-reviews* container. In the container, select **Upload (1)**. In the **Upload blob** pane, select **Select a file (2)**, and In the Explorer window, select **all** the files in the *reviews* folder, select **Open**, and then select **Upload (3)**.

    ![Screenshot that shows the files uploaded to the Azure container.](media/lab11-18.png)

1. After the upload is complete, you can close the **Upload blob** pane. Your documents are now in your *coffee-reviews* storage container.

## Exercise 2: Index the documents

After you have the documents in storage, you can use Azure AI Search to extract insights from the documents. The Azure portal provides an *Import data wizard*. With this wizard, you can automatically create an index and indexer for supported data sources. You'll use the wizard to create an index and import your search documents from storage into the Azure AI Search index.

1. In the Azure portal, browse to your Azure AI Search resource. 

   ![Screenshot that shows the import data wizard.](media/lab11-19.png)

2. On the **Overview** page, select **Import data**.

    ![Screenshot that shows the import data wizard.](media/lab11-20.png)

3. On the **Connect to your data** page, in the **Data Source** list, select **Azure Blob Storage (1)**. Complete the data store details with the following values:
    - **Data Source (2)**: Azure Blob Storage
    - **Data source name (3)**: coffee-customer-data
    - **Data to extract (4)**: Content and metadata
    - **Parsing mode (5)**: Default
    - **Connection string (6)**: Select **Choose an existing connection**.
    
       ![Picture1](media/lab11-21.png)
    
    - Select your the **AIstorage<inject key="DeploymentID" enableCopy="false" /> (1)** storage account, select the **coffee-reviews (2)** container, and then click **Select (3)**.

      ![Picture1](media/containers.png)

    - **Managed identity authentication (7)**: None
    - **Container name (8)**: *this setting is auto-populated after you choose an existing connection*.
    - **Blob folder (9)**: *Leave this blank*.
    - **Description (10)**: Reviews for Fourth Coffee shops.

4. Select **Next: Add Cognitive Skills (Optional) (11)**.

   ![Picture1](media/lab11-23.png)

5. In the **Attach AI Services (1)** section, select your **aiservice<inject key="DeploymentID" enableCopy="false" /> (2)** Azure AI services resource.  

   ![Picture1](media/lab11-24.png)

6. In the **Add enrichments (1)** section:
    - Change the **Skillset name** to **coffee-skillset (2)**.
    - Select the checkbox **Enable OCR and merge all text into merged_content field (3)**.
        > **Note**
        > It's important to select **Enable OCR** to see all of the enriched field options.
    - Ensure that the **Source data field** is set to **merged_content (4)**.
    - Change the **Enrichment granularity level** to **Pages (5000 character chunks) (5)**.
    - Don't select **Enable incremental enrichment (6)**

      ![Picture1](media/lab11-25.png)
    
    - Select the following enriched fields:

        | AI Skill | Parameter | Field name |
        | --------------- | ---------- | ---------- |
        | Extract location names | | locations |
        | Extract key phrases | | keyphrases |
        | Detect sentiment | | sentiment |
        | Generate tags from images | | imageTags |
        | Generate captions from images | | imageCaption |

        ![Picture1](media/lab11-26.png)

7. Under **Save enrichments to a knowledge store (1)**, If a warning asking for a **Storage Account Connection String (2)** appears.
    
   ![Screenshot that shows the Storage account connection screen warning with 'Choose an existing connection' selected.](media/lab11-27.png)
    
8. Select **Choose an existing connection**. Choose the storage account **aistorage<inject key="DeploymentID" enableCopy="false" /> (1)** you created earlier. Click on **+ Container (2)** to create a new container called **knowledge-store (3)** with the privacy level set to **Private (4)**, and select **Create (5)**.

9. Select the **knowledge-store (1)** container, and then click **Select (2)** at the bottom of the screen.

    ![Picture1](media/lab11-29.png)

10. Under **Save enrichments to a knowledge store**, Select:
    - Image projections
    - Documents
    - Pages
    - Key phrases
    - Entities
    - Image details
    - Image references

    ![Picture1](media/lab11-30.png)

11. Select **Azure blob projections: Document**. A setting for *Container name* with the *knowledge-store* container auto-populated displays. Don't change the container name.

    ![Picture1](media/lab11-31.png)

12. Select **Next: Customize target index**.

13. On the **Customize target index** page, follow the following steps:

    -  Change the **Index name** to **coffee-index (1)**.
    - Ensure that the **Key** is set to **metadata_storage_path (2)**.
    - Leave **Suggester name** blank.
    - **Search mode (3)** auto populated.
    - Review the index fields' default settings. Select **filterable (4)** for all the fields that are already selected by default.
    - Select **Next: Create an indexer (5)**.

    ![](media/lab11-32.png)

14. On the **Create an index** page, follow the following steps:

- Change the **Indexer name** to **coffee-indexer (1)**.
- Leave the **Schedule** set to **Once (2)**.
- Expand the **Advanced options**. Ensure that the **Base-64 Encode Keys (3)** option is selected, as encoding keys can make the index more efficient.
- Select **Submit (4)** to create the data source, skillset, index, and indexer. The indexer is run automatically and runs the indexing pipeline, which:
    - Extracts the document metadata fields and content from the data source.
    - Runs the skillset of AI skills to generate more enriched fields.
    - Maps the extracted fields to the index.

      ![Picture1](media/lab11-33.png)

15. In the bottom half of the **Overview** page for your Azure AI Search resource, select the **Indexers (1)** tab. This tab shows the newly created **coffee-indexer (2)**. Wait a minute, and select **&orarr; Refresh** until the **Status** indicates **success**.

     ![Picture1](media/lab11-34.png)

16. Select the indexer name to see more details.

    ![Screenshot that shows the coffee-indexer Indexer successfully created.](media/lab11-35.png)

## Exercise 3: Query the index

Use the Search Explorer to write and test queries. Search Explorer is a tool built into the Azure portal that gives you an easy way to validate the quality of your search index. You can use Search Explorer to write queries and review results in JSON.

1. In your Search service's *Overview* page, select **Search explorer** at the top of the screen.

   ![Screenshot of how to find Search explorer.](media/lab11-36.png)

1. Notice how the index selected is the *coffee-index* you created.

     ![](media/coffee-index.png)

1.  In the **Query string** field, enter `search=*&$count=true`, and then select **Search**.

     ![](media/lab11-37.png)

1.  The search query returns all the documents in the search index, including a count of all the documents in the **@odata.count** field. The search index should return a JSON document containing your search results.

     ![](media/lab11-38.png)

    > **Note**
    > If a **To search in the portal, please allow the portal origin in your index CORS settings** message appears, select **Allow portal**, and then select **Search**.

1. Now let's filter by location. Enter `search=locations:'Chicago'` in the **Query string** field, and then select **Search**. The query searches all the documents in the  index and filters for reviews with a Chicago location.

    ![](media/lab11-39.png)

1. Now let's filter by sentiment. Enter `search=sentiment:'negative'` in the **Query string** field, and then select **Search**. The query searches all the documents in the index and filters for reviews with a negative sentiment.

    ![](media/lab11-40.png)

   > **Note**
   > See how the results are sorted by `@search.score`. This is the score assigned by the search engine to show how closely the results match the given query.

1. One of the problems we might want to solve for is why there might be certain reviews. Let's take a look at the key phrases associated with the negative review. What do you think might be the cause of the review?

## Exercise 4: Review the knowledge store

Let's see the power of the knowledge store in action. When you ran the *Import data wizard*, you also created a knowledge store. Inside the knowledge store, you'll find the enriched data extracted by AI skills persists in the form of projections and tables.

1. In the Azure portal, navigate back to your Azure storage account.

1. In the left-hand menu pane, select **Containers (1)**. Select the **knowledge-store (2)** container.

    ![Screenshot of the knowledge-store container.](media/containe(1).png)

1. Select any of the items.

    ![](media/lab11-42.png)

1. Click the **objectprojection.json** file.

    ![Screenshot of the objectprojection.json.](media/lab11-44.png)

1. Select **Edit** to see the JSON produced for one of the documents from your Azure data store.

    ![Screenshot of how to find the edit button.](media/lab11-45.png)

1. Select the storage blob breadcrumb at the top left of the screen to return to the Storage account *Containers*.

    ![Screenshot of the storage blob breadcrumb.](media/knowledgestore.png)

1. In the **Containers (1)**, select the container **coffee-skillset-image-projection (2)**.

    ![Screenshot of the skillset container.](media/containe(2).png)

1.  Select any of the items.

     ![Screenshot of the skillset container.](media/lab11-48.png)

1. Select any of the *.jpg* files. Select **Edit** to see the image stored in the document. Notice how all the images from the documents are stored in this manner.

    ![Screenshot of the saved image.](media/lab11-43.png)

1. Select the storage blob breadcrumb at the top left of the screen to return to the Storage account *Containers*.

1. Select **Storage browser** on the left-hand panel, and select **Tables**. There's a table for each entity in the index. Select the table *coffeeSkillsetKeyPhrases*.

     ![Screenshot of the saved image.](media/lab11-49.png)

    Look at the key phrases the knowledge store was able to capture from the content in the reviews. Many of the fields are keys, so you can link the tables like a relational database. The last field shows the key phrases that were extracted by the skillset.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Navigate to the Lab Validation Page, from the upper right corner in the lab guide section.
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

## Learn more

This simple search index only some of the capabilities of the Azure AI Search service. To learn more about what you can do with this service, see the [Azure AI Search service page](/azure/search/search-what-is-azure-search).

## Review

In this exercise you:

- Created Azure resources
- Extracted data from a data source
- Enriched data with AI skills
- Used Azure's indexer in the Azure portal
- Queried your search index
- Reviewed results saved to a Knowledge Store

## You have successfully completed this lab.
