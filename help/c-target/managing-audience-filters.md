---
description: Audience filters (or audiences) are groups of visitors who share a specific characteristic or set of characteristics.
keywords: Targeting;audience filter;audiences;filter
seo-description: Audience filters in Adobe Target (or audiences) are groups of visitors who share a specific characteristic or set of characteristics.
seo-title: Audience filters for reporting in Adobe Target
solution: Target
title: Audience filters for reporting
uuid: ca2632c0-87e4-4a85-95e6-e63cf800ab2f
---

# Audience filters for reporting{#audience-filters-for-reporting}

Audience filters (or audiences) are groups of visitors who share a specific characteristic or set of characteristics.

Use audience filters to specify the audiences used for reporting. You can select an audience and compare its performance to the overall traffic. You might want to understand whether your winners were different for the various traffic sources, when compared to general traffic. This helps you discover audiences that should be potentially targeted to different content. One winner does not fit all traffic in many cases.

For example, visitors who arrive at your page from a certain search engine might be one audience. Other audiences might be based on gender, age, location, registration status, purchase history, or just about any other detail you can collect about your visitors. Use audience filters to divide visitor traffic and compare experience performance for each traffic segment.

When planning to use audience filters for an activity, consider the following guidelines:

* **Visitors can be in multiple audiences.** If there are two audiences set up (for example, "new visitors" and "visitors from Google"), and a person meets both criteria, then this visitor is counted and tracked in both audiences. As a result, the sum of the visitors in the audiences does not match the number of visitors in an activity. 
* **Set up audiences before launching the activity.** Audience data cannot be retrieved retroactively. If you do not configure audience filters before you start the activity, then decide to use them after the activity has run for a while, you will not collect the data for the time that has already passed. 
* **Begin with two to four audiences.** Focus on basic information, such as the traffic source. 
* **Rename audiences as needed.** You can rename an audience without affecting the data to make the audience name more meaningful for the results being collected, even if the activity is active. 
* **Enter precise values.** Audience filter values are case-sensitive. For example, if you are using an audience that filters on cities, you should use an "OR" condition to include possible spelling and capitalization variations, such as "Vienna," "vienna," "wien," and "Wien." 
* **Audiences created from the Audiences list are reusable.** Audiences created as part of an activity cannot be reused.

The following sections provide more information about setting up and reporting on audiences:

| Task | Topic |
|--- |--- |
|Create the appropriate activity or test.|[Activities and Tests](/help/c-intro/target-key-concepts.md)|
|Create audiences, if necessary.|[Create an Audience](/help/c-target/c-audiences/create-audience.md)|
|Combine multiple audiences, if necessary.|[Combine Multiple Audiences](/help/c-target/combining-multiple-audiences.md)|
|Apply audiences on the activity's  Goals & Settings page.|A/B Test: [Goals and Settings](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization:  [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>Experience Targeting: [Goals and Settings](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>Multivariate Test:  [Goals and Settings](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Recommendations activity settings](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br>Activity Settings: [Activity Settings](/help/c-activities/activity-settings.md)|
|View reports with information about your audience filters.|[Report settings](/help/c-reports/c-report-settings/report-settings.md)|

