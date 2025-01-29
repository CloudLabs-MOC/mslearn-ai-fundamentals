# Module 12: Explore Microsoft Copilot in Microsoft Edge

## Lab overview

In this exercise, you will explore some of the ways in which Microsoft Copilot can use generative AI to help you be more productive when creating new content. In the scenario for this exercise, you will start with some high-level notes for a business idea, and use Copilot in Microsoft Edge to help you develop a business plan and a presentation for potential investors.

## Lab objectives
In this lab, you will perform:

+ Task 1: Use Copilot to explore a document and research an idea
+ Task 2: Use Copilot to create content for a business plan
+ Task 3: Use Copilot to generate and visualize financial projections
+ Task 4: Use Copilot to create content for a presentation
+ Task 5: Use Copilot to arrange a funding meeting
  
## Estimated timing: 40 minutes

## Architecture Diagram

 ![](media/arch1diag.PNG)

### Task 1: Use Copilot to explore a document and research an idea

In this task, you will learn how to use **Copilot** to explore a document and research an idea, leveraging AI to gain insights and find relevant information more efficiently.

To start your exploration of generative AI, let's use Microsoft Copilot in Edge to examine an existing document and extract some insights from it.

1. In Microsoft Edge, browse to [OneDrive](https://onedrive.live.com) at `https://onedrive.live.com` and sign in using your Microsoft account - closing any welcome messages or offers that are displayed.
1. In another browser tab, open the document [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) from `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`. Then, when the document opens in Edge, select the option to **Save a copy to OneDrive** and save the document in your **Documents** folder in OneDrive. The document should then open in Microsoft Word online automatically.

    > **Note**: If you don't see the option to save a copy of the file to OneDrive, download it to your local computer. Then, in OneDrive, open the **Documents** folder and use the **+ Add new** button to upload the **Business Idea.docx** file from your local computer to OneDrive and you can access the file from My Files in the OneDrive menu .

1. View the text in **Business Idea.docx**, which describes some high-level ideas for a cleaning business in New York City.
1. Use the **Copilot** icon on the Edge toolbar to open the Copilot pane, as shown here:

    ![Screenshot of the Copilot pane in Microsoft Edge.](media/edge-copilotupd.png)

1. In the chat box at the bottom of the Copilot pane, enter following the prompt:

    ```
    Summarize this document into 5 key points, and suggest next steps.
    ```

    If prompted, confirm that you want to allow Copilot to access the page and acknowledge that the conversation will not be saved (note that Copilot protects the privacy of the conversation because it includes information from a personal document in your OneDrive).

1. Review the response from Copilot, which should summarize the main points in the document, as shown here:

    ![Screenshot of the Copilot pane with a response.](media/copilot-responseupd.png)

    > **Note**: The response may differ depending on the situation.

1. Enter the following prompt:

    ```
    How do I go about setting up a business in New York?
    ```

1. Review the response, which should contain some advice and links to resource to help you get started setting up a business in New York, and may include some suggested follow-up prompts to get more information.

    > **Important**: The AI-generated response is based on information publicly on the Web. While it may be useful to help you understand the steps required to set up a business, it is not guaranteed to be 100% accurate and does not replace the need for professional advice!

### Task 2: Use Copilot to create content for a business plan

In this task, you will learn how to use **Copilot** to create content for a business plan, leveraging AI to generate key sections, such as executive summaries, market analysis, and financial projections.

Now that you've done some initial research, let's have Copilot help you develop a business plan for your cleaning company.

1. With the **Business Idea.docx** document still open in Microsoft Edge, in the Copilot pane, enter the following prompt:

    ```
    Suggest a name for my cleaning business
    ```

1. Review the suggestions and select a name for your cleaning company (or continue prompting to find a name you like).
1. Enter the following prompt, replacing *Contoso Cleaning* with the company name of your choice:

    ```
    Based on the contents of this document, create a business plan for my cleaning business.
    ```

1. Review the response. Then in the Microsoft Word pane, in the **File** menu, create a new blank document. Close the **Designer** pane if it opens and change the name of the new document from *Document* to `Business Plan`.

1. Copy the business plan that was generated in the Copilot pane and paste it into the business plan document:

    ![Screenshot of a Word document with a Copilot-generated business plan.](media/generated-contentupd.png)

1. In the Copilot pane, enter the following prompt:

    ```
    Create a corporate logo for the cleaning company. The logo should be round and include an iconic New York landmark.
    ```
     Note: If it gives response to **Please sign in to create images**, click on **Image Creator** link and then     
     sign with your account by clicking on **Join & Create** on Copilot | Designer page. 

     ![](media/up3.png)
   
     ![](media/up2.png)
     
1. Review the response, which should present four options for a logo created by Microsoft Designer.
1. Use more prompts to iterate on the design (for example, `Make it green and blue`) until you have a logo with which you are happy.
1. Right-click the logo design you prefer and copy it to the clipboard. Then paste it into the top of the business plan document, like this:

    ![Screenshot of a Word document with a Copilot-generated image.](media/generated-image.png)

1. Close the Microsoft Word tab and return to the **Documents** folder in your OneDrive.

### Task 3: Use Copilot to generate and visualize financial projections

In this task, you will learn how to use **Copilot** to generate and visualize financial projections, enabling you to create charts, tables, and forecasts for business planning and decision-making.

1. In OneDrive, use the **(+)** button to add a new **Excel workbook**. Then change the name of the workbook to `Financial Projections`.
1. In the Copilot pane, enter the following prompt:

    ```prompt
    Create a table of projected profits for the next 5 years, starting with this year. The profit this year should be $10,000 and it should increase by 12% each year.
    ```

1. Review the response, which should include a table of projected profits for the next five years.
1. Copy the table to the clipboard (being careful to select just the table). Then select cell A1 in the Excel workbook, and on the **Home** tab, in the **Clipboard** menu, under **Paste special**, select **Values only** to that the values from the table are pasted into the spreadsheet like this:

    ![Screenshot of an Excel workbook with Copilot-generated data.](./media/generated-financialsupd.png)

1. In the Copilot pane, enter the following prompt:

    ```prompt
    What's a good way to visualize these projections in a chart?
    ```

1. Review the response, which should recommend a few ways to visualize the projections data. Then enter the following prompt:

    ```prompt
    How do I create a line chart in Excel?
    ```

1. Follow the guidance provided by Copilot to create a line chart.

    > **Tip**: You may need to adjust the default data axis selected by Excel. Select the chart in the spreadsheet, and on the **Chart** tab, select **Select Data**. Then in the **Chart** pane, on the **Data** tab, modify the setup so that the **Year** field is the horizontal label and only the **Projected Profit** field is used as a line value:

    ![Screenshot of an Excel workbook with a line chart.](./media/line-chartupd.png)

1. Close the **Chart** tab to see the chart in the spreadsheet.

1. Close the Microsoft Excel browser tab and return to your OneDrive.

### Task 4: Use Copilot to create content for a presentation

In this task, you will learn how to use **Copilot** to create content for a presentation, helping you generate slides, summaries, and key talking points efficiently.

Thanks to Copilot, you've created a business plan for the cleaning business and generated some financial projections. Now you'll need an effective presentation to convince an investor to lend you the funding to start the business.

1. In OneDrive, add a new **PowerPoint presentation**. If the **Designer** pane opens automatically, close it. Then change the name of the presentation from *Presentation* to `Business Presentation`.

1. On the title slide for the presentation, enter the the name of your cleaning company as the title, and `Investor Opportunity` as the subtitle.
1. Insert a new slide, using the **Two Content** slide layout (which includes a title and two placeholders for content).
1. Change the slide title to `Benefits of Hiring a Commercial Cleaner`.
1. In the Copilot pane, enter the following prompt:

    ```prompt
    Write a summary of the benefits of using a corporate cleaning company for your business. The summary should consist of five short bullet points.
    ```

1. Copy Copilot's response to the clipboard, and paste it into the left content placeholder. Then edit and reformat the text in the placeholder until you are satisfied.
1. In the Copilot pane, enter the following prompt:

    ```prompt
    Create a photorealistic image of a clean office.
    ```

1. When Copilot has generated an image you like, copy it to the clipboard and paste it into the content placeholder on the right of the slide.

    If the **Designer** pane opens automatically, select a slide design you like. Then close the **Designer** pane.

1. Apply any additional reformatting you think is required until you have a slide that you're happy with:

    ![Screenshot of a PowerPoint presentation with Copilot-generated content.](./media/powerpoint-slideupd.png)

1. Open a new browser tab and use it to download the [mopping.png](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/mopping.png) image from `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/mopping.png` to your local computer, saving it in any folder.
1. Return to the browser tab containing your PowerPoint presentation, and in the Copilot pane, use the **+** button next to the chat box to upload the **mopping.png** image to Copilot, and add the prompt `What does this image show?`.
1. Review the response, which should be similar to this:

    ![Screenshot of a Copilot description of an image.](./media/copilot-image-analysisupd.png)

1. Follow up with the following prompt, and review the response:

    ```prompt
    Would this image be helpful to promote a commercial cleaning business?
    ```

    Copilot has analyzed the image and assessed its usefulness for your specific business scenario in the same way you might ask a colleague's opinion.

1. In PowerPoint, add a new slide with the same **Two Content** layout as before. Then in one of the content placeholders, upload the **mopping.png** image to add it to the slide.

1. In the Copilot pane, enter the following prompt:

    ```prompt
    Write a short paragraph to accompany this image, emphasizing the professionalism of the cleaning staff we employ.
    ```

1. Review the resulting text, and then copy it to the empty content placeholder on the slide, editing and formatting it as you think necessary.
1. In the Copilot pane, enter the following prompt:

    ```prompt
    Suggest a good title for a slide that contains the image and text.
    ```

1. Use the suggested title for the slide, and then use the Designer in PowerPoint to format the slide. You should end up with a slide similar to this:

    ![Screenshot of a slide created using suggestions from Copilot.](./media/powerpoint-new-slideupd.png)

1. Close the PowerPoint browser tab and return to your OneDrive.

### Task 5: Use Copilot to arrange a funding meeting
You've created some collateral to help you get your business started. Now it's time to reach out to an investor seeking some startup funding.

1. Use the **App Launcher** (&#8759;) at the left end of the OneDrive title bar to open **Outlook**.
1. Switch to the **Calendar** page and change the view to **Work week**. If you don't already have any scheduled events in your calendar, you can add a couple so that Copilot has some information to work with.
1. In the Copilot pane, enter the following prompt:

    ```prompt
    What events do I have scheduled in this calendar?
    ```
    
    Copilot should be able to read the calendar in the web page and identify events in your calendar:

    ![Screenshot of an Outlook calendar with Copilot identifying events.](./media/calendar-eventsupd.png)

1. Try using this prompt to check your availability for a meeting with a a bank manager to seek funding for the business:

    ```prompt
    What's my availability for a meeting this week?
    ```

    Copilot should provide a summary of your availability based on the calendar information in the Outlook web page.

    > **Note**: Microsoft Copilot can read the calendar page that is open in the browser (and may "remember" details during the current session), but it cannot access your calendar data directly. In a corporate environment, your organization can use Microsoft 365 Copilot, which *does* have access to your calendar and email in Outlook, as well as information in other enterprise apps like Microsoft Teams.

1. Switch to the **Mail** page, and create a new email. Fill in the **To** box with your own email address and set the **Subject** to `Business funding meeting request`.
1. In the Copilot pane, enter the following prompt:

    ```prompt
    Write an email to a bank manager requesting a meeting to discuss funding for a commercial cleaning business. The email should be concise and the tone should be professional.
    ```
    
1. Use the generated content to complete your email, as shown here:

    ![Screenshot of an email message generated by Copilot.](./media/generated-emailupd.png)

    You can send the email to yourself if you wish!

## Challenge

Now you've seen how to use Copilot to research ideas and generate content, why not try exploring further? To start a new Copilot session, in the **+** menu next to the chat box, select **Start new chat**. Then, based on what you've learned in this exercise, try using Copilot to plan a meeting in which you'll propose the adoption of generative AI in your organization. Here are a few ideas to get you started:

- Research the benefits of generative AI and Microsoft Copilot for businesses, finding information about productivity benefits, cost-savings, and examples of organizations that have already successfully adopted AI.
- Create a discussion document that you can circulate as pre-reading before the meeting.
- Create a presentation that you can use to present your case, including data and visualizations to emphasize key elements of your pitch.
- Compose an email to tell your coworkers about the meeting and provide some context for it.

Be as inventive as you like, and explore how Copilot can help you by finding information, generating and refining text, creating images, and answering questions.

## Conclusion

In this exercise, you've used Copilot in Microsoft Edge to find information and generate content. Hopefully you've seen how using generative AI in a copilot can help with productivity and creativity.

While the free services used in this exercises are undoubtedly very powerful, you can achieve even more with services like [Microsoft 365 Copilot](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365), in which Microsoft Copilot is integrated into Windows and Microsoft Office productivity applications, providing highly contextualized help with common tasks. Microsoft 365 enables you to bring the power of generative AI to your business data and processes, while integrating into your existing IT infrastructure to ensure a manageable, secure solution.

### Review
In this lab, you have completed the following tasks:
- Used Copilot to explore a document and research an idea
- Used Copilot to create content for a business plan
- Used Copilot to generate and visualize financial projections
- Used Copilot to create content for a presentation
- Used Copilot to arrange a funding meeting

## You have successfully completed this lab.
