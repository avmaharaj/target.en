---
description: This page shows changes to each version of mbox.js.
keywords: mbox.js changes;mbox.js versions
seo-description: This page shows changes to each version of mbox.js.
seo-title: mbox.js version details
solution: Target
subtopic: Getting Started
title: mbox.js version details
uuid: 5f8e0511-637b-4c17-bb19-aa7f4d7c98ea
---

# mbox.js version details{#mbox-js-version-details}

This page shows changes to each version of mbox.js.

>[!NOTE]
>
>We recommend that all mbox.js users upgrade to version 57 or later. Some users have experienced timeout issues when `target.js` couldn't be loaded. Version 57 fixed that issue. However, if you are using the [!DNL Experience Cloud Visitor ID] service, version 58 or later is required.

The way Target responds to calls from your page depends on the version of the Target library you are using, whether the visitor ID implementation is present, and whether the visitor ID exists. For information, see [Target Call Responses by Library Version](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0).

>[!NOTE]
>
>The mbox.js library is no longer being developed. All customers should migrate from mbox.js to at.js. For more information, see [Migrate to at.js from mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## mbox.js version 63 {#section_ED8EFCF653A845ED8927F759578C4A33}

**Target Release:** 17.7.1

[!DNL mbox.js] version 63 is now available. For more information, see [Download mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/target-download-config-mbox.md).

The following enhancements and fixes are included in [!DNL mbox.js] version 63:

* Fixes an issue with SDID generation when using `mboxDefine()` and `mboxUpdate()`. This affects only clients that have Visitor API on the page.

## mbox.js version 62 {#section_723A9119FE204183847D3B0929A99B41}

* Fixed flicker issues in redirect activities when viewed in Google Chrome browsers. 
* Added `secureOnly` setting that indicates whether mbox.js should use HTTPS only or be allowed to switch between HTTP and HTTPS based on the page protocol. This is an advanced setting that defaults to False.

## mbox.js version 61 {#section_F3B59C5578B64883AE013B9342151193}

**Target Release:** 16.7.2

**Release Date:** July 28, 2016

mbox.js version 61 contains the following enhancements:

* The mboxSession ID generation algorithm in the JavaScript Date API now generates a random string instead of using a timestamp plus a random string. 
* The following details apply only if you have the Visitor API on the page:

    * [!DNL mbox.js] version 61 doesn't override the Visitor API `loadTimeout` property. Clients can use `visitorApiTimeout` + `visitorApiPageDisplayTimeout` to control Visitor API integration. 
    * Added an `optoutEnabled` setting to support future Adobe Experience Cloud opt-out functionality. The default value is false. If this property is enabled, all requests execute asynchronously against the [!DNL /ajax] endpoint, just like version 60. 
    * Body hiding is disabled by default. Target uses body hiding only when global mbox auto-create is enabled and body hiding is enabled. 
    * If there are no Experience Cloud Visitor ID cookies, all requests execute asynchronously against [!DNL /ajax] on the first page load. On the second page load, Target uses the normal flow because Visitor ID values are already present. 
    * If you use Adobe Analytics as your activity's reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). The mbox.js or at.js library automatically sends tracking server values to [!DNL Target]. During activity creation, you can leave the [!UICONTROL Tracking Server] field empty on the [!UICONTROL Goals & Settings] page.

## mbox.js version 60 {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Target Release:** 16.4.1

**Release Date:** April 21, 2016

By default, page content is not hidden. Version 60 hides page content only when the "auto-create global mbox" option is enabled. It uses the CSS `opacity:0` property for page hiding instead of `display:none`. This ensures proper delivery for responsive sites and aligns with [!DNL at.js].

You can enable body hiding using two settings:

* `bodyHidingEnabled` The default value is false, which means HTML BODY is not hidden. 

* bodyHiddenStyle

  The default value is `body{opacity:0}`. This value can be changed to something different, like `body{display:none}`.

These settings can be overridden by including something like:

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

The page hiding technique uses style tags to add and remove styles. This ensures that the site's styles remain unchanged after the page hiding code executes.

**DTM Users:** Note that this will prevent you from using the Automatic import option since there is no way to save the above configuration in the Target UI. You will have to use the instructions above and then paste the contents into the code box of the Custom hosting option.

Also in Version 60, if the [!DNL visitorAPI.js] file is present for the Experience Cloud Visitor ID service, all mboxes are requested via an AJAX endpoint. This is required because Visitor API methods are asynchronous. One benefit of this approach is that the Start Render time is decreased dramatically, because mbox requests do not block rendering. However, this also means that all [!DNL Target] offer content runs asynchronously, so all offer code must be written accordingly. Offers containing `document.write` and other code that assumes it will run on initial page load will not execute as expected.

* V60 asynchronous calls

  When using v60 with the visitor id service, all mbox calls are made asynchronously. This is a change from how mboxes have always worked, so be careful if upgrading to this version. Review the [Asynchronous Considerations](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953) section of the [!DNL at.js] documentation ( [!DNL at.js] also uses asynchronous calls) to understand some of the risks. 
* New Visitor scenarios might have flicker

  When using v58 to v60 with the visitor id service, mbox calls will wait for the visitor id to be set before firing (or until a timeout has occurred). This happens on the first page load of a new visitor.

## mbox.js version 59 {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Target Release:** 16.2.1

**Release Date:** February 17, 2016

mbox.js version 59 contains the following enhancements:

* Mbox disabled has been lowered to 30 minutes 
* An issue related to page hiding/unhiding has been fixed

  Rather than using `display:none` to hide the page as in version 58, `opacity:0` is used. This resolves issues with responsive-designed sites that resulted from the previous method of hiding the page.

## mbox.js version 58 {#section_5070B0D1C87F4937BB97727923DD36C7}

**Target Release:** 15.7.1

**Release Date:** July 30, 2015

This version of mbox.js is required if you use Analytics as the reporting source for Target and is highly recommended for Profiles and Audiences.

Version 58 of mbox.js ensures the Experience Cloud Visitor ID service returns with a visitor ID before Target calls are made. This ensures that audience data shared through the Profiles and Audiences core service are available for the first Target call in the visitor's session. To avoid flickering of default content before test content returns, Target hides the `<BODY>` until the visitor ID service returns. `display:none` is used to hide the page.

This update also fixes an issue when using Analytics as the reporting source for Target that caused an inflated number of visitors to be reported in Analytics for visits that only included one page.

Mbox.js sets timeout values in case the visitor ID service does not return. Default timeout for the visitor ID service is 500ms (0.5 seconds). An additional timeout sets the upper limit for how long the `<BODY>` tag will be hidden. That default is 500ms (0.5 seconds). These timeouts can be changed by inserting the following code before the mbox.js reference on each page:

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 

```

Mbox.js version 58 and later executes non-JavaScript content for the global mbox immediately after the HTML `BODY` tag is present. JavaScript content inside `<script>` tags for the global mbox executes after the `DOMContentLoaded` event is fired. This order of content delivery ensures that JavaScript content for the global mbox is delivered and rendered properly.

## mbox.js version 57 {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Target Release:** 15.4.1

**Release Date:** April 21, 2015

The following changes have been made in this version:

* Auto-created global mbox response for Target Standard no longer uses document.write() or creates a <div> element.

  This removes the requirement for the mbox.js file to be the last item in the <head> of the page. Strong QA is recommended when upgrading to this new version.

  This change might cause changes in behavior when delivering some offer types. Here are the specific conditions that will need to be considered:

    * HTML content returned as part of a "plug in offer" does not render correctly, but JavaScript within the offers executes as expected. 
    * JavaScript offers that are being returned to the global mbox can have the JavaScript code embedded in the `<script>` tag, or referenced by a `src` attribute.

      To do this, add the `async` attribute to the script call, as follows:

      `<script src='external-url' async='true'></script>`

      Note that the `async` attribute has limited support in Internet Explorer (details here: [https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility)) so you should exclude visitors who use older IE versions from tests that include these 3rd party scripts.

* Fixed problems reported in Version 56 due to changes in the Extra JavaScript section of mbox.js. All code in the Extra JavaScript section is again available in the global scope.

The following functionality is not supported in mbox.js version 57:

* An auto-created global mbox generated in Target Standard does not work with hosted offer types from Target Classic. Hosted offer types include "offer on your site" and "offer outside Test&Target."

  This means that in Target Classic, you must not select the auto-created global mbox from Target Standard when one of these offers is required. 
* Only JavaScript plugins are supported.

  If a plugin's offer combines JavaScript code, and HTML, then the JavaScript code is executed but the HTML content is not shown.

mbox.js version 57 also includes important fixes:

* Fixed an issue that caused the SiteCatalyst plugin to not work in mbox.js v56. 
* Fixed an issue that resulted in extra JavaScript errors due to scoping change. 
* Revert changes to constructor of mboxFactory.

## mbox.js version 56 {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Target Release:** 15.1.2

**Release Date:** February 17, 2015

>[!NOTE]
>
>Some users have experienced timeout issues when `target.js` couldn't be loaded. Version 57 fixed that issue. However, if you are using the [!DNL Experience Cloud Visitor ID] service, version 58 or later is required.

The following changes have been made in this version:

* Changes for Premium Recommendations to support passing parameters into global mbox 
* Adds a 5 second timeout to the target.js load call. In the rare case that the file doesn't load, the page will render and no Target Standard activities will display. 
* Moved "extra JavaScript" to be executed before global mbox

  All settings in v56+ are name spaced. If there are functions declared in "extra JavaScript," they must be prefixed with `window`.

  For example:

  `function foo {`

  `}`

  Becomes:

  `window.foo = function() {`

  `}`

  Any variables that should be globally accessible must also be prefixed with `window`. 

* Added a cookie called "em-disabled" that mbox.js gives to the user if target.js fails to load during delivery. This cookie prevents offers created using the Visual Experience Composer from rendering on the site. Users with this cookie neither see the test content nor get counted in those activity reports. All other offer content (from campaigns in Target Classic for example) will continue to load. The cookie has a lifetime of 30 min from the time of load failure.

## mbox version 55

**Target Release:** 15.1

**Release Date:** January, 19, 2015

Modifies version 53 with IE fixes.

## mbox version 54

**Target Release:** 14.9.2

**Release Date:** September 30, 2014

Changes the global mbox implementation to AJAX from document.write. This removes the requirement for the mbox.js file to be the last item in the page's <head> section. This version is only available via API. Clients can download it and use this mbox.js file. Some sites experience content flicker with this implementation, so please validate the integration on your site.

## mbox version 53

**Target Release:** 14.9.1

**Release Date:** September 14, 2014

Fixed an issue where Target page params do not fire correctly in Internet Explorer.

## mbox version 52

**Target Release:** 14.8

**Release Date:** August 14, 2014

mboxParameter function now works in Target Standard and Premium.

Fixed an issue that kept Analytics tracking from working in IE 9 & 11. This change only affects users of Analytics.

Now you can [pass in parameters](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) as an array, as a JSON object, or as a comma-delimited list (previously supported) to target-global-mbox using the targetPageParams() function.

Renamed M2PcId and everything related to VisitorId.

Allow the defaultDiv of a registered mbox to be cleared.

## mbox version 51

**Target Release:** 14.6

**Release Date:** June 25, 2014

Fixed a bug that set an incorrect cookie in sites with two characters in their top-level domain.

Fixed a minor bug in mbox.js that caused hashtag values to be returned.

## mbox version 50

Improved synchronization between Target Standard and Target Classic.

## mbox version 49

Improved Internet Explorer 10 support for nested mboxes.

## mbox version 48

Added support for Adobe Analytics as the reporting source for Target.

## mbox version 47

mbox.js now supports using a custom global mbox name for Target Standard.

## mbox version 46

Added complete support for Experience Cloud visitor ID service for Target Standard's single-line-of-code implementation. This enables server-side Adobe Analytics integration and the Experience Cloud shared profile.

Fixed an issue with delivering content in IE10 in document mode.

## mbox version 45

Added complete support for Experience Cloud visitor ID service. This enables server-side Adobe Analytics integration and the Experience Cloud shared profile.

## mbox version 44

Added new parameter in URL by mboxVizTarget:

mboxDOMLoaded

## mbox version 43

Added support for Target Standard.

## mbox version 42

Added initial support for Experience Cloud shared visitor ID service.

## mbox version 41

* Even with x-only setting, disable the first party cookie to improve load time and prevent continuous page refreshes

  A timeout cookie is set if the call to Target fails to return in time. This is a faster method than using only the 3rd-party cookie. With just the 3rd-party cookie, the page is continually refreshed while waiting for a good response from Target's servers.

* Fixed traffic limitation to occur only when mbox.js is enabled
    
  This issue occurred if a customer had a traffic limitation on their mbox.js, causing the timeout setting to not work. This resulted in the page refreshing while waiting foir a good response from the Target servers.
    
* Fixed SiteCalyst plugin to always use the Ajax fetcher

  Prior to this change, there were some situations for users of the Test&Target to SiteCatalyst plugin where, depending on when the plugin loaded, a document.write that would wipe out the page could be triggered.

## mbox version 38

Added support for page-based SiteCatalyst to Test&Target integration (must be enabled)

## mbox version 37

Encoded URL keys

## mbox version 36

Changed mbox to use tt.omtrdc.net

## mbox version 35

* Mbox debug is now always remote
* Added the mboxTime parameter. This parameter is the time as the user sees it, in ms since the epoch, GMT. This is only calculated once.

## mbox version 34

* Always try to get the latest default div instead of referring to a cached version.
    
  This fixes a problem with a cached default content div not being in the DOM due to an mboxUpdate , which provided the content for the default div .

* mbox.getDefaultDiv has a new optional boolean parameter. If true, it returns the current default div. If false, it returns the last cached default div.
* Updated mbox.loaded to support Ajax load
* mboxURL parameter is now encoded using encodeURIComponent rather than escape
* Test whether encodeURIComponent is supported by the browser and show default content if it isn't. Also removed the following mbox.js config options:
  * encode\_mbox\_parameters
  * mbox\_signal\_support
