---
description: Audiences determine who will see content and experiences in a targeted activity.
keywords: audience;audience rules;create audience;creating audience;targeting audience;reporting audience;report audience;segment;custom profile parameters;audience definition;audiences list
seo-description: Audiences in Adobe Target determine who will see content and experiences in a targeted activity.
seo-title: Create audiences in Adobe Target
solution: Target
title: Create audiences
topic: Advanced,Standard,Classic
uuid: 994eed40-11ca-460e-827c-75a4db8a942d
---

# Create audiences{#create-audiences}

Audiences determine who will see content and experiences in a targeted activity.

Audiences are used anywhere targeting is available. When targeting an activity, you can either select a reusable audience from the [!UICONTROL Audiences] list, [create an activity-specific audience](/help/c-target/creating-activity-only-audience.md) and target it, or [combine multiple audiences](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) to create an ad hoc audience.

You can also use audience data collected by [!DNL Analytics] for real-time targeting and personalization in [!DNL Adobe Target] and other [!DNL Experience Cloud] solutions. See [Audiences](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) in the *Core Services User Guide*.

[!DNL Target] defines two types of audiences:

* **Targeting Audiences:** Used to deliver different content to different types of visitors. 
* **Reporting Audiences:** Used to determine how different types of visitors respond to the same content so you can analyze your test results.

  In [!DNL Target], you can configure reporting audiences only if you use [!DNL Target] as your reporting source. If you use [DNL Adobe Analytics as your reporting source](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), you must configure your reporting audiences within [!DNL Analytics].

## Use the Audiences list

To access the [!UICONTROL Audiences] list, click **[!UICONTROL Audiences]** in the top menu bar:

![Audiences list](assets/audiences_list.png)

The [!UICONTROL Audiences] list contains all of the audiences that you can use in your activities. Use the [!UICONTROL Audiences] list to create, edit, delete, copy, or combine audiences. The list also shows the source where the audience was created ([!DNL Target], [!DNL Target Classic], [!DNL Adobe Audience Manager (AAM),] [!DNL Experience Cloud], and so forth). Predefined audiences, such as "New Visitors" and "Returning Visitors," cannot be renamed.

When working with audiences that were originally created in AAM, Target alerts you if you reference an audience in Target activities that have later been deleted in AAM.

* If an audience was deleted in AAM, a warning icon in both the [!UICONTROL Audience] list and the audience picker displays. A tool-tip in the UI also indicates that the audience was deleted in AAM. 
* If you attempt to combine multiple audiences with a deleted audience, or if you attempt to save an activity that references a deleted audience, a warning message displays.

You can also target custom profile parameters and `user.` parameters. When adding an audience, click **[!UICONTROL Add Rule]** > **[!UICONTROL Visitor Profile]**, then choose the parameter you want to use to target your activity. If the desired parameter does not appear, the parameter has not been fired by an mbox. Other custom mbox parameters are available in the [!UICONTROL Custom Parameters] drop-down list.

Use the search box to search your [!UICONTROL Audiences] list. You can search for any part of an audience name, or you can enclose a specific string in quotes.

You can sort the [!UICONTROL Audiences] list by audience name or by the date when it was last modified. To sort by name or date, click the column header, then select to display audiences in ascending or descending order.

## View audience definitions {#section_11B9C4A777E14D36BA1E925021945780}

You can view audience definition details on a pop-up card in various places in the Target UI without opening the audience. This functionality applies to audiences created in Target Standard/Premium and audiences imported from Target Classic or created via API.

For example, the following audience definition card is accessed by hovering over an audience on the Audience List, then clicking the View icon:

![Activities > Audience definition](assets/audience_definition_list.png)

The following audience definition card is accessed by clicking the View icon on an activity's Overview page:

![Activities > Audience definition](assets/audience_definition_list.png)

Click the [!UICONTROL Audience Usage] tab to see other activities that reference that audience, if applicable. This way you can avoid accidental impact to other activities while editing audiences. Information includes Live Activities, Inactive Activities, Archived Activities, And Syncing Activities. This feature is available for all audiences (Library audiences and [activity-only audiences](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

If an audience is combined with another audience and the combined audience is used to create an activity, the usage information for both audiences will list that newly created activity.

![](assets/audience_definition_list_usage.png)

The following audience definition card is for an audience imported from the Adobe Experience Cloud. In this instance, the audience was imported from Adobe Audience Manager (AAM).

![Usage tab on Audience Definition card](assets/audience_definition_mc.png)

The following details are available for these imported audience types:

| Audience Type | Details |
|--- |--- |
|Mobile audience|Marketing Name, Vendor, and Model.<br>The `matches | does not match` operator displays instead of `equals | does not equal`<br>![Imported Mobile Audience](/help/c-target/c-audiences/assets/imported_mobile_audience.png).|
|Visitor-behavior audience|**user.categoryAffinity:** `categoryAffinity` with `FAVORITE` parameter.<br>![Imported Category Affinity](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Monitoring:** Monitoring service equals true.<br>**No Monitoring Service:** Monitoring service equals false.<br>![Imported Monitoring](/help/c-target/c-audiences/assets/imported_monitoring.png)|
|Audiences using the NOT operator|**Single Rule:** Target displays the audience in the format `[All Visitor AND [NOT [rule]`. Single NOT rule displays with AND with `AllVisitor` audience.<br>![Imported Not Audience](/help/c-target/c-audiences/assets/imported_not_audience.png)|

Keep the following points in mind as you work with imported audiences:

* Expression target audiences are no longer supported in Target Standard/Premium. 
* Target Standard/Premium does not support some deprecated audiences or has improved operators for ease of use. Because of this, the definition of an imported audience, although working as per definition, does not mean that same is now available for creation in the Standard/Premium interface. For example, Social Audiences are visible with their rules but Target Standard/Premium does not allow social audiences to be created.

## Training video: Using Audiences

This video includes information about using audiences.

* Explain the term "audience" 
* Explain the two ways audiences are used for optimization 
* Find audiences in the Audiences List 
* Target an activity to an audience 
* Use audiences for passive reporting in an activity

>[!VIDEO](https://video.tv.adobe.com/v/17398)