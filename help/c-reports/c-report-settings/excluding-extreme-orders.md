---
description: You can exclude extreme values from affecting reports so a few unusual orders don't affect your activity results. An example of an unusual order might be a coach buying uniforms for an entire team instead of individual shoppers buying individual uniforms.
keywords: Target;reports;report settings;extreme orders;extreme values
seo-description: You can exclude extreme values from affecting reports in Adobe Target so a few unusual orders don't affect your activity results. An example of an unusual order might be a coach buying uniforms for an entire team instead of individual shoppers buying individual uniforms.
seo-title: Exclude extreme values in Adobe Target reports
solution: Target
title: Exclude extreme values
topic: Premium
uuid: bb151b54-09ef-40b5-bc04-95c61b761f5a
---

# Exclude extreme values{#exclude-extreme-values}

You can exclude extreme values from affecting reports so a few unusual orders don't affect your activity results. An example of an unusual order might be a coach buying uniforms for an entire team instead of individual shoppers buying individual uniforms.

>[!NOTE]
>
>The [!UICONTROL Exclude Extreme Values] flag applies to activities with Revenue and Engagement metric types only.

Extreme values are automatically flagged based on the rules described below. You can toggle between seeing and excluding the extreme values from your reports. An activity will have its extreme values excluded after the activity has run for an hour or after 15 orders, whichever comes first.

A value is considered extreme if it is more than +/- 3 standard deviations from the average order value using the last month of data (up to the point in time in which the calculation was made).

For example, the extreme value filter is often useful when using RPV. RPV combines conversion rate and average order value, and often exposes the volatility of those metrics. If you use RPV and determine that orders don't appear to be distributed normally, you might see more normal results if you apply the extreme order filter.

When a value is marked extreme, its order value is replaced with the average order value of the experience for the last month, excluding the extremes. The order is also marked as extreme in the Order Details report and in the CSV download for daily results.

**To exclude extreme values from your reports:** 

1. Open an activity that includes Revenue or Engagement metric types, then click the **[!UICONTROL Reports]** tab.
1. Click the gear icon.

   ![Report settings](/help/c-reports/c-report-settings/assets/report-settings-gear-icon.png)

   The [!UICONTROL Report Settings] options dialog box displays.

   ![Step Result](assets/exclude_extreme_values.png)

1. Toggle the **[!UICONTROL Exclude Extreme Values]** option on or off, as desired.
1. Click **[!UICONTROL Save]**.
