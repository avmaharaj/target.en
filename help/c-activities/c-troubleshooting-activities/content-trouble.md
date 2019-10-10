---
description: If your page does not display the expected content, there are a few steps you can take to debug content delivery.
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
seo-description: If your page does not display the expected content, there are a few steps you can take to debug content delivery in Adobe Target.
seo-title: Troubleshoot content delivery in Adobe Target
solution: Target
subtopic: Multivariate Test
title: Troubleshoot content delivery
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
---

# Troubleshoot content delivery{#troubleshoot-content-delivery}

If your page does not display the expected content, there are a few steps you can take to debug content delivery.

* Check your activity or campaign code carefully. A typo or other error could cause the expected content not to display. 
* Use mboxTrace or mboxDebug to troubleshoot the mbox. 
* Use the Adobe Experience Cloud Debugger, an easy-to-use tool that provides much of the same information as mboxDebug, to troubleshoot the mbox.

mboxDebug is especially useful when you are setting up Target on your page to make sure the mbox is firing and the cookie is being set. However, it does not go into the kind of detail that is useful when debugging content delivery. If your activity does not appear on your page or undesired content appears, use mboxTrace to examine and debug the page in detail.

## Retrieve the Authorization Token to Use With Debugging Tools {#section_BED130298E794D1FA229DB7C3358BA54}

Because mboxTrace and mboxDebug can expose campaign data and profile data to external parties, an authorization token is required. The authorization token can be retrieved in the [!DNL Target] UI. The token is valid for six hours.

To retrieve the authorization token:

1. Click **[!UICONTROL Setup]** > **[!UICONTROL Implementation]**. 
1. Select **[!UICONTROL mbox.js]** or **[!UICONTROL at.js]**. 
1. Click **[!UICONTROL Generate Authentication Token]**.

   ![Generate Authorization token](/help/c-activities/c-troubleshooting-activities/assets/generate-auth-token.png)

1. Add the generated token as a parameter to your URL to enable one of the advanced debugging tools.

   ![Authorization token](/help/c-activities/c-troubleshooting-activities/assets/gen-auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace enables you to receive trace information attached to mbox replies. Trace information reflects the outcome of an mbox call (for example, a conversion or an impression) and any additional data that may help in determining why this particular outcome happened, such as a set of available branches among which the selection was made in a campaign. Use this information to debug content delivery.

The following parameters are available:

| mboxTrace Options | Outcome |
|--- |--- |
|`?mboxTrace=console`|Prints into console log as objects.<br>For at.js, instead of popping a new browser window or outputting to the console as in  mbox.js, you will need to inspect the Network request and look under Preview (Chrome) or Response (Firefox).|
|`?mboxTrace=json`|Prints into console log as a literal JSON string|
|`?mboxTrace=window`|Prints into a popup window as a JSON string|
|`?mboxTrace=disable`|Turns off tracing session mode|

**Example mboxTrace Call**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

The output displays very detailed information about your content. mboxTrace shows details about your campaign or activity and profile It also provides a snapshot of the profile before execution, and a snapshot of what changed after execution. It also shows which campaigns or activities were evaluated for each location.

Some of the information includes matched and unmatched segment and target IDs:

* **SegmentId**: The IDs of segments, either from the reusable segments library or anonymous ones created for the particular campaign. 
* **TargetId**: The IDs of targets, either from the target expression library or anonymous targets for any segments from campaign. 
* **Unmatched**: The request did not qualify in this call for those segments or targets. 
* **Matched**: The request qualified for the specified segments or targets.

**Using mboxTrace on Recommendations pages**: Adding mboxTrace as a query parameter on pages with recommendations replaces the Recommendations design on the page with an mboxTrace details window, which displays in-depth information about your recommendations, including:

* Recommendations returned vs. recommendations requested 
* The key used, and if it is generating recommendations 
* Criteria-generated recommendations vs. backup recommendations 
* Criteria configuration 
* Exclusions and inclusions applied 
* Collection rules

You do not need to include `=console`, `=json`, or `=window` in the query parameter. When you are done with the mboxTrace details, add `=disable` and press **[!UICONTROL Enter]** to return to the normal display mode.

The normal functioning and appearance of your site is not affected by mboxTrace. Visitors will see your regular Recommendations design.

## mboxDebug {#mboxdebug}

To use mboxDebug, append an mboxDebug parameter to the end of your URL. The following table contains information about mbox-related URL parameters.

>[!NOTE]
>
>Some mboxDebug parameters are available with or without authentication.

| URL Parameters | Purpose |
|--- |--- |
|`mboxDebug=1`|Debugger<br>Adding this parameter to any URL with mboxes defined opens a pop-up window with valuable debugging details. Cookie information, PCid and Session ID values are written out, and all of the mbox URLs are visible. Click on a mbox URL to show the response for that mbox. More details are available in [mbox_debug.pdf](/help/assets/mbox_debug.pdf).|
|`mboxDebug=x-cookie`|Modify the cookie|
|`mboxDisable=1`|Disable mboxes on the page|
|`mboxDebug=x-profile`|View profiles set.|
|`mboxDebug=x-time`|Show response time for each mbox request|
|`mboxOverride.browserIp=<Insert IP address>`|Test geotargeting<br>Test geotargeting with this URL parameter. Type an IP address as the value for this attribute, and Test&Target's geotargeting evaluates that IP address to match against any geotargeting or segmentation set in a campaign.|

>[!NOTE]
>
>Ensure that the URL fragment is after query string parameters. Anything after the first `#` is a fragment identifier and causes debugging parameters not to function correctly.

## Adobe Experience Cloud Debugger {#section_A2798ED3A431409690A4BE08A1BFCF17}

The Adobe Experience Cloud Debugger makes it fast and easy to understand your Target implementation. You can quickly view your library configuration, examine requests to make sure your custom parameters are being passed correctly, turn on console logging, and disable all Target requests. Authenticate into the Experience Cloud and you can use the powerful Mbox Trace tool to inspect your activity and audience qualifications as well as your visitor profile.

For more information, see the training videos below:

For more detailed information, see [Debug at.js using the Adobe Experience Cloud debugger](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md).

## If target.js Fails to Load During Delivery {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

Mbox.js sends a cookie called "em-disabled" to the visitor if target.js fails to load during delivery. This cookie prevents offers created using the Visual Experience Composer from rendering on the site. Visitors with this cookie neither see the test content nor get counted in those activity reports. All other offer content (from campaigns in Target Classic for example) continues to load. The cookie has a lifetime of 30 min from the time of load failure.

## Top sellers are not appearing in Recommendations {#section_3920C857270A406C80BE6CBAC8221ECD}

The *`SIteCatalyst: purchase`* mbox can't be used for Purchase algorithm traffic data. Use the *`orderConfirmPage`* mbox instead.

## Check Activity Priority {#section_3D0DD07240F0465BAF655D0804100AED}

Form-based activities created with [!DNL Target Standard/Premium] might collide with activities created in the [!DNL Target Classic] UI that have the same priority and use the same mbox.

## Custom code does not produce the expected results in Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target no longer supports IE 8.

## JavaScript content delivered by the global mbox doesn't load when using mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

Upgrade to [!DNL mbox.js] version 58 or later.

Mbox.js version 58 and later executes non-JavaScript content for the global mbox immediately after the HTML `BODY` tag is present. JavaScript content inside `<script>` tags for the global mbox executes after the `DOMContentLoaded` event is fired. This order of content delivery ensures that JavaScript content for the global mbox is delivered and rendered properly.

## Target Cookie Does Not Get Set {#section_77AFEB541C0B495EB67E29A4475DF960}

If your site has a sub domain, such as [!DNL us.domain.com], but you need the Target cookie set on [!DNL domain.com] (instead of [!DNL us.domain.com]), you must override the `cookieDomain` setting. For more information, see [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Target content flickers or is not shown if an element is also part of AEM personalization. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

If a DOM element is part of Adobe Experience Manager (AEM) personalization targeting and a Target activity, Target content might flicker or not be shown.

To remedy this, you can disable AEM personalization on pages on which Target is running.

## Redirect and remote offers fail to deliver due to an invalid URL. {#section_7D09043B687F43B39DAEDF17D00375AC}

If the redirect or remote offer uses an invalid URL, it might fail to be delivered.

For redirect offers, the mbox response can contain `/* invalid redirect offer URL */`

Or

For remote offers, the mbox response can contain `/* invalid remote offer URL */`

You can check the mbox response in the browser or using mboxTrace. See [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) for more information on valid URLs. 

## mboxes are not firing on my site.

at.js does not fire Target mboxes if you are using an invalid doctype. at.js requires the HTML 5 doctype.

## Training videos

The following videos contain more information about the concepts discussed in this article.

### Add the Extension

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Basic Target Debugging

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)