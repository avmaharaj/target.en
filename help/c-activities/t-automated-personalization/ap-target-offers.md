---
description: In an Automated Personalization activity, you can target offers to specific audiences.
seo-description: In an Automated Personalization activity, you can target offers to specific audiences.
seo-title: Target Automated Personalization offers
solution: Target,Analytics
title: Target Automated Personalization offers
title-outputclass: premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Target Automated Personalization offers{#target-automated-personalization-offers}

In an Automated Personalization (AP) activity, you can target offers to specific audiences.

 Using this functionality reduces the number of offers a specific visitor is qualified to see. For example consider an AP activity that has three offers. Offer 1 has a targeting rule that limits its exposure to Audience A. Two visitors saw this AP activity.

| | Visitor 1 | Visitor 2 |
|--- |--- |--- |
|Audience Qualification|Audience A|Audience B|
|Offer 1 Target personalization model score|90|90|
|Offer 2 Target personalization model score|50|70|
|Offer 3 Target personalization model score|80|60|

In this scenario, Visitor 1 would see Offer 1 (because he or she qualifies as part of Audience A), which is that visitor's highest score. However, Visitor 2 would see Offer 2 even though his or her highest score is for Offer 1, because Visitor 2 is not part of Audience A. This example demonstrates why targeting rules should be used sparingly to meet business needs. Adding these rules can reduce the effectiveness of Target's personalization models.

## Set up targeting rules 

1. Create an [Automated Personalization activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) containing the offers you want to target.
1. After setting up the offers for the activity in the Visual Experience Composer, click **[!UICONTROL Manage Content]**.

   ![Manage Content](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   The Manage Content dialog box opens.

1. Click the Offers tab.

   ![Offers page](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Select the desired offer(s) and choose the audiences you want to qualify to see that offer.

   To set up targeting for a single offer, hover over the desired offer, then click the **[!UICONTORL Targeting]** icon.

   To set up targeting for multiple offers, select the checkboxes for the desired offers, then click the **[!UICONTROL Targeting] icon that displays at the top right of the list.

1. In the [!UICONTROL Choose Audience] dialog box, select the desired audience(s) for the offer(s), then click **[!UICONTROL Done]** to return to the [!UICONTROL Manage Content] dialog box.

   >[!NOTE]
   >
   >In addition to selecting an existing audience, you can combine multiple audiences to create ad hoc combined audiences rather than creating a new audience. For more information, see [Combining Multiple Audiences](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Click **[!UICONTROL Done]**.

>[!NOTE]
>
>You can set up 50 locations, and up to 250 offers per location.
