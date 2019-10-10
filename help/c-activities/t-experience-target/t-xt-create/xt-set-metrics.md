---
description: Use metrics in an Experience Targeting (XT) activity to determine when a visit is successful.
keywords: experience targeting;xt;metrics;set metrics;goal metric;activity settings;success metric;conversion;revenue;engagement
seo-description: Use metrics in an Adobe Target Experience Targeting (XT) activity to determine when a visit is successful.
seo-title: Set Metrics
solution: Target,standard
title: Set Metrics
uuid: 5b2f6613-0773-4614-9d39-d9a408566969
---

# Set metrics{#set-metrics}

Use metrics in an Experience Targeting (XT) activity to determine when a visit is successful.

For detailed information about success metrics, see [Success Metrics](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924). 

1. Specify the goal of the activity.
1. Select a [success metric](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Select success metric](/help/c-activities/t-experience-target/t-xt-create/assets/ab_metrics-new.png)

   The [!UICONTROL Select Metrics] page lists the success metrics you can choose for your activity. The success metrics are divided into the following categories:

   * Conversion 
   * Revenue 
   * Engagement

   You can use any of the pre-built success metrics, or create a custom success metric. You can also mark a success metric as a primary metric. Reports and Experience Cloud cards default to show the primary metric, if one is set. 
1. Specify the settings for your metrics.

   The available settings depend on the success metric you are using.

   If enabled, the [!UICONTROL Estimated Value of the Conversion]field (not available for the Page Score metrics) provides a value for your goal. This value enables Target to calculate an estimated lift in revenue. This field is optional; however, incremental revenue for any non-revenue metric cannot be calculated without it. The data type is currency. This field is progressively shown after the user indicates the action taken to satisfy the goal. See [Estimating Lift in Revenue](../../../administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md#concept_32F875D8F91349CE86AF391F65BEAEEE) for more information.

   The correct configuration of success metrics is critical for making sure you get the data you expect.

   For more information, see [Success Metrics](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924). 
1. (Optional) Add additional metrics.
1. Click **[!UICONTROL Continue]** when you are finished setting your metrics.
Note that when you name or rename a metric, the following characters are not allowed:

   | Character | Description |
   |--- |--- |
   |`/`|Forward slash|
   |`?`|Question mark|
   |`#`|Number sign|
   |`:`|Colon|
   |`=`|Equals to|
   |`+`|Plus|
   |`-`|Minus|
   |`@`|At sign|

## Training video: Activity Metrics (7:43)

This video includes information about working with success metrics.

* Understand "goal" metrics 
* Understand and build Conversion, Revenue, and Engagement metrics 
* Build a click-tracking metric

>[!VIDEO](https://video.tv.adobe.com/v/17380) 
