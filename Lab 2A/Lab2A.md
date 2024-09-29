# **Lab 2A: Adding a conversational action for Copilot for Microsoft 365**

**Objective**

Microsoft Copilot provides out of the box experiences to engage with
content and resources from across your organization. In some situations,
answers and interaction with external systems are required. With
Microsoft Copilot Studio, you can author a conversational topic that can
be published as a Copilot Plugin. Once your Tenant Admin approves the
Plugin, it can be added to your organization's M365 Chat experiences.

The Plugins will be available in the Microsoft Copilot in production, if
the organization has valid license for the same.

In this lab, we will learn how to create a Conversational action.

Lab duration – 15 minutes

## **Exercise 1: Setting up your environment**

1.  Login to the VM using the **Username** and **Password** from
    the **Resources** tab.

    ![](./media/image1.png)

2.  After logging into the VM, right click on the clock at the bottom
    right corner of the screen.

3.  Select **Adjust date and time.**

    ![](./media/image2.jpeg)

4.  On the Settings screen that opens up, click on the **Sync
    now** under Additional settings.

    ![](./media/image3.jpeg)

5.  This takes care of synchronizing the time just in case the automatic
    synchronization does not work.

    ![](./media/image4.jpeg)

## **Exercise 2: Create a Conversational plugin**

1.  Login to +++**https://copilotstudio.microsoft.com/**+++ using your
    tenant credentials.

2.  Sign in with the **Office 365 Tenant Credentials** provided under
    the **Resources** tab of your Lab VM.

    ![](./media/image5.png)

    ![](./media/image6.png)

3.  Once logged in, the Welcome to Microsoft Copilot Studio page, select
    your Country and click on **Start free trial**.

    ![](./media/image7.png)

4.  The Copilot Studio Home page opens.

    ![](./media/image8.png)

5.  Select **Contoso (default)** environment. Select **Copilot for
    Microsoft 365**.

    ![](./media/image9.png)

6.  Select **Actions**.

    ![](./media/image10.png)

7.  Select **+ Add an action**.

    ![](./media/image11.png)

8.  Select **Conversational** in the **New action** pane.

    ![](./media/image12.png)

9.  Provide the name for the action as +++**Conversational action**+++.
    Select **Create**.

    ![](./media/image13.png)
    
    ![](./media/image14.png)

10. Once ready, the created action opens in Authoring canvas. Select
    **Topics**.

    ![](./media/image15.png)

11. Name the topic as +++Holidaylist+++

    ![](./media/image16.png)

12. In the Trigger node’s description, provide a clear description of
    how the conversational plugin can help the user and what it can
    do. Let this topic help the user to find the list of holidays in the
    year 2024.

    Type +++**This plugin helps to retrieve the list of holidays for the
    year 2024.**+++ in the Trigger node’s description.

    ![](./media/image17.png)

    This description has functional purpose and is used by the Microsoft
    Copilot to determine whether to invoke your plugin or not.

13. Add a **message node** with the list of holidays.

    ```
    - New Year's Day - January 1

    - Martin Luther King, Jr.'s Birthday (Third Monday of January) -
      January 15, 2024

    - Washington's Birthday or Presidents' Day (third Monday of
      February) - February 19

    - Memorial Day (last Monday of May) - May 27

    - Juneteenth Day - June 19

    - Independence Day - July 4

    - Labor Day (first Monday of September) - September 2

    - Columbus Day (Second Monday of October) - October 14

    - Veterans Day or Veterans Day - November 11

    - Thanksgiving Day (fourth Thursday of November): November 28

    - Christmas Day - December 25
    
    ```
    ![](./media/image18.png)

14. Click on **Save** to save the action.

    ![](./media/image19.png)

    ![](./media/image20.png)

## **Exercise 3: Publishing your conversational action to Microsoft Copilot**

1.  Publishing your conversational plugin creates a new plugin in the
    Dataverse registry for your Tenant. Once available there, your
    tenant admin needs to approve your plugin to be available to users
    in the Microsoft Copilot plugins catalog.

2.  Click on **Publish**.

    ![](./media/image21.png)

3.  Select **Publish.**

    ![](./media/image22.png)

4.  Select **Publish** on **Publish latest content** dialog.

    ![](./media/image23.png)

5.  The publish status is shown on the screen.

    ![](./media/image24.png)

    >[!Note] **Note:** The publishing should be completed quickly. The actual
availability in the Microsoft Admin Center can take up to 4 hours.

6.  Your Admin can find the **Dataverse and Microsoft Copilot
    Studio** integrated app in the Microsoft Admin Center
    under **Settings**, then **Integrations to be reviewed and
    approved**.

    ?[!Alert] **Important:** For the admin to get it listed in the admin center,
the company will have to hold a valid Copilot license.

7.  Once your Tenant admin approves the Dataverse and Microsoft Copilot
    Studio integrated app, it should appear in the user's list of
    plugins in their Microsoft Copilot UI.

**Summary:**

In this lab, we have learnt how to create a conversational action and to
publish it.
