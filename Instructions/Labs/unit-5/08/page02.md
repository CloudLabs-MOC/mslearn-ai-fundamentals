# Hands-On-Lab: Exploring AI libraries and Tools

In this hands-on lab, you will explore AI and ML tools in Python and Azure ML Studio by building a machine learning pipeline. You will create an Azure ML workspace, upload and preprocess a dataset, and build a Linear Regression model to predict a team’s win percentage. The lab guides you through configuring compute resources, splitting data, training the model, and evaluating its performance using Azure ML Designer.

## Lab Objectives

In this lab, you will be able to complete the following tasks:

- Task 1: Create Azure ML Workspace
- Task 2: Upload the Dataset
- Task 3: Preprocessing Our Data
- Task 4: Add Select Columns in Dataset Component
- Task 5: Choose Features and Target Column and Add Split Data Module
- Task 6: Add and Configure Linear Regression and Train Model Module
- Task 7: Add and Configure Score Model and Evaluate Model
- Task 8: Configure Pipeline Job Basics and Run the Pipeline

## Architecture diagram
![](../images/unit5-lesson(8).png)

## Task 1: Create Azure ML Workspace

In this task you will set up an Azure Machine Learning workspace where all your machine learning assets and experiments will be organized and run. You will learn how to create a workspace in the Azure ML Studio, select the appropriate region and resource group, and navigate to the Designer interface to start building your pipeline.

1. Open a new tab in the browser, right-click on the following link [Azure Machine Learning Studio](https://ml.azure.com/), then **Copy link** and paste it in a new browser tab to log in to **Azure Machine Learning Studio**.

1. If prompted, provide the credentials below:

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

   - **Password:** <inject key="AzureAdUserPassword"></inject>
   
1. On the **Create a new workspace to get started with Azure ML** fill in the following fields:

   - **Name:** **ClemsonWinPredictor_<inject key="DeploymentID" enableCopy="false"/> (1)**  
   - **Friendly Name:** *(Optional)*  
      Azure will auto-fill this based on the name.
   - **Hub (Optional):** Leave this as “None” unless instructed otherwise **(2)**.
   - **Advanced Settings:**
   - **Subscription:** Select the appropriate Azure subscription from the dropdown. 
   - **Resource Group:** **ODL-SREB-<inject key="DeploymentID" enableCopy="false"/> (3)** 
   - **Region:** Select **<inject key="Region" enableCopy="false" /> (4)** for better performance.
   - After filling out all the required fields, click the **Create (5)** button.

        ![](../images/u5-l8-1.png) 

    >**Note:** If you **did not** see the page like Figure 1, simply click **“Create Workspace”** on your dashboard and fill out the fields as described in Step 2.

1. Now navigate to your newly created workspace. On the **left-hand menu**, click **Workspaces (1)**. Locate the workspace you just created **ClemsonWinPredictor_<inject key="DeploymentID" enableCopy="false"/> (2)**.

     ![](../images/u5-l8-2.png) 
   
1. Click on its name to open it. This will take you inside the workspace where you can build and run machine learning experiments.

    ![](../images/u5-l8-3.png) 

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

<validation step="edbc0978-37e1-4c4f-86b3-c450ca55b053" />

## Task 2: Upload the Dataset

In this task you will upload the SREB U5 L8 CleanedDataset data to your Azure ML workspace. You will create a tabular dataset from a local CSV file, configure the data source, and add it to your pipeline canvas for further processing.

1. Once you are inside your workspace PCA Anomaly Model, look at the left hand side menu to find the **Designer** tab under the **Authoring** section. Click on 
this tab.

    ![](../images/lab01-image5.png) 

   >**Note:**  This will open the Azure Machine Learning Designer interface where you can  begin creating your machine learning pipeline by dragging and dropping 
components.

1. Once the **Designer** page is loaded, make sure that you’re on the **Classic prebuilt** tab under the **New pipeline** section. From here, click on the box with a **➕ (plus icon)** that says, **Create a new pipeline using classic prebuilt components**.

    ![](../images/lab01-image6.png) 

1. On the **left panel**, under the **Data (1)** tab, click the **➕ (plus icon) (2)** to upload a dataset.  

    ![](../images/u5-l8-4.png) 

1. On **Create a new workspace to get started with Azure ML** page enter the following data then click on **Next (2)**.

   - Name the dataset: **Clemson_Dataset** **(1)** 
  
      ![](../images/U5lab08-image4.png) 

1. On the **Choose a source for your data asset** page, choose **From local files (1)** the click on **Next (2)**. 

    ![](../images/u5-l8-5.png) 

1. On the **Select a datastore** page select the following option:  
   
   - Under **Datastore type**, select **Azure Blob Storage (1)**
   
   - Choose the datastore named: **workspaceblobstore (2)**
   
   - Click **Next (3)**  

     ![](../images/lab01-image10.png)

1. On the **Choose a file or folder** page, select **Upload files or folder (1)** from the dropdown, then select **Upload files (2)**.

    ![](../images/lab01-image11.png) 

1. **File or Folder Selection**  
   
   - In the file browser, navigate to `C:\Labs\Allfiles\unit5-lesson8` and then select the file: `SREB_U5_L8_CleanedDataset` **(1)**  
   
   - Wait for the file to appear under Upload list  
   
   - Click **Next (2)**  

     ![](../images/U5lab08-image5.png) 

1. On the **Settings** page, review the fields and ensure they match the expected format then click **Next**  

    ![](../images/u5-l8-6.png)

1. On the **Schema** page, ensure the schema fields are correctly recognized then click **Next**  

    ![](../images/u5-l8-7.png)

1. On the **Review** page, click **Create** to finalize the dataset upload

   ![](../images/U5lab08-image9.png) 

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

<validation step="ec9fb2a9-f6d8-4715-af1c-733319e81e12" />

## Task 3: Preprocessing Our Data

In this task you will prepare your dataset for modeling by **Clemson_Dataset** values. You will add and configure the **Clemson_Dataset** component to handle incomplete or missing sensor readings, ensuring the dataset is reliable for training your anomaly detection model.

1. Under the **Data (1)** tab, locate the uploaded dataset named **Clemson_Dataset (2)**.

1. Drag **Clemson_Dataset** onto the canvas **(3)**.

    ![](../images/U5lab08-image6.png)

## Task 4: Add Select Columns in Dataset Component

In this task, you will add Select Columns in Dataset Component that filter your dataset to include only the columns (features) relevant to your machine learning model. This helps improve model performance and reduces unnecessary complexity.

1. Switch to the **Component (1)** tab and search for **Select Columns in Dataset (2)**. Then drag the component into your canvas **(3)**, placing it below the **Clemson_Dataset**.

    ![](../images/U5lab08-image7.png)

1. Connect the output circle of the dataset module to the input of this module

    ![](../images/U5lab08-image8.png)


## Task 5: Choose Features and Target Column and Add Split Data Module

In this task, you will split your cleaned dataset into training and testing sets, choose a Linear Regression model, and train it using historical data to predict team performance.

1. Double click on the **Select Columns in Dataset** module. In the right panel, click **Edit column** selection.

     ![](../images/U5lab08-image11.png)

1. Select **Column names** and then type or select all these columns **Rk, Year, W, L, T, Conf_W, Conf_L, Conf_T, Conf_Pct, SRS, SOS, AP_Pre, AP_High, AP_Post, CFP_High, CFP_Final, Pct** **(1)** and then **Save (2)**.

    ![](../images/U5lab013-image37.png)
     
1. Click on **Save**.

    ![](../images/U5lab08-image13.png)

1. Switch to the **Component (1)** tab in the left panel and search for **Split Data (1)**. Then drag the component into your canvas **(3)**.

    ![](../images/U5lab08-image14.png)

1. Connect it to the output of **Select Columns in Dataset** to **Split Data**.

     ![](../images/U5lab08-image15.png)

1. Double click on the **Split Data module (1)** and configure the following then click on **Save (4)**.

   a. Fraction of rows in the first output dataset: 0.8 (80% training) **(2)**

   b. Leave Stratified split as default **(3)**.  

      ![](../images/U5lab08-image16.png)

## Task 6: Add and Configure Linear Regression and Train Model Module

In this task, you will test your trained model on unseen data, evaluate its performance using scoring metrics, and run the full machine learning pipeline using Azure ML’s compute resources.

1. Switch to the **Component (1)** tab in the left panel and search for **Linear Regression (2)**. Then drag the component into your canvas **(3)** beside the Split Data component **(4)**.
   
1. Drag the **Linear Regression** module onto the canvas as shown in the below image.

    ![](../images/U5lab08-image17.png)

1. Switch to the **Component (1)** tab in the left panel and search for **Train Model (2)**. Then drag the component into your canvas **(3)** as shown in the below image **(4)**.

    ![](../images/U5lab08-image18.png)

1. Connect:

   - Left input → output of Linear Regression **(1)**
   - Right input → first output of Split Data **(2)**

      ![](../images/U5lab08-image19.png)

1. Double click on the **Train Model (1)** module. In the right panel, click **Edit column (2)** selection.

    ![](../images/u5-l8-8.png)

1. Set the Label column: Enter **Pct (1)** then click **Save (2)**.

    ![](../images/U5lab08-image20.png)

1. This step trains the regression model using the training portion of the data

## Task 7: Add and Configure Score Model and Evaluate Model

1. Switch to the **Component (1)** tab in the left panel and search for and search for **Score Model (2)**. Then drag the component into your canvas **(3)** as shown in the below image.

   **Connect:**

   a. Left input → output of Train Model **(4)**

   b. Right input → second output of Split Data (test data) **(5)**

      ![](../images/U5lab08-image21.png)

1. This module applies the trained model to the test dataset and generates 
predictions

1. On the **Component (1)** tab in the left panel and search for **Evaluate Model (2)**. Then drag the component into your canvas **(3)** as shown in the below image.

   **Connect:**
    
    - Connect the output of Score Model to the left input of Evaluate Model **(5)**. Leave the second (right) input empty, since only one model is being evaluated

      ![](../images/U5lab08-image22.png)

1. This module calculates performance metrics for the regression model.
   
1. Click **Save (1)** at the top right. Then select the **Configure & Submit (2)** button in the top-right corner.

     ![](../images/u5-l8-9.png) 

1. Now that your pipeline is fully built with all the components connected—from data ingestion to anomaly scoring—you’re ready to run it.

## Task 8: Configure Pipeline Job Basics and Run the Pipeline

In this task you will configure the details needed to run your pipeline, including setting up a new experiment and creating a compute cluster. You will submit the pipeline job to Azure ML to execute your workflow.

1. On the **Basics** page, perform the steps as mentioned below:

   - In the Experiment name select **Create new (1)**
   - In **New experiment name** filed provide **`Test_ClemsonWinPredictor` (2)**
   - Click the blue **Next (3)** button at the bottom-right corner of the screen

      ![](../images/U5lab08-image24.png) 

1. On the **Inputs & outputs** page, click on **Next** to skip.

1. On the Runtime Settings page, from the dropdown of the **Select Compute Type** section, click on **Compute Cluster (1)**. Since no cluster is currently available, we’ll need to create one. Click on **Create Azure ML Compute Cluster (2)**.

    ![](../images/u5-l8-10.png) 

1. On the **Select virtual machine** page, specify the following then click on **Next:**
  
    - Location: Confirm that the selected region is the same as your workspace **<inject key="Region" enableCopy="false" /> (1)**
    
    - Virtual Machine Tier: Leave as default **(2)**
    
    - Virtual Machine Type: Keep this as **CPU** (sufficient for our anomaly detection task) **(3)**

    - Virtual Machine Size: Choose **Standard_DS11_v2 (4)**
  
      ![](../images/ag2.png)

1. On the **Configure Settings** page, provide Compute name **Compute-cluster-<inject key="DeploymentID" enableCopy="false"/> (1)** then click on **Create (2)**

    ![](../images/lab07-image34.png)

1. Back on the **Runtime Settings** page, select the newly created **Azure ML compute cluster (1)** from the dropdown in the **Select Azure ML compute cluster** field, then click on **Review + Submit (2)**.

     ![](../images/lab07-image35.png)

      >**Note:** The creation of the compute cluster takes approximately 3–5 minutes. You’ll be able to select the cluster only after it’s fully created. Please wait until the process is complete, and keep refreshing the cluster.

1. On **Review + Submit** page, click on **Submit**. 

     ![](../images/lab07-image36.png)

1. Once submitted, a success notification appears at the top of the page. Click on **View details** to monitor the pipeline. It may take some time for the pipeline to complete.

      ![](../images/u5-l8-11.png)

1. Please wait for the pipeline to complete, which may take approximately `10–15` minutes. Once the **Pipeline** is Completed, you can see the similar result.

     ![](../images/U5lab08-image26.png) 

1. Double click on **Evaluation metrics** review the evaluation metrics values in Azure.

   ![](../images/U5lab08-image25.png) 
    
   >**Note:** Both the Jupyter Notebook and Azure ML pipelines were used to train a Linear Regression model to predict team win percentage (Pct) using the same input features!

## Resource Cleanup

> **NOTE:** Perform this task only if you are completed with the lab and no longer require Machine Learning Workspace.

1. Navigate back to Azure portal. In the Search bar, search for **Azure Machine Learning (1)** and select **Azure Machine Learning (2)** from the list.

    ![](../images/aml-cleanup-01.png)

1. Select the workspace **ClemsonWinPredictor_<inject key="DeploymentID" enableCopy="false"/>**.

    ![](../images/u5-l8-12.png)

1. Click on **Delete (1)**, there will a Delete Resource window opened at the right, select the **checkbox (2)** next to Delete this resource permanently. Provide the workspace name **ClemsonWinPredictor_<inject key="DeploymentID" enableCopy="false"/> (3)** to confirm deletion and click on **Delete (4)**.

    ![](../images/u5-l8-13.png)

## Review

In this lab, you have completed the following tasks:

- Task 1: Created Azure ML Workspace
- Task 2: Uploaded the Dataset
- Task 3: Preprocessed Our Data
- Task 4: Added Select Columns in Dataset Component
- Task 5: Choosed Features and Target Column and Added Split Data Module
- Task 6: Added and Configured Linear Regression and Train Model Module
- Task 7: Added and Configured Score Model and Evaluate Model
- Task 8: Configured Pipeline Job Basics and Run the Pipeline

## You have successfully completed the lab  
