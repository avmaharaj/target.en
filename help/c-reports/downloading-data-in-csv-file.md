---
description: Download data in a .csv format for quick import into Excel, Access, or other data analysis programs.
keywords: reports;download reports;csv;success metrics;order details
seo-description: Download data in a .csv format for quick import into Excel, Access, or other data analysis programs using Adobe Target.
seo-title: Downloading data in a CSV file using Adobe Target
solution: Target
subtopic: Multivariate Test
title: Downloading data in a CSV file
topic: Standard
uuid: 9ac151e1-45a9-4d46-b23b-e7c9ae518253
---

# Downloading data in a CSV file{#downloading-data-in-a-csv-file}

Download data in a .csv format for quick import into Excel, Access, or other data analysis programs.

To download data in a CSV file:

1. Click **[!UICONTROL Activities]**, then click the desired activity from the list.

   If you have many activities, you can filter the list by selecting options from the [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], and [!UICONTROL Activity Source] drop-down lists. 

1. Click the **[!UICONTROL Reports]** tab. 
1. Click the **[!UICONTROL Download]** icon, then select a report type to download for analysis in Excel and other tools.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

   ![Download options](/help/c-reports/assets/download-options.png)

## Export Report to CSV {#section_38BD9743EB254453B5F4A0A6F2720CD3}

The Success Metrics report shows you information about your success metrics, as well as the following metrics that are not available in the Target UI:

* Mean time to conversion in hours, so you can see how long it takes the average visitor to reach the conversion point 
* Sum of revenues, squared, for offline statistical confidence calculations

Data is saved until the end of the activity.

>[!NOTE]
>
>The CSV report includes only raw data and does not include calculated metrics such as revenue per visitor, lift, or confidence used for A/B tests. To calculate these calculated metrics, download the Target's [Complete Confidence Calculator](/help/assets/complete_confidence_calculator.xlsx) Excel file to input the activity's value, or review the [statistical calculations used by Target](/help/assets/statistical-calculations.pdf).

## Export Order Details to CSV {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

The Order Details report (known as the Audit report in [!DNL Target Classic]) shows you information about your orders, including:

* Order date and time 
* Order amount (if you inserted a Place Order mbox)

  The Order Details report works only if you have orders. 

* Order flag (duplicate or extreme orders)

  An order is flagged as extreme if it is more than +/- 3 standard deviations from the average order value using the last month of data (up to the point in time in which the calculation was made). An activity will have its extreme orders excluded once the activity has run for an hour or until after 15 orders, whichever comes first. For more information, see [Excluding Extreme Orders](../c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA). 

* Product ID

  The total length of product IDs, concatenated with commas, should not exceed 255 characters or the IDs will not display properly in the report. For example, if your order had products with IDs "aa, bb" then the total length is "aa,bb" = 5. 

* Experience

  In the [!UICONTROL Order Details] report for [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT), and [!UICONTROL Multivariate Test] (MVT) activities, the [!UICONTROL Experience] column contains the experience `localId`. This is the value output from the `$campaign.recipe.id` in offer tokens.

  There is not an [!UICONTROL Experience] column for [!UICONTROL Automated Personalization] (AP) activities. The current [!UICONTROL Algorithm Name] column has been replaced with "Control" versus "Targeted" terminology, as shown elsewhere in [!DNL Target].

  There was no impact on [!UICONTROL Recommendations] activities.

>[!NOTE]
>
>* Order report data includes four weeks of data for the default environment (host group) and two weeks for all non-default environments.
>* Revenue metrics that are set to "Increment count and keep the user in the activity" log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the Order Details report.

## Best Practices

* In order to record an order record, the `orderTotal` parameter must be passed. 
* Values passed via the `ProductPurchasedId` mbox parameter are listed in the Order Details report. 
* Best practice is to include an `orderID` as well as an `orderTotal`. This allows duplicate orders to automatically be ignored.

## Caveats {#section_49B9590904A645B18E694B4EFFFC1DEF}

The following information applies to the Download option:

* You can download both reports for A/B Test, Automated Personalization, Experience Targeting, and Multivariate activities. You cannot download the Success Metrics report for Recommendation activities. 
* The Download option is not available for A/B and Experience Targeting activities created before Target version 15.7.1 (July, 2015). 
* Experiences with no associated data are not recorded in the downloaded report.
* Audiences applied in the Target reporting UI do not carry over to the download report.
