---
description: The Activity URL determines the page that is used in the Experience Targeting activity, and that opens in the Visual Experience Composer (VEC) or Form-Based Experience Composer when the activity is designed.
keywords: Targeting
seo-description: The Activity URL determines the page that is used in the Experience Targeting activity, and that opens in the Adobe Target Visual Experience Composer (VEC) or Form-Based Experience Composer when the activity is designed.
seo-title: Activity URL
solution: Target
title: Activity URL
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
---

# Activity URL{#activity-url}

The Activity URL determines the page that is used in the Experience Targeting (XT) activity, and that opens in the Visual Experience Composer (VEC) or Form-Based Experience Composer when the activity is designed.

1. When prompted while [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), specify the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >[!DNL Target] does not differentiate between URL protocols ( [!DNL https] and [!DNL http]). As a result, [!DNL `https://www.adobe.com`] and [!DNL `http://www.adobe.com`] both match.
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). You can specify a different page during activity creation.
   >
   >If you specify a URL for a site that does not include the Target Standard JavaScript code, you cannot select page elements.

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![Page Delivery dialog box](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >If you change the URL after making changes to a page for one or more experiences, the experience is reset using the new page and the changes you made are lost.

1. (Conditional) Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

   Additional rules can be based on any of the following:

   * URL 
   * Domain 
   * Path 
   * Hash (#) Fragment 
   * Query 
   * mbox Parameter

   Additional rules can be joined to the Activity URL with AND or OR. All rules you add are evaluated against each other with AND.

1. Click **[!UICONTROL Save]** when you have finished.