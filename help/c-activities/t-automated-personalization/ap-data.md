---
description: Adobe Target automatically collects and uses a variety of data to build its personalization algorithms in Automated Personalization (AP) and Auto-Target (AT) activities. When a visitor enters the AP or AT activity, a snapshot of information is passed to a set of "training records" (the visitor data that the personalization algorithms will learn on).
keywords: environmental data;session data;geo data;geographical data;device data;mobile data;attributes;profile attributes
seo-description: Adobe Target automatically collects and uses a variety of data to build its personalization algorithms in Automated Personalization (AP) and Auto-Target (AT) activities. When a visitor enters the AP or AT activity, a snapshot of information is passed to a set of "training records" (the visitor data that the personalization algorithms will learn on).
seo-title: Data collection for Adobe Target's personalization algorithms
solution: Target
title: Data collection for Target's personalization algorithms
title-outputclass: premium
topic: Premium
uuid: f5ca2d84-0016-4af5-a139-bca567a3d0e8
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Data collection for the Target personalization algorithms{#data-collection-for-the-target-personalization-algorithms}

Target automatically collects and uses a variety of data to build its personalization algorithms in Automated Personalization (AP) and Auto-Target (AT) activities. When a visitor enters the AP or AT activity, a snapshot of information is passed to a set of "training records" (the visitor data that the personalization algorithms will learn on).

To learn more about the Target personalization algorithms, see [Random Forest Algorithm](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).

The following table shows the data collected by Automated Personalization and Auto-Target by default, without the marketer having to do anything, as well as the naming convention used to indicate these attributes in [Personalization Insights Reports](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767). You can augment the input data set at any time. To learn more about how to upload additional data, see [Uploading Data for the Target Personalization Algorithms](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

| Data Type | Description | Data Type Naming Convention | Example Attributes |
| --- | --- | --- | --- |
|[Device and mobile data](#device-mobile)|Device and mobile-specific information.<br>See "Device and mobile data" below.|`Device - [device attribute]`<br>`Mobile - [mobile attribute]`|Mobile Device OS<br>Mobile Screen Size|
|[Environmental data](#env)|Information about the visitor's operating system and how and when the visitor is accessing the activity.|`Browser - / Operating System] - [Attribute Name]`|Browser - Type|
|Experience Cloud segment|Audiences created in Audience Manager or Analytics and shared across the Experience Cloud|`Custom - Experience Cloud Audience - [Audience Name]`|Custom data|
|[Geographical data](#geo)|Information on where the visitor is located.<br>See "Geographical data" below.|`Geo - [geo attribute]`|City<br>Country<br>Region/State<br>Zip Code<br>Latitude<br>Longitude<br>ISP or Mobile Carrier|
|Profile attributes|Profile scripts or attributes directly uploaded to the Target profile via the Update API|`Custom - Visitor Profile - [attribute name]`|Custom data|
|Referring URL parameters|In general, the referring URL is the URL that referred to a particular page that initiated the mbox call.<br>Note that this variable can be impacted by the users' activity on your site as well as the technical implementation of your site.|`Custom - [Referring URL Parameter] - [Parameter value]`|Custom data|
|Reporting segments|Any segments set up in activity setup.|`Reporting Segment -[Segment Name]`|Custom data|
|[Session data](#session)|Information about the visitor's behavior in the session when accessing the activity.|`Visitor Profile - [Attribute Name]`|Visitor Profile - Start of Most Recent Visit|
|URL parameters|Target inspects the URL to extract the URL parameters.|`Custom - URL Parameter - [URL Parameter]`|Custom data|

The following sections contain detailed information about the various data types, including attribute names, descriptions, and sample values.

## Device and Mobile data {#device-mobile}

|Attribute name|Attribute description|Sample values|
| --- | --- | --- |
|Mobile - Device - Brand|The brand of the mobile device the visitor used to access the activity.|Apple|
|Mobile - Device - eReader|Specifies whether the device is an eReader.|0 is False, 1 is True|
|Mobile - Device - Game Console|Specifies whether the device is a game console.|0 is False, 1 is True|
|Mobile - Device - Media Player|Specifies whether the device is a media player.|0 is False, 1 is True|
|Mobile - Device - Mobile Phone|Specifies whether the device is a mobile phone.|0 is False, 1 is True|
|Mobile - Device - Model Name|The model name of the mobile device the visitor used to access the activity.|iPhone XS|
|Device - Set-Top Box|Specifies whether the device is a set-top box.|0 is False, 1 is True|
|Mobile - Device - Tablet|Specifies whether the device is a tablet.|0 is False, 1 is True|
|Mobile - Pixel Density (ppi)|The mobile device's pixel density the visitor used to access the activity.|1, 2, 3, etc.|
|Mobile - OS – OSX (Android, Windows, etc.)|Specifies whether the user used an OSX (or Android, Windows, etc.) device to access the activity.|0 is False, 1 is True|
|Mobile - Screen Height (px)|The mobile device's screen height (in pixels) the visitor used to access the activity.|1, 2, 3, etc.|
|Mobile - Screen Width (px)|The mobile device's screen width (in pixels) the visitor used to access the activity.|1, 2, 3, etc.|

## Environmental data {#env}

|Attribute name|Attribute description|Sample values|
| --- | --- | --- |
|Browser - Day of Week|The day of the week when the visitor accessed the activity.|0 to 6.<br>(0 is Sunday)|
|Browser - Hour of Day|The hour of the day when the visitor accessed the activity.|0 to 23<br>(0 is midnight)|
|Browser - Hour of Week|The hour of the week when the visitor accessed the activity.|0 to 168<br>(Sunday midnight is 0)|
|Browser - Language Setting|The language specified in the visitor's browser used to access the activity.|English<br>German|
|Browser - Screen Height (px)|The device's browser screen height (in pixels) the visitor used to access the activity.|1, 2, 3, etc.|
|Browser - Time of Day|The browser's time of day when the visitor accessed the activity.|0, 6, 12, 18<br>(0 is night, 6 is morning,<br>12 is afternoon, 18 is evening)|
|Browser - Timezone|The visitor's time zone while accessing the activity.|Pacific Time<br>Eastern Time<br>GMT|
|Browser - Type|The type of browser the visitor used while accessing the activity.|Chrome<br>Firefox<br>Internet Explorer<br>Safari<br>Other|
|Browser - Weekday/Weekend|The work status when the visitor accessed the activity (weekend, work hours, or weekday free-time).|Saturday and Sunday is weekend<br>Monday-Friday 0900 to 1800 is work time<br>Monday-Friday after 1800 until 0900 is weekday free time|
|Browser - Window Height (px)|The browser's window height (in pixels) the visitor used to access the activity.|1, 2, 3, etc.|
|Browser - Window Width (px)|The browser's window width (in pixels) the visitor used to access the activity.|1, 2, 3, etc.|
|Device - Screen Height|The device's screen height the visitor used to access the activity.|1, 2, 3, etc.|
|Device - Screen Width|The device's screen width the visitor used to access the activity.|1, 2, 3, etc.|
|Operating System|The operating system on the visitor's device used to access the activity.|Mac OS<br>Windows<br>Linux<br>Search Bot<br>Unknown OS|
|Operating System - Version|The operating system's version the visitor used to access the activity.|Windows 10<br>Mac OS 10|
|Traffic Sources - Referring Landing Page URL|The first page the visitor saw when accessing your site.|`https://www.adobe.com/ecloud.html`|

## Geographical data {#geo}

|Attribute name|Attribute description|Sample values|
| --- | --- | --- |
|Geo - City|The city from which the visitor accessed the activity.|San Francisco|
|Geo - Country|The country from which the visitor accessed the activity.|Germany|
|Geo - DMA|The Designated Marketing Area (DMA) from which the visitor accessed the activity.|Charlottesville|
|Geo - Latitude|The latitude from which the visitor accessed the activity.|47.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy)|
|Geo - Longitude|The longitude from which the visitor accessed the activity.|-122.269<br>Rounded to 3 decimal places (approximately 100 meters accuracy)|
|Geo - State/Region|The state or region from which the visitor accessed the activity.|Utah<br>New South Wales|
|Geo - Zip Code|The Zip Code from which the visitor accessed the activity.|84004|
|Mobile - Carrier|The mobile carrier the visitor used when accessing the activity.|Vodafone<br>T-Mobile|
|Network - Connection Speed|The network connection speed of the device when the visitor accessed the activity.|Broadband<br>Cable<br>DSL<br>Mobile<br>Wireless<br>Satellite|
|Network - Domain Name|The name of the network domain from which the visitor accessed the activity.|`nnt.net`|
|Network - ISP|The network from which the visitor accessed the activity.|nnt communications corporation|

## Session data {#session}

|Attribute name|Attribute description|Sample values|
| --- | --- | --- |
|Visitor Profile - Activity Lifetime Order Value|Specifies the sum of all order values across all visits/sessions to a particular activity.|Double|
|Visitor Profile - Activity Lifetime Time on Site|Specifies the visitor's total time spent on site, excluding the current session, and is updated when the session expires.|Double, milliseconds|
|Visitor Profile -Average Page Views per Visit during Activity|Specifies the average number of page views per session, excluding the current session.|Double|
|Visitor Profile - Average Time per Visit|Specifies the average time spent per visit/session. This does not include the current session.|Double, milliseconds|
|Visitor Profile - First Visit|Specifies the time of the first visit that the user interacted with Target.|Double, milliseconds|
|Visitor Profile - Hours since Last Visit|Specifies the hours since the last visit to this particular activity.|Double (Only integer positive number) 1, 2, 3, etc.|
|Visitor Profile - Impressions of Location/Content|Specifies the number of impressions to a particular location/content combination in a particular activity.|Double (Only integer positive number) 1, 2, 3, etc.|
|Visitor Profile - Last Target Interaction|Specifies the time of last interaction with Target. Interaction happens on every mbox request because the current implementation of Target updates the profile on each request.|Double, milliseconds|
|Visitor Profile - Pages Seen Before Activity|Specifies the number of total page views (impressions), including current visit/session until the visitor enters the activity.|Double (Only integer positive number) 1, 2, 3, etc.|
|Visitor Profile - Page Views in Current Visit|Specifies the number of page views in current visit/session until the visitor enters the activity. More precisely, the number of impressions. These impressions are not real page views, rather this is the number of times the request reached Target. Target is not capable of distinguishing between timeouts or any other reasons the user did not receive or view the content.|Double (Only integer positive number)|
|Visitor Profile - Start of Current Visit|Specifies the time when the current visit/session with Target started. The visit with Target can be initiated without entering an activity. All that is required is a call to any mbox. A visitor might take awhile until entering the activity and the snapshot is taken.|Double, milliseconds|
|Visitor Profile - Start of Most Recent Visit|Specifies the time of when last visit/session with Target started. This attribute gets updated when the session expires.<br>If this is the first session for the visitor, it will result in `LAST_SESSION_START = 0.`|Double, milliseconds|
|Visitor Profile - Time Since Most Recent Visit When First Enter Activity|Specifies the duration between the previous session and the time when the user enters the activity and the snapshot is performed.|Double, milliseconds|
|Visitor Profile - Time in Visit Before Enter Activity|Specifies the difference between the last interaction with Target and when the current visit started. This attribute could be considered visit/session duration until the user enters the activity and the snapshot is performed.<br>Negative values happen when the session start and the last update time is triggered by the same mbox call. Negatives values should be considered as 0 (zero).|Double, milliseconds|
|Visitor Profile -Total Visits|Specifies the total number of visits/sessions. Does not include the current visit/session.|Double (Only integer positive number) 1, 2, 3, etc.|
|Visitor Profile - Total Visits to Activity|Specifies the number of visits to a particular activity. If there is no previous visit, returns 0 (zero).|Double (Only integer positive number) 1, 2, 3, etc.|
|Visitor Profile - Total Visits to Activity with Conversion|Specifies the number of visits/sessions to a particular activity when there was at least one conversion during the visit.|Double|
|Visitor Profile - Visits to Activity with No Conversion|Number of visits/sessions with no conversions to a particular activity. This value is reset to zero after conversion, or -1 if conversion never happened.|Double (Only integer positive number) 1, 2, 3, etc.|
