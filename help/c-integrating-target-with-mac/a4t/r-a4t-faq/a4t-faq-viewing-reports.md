---
description: This topic contains answers to questions that are frequently asked about viewing reports when using Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
seo-description: This topic contains answers to questions that are frequently asked about viewing reports when using Analytics as the reporting source for Target (A4T).
seo-title: View reports - A4T FAQ
solution: Target
title: View reports - A4T FAQ
topic: Standard
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
---

# View reports - A4T FAQ{#view-reports-a-t-faq}

This topic contains answers to questions that are frequently asked about viewing reports when using Analytics as the reporting source for Target (A4T).

## What is the counting methodology and how do I use it? {#section_E9C21C47B5BE4E54BABF0CD7F03D3945}

The counting methodology specifies what Target uses as the denominator for the conversion rates. The choices are:

* impressions 
* visitors 
* visits

## Can I set a default metric for the Target reports? {#section_50C20D286AA042CCA958184C9C0767DD}

For the Activities report, Admins can change the default metric so every time they run the report it shows the same metrics. Otherwise, the report defaults to the last metric you applied to your last report.

For more information, see [Select default report metrics](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/metrics.html) in the *Analytics Analyze Guide*.

## When do I apply a segment to the metric (with a calculated metric) versus applying the segment to the report? {#section_BC29DEE6D2734911A5CD6FBF1189EB89}

Segments applied to the reports are like applying segments in Target classic. This technique is most useful for seeing how a the test affects a subset of people (for example, how did this test perform for people in the UK?).

It is possible to apply segments to metrics with a calculated metric. This is generally done when you want to create a new type of success event. For example, if you want to see how many return visitors your activity generated, or how many visitors made it to a certain page who see your test. Please note that lift and confidence cannot currently be generated for calculated metrics.

## Should I use visitors, activity impressions, or visits when viewing reports? {#metrics}

There are several options, each with its own advantages:

* ***Unique visitors*** increment once when a user first qualifies for an activity. 
* ***Visits*** increment for each session once a user (Unique Visitor) enters an activity, even if the activity is not viewed in subsequent visits. 
* ***Activity impressions*** increment each time activity content is served. (Measured by Target) 
* ***Instances*** increment once per page when activity content is served. (Measured by Analytics)

When a visitor views a page that contains an activity, a variable is set for that visitor that contains the name of that activity. See the detailed scenarios below for how each counting methodology compares.

Consider the following:

* All of the above metrics trigger when a user qualifies for an activity and content is returned from [!DNL Target]. This does not necessarily mean that the user saw the offer. If an activity experience is below the fold and the user does not scroll down the page, then the offer was served by [!DNL Target] but not seen by the user. 
* [!UICONTROL Activity Impressions] (measured by [!DNL Target]) and [!UICONTROL Instances] (measured by [!DNL Analytics]) are equal, unless there are multiple mbox calls on the same page in the same activity. This causes multiple [!UICONTROL Activity Impressions] to be counted, but only a single [!UICONTROL Instance]. 
* When using [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. Models can be applied by clicking the column settings gear, enabling [!UICONTROL Non-default attribution models], then selecting [!UICONTROL Same Touch]. Learn more about attribution in [Attributes IQ overview](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) in the *Analytics Tools Guide*.

## What does "activity conversions" mean if the marketer picks an Analytics metric during activity setup? {#section_F3EBACF85AF846E9B366A549AAB64356}

"Activity conversions" will be empty if an Analytics metric was selected as the conversion metric for the activity.

## Why do I see "unspecified" in the Analytics reports? What does it mean? {#unspecified}

![](assets/unspecified.png)

In other reports, "unspecified" means data did not meet a classification rule, but in A4T this should never happen. If you see "unspecified," then the classification service hasn't run yet. It generally takes between 24 to 72 hours for activity data to appear in the reports. Even though the activities do not appear in this report until that time, all visitor data tied to those activities is captured and will appear when the classification is complete.

After the classification period, data appears in these reports approximately an hour after it is collected from the website. All metrics, segments, and values in the reports come from the report suite you selected when you set up the activity.

## Why are Target metrics sent to Analytics even after the activity has been deactivated? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

The [!DNL Target] variable sent to [!DNL Analytics] has a default 90-day expiration period. This expiration period can be adjusted by Client Care if needed. This setting is global for all activities, however, so it should not be adjusted for one case.

You might see Target variables sent to Analytics after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled Target activity. If a user comes back to the site on day 45 and sees another activity, the entire A4T eVar value has its counter reset to 90 days. That means the first campaign from day 1 now could be persisting for up to 45 + 90 = 135 days. If the user keeps coming back, you might get to the point where you see metrics sent to Analytics in your reporting from much older activities. As users delete cookies and don’t return to the site, the numbers in that activity will drop, but you’ll still see them.

This means that activities continue to get page views, visits, and so forth for up to 90 days after the activity ends for visitors that became part of the activity while it was active. However, if you look at the [!UICONTROL Activity Impressions] metric, you should not see any impressions after the activity ended.

This is normal and expected behavior. The A4T variable functions like any other eVar—the value is associated with the user until it hits the expiration time period (90 days). As a result, if an activity is active for only two weeks, the value will still be associated with the user for at least the next 90 days.

Best practice is view reports for that activity only for the time period the activity was live. The dates should be set correctly by default when you view the activity in Analytics, so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

As an example, let’s assume that the A4T variable expires after 90 days and our test is active from January 1 through January 15.

On January 1, the user comes to the site and sees activity XYZ once and has five page views after that. In the next two weeks, the user never returns to the site. The data would look like this for this user:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors |
|--- |--- |--- |--- |--- |
|XYZ|1|5|1|1|

The user returns on February 1, views five more pages, and doesn’t encounter any more Target activities and the original activity is no longer active. Even though the activity is no longer active, it is still following the user via eVar persistence. The data now looks like this:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors |
|--- |--- |--- |--- |--- |
|XYZ|1|10|2|1|

The user comes back on March 1 and sees a new activity, ABC. The user also views five pages. Because activity XYZ is still following the user through persistence, and this user then has ABC set, we’ll see two line items in reporting:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors |
|--- |--- |--- |--- |--- |
|XYZ|1|15|3|1|
|ABC|1|5|1|1|


The user then comes back on April 1, views another five pages, and makes a purchase. The 90-day expiration of that first eVar value is reset on April 1, so we’ll see that in reporting. And all the Target activities the user sees receives the credit for the conversion, but the total number of conversions is deduplicated:

| Activity Name | Instances (Impressions) | Page Views | Visits | Unique Visitors | Orders |
|--- |--- |--- |--- |--- |--- |
|XYZ|1|20|4|1|1|
|ABC|1|10|2|1|1|
|Total|2|20|3|1|1|

Because both experiences were seen prior to the conversion, they both get “credit” for the order. But, only one order took place in the system and the total reflects that. For Target reporting, because you aren’t putting Target activity against activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. You’re comparing the results of two items within the single activity, and it's not possible for a user to see different experiences in the same activity so you don’t have to worry about cross-contamination of order credit.

For more information, see [Conversion Variables (eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## Why do Analytics and Analytics for Target (A4T) calculate numbers for the Unique Visitors metric differently? {#section_0C3B648AB54041F9A2AA839D51791883}

When you run an A/B test, which uses the Students t-test (the confidence metric) to choose a winner of a test, one of the assumptions is that there is a fixed time horizon. The test isn’t statistically valid unless you are looking at that fixed sample size.

The Unique Visitors metric is different in Analytics and Target only when you are looking at a period of time that is shorter than the actual test. If you haven’t reached your sample size, the test isn’t as reliable. See [How Not to Run an A/B Test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) on [Evan Miller's website](https://www.evanmiller.org/index.html) for more information.

The Unique Visitors metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. Those people are still part of the test and should be counted. If you want to see only the number of people who were exposed during a single week, you can create a segment of visitors who had an activity impression and apply it to the report.

You can shorten the amount of time the Target variable persists down to a session; however, that is usually problematic for tests where the conversion event isn’t as likely to happen within the same session.

## Why is the same visitor sometimes counted in multiple experiences in Analytics? {#section_1397E972D31C4207A142E4D2D6D794A2}

The following list explains reasons why the same visitor could be counted in multiple experiences in Analytics:

* The Target profile expired but the Analytics cookie is still there. In this situation, Target re-evaluates the user but Analytics considers the visitor to be the same person. 
* If the visitor is using the `mbox3rdPartyId`, when the anonymous visitor is merged with his or her 3rd-party ID profile, Target could put the visitor into a different experience to match up with the 3rd-party ID. For more information, see [Real-Time Profile Syncing for mbox3rdPartyID](../../../c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732). 
* Analytics might be tracking different devices as the same visitor in a different way than Target tracks those devices—the 3rd party ID setup in Target is different than in Analytics.

## Does A4T support virtual report suites?

Virtual report suites are *not* included in the Report Suite list and audiences from virtual report suites are not supported in A4T reporting.

## Can I change the percentage of traffic allocation in an activity that uses A4T after the activity has been activated?

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in Analytics because the change impacts only new visitors. Returning visitors are not impacted. 

As best practice, you should stop the existing activity and then create a new activity instead of changing the percentage after activation. Reporting for the new activity starts with new visitors and data from returning visitors will not cause inconsistent reporting.

## Can I view my Target activity data in Adobe Analysis Workspace?

You can use [!DNL Adobe Analysis Workspace] to dig deeper and to visualize the data or uncover insights hidden beneath the surface.

For detailed information and examples, open the [Analytics & Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.