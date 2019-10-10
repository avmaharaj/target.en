---
description: Two specialized reports are available to users of Automated Personalization (AP) and Auto-Target (AT) activities  the Automated Segments and Important Attributes reports.
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
seo-description: Two specialized reports are available to users of Automated Personalization (AP) and Auto-Target (AT) activities  the Automated Segments and Important Attributes reports.
seo-title: Personalization Insights reports
solution: Target
title: Personalization Insights reports
title-outputclass: premium
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Personalization Insights reports{#personalization-insights-reports}

Two specialized reports are available to users of Automated Personalization (AP) and Auto-Target (AT) activities: the Automated Segments and Important Attributes reports.

>[!NOTE]
>
>AP and AT activities are available as part of the [!DNL Target Premium] solution. They are not included with [!DNL Target Standard] without a [!DNL Target Premium] license.
>
>Personalization Insights reports are available only for AP and AT activities that use a conversion optimization goal. Activities where the optimization goal was changed to conversion from revenue after the activity was already live are also not supported.
>
>Personalization Insights reports are supported in the [default environment](../../administrating-target/hosts.md) only.
>
>Personalization Insights reports are generated only for activities that are in the Live status and have been activated and receiving traffic for at least 15 days.

## Personalization Insights Reporting overview {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

The goal of the [!UICONTROL Personalization Insights] reports is to provide more information on how the Target personalization models behind your AP and AT activities personalize visitor traffic. The [Random Forest algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md) is the basis for Target's personalization models.

Because the goal of the Personalization Insights reports is to understand how Target's personalization models decided to send which visitor to what piece(s) of content, the Personalization Insights reports reflect only a sub-segment of all the traffic served by your AP or AT activity. Specifically, the two reports are reflective of all traffic that used the personalization model. In other words, Personalization Insights reports do not consider control traffic or traffic that is served by the overall winner model.

Two Personalization Insights reports are available:

| Report | Details |
|--- |--- |
|Automated Segments|Different visitors respond differently to the offers/experiences in your AP/AT activity. This report shows how different automated segments defined by Target's personalization models responded to the offers/experiences in the activity.|
|Important Attributes|In different activities, different attributes are more, or less, important to how the model decides to personalize. This report shows the top attributes that influenced the model and their relative importance.|

## Interpreting attributes in Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

There are two types of attributes represented in [!UICONTROL Personalization Insights] reports that are used in your AP or Auto Target models:

* **Attributes automatically collected by Target:** Target uses a base data set to build its personalization algorithms in AP and AT activities that are reflected in Personalization Insights. See [Data Collection for Target's Personalization Algorithms](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058) for data types, example attributes, and their [!UICONTROL Personalization Insights] naming convention. Note that although these attributes are considered, an individual activity’s models might not use all of these attributes in the final model. 
* **Attributes passed to Target:** See [Uploading Data for the Target Personalization Algorithms](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

Target provides many ways for you to pass in additional data to Target to enrich the base data set used to build its personalization algorithms in AP and AT activities:

| Data Type | Description | Data Type Naming Convention |
|--- |--- |--- |
|Profile Attributes, including profile scripts, Profile Update API, and in-page profile attributes|Any information you've decided to include in Target's user profile.<br>This information could come from profile scripts, information uploaded using the Profile Update API, or in-mbox profile parameters prefixed with "profile."|`Custom - Profile - [parameter name]`|
|Page Parameters (also called “mbox parameters”)|Name/value pairs passed in directly through page code that are not stored in the visitor's profile for future use.|`Custom - Mbox Parameter - [parameter name]`|
|Customer Attributes|Customer attributes let you upload visitor profile data via FTP to the Experience Cloud. Once uploaded, leverage the data in Adobe Analytics and Adobe Target.|`Custom - Customer Attributes - [parameter name]`|
|Shared Audiences (Adobe Audience Manager or Adobe Analytics)|Audiences created through Adobe Audience Manager or Adobe Analytics and shared with Target.|`Custom - Experience Cloud Segment - [segment name]`|
|In-Activity Reporting Audiences/ Segments|Audiences defined in your AP or Auto Target activity during setup in “Goals & Metrics.”|`Custom - Reporting Segment - [segment name]`|

## Training video: Using the Personalization Insights reports

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

For more information, see [Using the Personalization Insights Reports in Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).
