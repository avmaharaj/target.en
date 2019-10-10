---
description: Information about the character limits and other limits (offer size, audiences, profiles, values, parameters, etc.) that affect activities and other elements in Adobe Target.
keywords: character limit;mbox parameters;batch delivery api;profile parameters;limits;built in profiles;maximum;limit;constraint;character;best practice;orderid;orderTotal;mbox3rdPartyID;category;categoryID
seo-description: Information about the character limits and other limits (offer size, audiences, profiles, values, parameters, etc.) that affect activities and other elements in Adobe Target.
seo-title: Limits
solution: Target
title: Limits
topic: Standard
uuid: 603fb800-a26c-43ec-b2d9-ef7a8ed8721e
---

# Limits{#limits}

Information about the character limits and other limits (offer size, audiences, profiles, values, parameters, etc.) that affect activities and other elements in Adobe Target.

>[!NOTE]
>
>The limits listed below should be considered "hard" limits unless specified as "recommended."
>
>When the limits designated as "recommended" are approached or exceeded, performance can slow. Slow interface load times can also be caused by a very complex activity, such as many audiences, targets, and experiences all in one activity.
>
>Highly complex activities should be reviewed with Adobe Consulting and tested in a limited environment before being released to production.

## Activities

**Recommended limit**: 10,000 active live activities.

**Recommended limit**: 10,000 active saved (and not ended) activities.

## Activity names

**Limit**: 250 characters.

## Audience names

**Limit**: 256 characters.

Values longer than 256 characters are truncated.

## Audiences

**Limit**: 50 audiences per mbox, metric, or experience.

## categoryId parameter

**Limit**: 250 characters.

## Customer attribute names

**Limit**: 128 characters.

## Customer attribute alias ID

**Limit** 50 characters.

## Entity custom attributes

**Limit**: The maximum length depends on the language.

* 15,000 characters (single-value, one- and two-byte languages)
* 500 values, 100 characters per value (multi-value)

The maximum length of single-value entity custom attributes is 15,000 characters (for one-byte and two-byte UTF-8 encoded languages such as English and other Latin-script alphabets) or 10,000 characters (for three-byte UTF-8 encoded languages such as Chinese, Japanese, and Korean).

Multi-value entity custom attributes can contain no more than 500 values. Each individual value is limited to 100 characters. The total number of characters across all values must conform to the limitations for the maximum length of single-value entity custom attributes (see above.)

## entityID parameters

**Limit**: 1,000 characters.

## excludedIds {#excludedid}

**Limit**: 5 KB for POST requests. 2,083 characters minus the length of the URL for GET requests.

For GET requests, although the limit on the back end is 5 KB, due to the fact that Microsoft Internet Explorer limits the URL to 2,083 characters, the realistic limit is 2,083 characters minus the current length of the URL.

## Experience names

**Limit**: 20 characters.

## Experiences per activity

**Limit**: 2,000 experiences per Experience Targeting (XT), A/B Test, Multivariate Test (MVT), and Auto-Target activity.

30,000 experiences per Automated Personalization (AP) activity.

## In-mbox profile attribute value

**Limit**: 256 characters.

Values longer than this get truncated.

## In-mbox profiles in an mbox request

**Limit**: 50 profiles.

All profiles after 50 are ignored.

## In-mbox profile names

**Limit**: 128 characters.

## mbox names

**Limit**: 250 characters.

## mbox parameters

**Limit**: The following limits apply to mbox parameters:

* mbox parameters: 500 parameters per mbox.
* Profile parameters: 500 parameters.
* profile parameters per mbox:
* Other Parameters (URL, referring URL, etc.): 50 per mbox for each other parameter type.

For parameters that get logged in the Target database, the limits above are for standard mbox requests. These limits apply unless the request is shortened due to web browser limitations.

If you are using the [Batch Delivery API](https://developers.adobetarget.com/api/#server-side-batch-delivery) in the Mobile Services SDK, the limit of 50 mbox parameters, 50 profile parameters, and 50 for other parameter types are limitations of the API itself. It is not possible to send a request containing more that these numbers using the Batch Delivery API. If a request contains more than these limits, the API will return the following error message:
"The number of mboxParameters cannot exceed 100."

## mbox request URLs

**Limit**: 2,083 characters.

This limit is due to Microsoft Internet Explorer URL length restrictions.

## mbox3rdPartyId parameter

**Limit**: 60 characters.

## Offer names

**Limit**: 250 characters.

## Offer size

**Limit**: The following size limits apply to offers:

* 256 KB for HTML offers. 
* 64 KB for visual offers from the UI. 
* 512 KB from the API.

If you are using a global mbox, the limit is for the whole set of content returned for the page. Limiting offer size improves page load times. If the limit is exceeded, the following message appears:

"The content for the experience is too large to deliver. Please modify the experience to affect less page code."

## Offers

**Recommended limit**: 50,000 total offers.

## orderId parameter

**Recommended limit**: 120 characters.

## orderTotal parameter

**Recommended limit**: 120 characters.

## productPurchasedId parameter

**Limit**: 47 characters per comma-separated value.

Anything longer is truncated by the system.

## Profile scripts

**Recommended limit**: 300 active profile scripts.

**Recommended limit**: 500,000 maximum number of loops per profile script.

## Properties

**Recommended limit**: 5,000 properties.

## Reporting audiences/segments

**Limit**: 50 reporting audiences/segments per activity.

## Reusable Audiences/Account

**Recommended limit**: 75 audiences.

JavaScript timeouts occur in the interface if you have too many.

## Script profile input box in the Target UI

**Recommended limit**: 2,000 characters.

Depends on the size of the encoded string, which could be much longer than the raw string. If the string is too large, it fails before it gets to Adobe Target.

## Script profile names

**Limit**: 50 characters.

## Script profile values

**Limit**: 2,048 characters.

For performance reasons, we recommend a return value that is no longer than 256 characters.

For a String return value, if the size of the return value exceeds 2,048 characters, the script is disabled by the system.

For an array return value, if the size of the concatenated values of the array exceeds 2,048 characters, the script is disabled by the system.

## Success metrics

**Limit**: 200 per activity.

## Target conditions

**Recommended limit**: 1,000 values.

This refers to the number of line-separated values in the targeting text area. For example, entering 1,000 zip codes into a zip code target.

## Targeting rules

**Recommended limit**: 2,500 unique values per targeting rule.

**Recommended limit**: 30,000 unique values per audience across targeting rules.

**Recommended limit**: 100,000 unique targeting rule values per activity.
