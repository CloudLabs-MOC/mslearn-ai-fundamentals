# Exit Activity: Solving a Manufacturing Problem Using Azure

## Scenario

You work in a factory where machines are supposed to run smoothly 24/7. One day, your manager notices that **some machines are acting strangely** at random times, but no one knows why.

Your job is to use **Azure Machine Learning** to **detect unusual machine behaviors** using the anomaly detection notebook you built in class.

---

## Activity: Answer in `SREB_U4_L3_Handout`

1. **What kind of data would you collect from the machines?**
2. **Which Azure tool would you use to build this workflow?**
   _(Hint: You used it today)_
3. **How would you clean the data if it has missing values?**
   _(What step would you use?)_
4. **Which model or technique could you use to detect anomalies?**
   _(You trained this model today)_

---

## What Is This Workflow, Really?

A **notebook-based workflow in Azure Machine Learning** is a **step-by-step process** that moves data through several stages:

1. **Input Dataset**
   - You register a CSV file of sensor readings as a Data Asset, then load it into a pandas DataFrame
   - Example:

   | timestamp | machine_id      | sensor_reading | anomaly_flag |
   | --------- | --------------- | -------------- | ------------ |
   | 12:00 PM  | Hydraulic_Press | 50.5           | 0            |
   | 12:01 PM  | CNC_Lathe       | 49.9           | 0            |
   | 12:02 PM  | CNC_Lathe       | 62.3           | 1            |

2. **Clean Missing Data**
   - `df.isna().sum()` checks for missing values; `dropna().copy()` removes any incomplete rows
   - Example:

   **Before Cleaning**

   | sensor_reading | machine_id      |
   | -------------- | --------------- |
   | 50.5           | Hydraulic_Press |
   |                | CNC_Lathe       |
   | 62.3           | CNC_Lathe       |

   **After Cleaning**

   | sensor_reading | machine_id      |
   | -------------- | --------------- |
   | 50.5           | Hydraulic_Press |
   | 62.3           | CNC_Lathe       |

3. **Model (Isolation Forest)**
   - Detects abnormal behavior without ever seeing the `anomaly_flag` labels during training
   - Isolates readings that separate from the rest of the data in fewer steps than normal readings

4. **Prediction Output**
   - Adds predictions and anomaly scores to the dataset

   | Predicted_Label | Anomaly_Score |
   | --------------- | ------------- |
   | 0               | 0.02          |
   | 0               | 0.05          |
   | 1               | 0.71          |

---

## Saving Your Model's Output to External Storage

### Why?

Without saving, model results **disappear** once the notebook session ends. Use **Azure Blob Storage** to save:

- Predictions
- Logs
- Outputs for reporting and compliance

---

### How to Export to Azure Blob Storage

1. **Save the DataFrame as a CSV file** using `dataset.to_csv("anomaly_predictions.csv", index=False)`
2. **Create a `Data` object** describing the file, its type, name, and version
3. **Register it** by calling `ml_client.data.create_or_update(results_asset)`
4. **Run the cell** — Azure uploads the CSV to Blob Storage and creates a new Data Asset automatically

---

### Accessing the Output in Azure Portal

1. Go to **Azure Machine Learning Studio**
2. Select **Data** from the left navigation pane
3. Find the new Data Asset (e.g., `anomaly_predictions`)
4. Alternatively, open **Azure Portal → Storage Accounts** and locate your workspace's storage account
5. Open **Containers → Blob Storage** and download the predictions file directly

---

## Final Reflection: Saving Model Output

### Scenario

Your factory runs anomaly detection every hour, but results weren't saved properly. Now your manager wants anomaly records from the past **30 days**.

Your task:

- Decide **what to save**
- Decide **where and how often**
- Justify your decision

---

## Handout Questions (Complete in `SREB_U4_L3_Handout`)

1. **What type of data would you save from your anomaly detection notebook?**
2. **Why is it important to save the output outside the notebook?**
   (Give at least two reasons)
3. **What Azure component did you use to connect your notebook to external storage?**
4. **Where in the notebook did you add the export code?**
   _(Before which step, or after which result?)_
5. **If your factory wanted to review problems from 3 months ago, would the data still be available? Why or why not?**
6. **In your own words, explain what Azure Blob Storage is and why it's helpful.**

---

## Final Deliverable: Status Report Slide (Public Audience)

**Prepare 3–4 bullet points for your operations manager:**

- ✅ What the model predicted
- 📊 How confident it was
- 🔧 What should be done next (e.g., notify maintenance)

---

## Thinking Extension – Comparing Rule-Based Alerts with Isolation Forest

| Approach                            | How It Works                                                                                     | When It's Useful                                                                   |
| ----------------------------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------- |
| Traditional Rule-Based Alerts       | Engineers write fixed rules (e.g., "alert if temperature > 80°C")                                | Best when the exact failure conditions are already known in advance                |
| Isolation Forest (Machine Learning) | Learns what normal behavior looks like and isolates readings that separate from the rest quickly | Best when anomalies are rare and may not match any rule engineers thought to write |

---

## Personal Reflection

- ❓ What step in the notebook was most confusing or difficult?
- 🔁 What part would you want to review again before a certification or job?
- 🧠 Optional: What's one question you still have about Azure ML or anomaly detection?

---

## Workflow Output Summary (Sample Table)

| Timestamp | Machine ID | Sensor Reading | Anomaly Flag (Actual) | Predicted Label | Anomaly Score |
| --------- | ---------- | -------------- | --------------------- | --------------- | ------------- |
|           |            |                |                       |                 |               |
|           |            |                |                       |                 |               |

---

### Follow-Up Prompt

- ✅ Did the model correctly identify anomalies?
- ⚠️ Any false positives or false negatives?
- 💡 What would you do to improve the model?
