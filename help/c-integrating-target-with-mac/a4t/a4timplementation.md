---
description: Several steps are required when implementing Adobe Analytics as the reporting source for Target (A4T).
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
seo-description: Several steps are required when implementing Adobe Analytics as the reporting source for Target (A4T).
seo-title: Analytics for Target implementation
solution: Target
title: Analytics for Target implementation
topic: Premium
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
---

# Analytics for Target implementation{#analytics-for-target-implementation}

Several steps are required when implementing Adobe Analytics as the reporting source for Target (A4T).

## Implementation Steps {#section_73961BAD5BB4430A95E073DE5C026277}

The following table describes the steps required to deploy this integration to your site. 

## Step 1: Request provisioning for Analytics and Target

After you implement Analytics as the reporting source for Target, you must be provisioned for Analytics and Target. [Use this form to request to be provisioned](http://www.adobe.com/go/audiences).

## Step 2: Set up user permissions

User account requirements must be met before you can create an Adobe Analytics-based activity in Adobe Target. See [User permission requirements](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Step 3: Implement the Experience Cloud Visitor ID service

The visitor ID service lets you identify users across Experience Cloud solutions. You must implement or migrate to the required version of the Experience Cloud Visitor ID. For more information, see "Implementation Requirements" in [Before you implement](/help/c-integrating-target-with-mac/a4t/before-implement.md).

See [Implement the Experience Cloud ID Service for Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) in the Experience Cloud Visitor ID Service documentation.

## Step 4: Update AppMeasurement for JavaScript or s_code

You must implement or migrate to the required version of appMeasurement.js. For more information, see "Implementation Requirements" in [Before you implement](/help/c-integrating-target-with-mac/a4t/before-implement.md).

For new implementations, see [JavaScript implementation overview](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) in the *Analytics Implementation Guide*.

For a migration, see [Migrating to AppMeasurement for JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) in the *Analytics Implementation Guide*.

## Step 5: Download and update at.js or mbox.js

You must implement or migrate to the required version of at.js or mbox.js using your production account. No modifications are required on the code.

For more information, see "Implementation Requirements" in [Before you implement](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Step 6: Host at.js or mbox.js

If you previously deployed at.js or mbox.js, you can replace your existing file with the updated version. For more information, see "Implementation Requirements" in [Before you implement](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Otherwise, this file can be hosted along with the Visitor ID service and AppMeasurement for JavaScript files. These files must be hosted on a web server that is accessible to all pages on your site. You need the path to these files in the next step.

## Step 7: Reference at.js or mbox.js on all site pages {#step7}

Include at.js or mbox.js below VisitorAPI.js by adding the following line of code in the tag on each page:

For at.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

For mbox.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

It is essential that VisitorAPI.js is loaded before at.js or mbox.js. If you are updating an existing at.js or mbox.js file, make sure that you verify the load order.

The way the out-of-the-box settings are configured for Target and Analytics integration from an implementation perspective is to use the SDID that is passed from the page to stitch the Target and  Analytics request together on the backend automatically for you. 

However, if you want more control on how and when to send analytics data related to Target to Analytics for reporting purposes, and you do not want to opt-in to the default settings of having Target and Analytics automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. Note: any versions below 2.1 do not support this approach.

For example:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

This set up has a global effect, which means that every call made by at.js will have **analyticsLogging: "client_side"** sent within the Target requests and an analytics payload will be returned for every request. When this is set up, the format of the payload that is returned looks like the following:

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

If a global setting is not desired and a more on-demand approach is preferable, then you can use the at.js function [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) to achieve this by passing in **analyticsLogging: "client_side"**. The analytics payload will be returned for only this call and the Target backend will not forward the payload to Analytics. By pursuing this approach, every at.js Target request will not return the payload by default, but instead only when desired and specified. 

For example:

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

This call invokes a response from which you can extract the analytics payload. 

The response looks like the following:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

The payload can then be forwarded to Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Step 8: Validate the implementation {#step8}

Load your pages after you have updated the JavaScript libraries to confirm that the mboxMCSDID parameter values in Target calls match the sdid parameter value in the Analytics page-view call.

This is especially important to confirm in Single Page Applications (SPAs) where the order of calls is not always predictable.

**Note:** The matching of these values is required in order for A4T to function correctly.

## Step 9: (Optional) Remove previous integration code

We recommend that you remove the previous integration to simplify your implementation and eliminate the need to sort out discrepancies between the systems. You can remove any code you might have deployed for a previous SC to T&T integration, including `mboxLoadSCPlugin`.

## Step 10: Enable the options for using Analytics as the reporting source for Target

In Target, click [!UICONTROL Setup > Preferences] and choose either [!UICONTROL Select per activity] or [!UICONTROL Adobe Analytics] to enable the options.

* Select per activity lets you choose between Target and Analytics when creating each activity.
* Adobe Analytics sets Analytics as the reporting source for all activities that you create.

