# Module 01: Explore Automated Machine Learning in Azure Machine Learning

## Lab overview

In this exercise, you'll use the automated machine learning feature in **Azure Machine Learning** to train and evaluate a machine learning model. You'll then deploy and test the trained model.

## Lab Objectives

In this lab, you will perform:

- Task 1: Creating an *Azure Machine Learning workspace* resource
- Task 2: Use automated machine learning to train a model
- Task 3: Deploy the model

## Exercise 1: Explore Automated Machine Learning in Azure Machine Learning

### Task 1: Create an Azure Machine Learning workspace

In this task, you will create an Azure Machine Learning workspace. You will search for Machine Learning, configure the necessary settings like subscription, resource group, and workspace name, and deploy the resource. Once deployed, you will access the workspace through Azure Machine Learning Studio.

1. In the Azure Portal, select **+ Create a resource** and search for **Machine Learning**.

    ![Picture1](media/ai900mod1img1.png)

2. In the Marketplace page search for **Azure Machine Learning (1)** and Select **Azure Machine Learning (2)**.
 
   ![Picture1](media/ai900-12.png)

3. On the **Azure Machine Learning** page, click **Create** to proceed.

   ![Picture1](media/ai900mod1cimg2.png)
  
4. Create a new **Azure Machine Learning** resource with an *Azure Machine Learning* plan. Use the following settings:

    - **Subscription**: Use existing Azure subscription. **(1)**
    - **Resource group**: Select **AI-900-Module-01-<inject key="DeploymentID" enableCopy="false" />** **(2)**
    - **Name**: Give name **AI-900-Workspace-<inject key="DeploymentID" enableCopy="false" /> (3)**
    - **Region**: Select <inject key="location" enableCopy="false" /> **(4)**
    - **Storage account**: Note the default new storage account that will be created for your workspace. **(5)**
    - **Key vault**: Note the default new key vault that will be created for your workspace. **(6)**
    - **Application insights**: Note the default new application insights resource that will be created for your workspace. **(7)**
    - **Container registry**: None (one will be created automatically the first time you deploy a model to a container) **(8)**

5. Select **Review + create (9)**.

    ![](media/LABB1.png)

6. After successfully completing the validation process, click on the **Create** button located in the lower left corner of the page.

   ![](media/lab1-9.png)
   
7. Wait for deployment to complete(it can take a few minutes), and then click on the **Go to resource** button, this will take you to your workspace resource.

   ![](media/lab1-10.png)

8. Select **Launch studio** (or open a new browser tab and navigate to [https://ml.azure.com](https://ml.azure.com?azure-portal=true), and if prompted, sign into **Azure Machine Learning studio** using your Microsoft account). Close any messages that are displayed.

   ![](media/ai900-1.png)

9. In Azure Machine Learning studio, navigate to **Workspaces (1)**, you should see your newly created workspace **(2)**. If not, select **All workspaces** in the left-hand menu and then select the workspace you just created.

    ![Picture1](media/ai900-2.png)

#### Enable preview features

Some features of Azure Machine Learning are in preview and need to be explicitly enabled in your workspace.

1. In Azure Machine Learning Studio, click on **manage preview features** (the loud speaker icon - &#128363;).

     ![](media/lab1-5.png)

1. Enable the following preview feature, if not enabled.

     ![](media/lab1-7.png)

### Task 2: Use automated machine learning to train a model

In this task, you will learn how to use automated machine learning to train a model efficiently without writing extensive code.

Automated machine learning enables you to try multiple algorithms and parameters to train multiple models, and identify the best one for your data. In this exercise, you'll use a dataset of historical bicycle rental details to train a model that predicts the number of bicycle rentals that should be expected on a given day, based on seasonal and meteorological features.

> **Citation**: *The data used in this exercise is derived from [Capital Bikeshare](https://www.capitalbikeshare.com/system-data) and is used in accordance with the published data [license agreement](https://www.capitalbikeshare.com/data-license-agreement)*.

1. In [Azure Machine Learning studio](https://ml.azure.com?azure-portal=true), naviage to the **Automated ML (1)** page (under **Authoring**), select  **+ New Automated ML job (2)**.

   ![](media/ai900-3.png)  

1. Create a new Automated ML job with the following settings, using **Next (5)** as required to progress through the user interface:

    **Basic settings**:

    - **Job name**: mslearn-bike-automl **(1)**
    - **New experiment name**: mslearn-bike-rental **(2)**
    - **Description**: Automated machine learning for bike rental prediction **(3)**
    - **Tags**: *Leave default* **(4)**

       ![](media/1.png)

   **Task type & data**:

    - **Select task type**: Regression **(1)**
    - **Select data**: Select **+ Create (2)** 

        ![](media/lab1-25.png)

    - To create new data with the following settings:

         - **Data type**:
            - **Name**: `bike-rentals`
            - **Description**: `Historic bike rental data`
            - **Type**: Table (mltable)

              ![](media/ai900j1.png)
        - **Data source**:
            - Select **From local files**

              ![](media/ai900j2.png)
        - **Destination storage type**:
            - **Datastore type**: Azure Blob Storage
            - **Name**: workspaceblobstore

              ![](media/ai900j3.png)
        - **MLtable selection**:
            - **Upload folder**: Download and extract the contents of the folder from* [`https://aka.ms/bike-rentals`](https://aka.ms/bike-rentals), *which contains the two files you will need to upload. Once uploaded, click on **Next**.

              ![](media/ai900j4.png)

              ![](media/ai900j5.png)

              ![](media/ai900j6.png)
        - Select **Create**. 
  
           ![](media/ai900j7.png)
      
        - After the dataset is created, select the **bike-rentals (1)** dataset to continue to submit the Automated ML job. Select **Next (2)**

           ![](media/ai900j8.png)
        
    **Task settings**:

    - **Task type**: Regression
    - **Data**: bike-rentals
    - **Target column**: rentals (integer) (1)

       ![](media/ai900j9.png)

    - Select **View additional configuration settings (2)** under Target Column:
        - Primary metric: **Normalized root mean squared error** **(3)**
        - Explain best model: **Unselected** **(4)**
        - **Use all supported models**: <u>Un</u>selected.  *You'll restrict the job to try only a few specific algorithms.*
        - **Allowed models**: *Select only **RandomForest** and **LightGBM** (5) — normally you'd want to try as many as possible, but each model added increases the time it takes to run the job.*

    - **Limits**: *Expand this section*
        - Max trials: **3** **(1)**
        - Max concurrent trials: **3** **(2)**
        - Max nodes: **3** **(3)**
        - Metric score threshold: **0.085** **(4)** (*so that if a model achieves a normalized root mean squared error metric score of 0.085 or less, the job ends.*)
        - Experiment Timeout: **15** **(5)**
        - Iteration timeout: **15** **(6)**
        - Enable early termination: *Selected* **(7)**

          ![](media/ai900j10.png)

    - **Validation and test**:
        - **Validation type**: Train-validation split **(1)**
        - **Percentage validation of data**: 10 **(2)**
        - **Test dataset**: None **(3)** and then select **Next (4)**

          ![](media/ai900j11.png)

    **Compute**:
    - **Select compute type**: Serverless **(1)**
    - **Virtual machine type**: CPU **(2)**
    - **Virtual machine tier**: Dedicated **(3)**
    - **Virtual machine size**: Standard_DS3_V2 **(4)**
    - **Number of instances**: 1 **(5)** and then select **Next (6)**

      ![](media/ai900j12.png)

1. Select **Submit training job**. It starts automatically.

   ![](media/ai900j13.png)

1. Wait for the job to finish. It might take around `10-15 minutes`, while — now might be a good time for a coffee break!

**Review the best model**

When the automated machine learning job has completed, you can review the best model it trained.

1. On the **Overview** tab of the automated machine learning job, note the best model summary.

    ![](media/lab1-2.png)

    > **Note**: You may see a message under the status "Warning: User specified exit score reached...". This is an expected message. Please continue to the next step.
  
1. Select the text under **Algorithm name** for the best model to view its details.

    ![](media/ai900-4.png)

1. Select the **Metrics** tab and select the **residuals** and **predicted_true** charts if they are not already selected. 

    ![](media/ai900--5.png)

    >**Note:** Review the charts which show the performance of the model. The **residuals** chart shows the *residuals* (the differences between predicted and actual values) as a histogram. The **predicted_true** chart compares the predicted values against the true values.

### Task 3: Deploy and test the model

1. On the **Model** tab for the best model trained by your automated machine learning job, select **Deploy (1)** and use the **Real-time endpoint (2)** option to deploy the model with the following settings:

   - **Instance count**: 3 (1) 
    - **Virtual machine**: Standard_DS3_v2 (2)
    - **Endpoint**: New (3)
    - **Endpoint name**: *Leave the default name* (4)
    - **Deployment name**: *Leave default* (5)
    - **Inferencing data collection**: *Disabled* (6)
    - **Package Model**: *Disabled* (7)

    ![](media/ai900j15.png)

    ![](media/ai900j16.png)

1. Select **Deploy (8)**

1. Wait for the **Deploy status** to change to *Succeeded*. This may take 5-10 minutes.

   >**Note**: Check the **Notifications** bar to verify the status of the operation.

### Task 4: Test the deployed service

Now you can test your deployed service.

1. In Azure Machine Learning studio, on the left hand menu, select **Endpoints** and open the **Real-timeendpoint**. in the page.

1. On the *real-time endpoint* page view the **Test** tab.

    ![](media/ai900j17.png)

1. In the **Input data to test endpoint** pane, replace the template JSON with the following input data:

    ```json
      {
     "input_data": {
       "columns": [
         "day",
         "mnth",
         "year",
         "season",
         "holiday",
         "weekday",
         "workingday",
         "weathersit",
         "temp",
         "atemp",
         "hum",
         "windspeed"
       ],
       "index": [0],
       "data": [[1,1,2022,2,0,1,1,2,0.3,0.3,0.3,0.3]]
     }
    }

    ```

1. Click the **Test** button.

    ![](media/ai900j18.png)

1. Review the test results, which include a predicted number of rentals based on the input features - similar to this:

    ```JSON
    [
      357.5136388769763
    ]
    ```

    The test pane took the input data and used the model you trained to return the predicted number of rentals.

Let's review what you have done. You used a dataset of historical bicycle rental data to train a model. The model predicts the number of bicycle rentals expected on a given day, based on seasonal and meteorological *features*.

### Review
In this lab, you have completed the following tasks:
- Created an *Azure Machine Learning workspace* resource
- Utilized automated machine learning to train a model
- Deployed the model

Let me know if you'd like any changes!
  
## You have successfully completed this lab.
