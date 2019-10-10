---
description: This page lists profiles, variables, and parameters that are useful in profile scripts.
keywords: variables;profiles;parameters;built in profiles;methods;url variables;geo profiles;third party profiles;mbox variables;campaign variables;customer attributes
seo-description: This page lists profiles, variables, and parameters that are useful in profile scripts.
seo-title: Profile and variable glossary
solution: Target
title: Profile and variable glossary
topic: Standard
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
---

# Profile and variable glossary{#profile-and-variable-glossary}

This page lists profiles, variables, and parameters that are useful in profile scripts.

## Built-In Profiles {#section_2B694370003C4F8E8E29E0B2F6E52045}

| Profile | Notes |
|--- |--- |
|user.activeActivities<br>user.activeCampaigns|Return the campaign ID for all campaigns/activities that the user is in, even if he or she has not interacted with the campaign/activity in the current session.|
|user.pcId||
|user.sessionId||
|user.categoryAffinity||
|user.categoryAffinities|Return an array of the affinities that a visitor has populated|
|user.isFirstSession||
|user.isNewSession||
|user.daysSinceLastVisit||
|user.browser|The user agent|
|user.header|All `user.header` profiles are built-in from mbox request header data|
|user.header('x-cluster-client-ip')|The public-facing IP address of the network connection that the visitor is on.<br>You can get this in several ways, for example [whatismyip.com](https://www.whatismyip.com/). The IP address is not the NAT address (internal address), starting with 10., 192.168., or 172.|
|user.header('host')|Website hostname|
|user.header('cookie')|Visitor cookie data|
|user.header('user-agent')|Visitor browser user-agent|
|user.header('accept-language')|Visitor language|
|user.header('accept-encoding')|Visitor character encoding|
|user.header('accept')|Visitor language and character encoding|
|user.header('connection')|Server connection. For example:  keep-live|
|user.header('referrer')|Website URL of visitor current page. Does not work for Internet Explorer.|
|user.getLocal('param_name','value');||
|user.setLocal('param_name','value');||
|user.get('param_name')||
|user.parameter|Persistent profile attributes created from profile scripts. Also references “system” profiles like geolocation, visit count, etc.|
|profile.get('param_name')||
|profile.param('param_name');||
|profile.parameter('parameter_name');|Mbox parameters that are made persistent due to their  profile.  prefix.|
|profile.browserTime|The visitor's local browser time. For system time, create a new date object in the profile script|
|profile.averageDaysBetweenVisits||
|profile.sessionCount||
|parameter=|Generic term for additional values passed with an mbox, usually as name/value pairs. Not persistent unless made so with `profile.parameter` or `user.parameter`.|

## URL Variables {#section_8F25958273164EBAA6DC659302993FD3}

|  `landing`  | `referrer`  | `page`  |
|---|---|---|
|  `landing.url`  | `referrer.url`  | `page.url`  |
|  `landing.domain`  | `referrer.domain`  | `page.domain`  |
|  `landing.protocol`  | `referrer.protocol`  | `page.protocol`  |
|  `landing.param`  | `referrer.param`  | `page.param`  |
|  `landing.query`  | `referrer.query`  | `page.query`  |

## Geo and Mobile Carrier Profiles {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country` 
* `profile.geolocation.state` 
* `profile.geolocation.city` 
* `profile.geolocation.zip` 
* `profile.geolocation.dma` 
* `profile.geolocation.domainName` 
* `profile.geolocation.ispName` 
* `profile.geolocation.connectionSpeed` 
* `profile.geolocation.mobileCarrier` 
* `profile.geolocation.latitude` 
* `profile.geolocation.longitude`

## Mbox Variables {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| Variable | Notes |
|--- |--- |
|`mbox.name`||
|mbox.param('param_name')||
|Parameters automatically passed with every request:<ul><li>mbox.param('browserHeight')</li><li>mbox.param('browserTimeOffset')</li><li>mbox.param('browserWidth')</li><li>mbox.param('colorDepth')</li><li>mbox.param('mboxXDomain')</li><li>mbox.param('mboxTime')</li><li>mbox.param('screenHeight')</li><li>mbox.param('screenWidth')</li></ul>|
|Parameters passed with order mboxes:<ul><li>mbox.param('orderId')</li><li>mbox.param('orderTotal')</li><li>mbox.param('productPurchasedId')</li></ul>|
|mbox3rdPartyId|An mbox parameter to sync a customer ID to Target's mboxPCID. A customer ID is an ID your company uses to track visitors, such as a CRM ID, membership ID, or something similar. This ID can then be used to add information via the Profile APIs and [Customer Attributes](/help/c-target/c-visitor-profile/working-with-customer-attributes.md).|
|mboxPageValue|In each mbox call the page is assigned a value.|
|mboxDebug|Only used for debug info. Added to the page url where the mbox.js looks for it.|
|mboxOverride.browserIp|Sets a different geo than the actual location so you can test how something would look in another location.<br>**Note:** Using mboxOverride parameters should be used only while testing the activity and not in production. The use of any  mboxOverride  parameters can cause reporting discrepancies when using  [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md)  (A4T). You should use [Activity QA mode](/help/c-activities/c-activity-qa/activity-qa.md) while testing to ensure that your activity works as expected before pushing the activity into your live environment.|

## Customer Attributes {#section_62B4821EB6564FF4A14159A837AD4EDB}

Customer attributes can be referenced in profile scripts, formatted as `crs.get('<Datasource Name>.<Attribute name>')`.

These attributes are also available as tokens in profile scripts and directly in offers without first requiring a profile script. The token should be in the form: `${crs.datasourceName.attributeName}`. Note that spaces in the `datasourceName` should be stripped from any API call.
