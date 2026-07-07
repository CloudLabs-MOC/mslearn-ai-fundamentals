# Module 01: Explore Automated Machine Learning in Azure Machine Learning

## Overview

In this module, you'll use the automated machine learning feature in **Azure Machine Learning** to train and evaluate a machine learning model. You'll then deploy and test the trained model.

## Objectives

In this lab, you will perform:

- Task 1: Creating an Azure Machine Learning workspace resource
- Task 2: Use automated machine learning to train a model
- Task 3: Deploy the model

### Task 1: Create an Azure Machine Learning workspace

In this task, you will create an Azure Machine Learning workspace. You will search for Machine Learning, configure the necessary settings like subscription, resource group, and workspace name, and deploy the resource. Once deployed, you will access the workspace through Azure Machine Learning Studio.

1. In the Azure Portal, select **+ Create a resource**.

    ![Picture1](media/mod1-e1t1p1.png)

2. In the Marketplace page search for **Azure Machine Learning (1)** and select **Azure Machine Learning (2)**.
 
   ![Picture1](media/ai900-12.png)

3. On the **Azure Machine Learning** page, click **Create** to proceed.

   ![Picture1](media/AI-900-lab1-0.png)
  
4. Create a new **Azure Machine Learning** resource with an *Azure Machine Learning* plan. Use the following settings:

    - **Subscription**: Use existing Azure subscription. **(1)**
    - **Resource group**: Select **machinelearning** **(2)**
    - **Name**: Give name **AI-900-Workspace-<inject key="DeploymentID" enableCopy="false" /> (3)**
    - **Region**: Select **<inject key="location" enableCopy="false" />** **(4)**
    - **Storage account**: Note the default new storage account that will be created for your workspace. **(5)**
    - **Key vault**: Note the default new key vault that will be created for your workspace. **(6)**
    - **Application insights**: Note the default new application insights resource that will be created for your workspace. **(7)**
    - **Container registry**: None (one will be created automatically the first time you deploy a model to a container) **(8)**

5. Select **Review + create (9)**.

    ![](media/T1S5-0707.png)

6. After completing the validation process, click on the **Create** button located in the lower left corner of the page.

   ![](media/T1S6-0707.png)
   
7. Wait for deployment to complete(it can take a few minutes), and then click on the **Go to resource** button. This will take you to your workspace resource.

   ![](media/T1S7-0707.png)

8. Select **Launch studio** (or open a new browser tab and navigate to [https://ml.azure.com](https://ml.azure.com?azure-portal=true), and if prompted, sign into **Azure Machine Learning studio** using your Microsoft account). Close any messages that are displayed.

   ![](media/T1S8a-0707.png)

   ![](media/T1S8b-0707.png)

9. In Azure Machine Learning studio, click on **All workspaces (1)** and the navigate to **Workspaces (2)**, you should see your newly created workspace **(3)**.

    ![](media/T1S9a-0707.png)

    ![](media/T1S9b-0707.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="19f87603-9f16-4107-b94f-d92593b422ce" />

### Enable preview features

Some features of Azure Machine Learning are in preview and need to be explicitly enabled in your workspace.

1. In **Azure Machine Learning** studio, click on **manage preview features** (the loud speaker icon - &#128363;).

     ![](media/lab1-5.png)

1. Enable the following preview feature, if not enabled: `Guided experience to importing from external data sources (PREVIEW)`

     ![](media/mod1-e1t1p7.png)

### Task 2: Use automated machine learning to train a model

In this task, you will learn how to use automated machine learning to train a model efficiently without writing extensive code.

Automated machine learning enables you to try multiple algorithms and parameters to train multiple models and identify the best one for your data. In this exercise, you'll use a dataset of ice cream sales to train a model that predicts the demand for ice cream that should be expected on a given day, based on seasonal and meteorological features.

1. In **Azure Machine Learning** studio, navigate to the **Automated ML (1)** page under **Authoring**, select  **+ New Automated ML job (2)**.

   ![](media/T2S1-0707.png)  

1. Create a new Automated ML job with the following settings, using **Next (5)** as required to progress through the user interface:

    **Basic settings**:

    - **Job name**: mslearn-icecream-automl **(1)**
    - **New experiment name**: mslearn-icecream-automl **(2)**
    - **Description**: Automated machine learning for ice cream demand prediction **(3)**
    - **Tags**: Leave default **(4)**

       ![](media/T2S2a-0707.png)

1. On the **Task type & data** page:

    - **Select task type**: Regression **(1)**
    - **Select data**: Select **+ Create (2)** 

        ![](media/lab1-25.png)

1. This will open a new Create data set page. To create new data with the following settings:

    - **Data type**:
      - **Name**: `ice-cream` **(1)**
      - **Description**: `Historic ice cream sales data` **(2)**
      - **Type**: Tabular **(3)**
      - Click **Next (4)**

          ![](media/lab1-e1t2p3.png)
      
    - **Data source**:
        - Select **From local files (1)**
        - Click **Next (2)**

            ![](media/AI-900-lab1-2.png)
        
    - **Destination storage type**:
        - **Datastore type**: Azure Blob Storage **(1)**
        - **Name**: workspaceblobstore **(2)**
        - Click **Next (3)**

            ![](media/AI-900-lab1-3.png)

    - **Files or Folder selection**:
        - **Upload files or folder**: Download and extract the contents of the folder from [`https://aka.ms/mslearn-ml-data`](https://aka.ms/mslearn-ml-data), by right-clicking the link and selecting **Copy Link**. Paste the link in a new browser tab to download the **ml-data.zip** file. 

            ![](media/T2copylink-0707.png)

        - Extract the downloaded **ml-data.zip** by navigating to **File explorer (1)** in VM. From **Downloads (2)**, right click on **ml-data.zip** and select **Extract all (3).** Note that one of these files is **ice-cream.csv**, which contains the ice cream sales data required for this exercise. Once uploaded, click on **Next**.

            ![](media/T2extract1-0707.png)

            ![](media/T2extract2-0707.png)              

    - On the **Create data asset – File or folder selection** page, click **Upload files or folder (1)** and choose **Upload files (2)** to upload files from your local drive.

        ![](media/AI-900-lab1-4.png)

        - In the **Open** dialog, select **ice-cream (1)**, then click **Open (2)** to upload the file.

          ![](media/lab1-e1t2p4.png)

          ![](media/lab1-e1t2p4(1).png)

    - On the **Create data asset - Settings** page, leave everything default click **Next**:

        ![](media/lab1-e1t2p5.png)
        
    - On the **Create data asset - Schema** page, 
      - Include **only** the following columns **(1)** (*Date* is unique for each row, and adds little predictive capability on its own):
        - **DayOfWeek**
        - **Month**
        - **Temperature**
        - **Rainfall**
        - **IceCreamsSold**
        - Review detected columns and types, then click **Next (2)**

          ![](media/lab1-e1t2p6.png)

    - Select **Create**. 
  
        ![](media/lab1-e1t2p7.png)
      
1. After the dataset is created, select the **ice-cream (1)** dataset to continue to submit the Automated ML job. Select **Next (2)**

    ![](media/lab1-e1t2p8.png)
        
1. On the **Task settings** page, configure the following settings:

    - **Target column**: IceCreamsSold **(1)**

    - Select **View additional configuration settings (2)** under Target Column:
        - Primary metric: **R2 score** **(3)**
        - Explain best model: **Unselected** **(4)**
        - Use all supported models: **Unselected**.  
        - Allowed models: Select only **RandomForest** and **LightGBM** **(5)** - normally you'd want to try as many as possible, but each model added increases the time it takes to run the job. Then click on **Save (6)**.

          ![](media/lab1-e1t2p9.png)

    - **Limits**: **Expand this section**
        - Use the limits to end the training job early based on specific criteria. In this exercise, set the following limits:
        - Metric score threshold: **0.9** **(1)**
        - Experiment Timeout (minutes): **15** **(2)**
        - Click **Next (3)**

          ![](media/lab1-e1t2p10.png)

          >**Note:** It's important to set these limits when using Azure Machine Learning, as running training jobs for every possible algorithm and featurization combination could potentially take hours.

1. On the **Compute** page, configure the following settings:

    - **Select compute type**: Serverless **(1)**
    - **Virtual machine type**: CPU **(2)**
    - **Virtual machine tier**: Dedicated **(3)**
    - **Virtual machine size**: Standard_DS3_V2 **(4)**
    - **Number of instances**: 1 **(5)** and then select **Next (6)**

      ![](media/lab1-e1t2p11.png)

1. Select **Submit training job**. It starts automatically.

   ![](media/lab1-e1t2p12.png)

1. Wait for the job to finish. It might take around `10-15 minutes`, while now might be a good time for a coffee break!

**Review the best model**

When the automated machine learning job has completed, you can review the best model it trained.

1. On the **Overview** tab of the automated machine learning job, note the best model summary.

    ![](media/T2S11-0707.png)

    > **Note**: The Warning message under the status "Warning: User specified exit score reached...". This is an expected message. Please continue to the next step.
  
1. Select the text under **Algorithm name** for the best model to view its details.

    ![](media/lab1-e1t3p2.png)

    - **Overview:** General details for the child job.

      ![](media/lab1-e1t3p2(1).png)

    - **Model:** Information about the model that was trained.

      ![](media/lab1-e1t3p2(2).png)

    - **Metric:** Select the **Metrics** tab and select the **residuals** and **predicted_true** charts if they are not already selected. 

      ![](media/lab1-e1t3p3.png)

      >**Note:** Review the charts which show the performance of the model. The **residuals** chart shows the *residuals* (the differences between predicted and actual values) as a histogram. The **predicted_true** chart compares the predicted values against the true values.

    - **Outputs and logs:** Information logged during the training process.

      ![](media/lab1-e1t3p2(3).png)

### Task 3: Deploy and test the model

1. On the **Model** tab for the best model trained by your automated machine learning job, select **Deploy (1)** and select the **Real-time endpoint (2)**. 

    ![](media/lab1-e1t3p4.png)

1. On the Deploy window, select the following settings and click on **Deploy (8)**:

   - **Instance count**: 3 **(1)** 
    - **Virtual machine**: Standard_DS3_v2 **(2)**
    - **Endpoint**: New **(3)**
    - **Endpoint name**: *Leave the default name* **(4)**
    - **Deployment name**: *Leave default* **(5)**
    - **Inferencing data collection**: *Disabled* **(6)**
    - **Package Model**: *Disabled* **(7)**

      ![](media/lab1-e1t3p5.png)

1. Wait for the **Deploy status** to change to *Succeeded*. This may take 5-10 minutes.

   >**Note**: Check the **Notifications** bar to verify the status of the operation.

### Task 4: Test the deployed service

Now you can test your deployed service.

1. In **Azure Machine Learning** studio, on the left-hand menu, select **Endpoints (1)** and open the **Real-time endpoints (2)** in the page.

    ![](media/lab1-e1t3p6.png)

1. On the *real-time endpoint* page view the **Test** tab.

    ![](media/lab1-e1t3p7.png)

1. In the **Input data to test endpoint** pane, replace the template JSON with the following input data **(1)**:

    ```json
    {
    "input_data": {
        "columns": [
            "DayOfWeek",
            "Month",
            "Temperature",
            "Rainfall"
        ],
        "index": [0],
        "data": [["Wednesday","June",70.5,0.05]]
     }
    }
    ```

1. Click the **Test (2)** button.

    ![](media/lab1-e1t3p8.png)

1. Review the test results, which include a predicted number of ice creams sold based on the input features - similar to this:

    ```JSON
    [
      121.98976731059767
    ]
    ```

    The test pane took the input data and used the model you trained to return the predicted number of ice creams sold.

Let’s review what you have done - you used a dataset of historical ice cream sales data to train a model. The model predicts the number of ice creams expected to be sold on a given day, based on seasonal and meteorological features.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

  <validation step="aa2662f4-59fd-4d38-9d2f-201214b4f21b" />

## Summary

In this module, you have learned how to use automated machine learning in Azure Machine Learning to train a model that predicts the number of ice creams expected to be sold on a given day, based on seasonal and meteorological features. You also learned how to deploy the model as a real-time endpoint and test it with sample input data.
  
### Congratulations! You have successfully completed this lab.
