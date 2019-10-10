---
description: Details about changes in each version of at.js.
keywords: at.js releases;at.js versions
seo-description: Details about changes in each version of at.js.
seo-title: at.js version details
solution: Target
subtopic: Getting Started
title: at.js version details
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
---

# at.js version details {#at-js-version-details}

Details about changes in each version of the [!DNL Adobe Target] at.js JavaScript library.

>[!IMPORTANT]
>
>The Target team maintains only two versions of [!DNL at.js]—the current version and the second-latest version. Please upgrade [!DNL at.js] as necessary to ensure that you are running a supported version.

## at.js version 2.2 (October 10, 2019)

This release of at.js includes the following enhancements and fixes:

* Improved performance when using both Experience Cloud ID Service (ECID) v4.4 and at.js 2.2 on your web pages.
* Previously, the ECID made two blocking calls before at.js could fetch experiences. This has been reduced to a single call, which significantly improves performance.

  >[!NOTE]
  >
  >Upgrade your ECID Launch Extension to v4.4 to take advantage of this performance enhancement.

* at.js version 2.2 also provides a new setting called `serverState`. This setting can be used to optimize page performance when a hybrid integration of Target is implemented. Hybrid integration means that you are using both at.js v2.2+ on the client-side and the delivery API or a Target SDK on the server-side to deliver experiences. `serverState` gives at.js v2.2+ the ability to apply experiences directly from content fetched on the server side and returned to the client as part of the page being served. For more information, see "serverState" in [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).

## at.js version 1.8 (October 10, 2019)

This release of at.js includes the following enhancements and fixes:

* Improved performance when using both Experience Cloud ID Service (ECID) v4.4 and at.js 1.8 on your web pages.
* Previously, the ECID made two blocking calls before at.js could fetch experiences. This has been reduced to a single call, which significantly improves performance.

>[!NOTE]
>
>Upgrade your ECID Launch Extension to v4.4 to take advantage of this performance enhancement.

## at.js version 2.1.1 (July 24, 2019)

This release of at.js is a maintenance release and includes the following enhancements and fixes:

(The issue numbers in parentheses are for internal Adobe use.)

* Fixed an issue that caused multiple beacons to fire when using the Click Tracking metric on the Goals & Settings page in the Visual Experience Composer (VEC). (TNT-32812)
* Fixed an issue that caused `triggerView()` to not render offers more than once. (TNT-32780)
* Fixed an issue with `triggerView()` to ensure that the request contains Marketing Cloud ID (MCID) information. (TNT-32776)
* Fixed an issue that prevented the `triggerView()` notification to fire even if there are no saved views. (TNT-32614)
* Fixed an issue that caused an error due to the use of decodeURIcomponent that caused issues when the URL contains a malformed query string parameter. (TNT-32710)
* The beacon flag is now set to "true" in the context of delivery requests sent via the `Navigator.sendBeacon()` API. (TNT-32683)
* Fixed an issue that prevented Recommendations offers from displaying on websites for a few customers. Customers could see the offer content in the delivery API call but the offer was not applied on the website. (TNT-32680)
* Fixed an issue that caused click-tracking across multiple experiences to not work as expected. (TNT-32644)
* Fixed an issue that prevented at.js from applying the second metric after the rendering of the first metric fails. (TNT-32628)
* Fixed an issue when passing `mboxThirdPartyId` using the `targetPageParams` function that caused the request payload to not be present in either the query parameters or in the request payload. (TNT-32613)
* Fixed an issue that caused display and click notification responses to be blocked in Chromium-based browsers (including Google Chrome). (TNT-32290)

## at.js version 2.1.0 (June 3, 2019)

This release includes the following features and enhancements:

* **Adobe Opt-in support**: Adobe Opt-In is a way to simplify Adobe solutions integrations with consent management platforms. For more information about Adobe Opt-in, see [Privacy and General Data Protection Regulation (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

* **Industry-standard CSP compliant**: at.js no longer uses eval() to execute JavaScript.

* **Client-side analytics logging**: Give customers full control on how they want to send analytics data to Adobe Analytics, whether on the client-side or server-side. 

  For more information, see [Client-side Analytics logging](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) in *Before you implement*.

* **Send notifications**: Allow developers to send notifications when an experience is rendered by their code instead of using `applyOffer()` or `applyOffers()`.

  For more information, see [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).

* **at.js size reduced by ~24%**: The size of at.js is reduced by ~24%. The smaller file size improves page load performance and reduces the time to download at.js on the page.

## at.js version 2.0.1 (March 19, 2019)

This is a maintenance release and includes the following enhancements and fixes:

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

* Fixed a race condition in the DOM polling code that caused JavaScript exceptions for certain customers. (TNT-31869)
* Notifications that views were rendered have been decoupled from click-tracking event handlers. Initially, Target did not send notifications if click-event handlers belonging to a rendered view could not be attached. Target now sends a view notification even when click elements are not found. (TNT-31969)
* Fixed an issue that caused the request-succeeded event redirect flag to always be set to true. (TNT-31907)
* Fixed an issue that caused the VEC rearrange action to be logged as success, even when elements were missing. (TNT-31924)
* Fixed an issue that caused notifications for certain customers to not contain the Enterprise Permissions property token. (TNT-31999)

## at.js version 1.7.1 (March 19, 2019)

This is a maintenance release and includes the following fix:

(The issue numbers in parentheses are for internal [!DNL Adobe] use.)

* Fixed a race condition in the DOM polling code that caused JavaScript exceptions for certain customers. (TNT-31869)

## at.js Version 2.0.0 {#at-js-200}

at.js 2.x provides rich feature sets that equip your business to execute personalization on next generation client-side technologies. This new version is focused on upgrading at.js to have harmonious interactions with single page applications (SPAs).

Here are some benefits of using at.js 2.x that are not available in previous versions:

* The ability to cache all offers on page load to reduce multiple server calls to a single server call.
* Tremendously improve your end-users' experiences on your site because offers are shown immediately via the cache without any lag time that traditional server calls introduce.
* Simple one-line of code and one-time developer setup to enable your marketers to create and run A/B and Experience (XT) activities via the Visual Experience Composer (VEC) on your single page applications.

at.js 2.x introduces the following new functions:

* getOffers()
* applyOffers()
* triggerView()

The following functions have been deprecated with the introduction of at.js 2.x:

* mboxCreate()
* mboxDefine
* registerExtension()

For more information, see [Upgrading from at.js 1.x to at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) and [at.js functions](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>
>If you require Adobe Opt-in support for the [General Data Protection Regulation](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR), you must currently use at.js 1.7.0 or at.js 2.1.0.

## at.js Version 1.7.0 {#at-js-170}

at.js 1.7.0 brings Adobe Opt-In support. Adobe Opt-In is a way to simplify Adobe solutions integrations with consent management platforms.

For more information about Adobe Opt-in, see [Privacy and General Data Protection Regulation](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR).

This release also fixes an issue where Target might override redirect URL parameters with parameters that are coming from the redirect URL.

>[! NOTE]
>
>If you require Adobe Opt-in support for GDPR, you must currently use at.js 1.7.0 or 2.1.0.<br>For a list of all versions, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## at.js Version 1.6.4 {#at-js-164}

at.js 1.6.4 is a maintenance release and addresses the following issue:

* Fixed a race condition manifesting in Microsoft Internet Explorer 11 that caused duplicate offers to be applied.

## at.js Version 1.6.3 {#section_484A56774E004282B98FFFF851E4E670}

at.js version 1.6.3 includes the following fixes and enhancements:

* Selectors are now CSS-escaped if they contain IDs or CSS classes that start with a digit, two hyphens, or a hyphen followed by a digit (for example #-123). (TNT-31061)
* Fixed an issue introduced with at.js 1.6.2 where Visual Experience Composer (VEC) offers from different activities that apply to the same CSS selector did not respect activity priority. (TNT-31052)
* Fixed an issue with timing out a promise in environments where there was no native support for promises. (TNT-30974)
* Issues are now correctly captured and reported via the content-rendering failed event. Previously, JavaScript might have been reported to have run successfully, even if that wasn't the case. (TNT-30599)

## at.js Version 1.6.2 {#section_88BE2F69943D4280B8170F377886B58E}

This is a maintenance release and addresses the following issue:

* Fixed an issue that on some customer sites lead to an infinite "async" loop.

>[!IMPORTANT]
>
>In addition, at.js Version 1.6.2 also contains all of the enhancements and fixes included in at.js Version 1.6.1 and 1.6.0. These versions are no longer available for download. We recommend that you upgrade to version 1.6.2 if using 1.6.1 or 1.6.0

Here are the enhancements and fixes that were included in at.js Version 1.6.1:

* Fixed an issue in at.js 1.6.0 that caused recommendations experiences to be duplicated in Microsoft Internet Explorer 11. (TNT-30593) 
* at.js now ensures that the edge override logic checks for the existence of an edge cluster cookie to avoid a different edge number if a user hops edges during a session. (TNT-30563) 
* Fixed an issue that prevented at.js from executing subsequent actions if the HTML content contained invalid JS code. at.js now logs the error and renders the remaining actions without issue. (TNT-30546) 
* Made changes so that there is an exception when a redirect page re-qualifies for a redirect activity. (TNT-30532) 
* Fixed an issue that prevented the correct request timeout being propagated from the getOffer() API request. (TNT-30498) 
* Fixed an issue that prevented at.js 1.6.0 from saving cookies when using file protocol. (TNT-30454) 
* Fixed an issue that made it appear that not all experiences were being delivered with redirects when using Analytics for Target (A4T). (TNT-30444) 
* Fixed an issue that caused the page to be hidden after the Target call succeeds. (TNT-30358)

Here are the enhancements and fixes that were included in at.js Version 1.6.0:

* Redirect offers are now automatically supported in the Analytics for Target (A4T) integration. The client-side workaround has been removed. (TNT-30247) 
* Client-side edge routing is now enabled by default. (TNT-30261) 
* Fixed an issue with Visual Experience Composer (VEC) action rendering when there are dependencies between actions. (TNT-30248)

## at.js Version 1.5.0 {#section_128C6761884C4DA8AE50D6A605FF6F55}

at.js version 1.5.0 is now available.

* The details of the `at-request-succeeded` event contain the redirect flag. This flag can be used to determine if the page will be redirected to a different URL. If you want to know the URL, subscribe to `at-content-rendering-redirect`. (TNT-29834) 
* Fixed an issue that caused `window.targetGlobalSettings.enabled` to fail with a runtime exception if it was set to false. (TNT-29829) 
* Fixed an issue that caused the page to fail while loading in the Visual Experience Composer (VEC) if using custom code to a fire global mbox request and using body hiding. (TNT-29795) 
* Added support for `screenOrientation`, `devicePixelRatio`, and `webGLRenderer`. These new Target request parameters are used for iPhone X and other modern device detection. For more information, see [Mobile](../../c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89). (TNT-29781) 
* Fixed an issue where the Adobe Audience Manager (AAM) location hint wasn't always sent. (TNT-29695) 
* For browsers that support it, at.js 1.5.0 switches to MutationObserver for selector polling. Versions prior to at.js 1.0.0 used a MutationObserver polyfill, which proved to be problematic. To avoid the polyfill issues, version1.5.0 uses the following pseudo code to decide which scheduling mechanism to use:

  ```
  if MutationObserver is supported
    scheduler = MutationObserver
  else if document is visible
    scheduler = requestAnimationFrame
  else
    scheduler = setTimeout
  ```

## at.js Version 1.3.0 {#section_24EAAE1CFA814EF8B19E61842F4D8321}

at.js version 1.3.0 is now available.

* The following new events are available to help in tracing, debugging, and customizing interaction with at.js:

  * LIBRARY_LOADED 
  * REQUEST_START 
  * CONTENT_RENDERING_START 
  * CONTENT_RENDERING_NO_OFFERS 
  * CONTENT_RENDERING_REDIRECT

  For more information, see [at.js custom events](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md). 

* You can augment an at.js request with additional parameters that come from data providers. Data providers should be added to `window.targetGlobalSettings` under the `dataProviders key`.

  For more information, see [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers). 

* at.js requests now use GET, but it will switch to POST when the URL size exceeds 2048 characters. There is a new property named `urlSizeLimit` where you can increase the size limit if necessary. This change allows Target to align at.js to AppMeasurement, which uses the same technique. 
* Target now enforces that the `mbox` key in the `adobe.target.applyOffer(options)` function is used. This key has been required in the past, but Target now enforces its use to ensure that Target has proper validation and customers are using the function correctly. 
* at.js has improved event and click tracking functionality. at.js uses `navigator.sendBeacon()` to send event tracking data and will fallback to synchronous XHR when `navigator.sendBeacon()` is not supported. This fallback mostly affects Internet Explorer 10 and 11 and some versions of Safari. Safari will add support for `navigator.sendBeacon()` in the upcoming iOS 11.3 release. 
* at.js can now render offers even when a page is opened in background tabs. Some Target Customers encountered an issue when `requestAnimationFrame()` was disabled because of the browser throttling behavior for background tabs. 
* This release adds many performance improvements, including shorter callstacks when inspecting a Chrome CPU profile. 
* at.js 1.3.0 no longer supports content delivery on Microsoft Internet Explorer 9. For a list of supported browsers, see [Supported Browsers](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100). Going forward, all requests are executed via `XMLHttpRequest` with CORS support with no JSONP requests. This change greatly improves security.

## at.js Version 1.2.3 {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

[!DNL at.js] version 1.2.3 is now available.

* Adds support for JSON offers. JSON offers are supported only in activities created using the Form-based Experience Composer. Currently the only way to use JSON offers is via direct API calls. See [Create JSON Offers](../../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D).

## at.js Version 1.2.2 {#section_4E96D13F2DFE4F1F81A1089877D53649}

[!DNL at.js] version 1.2.2 is now available.

* Fixed an issue that returned a JavaScript error when the Target library loaded on a page using QUIRKS mode. (TNT-28312) 
* Fixed an issue that caused Target click tracking to break Analytics data collection calls. (TNT-28261) 
* Fixed an issue that caused `getOffer() params` to fail when `targetPageParams()` returns an empty string. (TNT-28359) 
* Fixed an issue with session ID generation when using x-only. (TNT-28361)

## at.js Version 1.2.1 {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

[!DNL at.js] version 1.2.1 is now available.

* Fixed an issue when click tracking on a link with target="_blank" prevented Target from opening the link in a new tab.

## at.js Version 1.2.0 {#section_1C3A18C595C34B25A14A440D213F3B9C}

[!DNL at.js] version 1.2 is now available as a maintenance release that contains mostly bug fixes.

* Fixed an issue that prevented default actions for click-tracking special cases. (TNT-28089) 
* Fixed an issue when click-tracking on a link with `target="_blank"` that prevented Target from opening the link in a new tab. (TNT-28072) 
* IP addresses can be used as the cookie domain. (TNT-28002) 
* Fixed an issue that caused flicker in redirect offers with a global mbox or other regional mboxes. (TNT-27978) 
* Fixed an issue in Experience Targeting activity setup failing within the VEC when switching between Browse and Compose. (TNT-27942) 
* Fixed incorrect handling on flicker style classes for click-track elements. (TNT-27896) 
* Fixed an issue that caused global mbox parameters to become mixed up with all mbox parameters. (TNT-27846) 
* Made changes to ensure that Handlebars, Mustache, and other client-side templating libraries are properly handled by [!DNL at.js]. (TNT-27831) 
* Made changes to ensure that `sdidParamExpiry` is properly initialized and passed to the Visitor API. This is a regression that has been added to `at.js 1.1.0`. Previous [!DNL at.js] versions are not affected. This affects only clients using redirect offers and A4T. (TNT-27791) 
* Made changes to ensure that `SCRIPT` is executed regardless of the type attribute being used. (TNT-27865)

## at.js Version 1.1.0 {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**Date:** August 2, 2017

The following enhancements and fixes are included in [!DNL at.js] version 1.1:

* Added response token handling. For more information, see [Response Tokens](../../administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4). 
* Resolved issue so that `document.currentScript polyfill` doesn't interfere with Angular 1.X. 
* Made changes to ensure that click tracking doesn't interfere with visibility property. Click tracking elements are marked with the `at-element-click-tracking` CSS class instead of `at-element-marker`.

## at.js Version 1.0.0 {#section_37A3D23FC4AD42A68AA831B89E03E725}

**Date:** July 7, 2017

The following enhancements and fixes are included at.js version 1.0:

* Support for loading at.js asynchronously for faster page loads. 
* Support for pre-hiding page content when loading at.js asynchronously. 
* Better error messaging when content delivery is disabled. 
* Performance improvements when delivering multiple activities. 
* Support for YUI Compressor. 
* Bug/error reporting for custom events during activity delivery. 
* Fix for performance issues in Microsoft Internet Explorer 11. 
* Fix for `getOffer()` function giving an error on some websites. 
* Load the Target library asynchronously. For more information, see [at.js Frequently Asked Questions](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## at.js Version 0.9.7 {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**Date:** May 22, 2017

The following enhancements and fixes are included in [!DNL at.js] version 0.9.7:

* Fixed an issue related to an asset key that was missing from `insertAfter` and `insertBefore` actions in the Visual Experience Composer (VEC). These issues were related to the migration from visual offers to offer templates.

## at.js Version 0.9.6 {#section_EEFA6413F2F947AD8C4A88128B90245D}

**Date:** April 13, 2017

The following enhancements and fixes are included in [!DNL at.js] version 0.9.6:

* Redirect offer support for A4T. After you download and install [!DNL at.js] version 0.9.6, you can use redirect offers in activities that use [!DNL Adobe Analytics] as the Reporting Source for [!DNL Target] (A4T). Besides [!DNL at.js] version 0.9.6, there are other minimum requirements your implementation must meet in order to use redirect offers and A4T. For more information and additional important information you should know, see [Redirect Offers - A4T FAQ](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905). 
* Prior to [!DNL at.js] 0.9.6, when the Visitor API was present on the page and the `visitorApiTimeout` setting was too aggressive, Target could run into a situation when no MCID data was sent in the [!DNL Target] request. This could lead to issues like unstitched hits in [!DNL Analytics] when using A4T.

  This behavior has been changed in [!DNL at.js] 0.9.6, even if the `visitorApiTimeout` is set to say 1 ms, Target will try to collect SDID, tracking servers, and customer IDs data and send those in the Target request. 

* Added the `selectorsPollingTimeout` setting. For more information, see [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). 
* The format of the response from `getOffer()` has been changed. For more information, see [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md). 
* Console logging has been added for unsupported `<!DOCTYPE>` declarations. 
* Fixed an issue where [!DNL Target Classic] plugins weren’t being applied correctly when multiple default offers were delivered to a single mbox. (TGT-22664) 
* Improved cookie-setting for two letter top-level-domains (TLDs) to ensure that the mbox cookie is set correctly for these domains (for example, [!DNL test.no], [!DNL autodrives.ca], and so forth). 
* The algorithm for extracting the top-level domain that should be used when saving cookies has changed in at.js version 0.9.6. Because of this change, cookies cannot be saved to addresses that use IP. Most of the time, IP addresses are used for testing purposes, but as workarounds you can use DNS entries or adjust the hosts file on a local box. 
* Fixed move and rearrange actions handling when properties are string values instead of integers.

## at.js Version 0.9.4 {#section_A15B12F12CD94F07B3F56613A79A815F}

**Date:** January 19, 2017

* mbox names can now contain special characters, including ampersands ( & ), to be consistent with naming requirements for mbox names using mbox.js.

  For a list of allowable special characters, see [at.js Configurations](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812). 

* Added `secureOnly` setting that indicates whether at.js should use HTTPS only or be allowed to switch between HTTP and HTTPS based on the page protocol. This is an advanced setting that defaults to False and can be overridden via `targetGlobalSettings`. 
* The [!UICONTROL Legacy Browser Support] option is available in at.js version 0.9.3 and earlier. This option was removed in at.js version 0.9.4.

## at.js Version 0.9.3 {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**Date:** October 10, 2016

* Ensures mbox calls fire in Microsoft Internet Explorer 11 when legacy browsers are disabled in the at.js settings. 
* Ensures that default content is rendered if a dynamic remote offer fails (for example, if the URL is incorrect and returns a 404 error). 
* Ensures that elements are revealed quickly when VEC click-tracking selectors can't be found in the DOM.

## at.js Version 0.9.2 {#section_148549CBB4F046BAA8F79C79B64EC889}

**Date:** September 21, 2016

* Added an `optoutEnabled` setting to enable or disable the Device Graph opt-out. If this setting is set to `true` and the visitor has opted out of tracking, the visitor's browser will not make any mbox calls. Device Graph is currently in Beta. This setting is set to `false` by default, but must be set to `true` if you are using Device Graph. A similar option is part of mbox.js v61. 
* Added `CustomEvent` support for the notification mechanism. Previously, the at.js event notification mechanism could not be used via standard DOM APIs, such as `document.addEventListener()`. Now you can use `document.addEventListener()` to subscribe to at.js events, such as request events and content rendering events. 
* Fixed an issue related to offers created in the Visual Experience Composer (VEC). Prior to this release, Target hid the selectors and un-hid them only when all selectors matched. In at.js 0.9.2 Target un-hides the selectors as soon as they are matched.

## at.js Version 0.9.1 {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**Date:** July 14, 2016

* Provides at.js a timeout for the Visitor Id Service, which is independent of the service’s own timeout. 
* Corrects an issue in 0.9.0 that impacted implementations using at.js on some pages and mbox.js on other pages. 
* If you use Adobe Analytics as your activity's reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). The mbox.js or at.js library automatically sends tracking server values to [!DNL Target]. During activity creation, you can leave the [!UICONTROL Tracking Server] field empty on the [!UICONTROL Goals & Settings] page.

## at.js Version 0.9.0 {#section_2981CC9792F245389B39BB5B69F84C4E}

**Target Release:** 16.6.1

**Date:** June 23, 2016

* Fixes a whitescreen issue when using VEC offers. Anyone using [!DNL at.js] should upgrade to this new version. 
* New `registerExtension` API.

  This new API gives developers access to certain jQuery modules used in [!DNL at.js] to develop extensions (aka plugins) for the library. There are a few implications for this change. This impact only those users who are using these features:

    * `getSettings()` API has been removed, but the same functionality is available using `registerExtension()`. 
    * `getTracking()` API has been removed, but the same functionality is available using `registerExtension()`. 
    
    * Existing extensions (e.g. AngularJS extensions) must be updated to use the `registerExtension()` approach.

* New at.js notification] API.

  The goal of this notification system is to provide more insight into what [!DNL at.js] is doing on the page and when there are issues. A common issue seen with the VEC is that an IT release changes the page, a VEC selector breaks, and the test stops delivering content correctly. A goal of this notification system is to make this delivery issue known to the page, so developers can access this information, pass it to a system like [!DNL Adobe Analytics], and alerts can be sent to the business owners that their test broke. 

* New `targetGlobalSettings()` API method.

  You can override settings in the at.js library, rather than configuring the settings in the [!DNL Target Standard/Premium UI]or by using REST APIs.

## at.js Version 0.8.0 {#section_E1C7B08EC0494388A022C28A8B8FE807}

**Date:** May 5, 2016.

This is the first official release of the [!DNL at.js] library.

[!DNL at.js] is a new implementation library for [!DNL Target] designed for both typical web implementations and single-page applications.

[!DNL at.js] replaces [!DNL mbox.js] for [!DNL Adobe Target] implementations.

>[!NOTE]
>
>Although [!DNL at.js] replaces [!DNL mbox.js], mbox.js will continue to be supported. For most people, [!DNL at.js] provides advantages over [!DNL mbox.js]. This gives you time to test [!DNL at.js] and to change the implementation on your pages.

Among other benefits, [!DNL at.js] improves page load times for web implementations, improves security, and provides better implementation options for single-page applications.

[!DNL at.js] contains the components that were included in [!DNL target.js], so there is no longer a call to [!DNL target.js].

When implementing [!DNL at.js], be aware of the following:

* Internet Explorer versions earlier than 8 are not supported. 
* Asynchronous implementation means legacy integrations like the [!DNL Test&Target] to [!DNL SiteCatalyst] plugin may not work. 
* [!DNL Target] plugins that reference [!DNL mbox.js] objects and methods are not supported. 
* All calls to [!DNL Target] are made via XMLHTTPRequest and content is returned via JSON.
