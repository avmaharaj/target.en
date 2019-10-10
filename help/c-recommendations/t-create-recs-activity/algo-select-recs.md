---
description: Select the criteria to use in your Recommendations activity.
keywords: recommendations;recommendations activity;criteria
seo-description: Select the criteria to use in your Adobe Target Recommendations activity.
seo-title: Select criteria
solution: Target
title: Select criteria
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Select criteria{#select-criteria}

Select the [criteria](/help/c-recommendations/c-algorithms/algorithms.md) to use in your Recommendations activity. Criteria are rules that determine which products to recommend based on a predetermined set of visitor behaviors.

You can test multiple recommendation types against each other by adding more than one criteria.

If you select multiple criteria, traffic is split evenly between the selected criteria. For example, if you have selected two criteria and your activity is designed to display default content to 20% of activity entrants, then 40% of activity entrants will see the recommendations controlled by each criteria. There is no option to change the percentages for each criteria.

* To search for an existing criteria (for example, if many criteria cards display), type in the search field until the desired criteria appears, then select the criteria and click **[!UICONTROL Done]**.

  Some criteria are supplied with [!DNL Recommendations]. You and your team can also create your own custom criteria. 

* To create a new criteria, click **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. For information about creating new criteria, see [Create a New Criteria](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**To select criteria:**

1. While [creating a new recommendation](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), in the **[!UICONTROL Criteria]** dialog box, locate and select one or more criteria.

   ![Select Criteria dialog box](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   You can use the [!UICONTROL Industry Type] filter, [!UICONTROL Page Type] filter, and [!UICONTROL Compatible] checkbox to filter the list of criteria. These options help you locate the desired criteria.

   * **Industry Type:** The industry type is used to help categorize [!DNL Recommendations] criteria. To change your default industry vertical, click **[!UICONTROL Settings]** and select your desired default **[!UICONTROL Industry Vertical]** setting. 
   * **Page Type:** The page type helps you categorize your recommendations. There are also built-in criteria that can be chosen for each page type. 
   * **Compatible:** Show only those criteria where the selected page passes the required data. Not every criteria will run correctly on every page. The page or mbox needs to pass in `entity.id` or `entity.categoryId` for the current item/current category recommendations to be compatible. In general, it is best to show only compatible criteria. However, if you want incompatible criteria to be available for the activity, clear the **[!UICONTROL Compatible]** check box. This option can be disabled or enabled in your [!DNL Target] [!UICONTROL Preferences].

1. Click **[!UICONTROL Next]** to display the [Select Design](/help/c-recommendations/c-design-overview/design-overview.md) dialog box.
