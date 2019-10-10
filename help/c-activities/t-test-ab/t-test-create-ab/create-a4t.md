---
description: You can configure an Activity in Target Standard to use Adobe Analytics as the reporting source (A4T).
keywords: Targeting;analytics;tracking server
seo-description: You can configure an Activity in Target Standard to use Adobe Analytics as the reporting source (A4T).
seo-title: Using Analytics data
solution: Target
title: Using Analytics data
uuid: 4ac0c181-030b-4cf5-b138-acf02c7af4f6
---

# Using Analytics data{#using-analytics-data}

You can configure an Activity in Target Standard to use Adobe Analytics as the reporting source (A4T).

For detailed information about setting up Analytics as the data source for Target, see [Adobe Analytics as the Reporting Source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

Before you set up an activity that uses Analytics as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. Choose a final success metric for the campaign. Although you can select additional metrics at any time in Analytics, you must still specify a particular metric you expect this test to affect.

>[!NOTE]
>
>The Adobe Analytics option is available if you've linked your Adobe Experience Cloud account with both Analytics and Target, even if integration between Target and Analytics has not been set up for your account.

When selecting Analytics as the reporting source for Target, you select an Analytics report suite to receive Target activity data. To do this, first choose from any of the Analytics companies your account is tied to, and then select the appropriate report suite for the activity. Only report suites that are provisioned to connect to Adobe Target will be available for selection. If you don't see the report suite(s) you expect, first try logging out and logging back in to the Adobe Experience Cloud to try again. If the report suite is still missing from the list, please contact Customer Care.

Analytics for Target requires a tracking server to report results correctly. A default tracking server will appear in the Tracking Server field. If you use more than one tracking server, you should check to ensure you include the correct tracking server in this field. See [Using an Analytics Tracking Server](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) for more information.

>[!NOTE]
>
>If you use Adobe Analytics as your activity's reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). The mbox.js or at.js library automatically sends tracking server values to [!DNL Target]. During activity creation, you can leave the [!UICONTROL Tracking Server] field empty on the [!UICONTROL Goals & Settings] page.

When setting up activity after setting up Analytics as your reporting source, there is no option to set up audiences for reporting. Analytics segments are available in the Target Activities report.

You are required to select a success metric to uses as a goal for each test. Your activity goal is the conversion activity that signals a successful campaign. It is best practice never to run a test without having a goal to improve in some specific way. You can choose any Analytics metric available in the Analytics metric selector.

Setting a goal doesn't mean you can't use another metric when evaluating test results. The goal is, however, a reminder of the one thing you want to improve with the test.

After a visitor completes your goal, that visitor is no longer included in the campaign. If the visitor re-enters your campaign after completing an activity, he or she is counted as a new visitor. 
