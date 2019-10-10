---
description: Information about common integrations with Target and their support status with at.js.
keywords: at.js integration;supported integrations;unsupported integrations;third party integrations
seo-description: Information about common integrations with Target and their support status with at.js.
seo-title: at.js integrations
solution: Target
title: at.js integrations
topic: Standard
uuid: 19036a1d-941c-4d31-8c7b-f50c86996b1c
---

# at.js integrations{#at-js-integrations}

Information about common integrations with [!DNL Target] and their support status with at.js.

If you have a compelling need for an integration that is not supported or mentioned here, please contact your account representative or consultant.

## Supported Integrations {#section_3B44A970D3FB42D1973701452C868B55}

| Integration | Details |
|--- |--- |
|Analytics for Target (A4T)|See [Adobe Analytics as the Reporting Source for Adobe Target (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).|
|Profiles & Audiences (P&A)|See [Audiences](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) in the *Core Services User Guide*.|
|Experience Cloud ID Service|See the [Adobe Experience Cloud ID Service documentation](https://docs.adobe.com/content/help/en/id-service/using/home.html).|
|Adobe Launch|Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.  See [Implementing Target using Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25).|
|Dynamic Tag Management (DTM)|See the [Best Practices for Implementing Target Using Dynamic Tag Management guide](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html).   Important: [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) is the preferred, up-to-date method for implementing Target and the at.js library. For new Target implementations, use Launch. The following guide is for existing clients using a DTM implementation.   Consider the following when using a DTM integration: <ul><li>Library Management: Use the "Custom" hosting option to use at.js. "Automatic" management is not currently supported. </li></ul>|
|Adobe Experience Manager (AEM) Cloud Service|The AEM Cloud Service enables the creation of A/B tests and Experience Targeting activities within the AEM workflow. Supports at.js with Adobe Experience Manager 6.2 with FP-11577 (or later) . For more information, see [Integrating with Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) and select your AEM version.|
|AEM Experience Fragments|Experience fragments created in AEM in Target activities let you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in Target to test and personalize experiences at scale.  AEM brings together all of your content and assets in a central location to fuel your personalization strategy. AEM lets you easily create content for desktops, tablets, and mobile devices in one location without writing code. There’s no need to create pages for every device—AEM automatically adjusts each experience using your content.  See [AEM experience fragments](../../../c-experiences/c-manage-content/aem-experience-fragments.md#topic_1E1E4EA01F074349B2CF8785387B5FE8).|

## Unsupported Integrations {#section_8EFCAED418DC42E0B07F95924819EAC2}

| Integration | Details |
|--- |--- |
|[!DNL Legacy Target to SiteCatalyst Integration]|This was the integration that sent campaign and recipe ids to [!DNL SiteCatalyst] via the page call so you could do reporting in the  [!DNL SiteCatalyst] UI. This functionality is replaced by A4T.|
|[!DNL Legacy Target to SiteCatalyst Integration]|This was the integration that made mbox calls named `"SiteCatalyst: Event"` and `"SiteCatalyst: Purchase"` so you could build success metrics and user profiles based on evars and props. This functionality is replaced by A4T and P&A.|
|[!DNL Legacy Audience Manager (AAM) to Target Integration]|This was the integration that made a front-end API call to retrieve AAM segments and then sent them as mbox parameters on every mbox call on the page.|

## Third-Party Integrations {#section_EE599839CCAD49DD97640E5EDAD9082E}

| Integration | Details |
|--- |--- |
|Other Tag Managers|at.js should work with non-Adobe tag management platforms, but be careful using custom integration features that other vendors have developed. Their integrations might be dependent on internal  mbox.js functions that no longer exist in  at.js.|
|Third-party data providers (e.g. Demandbase, Bluekai, weather APIs)|Many third-party data providers used to supplement Target's user profiling can be integrated using the at.js [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers) feature.|