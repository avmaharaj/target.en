---
description: Release notes that provide information about features, enhancements, and fixes for the latest or upcoming Adobe Target releases.
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
seo-description: Release notes that provide information about features, enhancements, and fixes for the latest or upcoming DNL Adobe Target releases.
seo-title: Adobe Target prerelease notes
solution: Target
title: Target release notes (prerelease)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
---

# Target release notes (prerelease){#target-release-notes-prerelease}

These release notes provide information about features, enhancements, and fixes for the latest or upcoming [!DNL Adobe Target] releases.

**Last Updated: October 2, 2019**

>[!NOTE]
>
>These release notes contain prerelease information. Release dates, features, and other information are subject to change without notice. To view information about the current release, see [Target Release Notes](release-notes.md). The information on these pages might be the same or it might differ, depending on the timing of releases.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target platform

|Feature / Enhancement|Description|
| --- | --- |
|Node.js SDK version 1.0<br>(October 9, 2019)|The Target Node.js SDK lets you deploy Target server-side.<br>This Node.js SDK helps you easily integrate Target with other Experience Cloud solutions, such as the Adobe Experience Cloud Identity Service, Adobe Analytics, and Adobe Audience Manager.<br>The Node.js SDK introduces best practices and removes complexities when integrating with Adobe Target via our delivery API so that your engineering teams can focus on business logic. The following are notable features that we are introducing in the latest version:<ul><li>Support for prefetching and notifications that allows you to optimize for performance via caching.</li><li>Support for optimizing performance when you have a hybrid integration of Target on both your web pages and server-side. We are introducing a setting called `serverState` that will be populated by experiences retrieved via the server-side so that at.js 2.2 will no longer make an additional server call to retrieve the experiences. This approach optimizes page load performance.</li><li> Support for retrieving VEC-created activities via the Node.js SDK, which is made possible by the new Delivery API.</li><li>Open sourced so your developers can contribute to the Node.js SDK.</li></ul>For more information, see [Release notes - Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md).|
|Delivery API<br>(October 9, 2019)|An entirely new delivery API endpoint (/v1/delivery) will be available in production. Notable features are:<ul><li>One endpoint to retrieve experiences for one or more mboxes.</li><li>Retrieve VEC-created activities via the API.</li><li>Support for an entirely new object called Views that is used for Single Page Applications (SPAs) and Mobile applications.</li></ul>For more information, see [Release notes - Target server-side APIs](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md).|
|at.js version 2.2<br>and<br>at.js version 1.8<br>(October 10, 2019)|These versions of at.js provide:<ul><li>Improved performance when using both Experience Cloud ID Service (ECID) v4.4 and at.js 2.2 or at.js 1.8 on your web pages.</li><li>Previously, the ECID made two blocking calls before at.js could fetch experiences. This has been reduced to a single call, which significantly improves performance.</li></ul> In order to take advantage of these performance improvements, upgrade to at.js 2.2 or at.js 1.8 along with ECID Library v4.4.<br>at.js 2.2 provides:<ul><li>**serverState**: A setting available in at.js v2.2+ that can be used to optimize page performance when a hybrid integration of Target is implemented. Hybrid integration means that you are using both at.js v2.2+ on the client-side and the delivery API or a Target SDK on the server-side to deliver experiences. `serverState` gives at.js v2.2+ the ability to apply experiences directly from content fetched on the server side and returned to the client as part of the page being served.<br>For more information, see "serverState" in [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul>|


## Target Standard/Premium 19.10.1 (October 22, 2019)

|Feature / Enhancement|Description|
| --- | --- |
|![Premium badge](/help/assets/premium.png) User-Based Recommendations|Recommends items based off of each visitor's browsing, viewing, and purchasing history. These items are generally referred to as "Recommended for You."<br>This criteria lets you deliver personalized content and experiences to both new and returning visitors. The list of recommendations is weighted towards the visitor's most-recent activity and is updated in-session and becomes more personalized as the visitor browses your site.|

## Prerelease information {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63} 

To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) 
