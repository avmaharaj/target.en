---
description: Manage exclusions by creating exclusion groups, excluding duplicate offers, excluding specific experiences, and excluding default content in Automated Personalization (AP) activities.
keywords: dedupe;allow duplicates;exclude duplicate offers;automated personalization;disallow duplicate offers
seo-description: Manage exclusions by creating exclusion groups, excluding duplicate offers, excluding specific experiences, and excluding default content in Adobe Target Automated Personalization (AP) activities.
seo-title: Manage exclusions
solution: Target,Analytics
title: Manage exclusions
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
---

# ![Premium badge](/help/assets/premium.png) Manage exclusions{#manage-exclusions}

Manage exclusions by creating exclusion groups, excluding duplicate offers, excluding specific experiences, and excluding default content in Automated Personalization (AP) activities. 

## Create exclusion groups {#task_AAAA6C7239A84F7696C8492F04B575A2}

Create exclusion groups in Automated Personalization(AP) activities to ensure that experiences with the designated offers are automatically excluded. 

Exclusion groups are a great way to ensure that incompatible offers are not presented in the same experience in different locations. For example, suppose you have two offers: one is for 20% off of all merchandise and the other is for 15% off. You would never want these two offers to be presented to visitors in the same experience. If you add these two offers to an exclusion group, you can ensure that this will never be the case.

You can also limit which audiences can see specific offers in AP activities. For more information, see [Target Automated Personalization offers](/help/c-activities/t-automated-personalization/ap-target-offers.md).

**To create an exclusion group:** 

1. While [creating or editing an AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md), click **[!UICONTROL Manage Content]** in the header bar.

   ![Manage Content link](/help/c-activities/t-automated-personalization/assets/manage-content.png)

1. In the [!UICONTROL Manage Content] dialog box, click **[!UICONTROL Exclusion Group]**.

   ![Manage Content > Exclusion Groups dialog box](/help/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   If you have previously created exclusion groups, they display in the list. If you have not yet created an exclusion group, you are prompted to create one.

1. Click **[!UICONTROL Create Exclusion Group.]**

   ![Create Exclusion Group dialog box](/help/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Required) Specify a descriptive name for the exclusion group.

   A descriptive name helps you or others quickly locate and understand a group's purpose.

1. Locate and select the desired offers that you want to add to the exclusion group.

   You can select multiple offers from the same location in an exclusion group.

1. Click **[!UICONTROL Save]**.

The offers in the exclusion group will be automatically excluded from the same experiences going forward. 

## Exclude duplicate offers {#concept_4EF78013F80E48EFA024AE0274C9F037}

Prevent offers from the offer library from being duplicated when used in different locations in [!UICONTROL Automated Personalization] activities. 

You might have an activity, for example, with six locations on a page with 12 offers. There is a chance that the same offer could be placed in one or more locations in the activity. This feature prevents duplicate offers from displaying at the same time in different locations within the same activity. 

Click **[!UICONTROL Configure]** > **[!UICONTROL Duplicate Offers]**, then click **[!UICONTROL Allow Duplicates]** or **[!UICONTROL Disallow Duplicates]**. 

![Duplicate offers options](/help/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exclude specific experiences {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Exclude specific experiences if you want to exclude certain offer combinations from your Automated Personalization activity. 

There might be certain combinations that don't work well together, or you might be limiting the number of experiences tested to decrease traffic requirements for your activity. 

1. While [creating or editing an AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md), click **Manage Content** in the header bar.

   ![Manage Content link](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   The [!UICONTROL Experiences] list shows each experience generated from the permutations of all content and location options. 

1. Exclude experiences, as desired.

   You can exclude specific experiences by hovering over the desired experience and then clicking the exclude icon. 

   ![Exclude experience by hovering](/help/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Or you can batch exclude/include experiences by selecting the checkbox for the relevant experiences and then clicking the **[UICONTROL Exclude]** icon in the top right corner of the dialog box. The [!UICONTROL Exclude] icon appears when one or more experiences are checked. 

   ![Batch exclude experiences](/help/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   You can filter this list view to see only excluded or only included activities by clicking on the [!UICONTROL Status] drop-down list. 

   The experiences will now be excluded from the activity and their [!UICONTROL Status] will show as [!UICONTROL Excluded]. 

   ![Excluded experiences](/help/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Exclude default content {#task_DCB4528989DF4C05A3A4729E5891D18F}

In some cases, you might not want to include your default content as part of your Automated Personalization activity. How you access this setting is different from creating exclusion groups. You can use this method to have only one offer (different from your default content) in a location as part of your AP activity. 

Excluding default content is a great way to change the look and feel of the rest of the page to suit the offers you are testing with your AP activity. For example, suppose you want to match the color palette of the offers you are testing, you could change the background color of your page and exclude the default background color. 

**To exclude default content using the Visual Experience Composer (VEC):** 

1. While [creating or editing an AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md), select the content you want to replace and click to access **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]**, or **[!UICONTROL Change Background Color]**.
1. In the dialog box, create your new content and uncheck **Include** to the right of the default content (or uncheck the Default Image/Video in the Select Content screen).

   Depending on the content/offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)
   
1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You'll notice no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![](assets/exclude_content_vec_4.png)

**To exclude default content using the Form-Based Experience Composer:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the Select Content screen). 

   Depending on the content/offer type, the Include checkbox will be in a slightly different place. 

   For Text/HTML content: 

   ![](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You'll notice no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![](assets/exclude_content_form_3.png)
