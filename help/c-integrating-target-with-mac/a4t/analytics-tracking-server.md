---
description: If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use Analytics for Target (A4T).
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
seo-description: If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use Analytics for Target (A4T).
seo-title: Use an Analytics tracking server
title: Use an Analytics tracking server
uuid: ad700b90-f409-496a-bc26-0f0367410a85
---

# Use an Analytics tracking server{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use Analytics for Target (A4T).

>[!NOTE]
>
>If you use Adobe Analytics as your activity's reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). The mbox.js or at.js library automatically sends tracking server values to [!DNL Target]. During activity creation, you can leave the [!UICONTROL Tracking Server] field empty on the [!UICONTROL Goals & Settings] page.

To ensure that data from Target goes to the correct location in Analytics, A4T requires an analytics tracking server to be sent in all calls to Modstats from Target. For implementations using multiple tracking servers you can use the Adobe Experience Cloud Debugger to determine the correct tracking server for your activity.

The debugger should be viewed on a page where the activity will be delivered to ensure you select the correct tracking server. You can also specify a default tracking server for each account. Contact Customer Care to specify or modify the default. 

1. From the page on which you are creating your activity, open the Adobe Experience Cloud Debugger.

   If you have not installed the debugger, see [Install Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

   The analytics tracking server is found in the SiteCatalyst Image section of the debugger. The field is called *First Party Cookies* or *Third Party Cookies* depending on the implementation, and the Analytics tracking server value will be in one of these formats:

   * (for CNAME implementations) 
   * (for non-RDC implementations) 
   * (for RDC implementation)

   *Company* represents the Analytics company name, *metrics* is an example of a CNAME value, and *d1* is an example of an Analytics data center. 
1. Copy the entire contents of the field.
1. In the [!UICONTROL Reporting Settings] section of the [!UICONTROL Goal & Settings] screen of your activity, paste the tracking server information in the **[!UICONTROL Tracking Server]** field.

   >[!NOTE]
   >
   >You must select Adobe Analytics as the Reporting Source for your activity for the Tracking Server field to be available.

