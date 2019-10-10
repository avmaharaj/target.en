---
description: List of frequently asked questions about reporting in Target.
keywords: troubleshooting;metric discrepancies;FAQ;reports
seo-description: List of frequently asked questions about reporting in Adobe Target.
seo-title: Reporting FAQ for Adobe Target
solution: Target
title: Reporting FAQ
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
---

# Reporting FAQ{#reporting-faq}

List of frequently asked questions about reporting in [!DNL Target].

## Why do my [!UICONTROL Experience Targeting] (XT) reports contain metrics for control experiences?

XT activities should always have a control experience. If you are using an XT activity in a similar manner to an [!UICONTROL A/B Test] activity, which is a fairly common scenario, the control experience data is useful. You can ignore the control experience data if you find it not useful in your reports.

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

Metric numbers, for example visits, reported by [!DNL Target] will always be lower than the reported numbers in other [!DNL Experience Cloud] solutions for a number of reasons:

* [!DNL Target] counts visits only for visitors that qualified for the activity. Other solutions count visits for visitors that display the page, regardless of which activity brought them to the page. 
* There might be situations where different activities compete for the same location (mutually exclusive). As a result, visitors see different content on a web page, which affects the metric numbers reported by [!DNL Target].

## Why is there no data available for my activity's report? {#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/administrating-target/hosts.md)) selected in the report's settings.

If you have a development environment selected, you might see the following error message: "There is no data available for the selected report settings."

To change the environment for an activity's report:

1. Click **[!UICONTROL Activities]**, click the desired activity from the list, then click the **[!UICONTROL Reports]** tab. 
1. Click the gear icon to configure report settings.

   ![A/B Settings dialog box](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. From the **[!UICONTROL Environment]** drop-down list, select **[!UICONTROL Production]**.

   Report data might not be available if you have a development environment selected. 

1. Click **[!UICONTROL Save]**.

For more information about environments, see [Hosts](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
