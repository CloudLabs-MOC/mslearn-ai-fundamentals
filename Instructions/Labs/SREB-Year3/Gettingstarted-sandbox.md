# SREB Year-3 Labs Design Sandbox

Using this environment, you’ll be able to explore complete features and offerings offered by below services. Please find the detailed overview of the Lab environment below.

## About the Lab Environment

| Resources | Value | Remarks |
|  -- | -- | -- |
| Enabled Services | `Visual Studio, SSMS, Azure Data Studio, DAX Studio, Power BI Desktop, Power BI Report` | You can explore these services |
| Azure Entra ID User | Pre-created Entra ID user account  | You will get one Entra ID User Account. |
| Azure Subscription Permissions | Custom role over Subscription |You will get Custom role access on subscription which have permissions on SQL, Azure Machine Learning, Storage account and Cost Management.   |
| Azure Credit | $100 USD | The consumption limit is set on Azure spend to $100 USD.|
| Credit Alerts	 | Credit Alerts are set on consumption of 25%, 50%, 75%, 90%, and 100% of total Azure credits. | Make sure to check your registered email's inbox for any alert-related mails. Alerts give you a head start to keep your Azure spending in control and to plan out the remaining credits in the best way possible. |
| Environment Duration | For a duration of four months or until the Azure Consumption Credits are fully utilized, whichever occurs first. | Once the Azure consumption credits are exhausted, resources will be deallocated and permissions will be removed. Please reach out to our team if you need additional credits. |
| Resource deallocation | You can stop the VM when not in use | To reduce unnecessary costs, you can stop the VM from the Lab Guide's Resource tab by selecting the Stop button when it is not in use |

## Steps to Deallocate/Stop VM

Please follow the below steps to **Deallocate/Stop** the Lab VM.

1. Navigate to **Resource (1)** tab from the lab guide and then select **Stop (2)** button

    ![](./images/rsc1.png)    

## Steps to Start the VM

Please follow the below steps to **Start** the Lab VM.

1. Navigate to **Resource (1)** tab from the lab guide and then select **Start (2)** button.

    ![](./images/rsc2.png) 

## Steps to access Azure Data Studio

1. Search for **Azure Data Studio (1)** from the Lab VM Search bar and then select **Azure Data Studio (2)**.

    ![](./images/s5.png) 

## Notes:

- You will be assigned a dedicated hands-on environment. The Azure credit consumption includes all the resources which you will be deploying while using the lab environment for your testing.

- You will have Contributor privilege access on the Azure subscription, you can freely explore the features of required services and are recommended to use it only for testing purposes.

- The environment has a fixed budget/cap of $100 USD, kindly do not deploy any other resources that are not related to the testing as they can consume the Azure credit leading to the automatic deallocation of the environment as soon as the credit limit is reached.

## Cost Monitoring:
To monitor and analyse your Azure credit spend, you can navigate to the Azure Subscription page by following the steps mentioned below.

1. On your virtual machine, click on the **Azure Portal** icon as shown below:
 
   ![Launch Azure Portal](./images/g43.png)

2. You'll see the **Sign into Microsoft Azure** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
       ![Enter Your Username](./images/sc900-image-1.png)
 
3. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
     ![Enter Your Password](./images/sc900-image-2.png)
 
4. If prompted to stay signed in, you can click **No**.

1. From the Azure portal home page, search for **Subscriptions (1)** using the search bar and select the same from the suggestions.

    ![](./images/s1.png) 

1. Select the **Cost Analysis** tab from the Cost Management pane. You can access a comprehensive breakdown of your Azure spending, offering a granular view of costs associated with various services, and resources.

    ![](./images/s2.png) 

1. To get the accurate consumed cost by you, select the **Calendar (2)** from **Cost analysis (1)** then **Custom date Range (3)**.

    ![](./images/s3.png) 

1. Now, select the custom dates.

    - **Start Date: (1)** The date when you redeemed voucher and launch the Sandbox environment.
    - **End Date: (2)** Current or future date. If you select the future date, you can also get the forecasted cost based on the current resources you deployed and then **Appy (3)**
    - You can see the **ACTUAL COST (USD) (4)** and the **FORECAST: CHART VIEW ON (5) cost**.

      ![](./images/s4.png)     

## Best Practices:

1. **Resources usage:** Please stop the virtual machines resources when not in use to minimize the Azure spend.
1. **Azure Cost Analysis:** Maintain a practice of regularly checking the Cost Analysis report for the assigned Azure subscription to ensure the sustainability of the environment over an extended period.
1. **Alert notifications:** Make sure to check your registered email's inbox for any alert-related emails. Alerts give you can head start to keep your Azure spending in control and to plan out the remaining credits in the best way possible.    

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels explicitly tailored for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.
 
Learner Support Contacts:
 
- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support
