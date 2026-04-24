## Hands-On-Lab: Using Machine Learning to Detect Anomalies in Manufacturing

In this hands-on lab, you will build and deploy a machine‑learning pipeline in Azure Machine Learning Designer that detects anomalies in factory‑floor sensor data using Principal Component Analysis (PCA), connects to external data storage for scalable ingest, and triggers simulated robotic responses when potential machine failures are identified.

## Lab Objectives

In this lab, you will be able to complete the following tasks:

- Task 1: Create Azure ML Workspace
- Task 2: Upload Our Dataset
- Task 3: Preprocessing our Data
- Task 4: Split Data
- Task 5: Adding Detection Models 
- Task 6: Convert and View Results
- Task 7: Configure Pipeline Job Basics 
- Task 8: Explore the Output with Azure's Built-In Visualization Tools

## Architecture diagram

![](../images/unit4-lesson4.png) 

### Task 1: Create Azure ML Workspace

In this task, you will set up an Azure Machine Learning workspace where all your machine learning assets and experiments will be organized and run. You will learn how to create a workspace in the Azure ML Studio, select the appropriate region and resource group, and navigate to the Designer interface to start building your pipeline.

1. Open a new tab in the browser, right-click on the following link [Azure Machine Learning Studio](https://ml.azure.com/), then **Copy link** and paste it in a new browser tab to log in to **Azure Machine Learning Studio**.

1. If prompted, provide the credentials below:

   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>

   - **Password:** <inject key="AzureAdUserPassword"></inject>

1. On the **Create a new workspace to get started with Azure ML** page, fill in the following fields:

   - **Name**: Enter **PCA_Anomaly_Model<inject key="Deployment ID" enableCopy="false"></inject> (1)**
   - **Friendly Name**: *(Optional)* — Azure will auto-fill this based on the name.
   - **Hub (Optional)**: Leave this as **None** unless instructed otherwise **(2)**
   - **Advanced Settings**:
     - **Subscription**: Select the appropriate Azure subscription from the dropdown **(3)**
     - **Resource Group**: Select **ODL-SREB-U4L4** **(4)**
     - **Region**: Select **<inject key="Region" enableCopy="false" />** **(5)** for better performance.

   - After filling out all the required fields, click the **Create** **(6)** button.

     ![](../images/ag1.png)

      > **Note**: If you **did not** see the page like Figure 1, simply click **“Create Workspace”** on your dashboard and fill out the fields as described in Step 3.

1. Wait for the workspace to create — it may take around 2–3 minutes.

1. Now navigate to your newly created workspace. On the **left-hand menu**, click **Workspaces** **(1)**. Select the workspace you just created **PCA_Anomaly_Model<inject key="Deployment ID" enableCopy="false"></inject> (2)**.

   ![](../images/lab01-image3.png)

1. This will take you inside the workspace where you can build and run machine learning experiments.

   ![](../images/lab01-image4.png)

1. Once you are inside your workspace `PCA_Anomaly_Model`, look at the left-hand side menu and select the **Designer** tab under the **Authoring** section.

   ![](../images/lab01-image5.png)

   > **Note**: This will open the Azure Machine Learning Designer interface where you can begin creating your machine learning pipeline by dragging and dropping components.

1. Once the **Designer** page is loaded, make sure that you’re on the **Classic prebuilt** **(1)** tab under the “New pipeline” section. From here, click on the box with a plus sign that says **Create a new pipeline using classic prebuilt components** **(2)**.

   ![](../images/nc2.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
>
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

<validation step="e7587121-668b-41b5-abc2-ec1d3900848d" />

---

### Task 2: Upload Our Dataset

In this task, you will upload the anomaly data to your Azure ML workspace. You will create a tabular dataset from a local CSV file, configure the data source, and add it to your pipeline canvas for further processing.

1. On the **left panel**, under the **Data** **(1)** tab, click the **➕ (plus icon)** **(2)** to upload a dataset.

   ![](../images/lab01-image7.png)

1. On the **Create data asset** page, enter the following information:

   - **Name**: Enter `anomaly_dataset_manufacturing` **(1)**
   - **Select type**: Choose **Tabular** **(2)**
   - Click **Next** **(3)**

     ![](../images/lab01-image8.png)

1. On the **Choose a source for your data asset** page, choose **From local files (1)** the click on **Next (2)**. 

   ![](../images/lab01-image9.png) 

1. On the **Select a datastore** page select the following option:  
    
    - Under **Datastore type**, select **Azure Blob Storage (1)**  
    - Choose the datastore named: **`workspaceblobstore` (2)**  
    - Click **Next (3)**  

      ![](../images/lab01-image10.png) 

1. On the **Choose a file or folder** page, select **Upload files or folder (1)** from the dropdown, then select **Upload files (2)**.

   ![](../images/lab01-image11.png)  

1. **File or Folder Selection**  

    - In the file browser, navigate to  `C:\Labs\Allfiles\unit4-lesson4` and then select the file: `anomaly_data.csv` **(1)** 
    - Wait for the file to appear under “Upload list”  
    - Click **Next (2)**  

      ![](../images/lab01-image12.png) 

1. On the **Settings** page, review the fields and ensure they match the expected format then click **Next**  

   ![](../images/lab01-image13.png) 

1. On the **Schema** page, ensure the schema fields are correctly recognized then click **Next**  

   ![](../images/lab01-image14.png) 

1. On the **Review** page, click **Create** to finalize the dataset upload

   ![](../images/lab01-image15.png) 

1. Under the **Data** tab, locate the uploaded dataset named **`anomaly_dataset_manufacturing`**.  

   ![](../images/lab01-image16.png)          

1. Click on the dataset card. **Drag it from the left panel** and **drop it onto the empty space in the pipeline canvas on the right (1)** and then **Save (2)**.

   ![](../images/nc3.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
>
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

<validation step="2bbe0a28-d6c1-4fd6-b4d3-63ff8be787f2" />

---   
     
### Task 3: Preprocessing our Data

In this task, you will clean missing values from the sensor_reading column in the dataset using the Clean Missing Data component. This prepares the data for accurate model training by handling incomplete entries.

1. Drag the **anomaly_dataset_manufacturing** dataset into the canvas.

   ![](../images/ncc1.png) 

1. Switch to the **Component (1)** tab and search for **"Clean Missing Data" (2)** by Microsoft. Click on the **Clean Missing Data (3)** data component,  
    
   ![](../images/lab01-image20.png) 

1. Then drag it from the left panel and drop it below the **Dataset card** in the pipeline canvas on the right.

   ![](../images/cn4.png) 

1. Now connect the Dataset to the Cleaning Component, hover over the small **circle at the bottom** of the dataset block labeled **Data output (1)**. Click and **drag a line** to the **left circle** of the Clean Missing Data component labeled **Dataset (2)**. Save your progress by clicking **Save (3)** at the top right of the canvas.

   ![](../images/lab01-image21.png)     

1. Now you will Configure the Clean Missing Data component. Double-click the **Clean Missing Data (1)** block on the canvas. Then click the blue **Edit column (2)** link next to **Columns to be cleaned**. This will open a pop-up window.  

   ![](../images/lab01-image23.png) 

1. Select only **sensor_reading (1)** - Do **not** include columns like `timestamp`, `machine_id`, or `anomaly_flag`. Click **Save (2)** in the pop-up,

   ![](../images/lab01-image24.png) 

1. Click **Save** again on the main screen.  

   ![](../images/lab01-image25.png)     

### Task 4: Split Data

In this task, you will split the cleaned dataset into training (70%) and testing (30%) sets using the Split Data component. This ensures a randomized and consistent data division for model evaluation.

1. Switch to the **Component (1)** tab, search for **Split Data (2)** by Microsoft and then drag it from the left panel and drop it below **Clean Missing Data** in the pipeline canvas on the right **(3)**.

    ![](../images/cn5.png)     

1. Connect the **Cleaning Component** to the **Split Data** Component by hovering over the small circle at the bottom of the **Clean Missing Data**. Then, **click and drag a line to the circle of the Split Data component**

    ![](../images/cn6.png)  

1. Save your progress by clicking **Save** at the top right of the canvas.

1. Double-click the **Split Data block (1)** on your canvas. The settings panel will appear on the right-hand side.

    - Under **Splitting mode**, make sure **Split Rows (2)** is selected. (This means the data will be divided by rows, not by columns)
    - In the field labeled **Fraction of rows in the first output dataset**, type:`0.7` **(3)**. This means 70% of your data will be used for training, and the remaining 30% for testing.
    - Ensure **Randomized split** is set to: **True (4)** (This ensures a random and fair mix of rows in each set)
    - In the **Random seed** field, type: `42` **(5)**. This ensures that every time you run the pipeline, the data is split the same way. This is useful for consistency across student runs
    - Confirm **Stratified split** is set to: **False (6)**
    - Click **Save (7)** at the top of the page to lock in your configuration

      ![](../images/nc4.png)    

### Task 5: Adding Detection Models 

In this task, you will train a PCA-Based Anomaly Detection model using the training dataset and score it using the testing dataset. This helps identify anomalies and evaluate the model’s performance.

1. On the **Component (1)** tab, search for **PCA-Based Anomaly Detection (2)**. Then **Drag** the **PCA-Based Anomaly Detection** component into the canvas **(3)**.

    ![](../images/nc5.png)
   
     >**Note**: This is a built-in model that detects outliers in time-series data using **Principal Component Analysis**.

1. Now that the **PCA-Based Anomaly Detection model** has been added, the next step is to train that model using your cleaned dataset. For this, you’ll add the **Train Anomaly Detection Model** component. This component will receive:

    - Your untrained model (from the PCA component)
    - The cleaned data (from the Clean Missing Data component)     

1. In the **Component (1)** tab, search for **Train Anomaly Detection Model (2)**. Select the **Train Anomaly Detection Model (3)**. Drag the component into your canvas, placing it below the **PCA-Based Anomaly Detection** block **(4)**.  

    ![](../images/lab01-image27.png)  

1. Once added, 
    - You’ll connect the **Untrained model output** from the **PCA-Based Anomaly Detection** to the **Model input** of **Train Anomaly Detection Model** **(1)**

    - The **left output of Split Data** to the respective **Dataset input ports of this Train Anomaly Detection Model** component **(2)**     

    - Then select **Save (3)**

      ![](../images/nc6.png)

1. The next step is to score the dataset. For this, we’ll use the **Score Model**. The Score Model runs predictions using your **trained anomaly detection model**. It will output:

    - Predicted labels (normal or anomaly)
    - Confidence scores or probabilities, depending on the model type

    - These results will be used in the next step for visualizing and interpreting model performance     

1. In the left pane under the **Component (1)** tab, search for **“Score Model” (2)** by Microsoft. Drag the **Score Model** component into your canvas and place it below the **Train Anomaly Detection Model** component **(3)**. 

    ![](../images/nc7.png) 

1. Connect:

    - Connect the **“Trained model”** output from the **Train Anomaly Detection Model** component to the **“Trained model”** input of the **Score Model** **(1)**  

    - Connect the **“Right”** output from the **Split Data** component to the **“Dataset”** input of the **Score Model (2)**

      >**Note**: This ensures that your newly trained model is being used to score the test data

    - Select **Save (3)**

      ![](../images/nc8.png) 


### Task 6: Convert and View Results

In this task, you’ll convert the model’s scored output into a format suitable for visualization using the Convert to Dataset component. This enables you to inspect anomaly predictions and analyze model performance in Azure ML Designer.

1. In the left-side pane under the **Component (1)** tab, search for the **Convert to Dataset (2)** Component by Microsoft. This tool takes the output from the model and converts it to a format that can be visualized in the Designer.

    - Drag the **Convert to Dataset** component onto the canvas and place it under the **Score Model component (3)**

      ![](../images/nc9.png) 

1. Connect the **Scored dataset output** from the **Score Model** to the **Dataset input** of the **Convert to Dataset** component **(1)**. Once connected, click **Save (2)** at the top to preserve your updated pipeline.

    ![](../images/nc10.png) 

1. Now that the pipeline is fully built with all the components connected—from data intake to anomaly scoring—we're ready to run it to view our results.

    ![](../images/nc-11.png) 

1. First, let’s make sure all components are connected as shown. Confirm that:

    - The dataset flows through **Clean Missing Data**.
    - The **Split Data** connects to both:
        - Train Anomaly Detection Model
        - Score Model

    - **PCA-Based Anomaly Detection** is connected to the **Train component**.
    - **Score Model** connects to **Convert to Dataset**.

1. Save your pipeline, if not auto-saved already.

1. Click the **Configure & Submit** button in the top-right corner.   

    ![](../images/nc11.png) 

### Task 7: Configure Pipeline Job Basics    

In this task, you will configure the experiment settings, create a compute cluster, and submit your pipeline job for execution in Azure ML Designer.

1. On the **Basics**: First, for easy tracking, we’ll set up a new experiment.

    - Under **Experiment name**, select **Create new** **(1)**
    - In the field labeled **“New experiment name”**, type **Test_Anomaly_Manufacturing (2)**
    - The **Job Display Name** is automatically generated based on today’s date.
    - You may skip the Optional Fields section.
    - Click the blue **Next (3)** button at the bottom-right corner of the screen

      ![](../images/nc12.png)    

1. **Inputs & Outputs**: We'll skip the section by clicking **Next**.

    ![](../images/nc13.png) 

1. On the **Runtime Settings**, provide the following details:

    - **Select Compute Type** section, select **Compute Cluster** from the drop down **(1)**

    - Since no cluster is currently available, we’ll need to create one. Click on **Create Azure ML Compute Cluster (2)**.        

      >**Note**: This will open a new pane or pop-up for you to configure your compute cluster

       ![](../images/nc14.png) 

1. **Virtual Machine**: 

    - **Location**: Confirm that the selected region is the same as your workspace (**<inject key="Region" enableCopy="false" />**) **(1)**
    - **Virtual Machine Tier**: Leave as default. (do not select "Dedicated" or "Low priority" unless specified otherwise for cost-saving purposes) **(2)**
    - **Virtual Machine Type**: Keep this as **CPU (3)** 
    - **Virtual Machine Size**: Choose **Standard_DS11_v2 (4)**
    - Click **Next (5)**  

      ![](../images/ag2.png)     

1. **Advanced Settings**: Give a Compute Name as **Test (1)** and leave everything default. Then click **Create (2)**.

    ![](../images/nc16.png) 

1. Select the Compute Created **Test (1)** and click **Next (2)**.   

    ![](../images/nc17.png) 

     >**Note**: The creation of the compute cluster takes approximately 3–5 minutes. You’ll be able to select the cluster only after it’s fully created. Please wait until the process is complete, and keep refreshing the cluster.

1. Once on the **final** page, click **Submit**.     

    ![](../images/nc18.png) 

1. Once submitted, a success notification appears at the top of the page. Click on **'View details'** to monitor the pipeline. It may take some time for the pipeline to complete.

    ![](../images/nc-19.png)    

1. Please wait for the pipeline to complete, which may take approximately `10–15 `minutes. Once it's finished successfully, the status will show as **Completed**.

    ![](../images/nc20.png)  

1. Right-click on the **Convert to Dataset** component **(1)**. Hover over **Preview data (2)** to click on **Results dataset (3)**.

    ![](../images/nc21.png) 
    ![](../images/nc22.png) 

### Task 8: Explore the Output with Azure's Built-In Visualization Tools

In this task, you will register the scored results as a dataset and explore them using Azure ML’s visualization tools to understand model predictions and data distribution.

1. On the left-hand menu under the **Assets** section, click on **Jobs (1)**. Click on the experiment name **Test_Anomaly_Manufacturing (2)**.

   This is where you can view all the pipeline runs, including their: 
    - Status (e.g., completed, failed, running) 
    - Start time and duration 
    - Output data 
    - Visualizations and logs

      ![](../images/nc23.png) 

1. You will see the most recent pipeline execution. Click on your latest pipeline job run.

    ![](../images/nc24.png)

1. You can see the Successfully completed Pipeline.

    ![](../images/nc-24.png)

1. Scroll to the bottom of your pipeline diagram where the **Convert to Dataset** and **Score Model** output is `connected`. You will see the output labeled as **Results dataset**.    

    ![](../images/nc25.png)

1. Right-click on the  **Convert to Dataset** component **(1)**. From the right-click menu, hover over **“Register data” (2)** and then select **“Results dataset.” (3)**.   

    ![](../images/nc26.png)

    What This Does:

    - Registering the dataset makes it available under **Assets > Data > Datasets** in your Azure workspace. 
    - Once registered, you can explore it, reuse it in other pipelines, or visualize it using Azure ML’s built-in tools.

1. On the **Register as Dataset**,

    - Select **New data asset (1)**
    
    - **New data asset name** field, type **Model Output (2)**

    - In the **Data asset** type dropdown, choose **Tabular (3)**

    - Select **Save (4)**

      ![](../images/nc27.png)

1. **What Happens Next**: 

    - Your model output is now registered as a dataset asset. 
    - You can find it under the left-hand panel: **Assets > Data > Datasets** 
    - This lets you **explore, reuse, or visualize** the output in other ML experiments.      

1. From the left navigation pane, select **Data (1)** under **Assets**. Under **Datasets (2)** tab select **Model Output (3)** Data.

    ![](../images/nc28.png)

1. Select **Explore** tab, where you will see the table of your dataset. Select **Preview (2)**. This Preview view shows **(3)**: 
    - First 50 rows (out of your total dataset, like 1000 rows).
    - Columns like `timestamp, machine_id, sensor_reading, anomaly_flag, Scored Labels`, and `Scored Probabilities`.

      ![](../images/nc29.png)

      **The dataset includes**: 

      - `timestamp`: Time the sensor reading was recorded.
      - `machine_id`: Machine identifier (like CNC_Lathe, Injection_Molder).
      - `sensor_reading`: Numeric values from machine sensors.
      - `anomaly_flag`: Ground truth labels (0 = normal, 1 = anomaly).
      - `Scored Labels`: Predicted label from the model.
      - `Scored Probabilities`: Confidence of the model's prediction.  

1. At the top of the table, next to Preview, click **Profile**. This switches the view from basic table preview to deeper visual and statistical 
analysis of each column.

    ![](../images/nc30.png)

    **For each column, you see**: 
    - `Distribution Graphs` (bars showing how values are spread). 
    - `Type`: What kind of data it is (e.g., String, Integer, Date, Decimal). 
    - `Min/Max`: Minimum and maximum values. 
    - `Count`: How many entries (should match total rows, here 1000). 

1. Scroll down to the column you want to analyze. Select the **“Scored 
Labels”** column **(1)**. After selecting the column, a panel will appear on the right. From the dropdown at the top of that panel, choose **“Box and whisker plot.” (2)**.

    What This Does **(3)**: 

    **Box and whisker plots** help you understand the distribution of the column's values. 
    You will see: 
    - Minimum and maximum values 
    - Quartiles (Q1, Median, Q3) 
    - Mean (average)

      ![](../images/nc31.png)

1. You can also View **Histogram** of **“Scored Labels”** in Azure ML Studio.

1. Scroll down and click on the **“Scored Labels (1)”** column. 

    - On the right-side panel, locate the dropdown menu labeled with the current visualization type (e.g., **"Box and whisker plot"**). 

    - Click the dropdown and select **“Histogram.” (2)**

    - The histogram will now display the distribution of the model's predictions (0 for normal, 1 for anomaly).

      ![](../images/nc32.png)
      
### Resource Cleanup

> **NOTE:** Perform this task only if you are completed with the lab and no longer require Machine Learning Workspace.

1. Navigate back to Azure portal. In the Search bar, search for **Azure Machine Learning (1)** and select **Azure Machine Learning (2)** from the list.

    ![](../images/aml-cleanup-01.png)

1. Select the workspace **PCA_Anomaly_Model<inject key="Deployment ID" enableCopy="false"></inject>**.

    ![](../images/aml-cleanup-U4L03.png)

1. Click on **Delete (1)**, there will a Delete Resource window opened at the right, select the **checkbox (2)** next to Delete this resource permanently. Provide the workspace name **PCA_Anomaly_Model<inject key="Deployment ID" enableCopy="false"></inject> (3)** to confirm deletion and click on **Delete (4)**.

    ![](../images/aml-cleanup-U4L03-1.png)

## Review

In this lab, you have completed the following tasks:

- Created Azure ML Workspace
- Uploaded Dataset
- Preprocessed our Data
- Split Data
- Added Detection Models 
- Converted and View Results
- Configured Pipeline Job Basics 
- Explored the Output with Azure's Built-In Visualization Tools

## You have successfully completed the lab
