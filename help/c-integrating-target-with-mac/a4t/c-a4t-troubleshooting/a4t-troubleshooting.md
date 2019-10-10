---
description: This topic covers some common issues that have been encountered when using Analytics as the reporting source for Target (A4T).
keywords: analytics tracking server;A4T;analytics segments;report suites;incorrect data;orphaned;sdid;VisitorAPI.js;mboxMCSDID;phantom;unspecified
seo-description: This topic covers some common issues that have been encountered when using Analytics as the reporting source for Target (A4T).
seo-title: Troubleshoot the Analytics and Target integration (A4T)
solution: Target
subtopic: Multivariate Test
title: Troubleshoot the Analytics and Target integration (A4T)
topic: Standard
uuid: a5aa3be5-68a2-4f12-8226-f32a76136bbd
---

# Troubleshoot the Analytics and Target integration (A4T){#troubleshoot-the-analytics-and-target-integration-a-t}

This topic covers some common issues that have been encountered when using Analytics as the reporting source for Target (A4T).

## Activities do not show data in Analytics, but are instead listed as "unspecified." {#unspecified}

There are several reasons why this could happen:

* Classification in [!DNL Target] hasn't fully processed.

  Classification generally takes between 24 and 72 hours to classify reports after the first save.

* The report suite doesn't contain any data, but [!DNL Target] has tried to classify hits. [!DNL Target] cannot classify data until the first hit occurs.

  Ensure that the report suite has had at least one hit. 

* The classification call from [!DNL Target] to [!DNL Analytics] failed.

  [Contact Customer Care](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for assistance.

>[!NOTE]
>
>Sometimes data displays correctly in reports, but then reverts back to "unspecified" because a new activity was added that hasn’t completed classification. Remember that it generally takes between 24 and 72 hours to classify reports after the first save.
>
>No data is lost when listed as "unspecified." The data is properly assigned to the appropriate activity or experience after the classification runs.

## My Analytics data shows an inflated visit or visitor count since starting A4T. {#section_4BE374E573D44FB7918611699B74F58E}

For more information, see [Minimizing Inflated Visit and Visitor Counts in A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## Estimated lift in revenue metric does not show correct data. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Lift and confidence details are not available in Analytics. They are, however, available in the Target reports.

## Activities do not appear in Analytics reports. {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T activities require an analytics tracking server to be specified. See [Using an Analytics Tracking Server](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) to make sure your Analytics Tracking Server is set up correctly.

>[!NOTE]
>
>If you use Adobe Analytics as your activity's reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). The mbox.js or at.js library automatically sends tracking server values to [!DNL Target]. During activity creation, you can leave the [!UICONTROL Tracking Server] field empty on the [!UICONTROL Goals & Settings] page.

## My Analytics segments don't appear in Target. {#section_DEE87F1557834F448E99381D3D02EEEF}

Make sure you have the right permissions before you start creating A4T activities:

* You must belong to the Web Services Access group in Adobe Analytics to be able to use Analytics as the reporting source for Target. 
* You must be a member of one or more Experience Cloud groups that have access to Analytics and Target. 
* Verify that Analytics and Target appear in the Marketing Apps section of the left navigation.

## Bounce rates, bounces, and exits metrics appear as positives in reports. {#section_B5C3D56EF0344407AE67ABEB93037F5A}

This is a known issue.

Although these metrics are negative, the lift is shown as if they were positive in the Target reports. For example, even though you want a lower bounce rate, the higher bounce rate is shown as the winner with highest lift. Be aware of these and similar metrics, and whether you'd prefer to decrease or increase the numbers, when making decisions based on your reports.

## The report suite I need does not appear. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

The list of report suites that appears in Target Standard/Premium is the list of report suites that have been configured for Analytics as the reporting source for Target. This means you might not see every report suite you have. If you don't see the report suite you are looking for, you should contact Client Care to get it enabled.

## I'm not seeing as much data in reports as expected. {#section_75002584FA63456D8D9086172925DD8D}

Review your implementation, especially on pages where your visitors qualify for experiences and ensure that the supplemental data IDs match in the [!DNL Target] and [!DNL Analytics] calls. In the [!DNL Target] call, the supplemental ID is contained in the `mboxMCSDID` parameter. In the [!DNL Analytics] call, the supplemental ID is contained in the `sdid` parameter.

If there is no supplemental data ID in the [!DNL Target] call, confirm that the [!DNL VisitorAPI.js] file is loaded before [!DNL at.js] or [!DNL mbox.js]. If there is no supplemental data ID in the [!DNL Analytics] call, confirm that the [!DNL Target] call fires before the [!DNL Analytics] call.

For more information, see [Analytics for Target Implementation](../../../c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) or contact [Customer Care](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).