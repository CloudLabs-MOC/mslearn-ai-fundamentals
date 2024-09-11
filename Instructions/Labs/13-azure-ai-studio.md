# Module 13: Explore the components and tools of the Azure AI Studio

## Lab overview

In this Exercise, you will explore Azure AI Studio and learn how to create, manage, and deploy generative AI models within the Azure ecosystem. You will gain hands-on experience working with Azure AI hubs, projects, and deploying AI models like GPT-35-Turbo.

## Lab objectives

In this exercise, you will perform:
- Task 1: Open Azure AI Studio
- Task 2: Create an Azure AI hub
- Task 3: Create a project
- Task 4: Deploy and test a model

## Estimated timing: 30 minutes

## Architecture Diagram


## Exercise 1: Explore the components and tools of the Azure AI Studio

### Task 1: Open Azure AI Studio

In this task, you will sign in to Azure AI Studio and explore its interface, learning how to navigate the platform and access its various features for managing AI resources.

1. In a edge browser, open https://ai.azure.com and **Sign in** using your Azure credentials. The home page of Azure AI Studio looks similar to the following image:

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
   - **Password:** <inject key="AzureAdUserPassword"></inject>

    ![](media/lab13-a1.png)

2. Review the information on the home page and view each of the tabs, noting the options to explore models and capabilities, create projects, and manage resources.

    ![](media/lab13-a2.png)

### Task 2: Create an Azure AI hub

In this task, you will create an Azure AI hub, gaining hands-on experience in setting up a collaborative workspace for AI projects and configuring essential resources and connections.

1. In the **Management** section, navigate to **All hubs (1)** and click on **+ New hub (2)**. Set the following configuration settings for the new hub, and then click **Next** to proceed.

    ![](media/lab13-a3.png)

    | Setting | Action |
    | -- | -- |
    | **Hub name** | **azureai-<inject key="DeploymentID" enableCopy="false"/>** |
    | **Subscription** | *Default Azure subscription* |
    | **Resource Group** | **AI-900-Module-13-<inject key="DeploymentID" enableCopy="false" />** |
    | **Location** | **East US** |
    | **Connect Azure AI Services or Azure OpenAI** | *create a new AI Services **ai-azureai-<inject key="DeploymentID" enableCopy="false" />*** |
    | **Connect Azure AI Search** | *Skip connecting* |

    ![](media/lab13-a4.png)

2. Review your details and click on **Create**.

    ![](media/lab13-a5.png)

3. After the Azure AI hub has been created, it should look similar to the following image:

    ![](media/lab13-a6.png)

4. While keeping the Azure AI Studio tab open in the Edge browser, open another tab within the same Edge browser and navigate to the Azure portal.

5. Browse to the resource group **AI-900-Module-13-<inject key="DeploymentID" enableCopy="false" />** , and view the Azure resources that have been created.

    ![](media/lab13-a7.png)

6. Return to the Azure AI Studio browser tab.

7. View each of the pages in the pane on the left side of the page for your Azure AI hub, and note the artifacts you can create and manage. On the **Connections** page, observe that connections to Azure OpenAI and AI services have already been created.

    ![](media/lab13-a8.png)

### Task 3: Create a project

In this task, you will create a new project within your Azure AI hub, learning how to organize and manage your AI solutions effectively.

1. In Azure AI Studio, navigate to the **azureai-<inject key="DeploymentID" enableCopy="false" />** hub you have created.

2. Navigate to **All projects (1)** using the menu on the left, Select **+ New project (2)**.

    ![](media/lab13-a9.png)

3. In the **Create a project** wizard, create a project with the following settings, and then click **Create a project** to proceed

    - **Current hub**: **azureai-<inject key="DeploymentID" enableCopy="false"/>**
    - **Project name**: **ai-project-<inject key="DeploymentID" enableCopy="false"/>**

    ![](media/lab13-a10.png)

4. Wait for your project to be created. When it's ready, it should look similar to the following image:

    ![](media/lab13-a11.png)

5. View the pages in the pane on the left side, expanding each section, and note the tasks you can perform and the resources you can manage in a project.

### Task 4: Deploy and test a model

In this task, you will deploy and test the [GPT-35-Turbo](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/chatgpt?tabs=python-new) model, understanding how to configure deployment settings and validate the model's functionality through interactive testing.

1. In the pane on the left for your project, in the **Shared resources** section, select the **Deployments** page.

2. On the **Deployments (1)** page, under the **Model deployments** tab, click **+ Deploy model (2)**, and then select **Deploy base model (3)**.

    ![](media/lab13-a12.png)

3. Search for the **gpt-35-turbo** model from the list, select and confirm.

    ![](media/lab13-a13.png)

4. Enter **gpt-35-turbo** as your **Deployment name**, then click on **Customize** to adjust the other values accordingly.

    ![](media/lab13-a14.png)

5. Deploy the model with the following settings:

    | Setting | Action |
    | -- | -- |
    | **Connected Azure OpenAI resource** | *Select the default connection that was created when you created your hub* |
    | **Model version** | *Select the default version* |
    | **Deployment type** | **Standard** |
    | **Tokens per Minute Rate Limit (thousands)** | **5K** |
    | **Content filter** | **Default** |
    | **Enable dynamic quota** | **Disable** |

    ![](media/lab13-a15.png)

    > **Note**: Reducing the TPM helps avoid over-using the quota available in the subscription you are using. 5,000 TPM is sufficient for the data used in this exercise.

6. After the model has been deployed, in the deployment overview page, select **Open in playground**.

    ![](media/lab13-a16.png)

7. In the **Chat playground** page, ensure that your model deployment is selected in the **Deployment** section.

8. In the chat window, enter a query such as *What is AI?* and view the response:

    ![](media/lab13-a17.png)

### Validation

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
 
- Navigate to the Lab Validation Page, from the upper right corner in the lab guide section.
- Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
- If not, carefully read the error message and retry the step, following the instructions in the lab guide.
- If you need any assistance, please contact us at labs-support@spektrasystems.com. We are available 24/7 to help you out.

### Summary

After performing this lab, you learned how to navigate Azure AI Studio, create and manage Azure AI hubs and projects, and deploy and test generative AI models. You gained practical experience in setting up and configuring AI resources, as well as using Azure AI Stuido tools to develop and validate AI solutions effectively.

### Review

In this exercise, you have completed:
- Open Azure AI Studio
- Create an Azure AI hub
- Create a project
- Deploy and test a model

##   You have successfully completed this lab.
