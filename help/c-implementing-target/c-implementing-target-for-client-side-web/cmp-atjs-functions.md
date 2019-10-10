---
description: List of functions that can be used with the Adobe Target at.js JavaScript library.
keywords: at.js;functions;javascript library
seo-description: List of functions that can be used with the at.js JavaScript library in Adobe Target.
seo-title: Adobe Target at.js functions
solution: Target
subtopic: Getting Started
title: at.js functions
topic: Standard
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
---

# at.js functions{#at-js-functions}

List of functions that can be used with the Adobe Target at.js JavaScript library. Click the links in the Function column for more information and examples.

|Function|Details|
| --- | --- | 
|[adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md)|This function fires a request to get a Target offer. Use with `adobe.target.applyOffer()` to process the response or use your own success handling.|
|[adobe.target.getOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at.js 2.x)|This function lets you retrieve multiple offers by passing in multiple mboxes. Additionally, multiple offers can be retrieved for all views in active activities.<br>**Note:** This function was introduced with at.js 2.x. This function is not available for at.js version 1.*x*.|
|[adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md)|This function is for applying the response content.|
|[adobe.target.applyOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at.js 2.x)|This function lets you apply more than one offer that was retrieved by adobe.target.getOffers().<br>**Note:** This function was introduced with at.js 2.x. This function is not available for at.js version 1.*x*.|
|[adobe.target.triggerView (viewName, options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at.js 2.x)|This function can be called whenever a new page is loaded or when a component on a page is re-rendered.<br> This function should be implemented for single page applications (SPAs) in order to use the Visual Experience Composer (VEC) to create A/B Tests and Experience Targeting (XT) activities.|
|[adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md)|This function fires a request to report user actions, such as clicks and conversions. It does not deliver activities in the response.|
|[mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at.js 1.x)|Executes a request and applies the offer to the closest DIV with mboxDefault class name.<br>**Note:** This function is available for at.js versions 1.*x* only. This function was deprecated with the release of at.js 2.x. This function returns default content if used with at.js 2.x.|
|[mboxDefine(options) and mboxUpdate(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at.js 1.x)|Define and update an mbox.<br>**Note:** This function is available for at.js versions 1.*x* only. This function was deprecated with the release of at.js 2.x. This function returns default content if used with at.js 2.x.|
|[targetGlobalSettings(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)|You can override settings in the at.js library using `targetGlobalSettings()`, rather than configuring the settings in the Target Standard/Premium UI or by using REST APIs.<ul><li>Data Providers: This setting lets customers gather data from third-party data providers, such as Demandbase, BlueKai, and custom services, and pass the data to Target as mbox parameters in the global mbox request.</li></ul>|
|[targetPageParams(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md)|This method allows you to attach parameters to the global mbox from outside of the request code.|
|[targetPageParamsAll(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md)|This method allows you to attach parameters to all mboxes from outside of the request code.|
|[registerExtension(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at.js 1.x)|Provides a standard way to register a specific extension.<br>**Note:** This function is available for at.js versions 1.*x* only. This function was deprecated with the release of at.js 2.x. This function returns default content if used with at.js 2.x.|
|[at.js custom events](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md)|at.js custom events let you know when an mbox request or offer fails or succeeds.|
|[adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)<br>(at.js 2.1.0)|This function sends a notification to Target edge when an experience is rendered without using `adobe.target.applyOffer()` or `adobe.target.applyOffers()`.<br>**Note**: This function has been introduced in at.js 2.1.0 and will be available for any versions above 2.1.0.|

