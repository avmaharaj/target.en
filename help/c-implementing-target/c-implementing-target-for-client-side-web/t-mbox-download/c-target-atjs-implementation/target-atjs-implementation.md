---
description: The at.js library is a new implementation library for Adobe Target designed for both typical web implementations and single-page applications.
keywords: Target Standard;at.js;implementation
seo-description: The at.js library is a new implementation library for Adobe Target designed for both typical web implementations and single-page applications.
seo-title: Migrate from mbox.js to at.js
solution: Target
title: Migrate from mbox.js to at.js
topic: Standard
uuid: 10da01d7-d308-44e3-9c6e-ff4f713bd312
---

# Migrate from mbox.js to at.js{#migrate-from-mbox-js-to-at-js}

The at.js library is a new implementation library for [!DNL Adobe Target] designed for both typical web implementations and single-page applications.

Among other benefits, [!DNL at.js] improves page-load times for web implementations and provides better implementation options for single-page applications.

[!DNL at.js] replaces [!DNL mbox.js] for [!DNL Target] implementations. The [!DNL at.js] library also includes the components that were included in [!DNL target.js], so there is no longer a call to [!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 with FP-11577 (or later) supports at.js implementations with its Adobe Target Cloud Services integration. For more information, see [Feature Packs](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) and [Integrating with Adobe Target](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) in the *Adobe Experience Manager 6.2 documentation*.

## Benefits of at.js {#benefits}

The following table explains the differences between the two libraries:

| Library Reference | Description |
|--- |--- |
|at.js|at.js replaces mbox.js for [!DNL Target] implementations.<br>Among other benefits, at.js improves page-load times for web implementations, improves security, prevents  document.write warnings in Google Chrome, and provides better implementation options for single-page applications.<br>For more information, see [at.js Implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md).|
|mbox.js|Prior to [!DNL Target] 16.3.1 (March 2016), [!DNL Target] required a call to mbox.js to create the global mbox required for [!DNL Target] to deliver activities, track clicks, and track most success metrics. This file contains the libraries needed for all of your activities. You do not need to maintain different activity-specific versions of the file.<br>If you already have wrapping mboxes on your pages from an older style of [!DNL Target] implementation, these mboxes can still be used in the new interface. The updated mbox.js file is still required, but these mboxes can be selected for activities and edited using the  Visual Experience Composer.<br>[!DNL Target] Standard and Premium update and supplement mbox.js with a reference to a  target.js file. The  target.js file is hosted by Adobe. The  Target.js file makes it possible to edit content on any page using the  Visual Experience Composer, even if the page does not contain predefined mboxes. You must reference this file on every page on your site.<br>For more information, see [mbox.js Implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Important**: The mbox.js library is still supported, but there will be no feature updates. All customers should migrate to at.js. For more information, see [Migrate to at.js from mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br>|

## Implement at.js

To use [!DNL at.js], replace the [!DNL mbox.js] reference on pages where you want to implement it. You cannot use both [!DNL mbox.js] and [!DNL at.js] on a single page. However, you can use either on each page on your site.

The [!DNL at.js] library works for existing implementations using the `mboxCreate()`, `mboxDefine()`, and `mboxUpdate()` functions and supports new functionality focused on single-page-app based implementations.

You can use [!DNL at.js] anywhere you currently use [!DNL mbox.js].

The [!DNL at.js] library offers several improvements over the [!DNL mbox.js] library, including:

* Completely asynchronous communication via cross domain AJAX

  >[!IMPORTANT]
  >
  >Although [!DNL at.js] communicates with the [!DNL Target] servers asynchronously, the [!DNL at.js] file itself must load synchronously in the `<head>` section of your page. Ideally, it should be one of the first scripts loaded. Once loaded, [!DNL at.js] executes mbox calls asynchronously through `XMLHttpRequest`, and does not block page rendering.

* No more blocking calls 
* No `document.write()` used 
* No immediate execution of JavaScript in [!DNL Target] responses 
* Better timeout and error handling

    * Customizable [timeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) per call 
    * No reloads on timeouts

* Functions designed specifically for single-page apps/MVC frameworks

## Training video: at.js - Advantages and Implementation Best Practices

This video is a recording of " [Office Hours](../../../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)," an initiative led by the Adobe Customer Care team.

* How the at.js library works 
* The advantages of at.js over mbox.js 
* How at.js manages flicker 
* Error handling in at.js 
* Debugging methodologies 
* Known issues and future roadmap

>[!VIDEO](https://video.tv.adobe.com/v/22223/) 
