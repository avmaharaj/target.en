---
description: Information about known issues for this release of Target. Also includes information about issues that have been resolved.
keywords: known issues;resolved issues;release notes;bugs;issues;fixes
seo-description: Information about known issues for this release of Adobe Target. Also includes information about issues that have been resolved.
seo-title: Known issues and resolved issues in Adobe Target
solution: Target
title: Known issues and resolved issues
topic: Premium
uuid: f8e8e057-1842-4922-ab7f-4d5441048573
---

# Known issues and resolved issues{#known-issues-and-resolved-issues}

Information about known issues for this release of Target. Also includes information about issues that have been resolved.

>[!NOTE]
>
>The issue numbers in parentheses are for internal Adobe use.

## Known Issues {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

The following sections list the known issues for [!DNL Target]:

### Activity QA preview links {#preview}

[Activity QA preview](/help/c-activities/c-activity-qa/activity-qa.md) links for saved activities might not load if there are too many saved activities in your account. Re-trying the preview links should work. To prevent this from continuing to happen, archive saved activities that are no longer actively used. (TNT-32697)

### Redirect offers {#redirect}

The following are known issues with redirect offers:

* Under some conditions, a limited number of customers have reported higher degrees of variance in traffic distribution when using a redirect offer in activities configured with Analytics for Target (A4T). Adobe engineers are currently working on this issue.
* Redirect activities in at.js implementations might cause the preview URL to enter into a loop (the offer is delivered repeatedly). You can use [QA Mode](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) instead to perform Preview and QA. This issue does not impact the actual delivery of the offer. (TGT-23019)

### Graph report for an Auto-Target activity fails to render when using a custom experience as control

The graph report for an Auto-Target activity fails to render for "differential" modes (Average Lift and Daily Lift) if there is no data (0 visits) in any experience. This situation might occur during the early stage of an activity if the control experience is set to custom. For the other modes (Running Average Control and Targeted, Daily Control and Targeted, and Visits) it works fine. As soon as there is some data (non-zero visits), the report renders as expected.

### Cancel loading of a page within the VEC {#cancel}

* The following known issue currently exists when cancelling the loading of an [!UICONTROL A/B Test] or [!UICONTROL Experience Targeting] (XT) activity within the VEC that contains a redirect URL.

  In step one of the three-part guided workflow inside the VEC, when you cancel page loading, the [!UICONTROL Modifications] panel in the VEC displays and the redirect to URL template is applied on the experience (for example, "Experience B). When you progress to steps two or three and then come back to step one, the following situation occurs.

  On "Experience B," by default, the cancelled website loading template renders and the [!UICONTROL Modifications] panel is accessible, which should not be the case because this experience has a redirect to URL template applied. The redirect to URL template should display.

  To show the correct state of the experience in the VEC:

  If you switch to another experience and then switch back to "Experience B," [!DNL Target] displays the redirect to URL template applied on this experience and the [!UICONTROL Modifications] panel is not accessible. (TGT-32138)

* For the Single Page Application (SPA) websites, cancelling loading does not allow you to edit actions under the [!UICONTROL Modifications] panel.

### Enterprise Permissions support in Target APIs {#api}

Code offers created from the Target UI in the Offers library might display in the default workspace if the list of offers is pulled using GET APIs. This issue will be fixed in first week of March 2019. After this fix is in place, code offers will display in the appropriate workspace when pulled from APIs. This issue does *not* affect offers created from APIs. For example, code offers created from APIs display in the workspace in which they were created, whether fetched using GET APIs or from within the Target UI.

### Recommendations

The following are known issues with Recommendations activities:

* Entities are correctly expired after 60 days of receiving no updates via feed or API; however, the expired entities are not removed from the Catalog Search index after expiration. (IRI-857)
* The "Usage Info" overlays for Criteria and Designs do not reflect their usage in A/B and Experience Targeting activities (TGT-34331)
* Recommendations Offers in A/B and Experience Targeting activities do not show a visual preview of the Recommendations tray (TGT-33426)
* Collections, exclusions, criteria, and designs created via API are not visible in the Target user interface and can only be edited via API. (TGT-35777)
* Recommendations activities created via API can be viewed in the user interface, but can only be edited via API.

### Multivariate Test (MVT) activities

In an MVT activity, the winner shown in the table and graph are not consistent when checking metrics. This occurs if a user switches from Summary to Graph View, then switches back to Summary View, changes a metric and then switches to Graph View. When this issue occurs, the Summary View always shows the correct winner. If the user never switches Graph View between Summary views, the Graph View shows the correct winner.

### at.js

The following are known issues with at.js:

* If you create an experience with no modifications using at.js 2.*x* (for example, a default experience), the experience might not be counted in reports, Analytics for Target (A4T), Analytics, or Google Analytics. In addition, the [ttMeta plug-in](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md) might not work correctly.

  As a workaround, use a whitespace in the experience content. (TNT-33366)

* When a page is loaded into the Visual Experience Composer (VEC), Target needs to determine if the global mbox setting is enabled or disabled and whether entityID or categoryID is present at the location where the user is trying to apply the recommendation in the VEC. Based on this information the criteria list is filtered. The default list has filtered algorithms, but the [Compatible checkbox](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md) lets you view the complete algorithms list.

  When using at.js , the Compatibility checkbox is hidden, so you cannot see incompatible algorithms.

  This issue applies only to Recommendations activities that use the VEC.

  **Workaround**: Disable the [!UICONTROL Filter Incompatible Criteria] option in [!UICONTROL Recommendations > Settings]. After disabling this setting, all criteria (compatible and incompatible) will be shown in the criteria picker. (TGT-25949)

* Mboxes not firing on Microsoft Explorer 11 browsers after upgrading to at.js version 1.0 due to the interaction between at.js and Visitor API 2.2.0. This issue affects at.js version 0.9.6 and later. (TNT-27600)
* at.js might not work with Cordova/Hybrid apps because first-party cookies are not currently supported in them. (TNT-26166)

  **Workaround**: Configure at.js with the "x-only" option enabled and pass `mboxThirdPartyId` in calls to manage users.

### mbox.js

The mbox.js library does not support client-side templating languages, such as Handlebars and Mustache. The at.js library *does* support these languages.

**Note**: The mbox.js library is no longer being developed. All customers should migrate from mbox.js to at.js. For more information, see [Migrate to at.js from mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

### Implementation: Global Mbox Auto Create

On the Implementation tab ([!UICONTROL Setup > Implementation]) the [!UICONTROL Global Mbox Auto Create] field will be "false" by default for a newly provisioned tenant.

When mbox.js is downloaded for the first time after provisioning, the [!UICONTROL Global Mbox Auto Create] field is set to "true" in the downloaded mbox.js file and in the [!DNL Target] backend, but it will continue to display as "false" on the [!UICONTROL Implementation] page in the UI until the page is refreshed (after the page is refreshed, the status will be "true.")

at.js will be downloaded with `global_mbox_autocreate = false` for a newly provisioned tenant. If mbox.js is downloaded first, global\_mbox\_autocreate is set to "true" and at.js will also be downloaded with `global_mbox_autocreate = true`. (TGT-15929)

### Success metrics

Success metrics with the advanced option "How will the count be incremented" set to "every impression" or "every impression (excluding refreshes)" cannot be used as a success metric that another metric is dependent on.

When a success metric is set to be incremented on every impression, Target counts the visitor again every time the visitor visits this success metric. Target then resets the success metric "membership" to 0 so it can count again on the next impression. Thus, if another metric requires this metric to have been seen first, Target will never recognize that the user has seen the first metric.

### Analytics for Target (A4T)

Target activity impressions and conversions are currently counted incorrectly in Analysis Workspace .

As a workaround, please rely on A4T data in Reports & Analytics until this issue is fixed.

### Target APIs

Customers cannot perform CRUD operations on Auto-Allocate activities through the v3 version of the A/B Activities API on Adobe I/O.

## Resolved Issues {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

As known issues above are resolved, they will be moved to the following sections and additional notes, if necessary, will be added.

### Recommendations

* Recommendations feed index can show "Waiting for index" if the items in the feed are the same as in the previous run. The product ingestion for delivery is not impacted. (RECS-6663)

  This issue was fixed in the Target 19.4.2 release.

* Recommendations feeds take longer to process than expected. (COR-2836)

  Fixed in the Target 16.10.1 release.

* The Recommendation Feeds UI does not show the correct status of indexing. The backend jobs are functioning correctly, but the UI is not able to fetch and display the current state.

  This was fixed in the 17.10.1 release.

### Redirect offers

A race condition on your page might cause page views on the original page and on the redirect page to be counted. Updates are planned to the at.js implementation to ensure that this race condition can be avoided.

This issue was fixed in at.js 1.6.3.

### Exclusion groups

* When auto-dedupe is applied after creating exclusion groups, the count on the activity diagram might be incorrect in the UI.
* When existing activity with Exclusion Group is edited, the manual inclusions might not be correctly reflected in the UI.

These issues were resolved.

### Target APIs

v1 version of the Offer APIs on Adobe I/O treats all offers created through Target to be in the default workspace. (TTTEAM-41957)

This issue was resolved.

### at.js

Mboxes not firing on Microsoft Explorer 11 browsers after upgrading to at.js version 1.0 due to the interaction between at.js and Visitor API 2.2.0. This issue affects at.js version 0.9.6 and later. (TNT-27600)

Fixed with the release of API 2.3.0 or later.

### Geo targeting

Searching for a string that contains special characters (such as a space or a comma) is currently not working when creating geo-targeting audiences. This issue surfaces, for example, when creating audiences based on cities, states, countries, etc. For example, when searching for "new york", the search does not return valid results.

Fixed in November, 2018.

### at.js

When using at.js version 1.6.0, Analytics for Target (A4T) redirects occur, but without activity qualification.

Fixed with the release of at.js 1.6.2.

### Activities, Workspaces, and Delete activity API

Activities in the default workspace deleted via API continue to display in the Target UI. As a workaround, delete all activities in the default workspace using the Target UI. (TGT-31315)

Fixed October 25, 2018

### Automated Personalization (AP) offer-level reporting

When you click the targeted experience in an Automated Personalization (AP) activity's report to view offer-level reporting, currently you see empty results, an error message, or a spinning icon. (TNT-30695)

Fixed September 27, 2018.

### Code Editor

If you reload the VEC on step 1 of the three-step guided workflow while working with the Code Editor in Firefox and Internet Explorer, the Modifications tab does not render properly; however, the VEC's functionality is not impacted. (TGT-28730)

This was fixed in the 18.9.1 release.

### Recommendations activity that uses an Attribute Promotion rule

When you edit or copy a Recommendations activity that uses an Attribute Promotion rule, the "Has missing field" error displays when clicking Save .

This was fixed in the 17.8.1 release.

### Backup Recommendations

Backup recommendations erroneously display "Enabled" on Recently Viewed Items cards in the Target UI. (TGT-29308)

This was fixed in the 18.4.1 release so that "Disabled" displays.

### Auto-Target activities and reporting audiences

When a reporting audience's name used in an Auto-Target activity is changed, further updates from Target for that activity might fail with an error message.

This issue was fixed with the Target 18.5.1 (May 22, 2018) release.

### at.js

The algorithm for extracting the top-level domain that should be used when saving cookies has changed in at.js version 0.9.6. Because of this change, cookies cannot be saved to addresses that use IP. Most of the time, IP addresses are used for testing purposes, but as workarounds you can use DNS entries, adjust the hosts file on a local box, or use the targetGlobalSettings() at.js function to insert a code snippet to support IP addresses.

This issue was remedied in at.js version 1.2.

### Enterprise User Permissions for Target Premium

As part of the Enterprise Permissions migration, all Target Premium user management was moved from the Adobe Target UI to Adobe Admin Console.

As a result of the migration, there are two potential issues you should be aware of:

* Non-admin users received an email indicating that they now have access to Adobe Target. This indicates that the migration was completed for your organization. The email itself can be disregarded.
* Following the migration, there have been some reports of previously disabled users reappearing in the Adobe Admin Console. This could be an issue for your organization if disabled users in the Adobe Admin Console were still appearing on your user list in Target prior to the migration. We recommend that administrators review the list of users in Admin Console to validate access.

This issue was fixed on August 30, 2017

### Activity Creation

An issue with the 17.6.2 release may have affected activities created and/or updated between June 22, 2017 and June 29, 2017. Activities with the following were affected:

* Any experiences that were rearranged in Experience Targeting (XT) would have reverted back to the original order
* Any segment rules local to the activity (not saved within an audience) would have been lost: combined audiences, location refinements, and any rules on success metrics.

No other activities were affected.

**Important**: This issue is not fixed automatically. You must re-save any activity that was affected to fix the issue.

This issue was fixed on June 29, 2017

### Form-Based Experience Composer

The following known issues have been reported when using the Form-Based Experience Composer:

* If you use the Form-Based Experience Composer with an mbox other than the auto-created global mbox ( target-global-mbox ), and then choose an engagement metric as a success metric, the metric increments only on pages that have the mbox used in the activity. As an example, if your mbox is homepage\_mbox , the Pages Per Visit metric is the number of hits to the homepage\_mbox during that visit. (TGT-22789)
* A JavaScript exception is thrown when you delete an experience in an Experience Targeting (XT) activity when using the Form-Based Experience Composer during step 1 of the process. (TGT-24366)

The first issue was fixed in the Target 17.3.1 release (March 2017).

The second issue was fixed in the Target 17.6.1 release (June 2017).

### at.js

Since the release of Target 17.4.1 (April 27, 2017), using the Insert Image action in the Visual Experience Composer (VEC) causes the offer content to not be delivered when using the at.js library.

A fix for this issue has been made to at.js version 0.9.7 released May 22, 2017.

### Reporting: A/B and Experience Targeting (XT) activities

Between April 27 at 9:00 p.m. PST and May 5 at 6:00 a.m. PST, A/B and XT activities created or edited with any metrics using the “Viewed a Page” conversion action (that were not based on other metrics), might have incorrectly recorded conversions. This issue is now resolved; however, reporting on the “Viewed a Page” conversion action for these activities during the impacted time period might not be accurate and, unfortunately, cannot be corrected. We recommend that for any decisions based on “Viewed a Page” conversion actions for these activities you rely only on data recorded before or after the impacted period.

Reporting data for other metrics can still be used because they were not impacted.

Fixed in the Target 17.4.3 hotfix.

### Offers: A/B and Experience Targeting (XT) activities

The delivery and preview was impacted for offers in A/B and XT activities having at least two experiences and that were either created or edited using the Form-Based Experience Composer between Friday April 28 (9 p.m. PT) and Monday May 1 (9:15 p.m. PT). Only offers with default content were displayed.

Fixed in the Target 17.4.3 hotfix.

### at.js

The following actions caused the offer to not be delivered when using the Visual Experience Composer (VEC) and at.js: Move and Rearrange.

A fix for this issue was made to at.js version 0.9.6.

### Reports

The ability to view multiple metrics in a report, included in the Target 17.3.1 release (March 30, 2017) has been removed due to unexpected behavior. This feature will be available again in an upcoming release.

The ability to view multiple metrics in a report was included in the Target 17.4.1 release (April 27, 2017).

### Offers

Images deleted from the Image Offers library ( Offers \> Image Offers ) remain visible in the UI. In an upcoming release, these deleted images will no longer display. In the meantime, deleted images display in the UI, but have a status of Deleted . (TGT-23793)

Fixed in the Target 17.4.1 release (April 27, 2017).

### Redirect offers

For Recently Viewed criteria, entity based dynamic rules will lead to no recommendation if the entity.id parameter is not passed in the mbox request. (RECS-6241)

This issue was fixed after the Recommendations release (March 22, 2018). After the Recommendations release, Target skips the entity-based dynamic rules if entity.id is not passed in the mbox request.

### at.js

When users attempt to download at.js from the Implementations details page after updating at.js settings, mbox.js is downloaded instead of at.js . (TGT-23069)

Fixed in the Target 17.3.1 release (March 30, 2017).

### Global exclusion rules

Global exclusion rules are taking 10-20 minutes to propagate to the edge for Premium Recommendations. (RECS-5270)

Fixed in the Recommendations 17.2.2.0 release (March 6, 2017).

### Analytics for Target (A4T) reporting

Reports are not updated when the reporting metric is switched. This is a UI issue. There is no impact on reporting data collection or delivery. (TGT-22970)

Fixed in the Target 17.2.2.0 release (February 24, 2017).

### CSV reports

Downloaded reports do not honor the Exclude Extreme Orders setting. (TGT-21871)

Fixed in the Target 17.2.1.0 release.
