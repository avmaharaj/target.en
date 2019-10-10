---
description: This topic contains answers to questions that are frequently asked about using redirect offers when using Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;redirect;redirect offer;adobe-mc-sdid;adobe_mc_ref
seo-description: This topic contains answers to questions that are frequently asked about using redirect offers when using Analytics as the reporting source for Target (A4T).
seo-title: Redirect offers - A4T FAQ
solution: Target
title: Redirect offers - A4T FAQ
topic: Standard
uuid: a45cef89-3003-4177-bf84-3d5a486b950d
---

# Redirect offers - A4T FAQ{#redirect-offers-a-t-faq}

This topic contains answers to questions that are frequently asked about using redirect offers when using Analytics as the reporting source for Target (A4T).

## Does Analytics for Target (A4T) support redirect offers? {#section_46B8B03ED4D542C6AD875F5F61176298}

Yes, provided that your implementation uses [!DNL at.js]. However, your implementation must meet the minimum requirements listed below in order to use [redirect offers](../../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) in activities that use Analytics as the reporting source.

>[!NOTE]
>
>A known issue exits that is causing a limited number of customers using redirects with A4T to see a higher percentage of unstitched hit rates. See [Known issues and resolved issues](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## What are the minimum requirements needed to use redirect offers with A4T? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Your implementation must meet the following minimum requirements:

* Experience Cloud Visitor ID Service: [!DNL visitorAPI.js] version 2.3.0 or later. 
* Adobe Analytics: [!DNL appMeasurement.js] version 2.1. 
* Adobe Target: [!DNL at.js] version 1.6.2 or later.

  The [!DNL mbox.js] library does not support redirect offers with A4T. Your implementation must use [!DNL at.js].

The three libraries must be included on both the page with the redirect offer and the page to which the visitor is redirected.

## Why are there sometimes data discrepancies between A4T and Analytics?

Some data discrepancies are expected. For more information, see [Expected data variances between Target and Analytics when using and not using A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md). 

## Why are page views on the original page and on the redirect page sometimes counted? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

When using at.js version 1.6.3 or later, this is not an issue. This race condition affects only customers using earlier versions. The Target team maintains two versions of at.js: the current version and the second-latest version. Upgrade at.js as necessary to ensure that you are running a [supported version](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

If you are using an earlier, non-supported version of at.js, there is a possibility that a race condition can occur that might cause the Analytics call to fire before the redirect executes on the first page. This can cause page views on the original page and on the redirect page to all be counted. This situation results in an extra page view on the first page, when the visitor never really "saw" this first page.

Using the form-based composer to build a redirect activity is recommended to increase the speed of the page redirect. This is because of where the code gets executed on the page. Also, creating a redirect offer for every experience, even the default experience, where the redirect would return the original page is recommended. This ensures that if mis-counting occurs, it happens across all experiences so reporting and analysis is still valid for the test.

One reason you might want to use redirect offers for all experiences in the activity, including the default (control) experience, is to put the same conditions on all experiences. For example, if the default experience does not have a redirect offer but the other experiences have redirect offers, the speed of the experience without the redirect offer has an inherent advantage. Redirect offers are recommended for temporary scenarios only, such as testing. Redirect offers are not recommended for permanent scenarios, such as personalization. After you determine the “winner,” you should remove the redirect to improve page-load performance.

For more information about this issue, see the "Redirect offers" information in [Known Issues](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Can I use redirect offers with A4T if I'm using the mbox.js JavaScript library? {#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

The [!DNL mbox.js] library does not support redirect offers with A4T. Your implementation must use [!DNL at.js].

## Are both the Visual Experience Composer (VEC) and Form-Based Experience Composer supported? {#section_FDA26FE7909B48539DA770559E687677}

Yes, both composers are supported as long as you use the built-in redirect offers.

If you use your own custom code for the redirect, you must ensure that you populate the two new parameters associated with redirect URLs ( `adobe_mc_sdid` and `adobe_mc_ref`, explained below).

## What are the new query string parameters added to the redirect URLs? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

The following query string parameters are associated with redirect offers:

| Parameter | Description |
|--- |--- |
|`adobe_mc_sdid`|The `adobe_mc_sdid` parameter passes the Supplemental Data Id (SDID) and Experience Cloud Org Id from the default page to the new page in order for A4T to "stitch" together the  Target request on the default page with the  Analytic request on the new page.|
|`adobe_mc_ref`|The `adobe_mc_ref` parameter passes the referring URL of the default page to the new page. When used with  AppMeasurement.js version 2.1 (or later),  Analytics will use this parameter value as the referring URL on the new page.|

These parameters are automatically added to the redirect URLs when using the built-in redirect offers in the VEC and Form-Based Experience Composer when the Visitor Id service is implemented on the page. If you are using your own custom redirect code in the VEC or Form-Based Composer, you must be sure to pass these parameters with your custom code.

## My web servers are stripping these parameters from my URLs, what should I do? {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

You will need to work with your IT team to have these parameters ( `adobe_mc_sdid` and `adobe_mc_ref`) whitelisted.

## What if I am not using A4T with my redirect activity and don't want to have these extra parameters added to my URLs? {#section_9E608D75FF9349FE96C65FEDD7539F45}

If you are not using A4T with your redirect activity, you have the Visitor Id service implemented, and you don't want these parameters to be automatically added to your URLs, you must use a custom-coded redirect.

However, as best practice, you might want to keep the `adobe_mc_ref` parameter in the URL in order to report the referrer information to [!DNL Analytics] correctly.

## Why are the adobe_mc_ref and adobe_mc_sdid parameters double URL encoded in my implementation? {#section_5EFE5F012B944C40865731EA18E7E79E}

If you use A4T and redirect offers, Target appends the `adobe_mc_ref` and `adobe_mc_sdid` parameters to the URL. These values are already URL encoded. Most of the time everything works as expected, however, some customers might have load balancers or WEB servers that try to encode the query string parameters one more time.

Because of this double encoding when the Visitor API tries to decode the `adobe_mc_sdid` value, it can't extract the SDID value and generates a new SDID. This leads to incorrect SDID values being sent to Target and Analytics and you'll see uneven split for redirects in Analytics reports.

We recommend that you talk to their IT team to ensure that `adobe_mc_ref` and `adobe_mc_sdid` are white-listed so that these values are not transformed in any way.

## Why does the referring URL need to be passed to the new page? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Suppose a visitor clicks a link on [!DNL `www.google.com`] to your homepage ( [!DNL `www.mysite.com/index.html]`) on which a redirect activity is live and is then redirected to a new page ( [!DNL `www.mysite.com/index2.html`]).

Previously, the [!DNL Analytics] request on the new page would report a referring URL of [!DNL `www.mysite.com/index.html`] instead of [!DNL `www.google.com`]. This caused inaccurate reporting in [!DNL Analytics] associated with the referring URLs (Marketing Channel reports, for example). The reports had lost the fact that you came to the site from [!DNL `www.google.com`].

With [!DNL at.js] version 0.9.6 (or later) and [!DNL AppMeasurement.js] 2.1 (or later), the [!DNL Analytics] request on the new page will report a referring URL of [!DNL `www.google.com`].

## Can I use custom/HTML redirect offers? {#section_E49F9A83A286488C8F1098A040203D7E}

No, you must use a built-in redirect offer for activities that use [!DNL Analytics] as the reporting source (A4T). From the [!DNL Target] perspective, HTML offers are opaque: [!DNL Target] can't know that a particular piece of HTML contains JavaScript that instantiates a redirect. 
