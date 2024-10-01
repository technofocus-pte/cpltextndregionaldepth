# **Lab 3B_Create a flow and invoke it from a copilot topic**

**Objective**

In this lab, you will learn how to create a flow that fetches a weather
forecast and use a Call an action node in a copilot topic to invoke the
flow when a customer asks about the weather.

**Duration:** 30 minutes

## Exercise 1: Create a flow to use with a copilot

1.  Login to +++**https://copilotstudio.microsoft.com/**+++ using your
    user credentials if not logged in already.

2.  Open the **Customer service** copilot.

    ![](./media/image1.png)

3.  Click on **Topics**, open the topic – **Get store locations**.

    ![](./media/image2.png)

4.  Click on + symbol to add a node after any existing node, select
    **call an action** and then **Create a flow**.

    >[!Note] **Note:** This action will not add anything here but will only open the flow creation page on Power Automate with the proper template.

    ![](./media/image3.png)

5.  The Power Automate is opened with the basic template required for a
    Copilot.

    ![](./media/image4.png)

## Exercise 2: Author the flow on the Power Automate portal

1.  Name the flow that just got opened as, +++**Get weather
    forecast**+++

    ![](./media/image5.png)

2.  Click on the node, **When Copilot Studio calls a flow**. In the node
    details pane that opens, click on **+ Add an input**.

    ![](./media/image6.png)

3.  Choose a **Text** input and name it as +++**City**+++.

    ![](./media/image7.png)

4.  Click on **+ Add an input** to add another input field.

    ![](./media/image8.png)

5.  Select a **Number** input and name it as +++**Zipcode**+++. Click on
    the **back(<<)** symbol on the right corner to come out of the node
    details pane.

    ![](./media/image9.png)

6.  Click on **Add an action** to a add node after the **When Copilot
    Studio calls a flow** node.

    ![](./media/image10.png)

7.  Search for +++**msn weather**+++ and select **Get forecast for
    today** under **MSN Weather**.

    ![](./media/image11.png)

    >[!Note] **Note:** If asked to create a new connection, select **Create New**.

    ![](./media/image12.png)

8.  In the **Get forecast for today** action, in the **Location** box,
    select **Add dynamic content**, and then
    select **City** and **Zipcode**.

    ![](./media/image13.png)

    ![](./media/image14.png)

9.  **City** and **Zipcode** will be passed on to this node as input.

    ![](./media/image15.png)

10. Click on **Return value(s) to Power Virtual Agents** node. In the
    node details pane that opens, click on **+ Add an output**.

    ![](./media/image16.png)

11. In the Return value(s) to Microsoft Copilot Studio **Parameters** tab, add the following output parameters and variables.

    |    |    |    |
    |:-----|:----|:------|
    |  Output Parameter Name  |   Type | Variable   |
    | +++day_summary+++   |  Text  |    Day Summary|
    | +++Location+++   |  Text  | Location|
    |  +++chance_of_rain+++  |  Text  | Day Rain Chance|
    
    >[!Note] **Note:** Select **Add dynamic content**, click on **See more** next to **Get forecast for today** to see the above variable options

    ![](./media/image17.png)

    ![](./media/image18.png)

    ![](./media/image19.png)

12. Click on **Save Draft** to save the flow.

    ![](./media/image20.png)

13. Look for a success message as in the screenshot below.

    ![](./media/image21.png)

14. Click on **Publish** and look for a success message.

    ![](./media/image22.png)

    ![](./media/image23.png)

**Exercise 3: Turn off asynchronous responses in the flow**

    Flows that you want to use in a bot must return values in real time, or synchronously.
Flows that run in the background, or asynchronously, may cause an error
when your bot tries to run them. Instead of running the flow, the bot
will say, "Something unexpected happened. We're looking into it. Error
code: 3000."

    When you create a flow from Microsoft Copilot Studio, **asynchronous
responses** are turned off by default. If you modified an existing flow
that has asynchronous responses turned on, you'll need to change the
setting.

1.  Select the **Settings** tab in the **Return value(s) to Power
    Virtual Agents** pane.

    ![](./media/image24.png)

2.  Ensure that Asynchronous response is set to **Off**.

    ![](./media/image25.png)

## Exercise 4: Call a flow from a topic

1.  Go back to Microsoft Copilot Studio page, select **Done** on **Save
    & refresh** pop up.

    ![](./media/image26.png)

2.  Select **Topics**. Click on **+ Add -\> Topic -\> From blank**.

    ![](./media/image27.png)

3.  Name the topic as +++**Get weather**+++. Click on **Edit** under
    Phrases to add in the Trigger phrases.

    ![](./media/image28.png)

4.  Add the following **trigger phrases**:

    - +++**will it rain**+++
    
    - +++**today's forecast**+++
    
    - +++**get weather**+++
    
    - +++**what's the weather**+++

    Enter the phrase and then click on **+** symbol to add it.

    ![](./media/image29.png)

    Similarly, add the other phrases as well.

    ![](./media/image30.png)

5.  After the Trigger node, add a **Message** node and enter the message
    as +++**I can help you with that**+++.

    ![](./media/image31.png)

6.  Next, add an **Ask a question** node.

    ![](./media/image32.png)

7.  Add the question +++**What is your city?**+++

    |  **Property**  |  **Value**  |
    |:----------|:----------|
    |  Question  |  +++What is your city?+++  |
    |  Identify  |   Select **User’s entire response** |
    |  Save Response as  | Click on **Var1** to open the Variable properties tab and provide the variable name as +++**city**+++   |

    ![](./media/image33.png)

9.  Add another question node and provide the following details.

    |  **Property**  |  **Value**  |
    |:----------|:----------|
    |  Question  |  +++What is your Zipcode?+++  |
    |  Identify  |   Select **Number** |
    |  Save Response as  | Click on **Var1** to open the Variable properties tab and provide the variable name as +++**Zipcode**+++   |

    ![](./media/image34.png)

10.  Select **Add node** (**+**) under the **Zipcode** question node.

    In the node selection window, select **Call an action**, and then select the flow you created earlier, **Get weather forecast**.

    ![](./media/image35.png)

11. Assign the flow inputs to the output variables from the question
    nodes. **City (text)** gets its value from the variable **city** and
    **Zipcode (number)** gets its value from the variable **Zipcode**.

    ![](./media/image36.png)

12. Under the flow node, add a **Message** node, and then enter a
    message that uses the flow's outputs as below.

    +++Today's forecast for+++ <Select X and choose location> +++:+++  <Select X and choose day_summary> +++Chance of rain is+++ <Select X and choose chance_of_rain.>+++
    
   ![](./media/image37.png)

13. Click on **Save** to save the topic.

    ![](./media/image38.png)

## Exercise 5: Test your flow and topic

1.  In **Test your Copilot**, type +++**get weather**+++ and click send.
    Give the City as +++**Redmond**+++ and **Zipcode** as
    +++**98004**+++ as per the questions from the copilot.

    ![](./media/image39.png)

2.  After sending the Zipcode, your flow will be invoked and the weather
    details of the specific region is provided by the copilot.

    ![](./media/image40.png)

**Summary:**

In this lab, we have learnt to create a flow and invoke it from a topic.
