# **Lab 3B_Creating and deploying a Microsoft Copilot Studio copilot from Teams**

**Objective:**

In this lab, we will learn to create Copilots from Teams, add a channel
and send messages to it and then publish it.

**Lab duration:** 30 minutes

## **Exercise 1: Install the Copilot Studio app in Microsoft Teams**

1.  Open **Microsoft Teams** from the VM and sign in using your **Office
    365 tenant credentials**.

2.  Click on **Apps**. Search for +++**Copilot Studio**+++ and select
    **Microsoft Copilot Studio** and click on **Add**.

**Note:** If you are not able to find Copilot Studio, you will have to
search for and select **Power Virtual agent** and add it.

![](./media/image1.png)

![](./media/image2.png)

3.  Click on **Start now**.

![](./media/image3.png)

## **Exercise 2: Create a new copilot in a team**

1.  Select **Contoso** and click on **Continue**.

![](./media/image4.png)

![](./media/image5.png)

2.  In the Create a copilot pane, provide the name of the Copilot as
    +++**HR Support Copilot**+++ and click on **Create**.

![](./media/image6.png)

3.  A success message stating, **Your chatbot is provisioned** is
    obtained.

![](./media/image7.png)

## **Exercise 3: Build an employee time-off topic for common time-off queries**

1.  Click on **Topics** from the left pane. Click on **+ New topic -\>
    From blank.**

![](./media/image8.png)

**Note:** Close the Trigger phrases pane, if appears.

 ![](./media/image9.png)

2.  Click on the **Details** icon.

![](./media/image10.png)

3.  In the Details pane, provide the name as +++**Employee time off**+++
    and Description as +++**Employee time off topic for common time-off
    queries**+++.

![](./media/image11.png)

4.  **Close** the Details pane.

![](./media/image12.png)

5.  Click on the **Trigger phases.**

![](./media/image13.png)

6.  Add in a trigger phrase, +++**I need help with time off**+++ and
    click on **+.**

![](./media/image14.png)

7.  Add in the below trigger phrases.

- +++**Need information on time off**+++

- +++**I need help with time off**+++

- +++**How many days of paid vacation do I have**+++

- +++**What are the national holidays**+++

- +++**I need extended leave**+++

![](./media/image15.png)

8.  Add a Message node and enter the text, +++*I can help with questions
    related to time-off+++*.

9.  As an HR employee, you know the most common time-off questions are
    about paid vacation time and national holidays. When a question node
    with user response options is added, the topic automatically gets a
    forked branch for each response.

10. Select the (**+**) icon below the message node, then select **Ask a
    question** to add a question node to the topic.

11. Enter *What information are you looking for?* in the **Ask a
    question** text box. The employee might ask this question.

![](./media/image16.png)

12. Under **Options for user**, add +++Paid
    vacation*+++* and +++National Holidays*+++* as two options.

![](./media/image17.png)

13. User choices are stored in a variable and the topic branches off,
    based on the option the user chooses. You can rename the variable to
    track it better in the topic.

14. On the variable, under **Save response as**, select the pencil icon
    to edit the variable properties.

15. The **Variable properties** pane opens. Rename the variable
    to +++*TimeoffType+++*. Close the **Variable properties** pane and
    you see the changes reflected in the authoring canvas.

![](./media/image18.png)

16. Add a message node for the Paid vacation branch with this message to
    the user: +++**For paid vacation time-off, go to
    www.contoso.com/HR/PaidTimeOff**+++ to submit time-off requests.

![](./media/image19.png)

17. Add a node by selecting the (**+**) icon to end the conversation
    with a survey. Select **End the conversation**, then **End with
    survey**. This survey is the customer satisfaction survey prebuilt
    in the copilot for use in topics.

![](./media/image20.png)

18. In the *National Holidays* path, add a message node with the
    following text:

> National holidays for 2020:

1.  New Year's Day: January 1st

2.  Memorial Day: May 25th

3.  Independence day: July 4th

4.  Labor Day: September 7th

5.  Thanksgiving: November 26th - 27th

6.  Christmas Eve and Christmas Day: December 24th - 25th

![](./media/image21.png)

19. Click on **Save**.

![](./media/image22.png)

![](./media/image23.png)

## **Exercise 4: Test copilot for expected behavior**

1.  Select the copilot icon at the bottom of the screen to launch the
    test copilot canvas.

![](./media/image24.png)

2.  Type +++I need time off information+++ into the copilot chat.

3.  Select **Paid vacation**.

4.  You receive the response as per our configuration.

![](./media/image25.png)

![](./media/image26.png)

## **Exercise 5: Add channel and Team**

1.  Select **Teams** option in MS Teams.

![](./media/image27.png)

2.  From the Teams, select **More options** and select **+ -\>**
    **Create team**.

![](./media/image28.png)

3.  Name the team as +++**HR Team**+++ and select **Create**.

![](./media/image29.png)

4.  Select **Skip** on ‘Add members to HR Team’ window.

![](./media/image30.png)

5.  Select **More options** (…) infront of the **HR Team** and then
    select under **Add channel.**

![](./media/image31.png)

6.  Provide the Channel name as +++**HR Experts**+++. Choose the Privacy
    as **Private** and click on **Create**.

![](./media/image32.png)

7.  Select **Skip** on ‘Add members to the HR Experts channel’ window.

![](./media/image33.png)

## **Exercise 6: Enhance topic to handle complex queries by escalating to HR experts**

1.  From the Teams app, select the Copilot Studio app(Power Virtual
    Agents), select **Copilots** tab and open the **HR Support
    Copilot**.

![](./media/image34.png)

> **Note:** If Copilot Studio shortcut is not found, search for
> **Copilot Studio/Power Virtual Agents under Apps** and select
> **Open**)

2.  Select **Topics** from left pane and return to the topic you created
    earlier(**Employee time off**) and go to the authoring canvas.

![](./media/image35.png)

3.  In the **Ask a question node**, add an option named ***Extended
    leave***.

![](./media/image36.png)

4.  Under the Condition node of Extended leave, add a question node
    asking for a description for the issue and add the text +++**How
    would you describe the issue?***+++*

![](./media/image37.png)

5.  Select **User’s entire response** under Identity and save the
    description in a variable named +++***Description**+++*.

![](./media/image38.png)

6.  Select **Save**.

![](./media/image39.png)

7.  Add a node under the question and select **Call an action**. Select
    **Create a flow** which launches the Power Automate within the
    Copilot Studio in Teams.

![](./media/image40.png)

8.  Choose the **Power Virtual Agents Flow** Template option.

![](./media/image41.png)

![](./media/image42.png)

9.  Add a **Text** input field by clicking on **+ Add an input** in the
    first step. Replace the Input by **Description**.

![](./media/image43.png)

10. Insert a **new step** and select **Add an action**.

![](./media/image44.png)

![](./media/image45.png)

![](./media/image46.png)

11. Select **Microsoft Teams** under **Choose an operation**.

![](./media/image47.png)

12. Select **Post message in a chat or channel**.

![](./media/image48.png)

13. Provide the below details:

- Post as – **User**

- Post in – **Channel**

- Team – **HR Team**

- Channel – **HR Experts**

- Message **– Description** from **Dynamic Content**

![](./media/image49.png)

14. Rename the flow as +++**Send a message to HR team**+++ and click on
    **Save**.

![](./media/image50.png)

15. Click on **Close** to close the Power Automate and return to the
    Authoring canvas.

![](./media/image51.png)

16. From the Authoring canvas, **add a node**(under the** Extended
    leave **branch) – **call an action** -\> **Send a message to HR
    team**.

![](./media/image52.png)

17. Add in the input as **Description**.

![](./media/image53.png)

18. Add in a message node with the message, +++**We notified the expert.
    They’ll reach out shortly**+++.

![](./media/image54.png)

19. End the conversation \> End the survey.

![](./media/image55.png)

20. Click on **Save** to save the topic.

![](./media/image56.png)

21. A success message of **Topic saved** is obtained.

![](./media/image57.png)

## **Exercise 7: Test your chatbot**

1.  Select **Test your chatbot** from the left pane.

![](./media/image58.png)

2.  Send a message +++**I need help with time off**+++ and select
    Extended leave to answer the chatbot.

![](./media/image59.png)

3.  Describe a reason for your leave extension. Here, we have given it
    as +++**I need extended leave of one month for travelling**+++.

![](./media/image60.png)

4.  The bot replies with “We notified an expert…..” message.

![](./media/image61.png)

![](./media/image62.png)

## **Exercise 8: Check the message in Teams.**

1.  Click on Teams from the left menu of the MS Teams app.

![](./media/image63.png)

2.  Select the **HR Experts** channel under the **HR Team** team. Notice
    that the message from the user to the bot has been sent here.

![](./media/image64.png)

## **Exercise 9: Publish your copilot – Teams**

1.  Go back to Microsoft Copilot Studio app. Select the chatbot **HR
    Support Copilot**.

2.  Select Publish from the left pane.

![](./media/image65.png)

3.  Click on **Publish**.

![](./media/image66.png)

4.  Select Publish in the **Publish latest content?**

![](./media/image67.png)

5.  Success message is obtained as in the screenshot below. Click on the
    **Availability options**.

![](./media/image68.png)

6.  The **Add to Contoso** option adds the bot to the specific team.

7.  **Show to my team mates and shared users** makes the bot to appear
    under the Built by colleagues section.

8.  **Show to everyone in the org** submits the request to the admin to
    get the bot listed under the **Built by org** section.

![](./media/image69.png)

> **Summary:**
>
> In this lab, we have learnt to add the Copilot Studio app to Teams and
> create a classic bot in Teams. We have also learnt to post a message
> to the Teams channel from the bot.
