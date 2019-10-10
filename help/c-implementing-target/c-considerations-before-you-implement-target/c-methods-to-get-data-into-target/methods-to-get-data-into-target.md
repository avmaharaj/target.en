---
description: Information about the various methods you can use to get data into Target, including page parameters, in-page profile attributes, script profile attributes, data providers, the bulk profile update API, the single profile update API, and Customer Attributes.
keywords: implement;implementing;setting up;setup;page parameter;tomcat;url encoded;in-page profile attribute;mbox parameter;in-page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;dataprovider;data provider
seo-description: Information about the various methods you can use to get data into Target, including page parameters, in-page profile attributes, script profile attributes, data providers, the bulk profile update API, the single profile update API, and Customer Attributes.
seo-title: Methods to get data into Target
solution: Target
subtopic: Getting Started
title: Methods to get data into Target
topic: Standard
uuid: a6d64e39-6cdc-49fe-afe5-ecf7dcacf97d
---

# Methods to get data into Target{#methods-to-get-data-into-target}

Information about the different methods you can use to get data into Target, including page parameters, in-page profile attributes, script profile attributes, data providers, the bulk profile update API, the single profile update API, and Customer Attributes.

## Page parameters (also called "mbox parameters") {#section_5A297816173C4FE48DC4FE03860CB42B}

Page parameters are name/value pairs passed in directly through page code that are not stored in the visitor's profile for future use.

Page parameters are useful to send additional page data to Target that does not need to be stored with the visitor's profile for future targeting use. These values are instead used to describe the page or the action the user took on the specific page.

### Format

Page parameters are passed into Target via a server call as a string name/value pair. Parameter names and values are customizable (although there are some "reserved names" for specific uses).

Examples:

* `page=productPage`

* `categoryId=homeLoans`

### Example Use Cases

**Product pages**: Send information about the specific product viewed (this is how Recommendations works)

**Order details**: Send order ID, orderTotal, and so forth for order collection

**Category affinity**: Send category-viewed information to Target to build knowledge of the user's affinity to particular site categories

**3rd-party data**: Send information from 3rd-party data sources, such as weather targeting providers, account data (for example, DemandBase), demographic data (for example Experian), and more.

### Benefits of Method

Data gets sent to Target in real-time, and can be used on the same server call the data on which it comes in.

### Caveats

* Requires page code update (directly or via a tag management system).
* If the data needs to be used for targeting on a subsequent page/server call, it needs to be translated to a profile script.
* Query strings can contain only characters as per the [Internet Engineering Task Force (IETF) standard](https://www.ietf.org/rfc/rfc3986.txt) .

  In addition to those mentioned on the IETF site, Target allows the following characters in query strings:

  `< > # % " { } | \\ ^ \[\] \``
  
  Everything else must be url-encoded. The standard specifies the following format ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), as illustrated below:

  ![](assets/ietf1.png)

  Or, the full list for simplicity:

  ![](assets/ietf2.png)

### Code Examples

targetPageParamsAll (appends the parameters to all mbox calls on the page):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (appends the parameters to the global mbox on the page):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Parameters in mboxCreate code:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

### Links to Relevant Information

Recommendations: [Implementation According to Page Type](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Order confirmation: [Track Conversions](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Category affinity: [Category Affinity](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)

## In-page profile attributes (also called "in-mbox profile attributes) {#section_57E1C161AA7B444689B40B6F459302B6}

In-page profile attributes are name/value pairs passed directly through page code that are stored in the visitor's profile for future use.

In-page profile attributes allow user-specific data to be stored in Target's profile for later targeting and segmentation.

### Format

In-page profile attributes are passed into Target via a server call as a string name/value pair with the prefix "profile." before the Attribute name.

Attribute names and values are customizable (although there are some "reserved names" for specific uses).

Examples:

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

### Example Use Cases

**Login information**: Share non-PII (Personally Identifiable Information) data to Target based on the user's login. This could be membership status, order history, or more.

**Store info**: Track which store is this user's preferred location.

**Previous interactions**: Track what the user has done on the site previously to inform future personalization.

### Benefits of Method

Data gets sent to Target in real-time, and can be used on the same server call on which the data comes in.

### Caveats

Requires page code updates (directly or via a tag management system).

Attributes and values are visible in server calls, so a visitor can see the values. If sharing information such as credit ranges or other potentially private information, this might not be the best approach.

### Code Examples

targetPageParamsAll (appends the attributes to all mbox calls on the page):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (appends the attributes to the global mbox on the page):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Attributes in mboxCreate code:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

### Links to Relevant Information

[Profile Attributes](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Visitor Profile](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)

## Script profile attributes {#section_3E27B58C841448C38BDDCFE943984F8D}

Script profile attributes are name/value pairs defined in the Target solution. The value is determined from executing a JavaScript snippet on Target's server per server call.

Users write small code snippets that execute per mbox call, and before a visitor is evaluated for audience and activity membership.

### Format

Script profile attributes are created in the Audiences section of Target. Any attribute name is valid, and the value is the result of a JavaScript function written by the Target user. The attribute name is automatically prefixed by " user. " in Target to distinguish them from in-page profile attributes.

The code snippet is written in the Rhino JS language and can reference tokens and other values.

### Example Use Cases

**Cart Abandonment**: When the visitor reaches the shopping cart, set the profile script to 1. When the visitor converts, reset it to 0. If the value =1, then the visitor has an item in the cart.

**Visit Count**: On every new visit, increment the count by 1 to keep track of how often a visitor returns to the site.

### Benefits of Method

Requires no page code updates.

Executes before audience and activity membership decisions, so these profile script attributes can affect membership on a single server call.

Can be very robust. As many as 2,000 instructions can be executed per script.

### Caveats

Requires JavaScript knowledge.

The execution order of profile scripts cannot be guaranteed, so they cannot rely on each other.

Can be difficult to debug.

### Code Examples

Profile scripts are quite flexible:

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### Links to Relevant Information

[Profile Script Attributes](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)

## Data Providers {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

Data Providers is a capability that allows you to easily pass data from third parties to Target.

Note: Data Providers requires at.js 1.3 or later.

### Format

The `window.targetGlobalSettings.dataProviders` setting is an array of data providers.

For more information about the structure for each data provider, see [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Example Use Cases

Collect data from a third party, such as a weather service, a DMP, or even your own web service. You can then use this data to build audiences, target content, and enrich the visitor profile.

### Benefits of Method

This setting lets customers gather data from third-party data providers, such as Demandbase, BlueKai, and custom services, and pass the data to Target as mbox parameters in the global mbox request.

It supports the collection of data from multiple providers via async and sync requests.

Using this approach makes it easy to manage flicker of default page content, while including independent timeouts for each provider to limit the impact on page performance

### Caveats

If the data providers added to `window.targetGlobalSettings.dataProviders` are async, they will be executed in parallel. The Visitor API request will be executed in parallel with functions added to `window.targetGlobalSettings.dataProviders` to allow a minimum wait time.

at.js won't try to cache the data. If the data provider fetches data only once, the data provider should make sure that data is cached and, when the provider function is invoked, serve the cache data for the second invocation.

### Code Examples

Several examples can be found in [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Links to Relevant Information

Documentation: [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

### Training Videos:

* [Using Data Providers in Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implement Data Providers in Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html)

## Bulk profile update API {#section_92AB4820A5624C669D9A1F1B6220D4FA}

Via API, send a .csv file to Target with visitor profile updates for many visitors. Each visitor profile can be updated with multiple in-page profile attributes in one call.

This option is very similar to Customer Attributes with a few differences:

* Customer Attributes use an FTP upload while the Target Bulk Profile Update API uses an HTTP POST API.
* Customer Attributes data can be shared with Analytics. Bulk Profile Update is useable only in Target.
* Customer Attributes support creating a profile for a user Target has not yet seen. The Bulk Profile Update API updates existing Target profiles only.
* Customer Attributes require the use of the Experience Cloud ID (ECID). The Bulk Profile Update API requires either the TNT ID or the `mbox3rdPartyId`.
* You cannot send the following characters in `mbox3rdPartyID`: plus sign (+) and forward slash (/).

### Format

The .csv file must refer to each visitor via his or her Target PCID or mboxThirdPartyId . The Experience Cloud ID (ECID) is not supported. All profile attributes/values are created and updated via the API. Format details are available in the API documentation.

### Example Use Cases

Your CRM or other internal system stores valuable data about your visitors that you want to consistently update into Target, without exposing the profile data in your page implementation.

### Benefits of Method

No limit on the number of profile attributes.

Profile attributes sent via the site can be updated via the API and vice versa.

### Caveats

The size of the batch file must be less than 50 MB. In addition, the total number of rows should not exceed 500,000 rows per upload.

There is no limit on the number or rows you can upload over a period of 24 hours in subsequent batches. However, the ingestion process might be throttled during business hours to ensure that other processes run efficiently.

Consecutive [V2 batch update calls](https://developers.adobetarget.com/api/#updating-profiles) without mbox calls in between for the same thirdPartyIds override the properties updated in the first batch update call.

### Code Examples

See [Updating Profiles](https://developers.adobetarget.com/api/#updating-profiles).

### Links to Relevant Information

[Updating Profiles](https://developers.adobetarget.com/api/#updating-profiles)

## Single profile update API {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Almost identical to the Bulk Profile Update API, but one visitor profile is updated at a time, in line in the API call instead of with a .csv file

### Format

The visitor must be identified via the Target mboxPC value or mboxThirdPartyId value. The Experience Cloud ID (ECID) is not supported.

### Example Use Cases

You want to update Target in real-time when a visitor performs some offline action, such as reaching a call center, a loan is funded, using a loyalty card in store, accessing a kiosk, and so forth.

### Benefits of Method

No limit on the number of profile attributes.

Profile attributes sent via the site can be updated via the API and vice versa.

### Caveats

Limit of 1,000,000 API calls (1 million) per 24-hour period

Updates profiles only. Cannot create a profile for a potential user Target has yet to see.

### Code Examples

GET and POST supported. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Links to Relevant Information

[Updating Profiles](https://developers.adobetarget.com/api/#updating-profiles)

## Customer Attributes {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Customer attributes let you upload visitor profile data via FTP to the Experience Cloud. Once uploaded, leverage the data in Adobe Analytics and Adobe Target.

Target Standard customers can leverage 5 attributes, Target Premium customers can leverage 200 attributes.

### Format

A .csv file with Experience Cloud IDs (ECIDs) and attribute name/value pairs is uploaded via FTP or manually in the Experience Cloud UI.

### Example Use Cases

Your CRM or other internal system stores valuable information you want to share with Adobe's Experience Cloud, including Target and Analytics.

### Benefits of Method

Uploading customer data creates a profile entry for that visitor in Target, even if Target has yet to see the visitor.

Same data is automatically available in Target and Analytics.

FTP can be a simpler implementation method than API.

### Caveats

Target Standard customers can leverage 5 attributes, Target Premium customers can leverage 200 attributes

Can only update values via Customer Attributes, not on page.

Requires Experience Cloud ID (ECID) implementation.

### Code Examples

Details can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

### Links to Relevant Information

[Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).