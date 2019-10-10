---
description: Use the Visual Experience Composer in Target to create your test directly on a Target-enabled page and to modify portions of the page within Target.
keywords: Create A/B;A/B test;A/B activity;new a/b activity
seo-description: Use the Visual Experience Composer in Target to create your test directly on a Target-enabled page and to modify portions of the page within Target.
seo-title: Create an A/B Test
solution: Target
title: Create an A/B Test
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
---

# Create an A/B Test{#create-an-a-b-test}

Use the Visual Experience Composer in Target to create your test directly on a Target-enabled page and to modify portions of the page within Target.

1. From the [!UICONTROL Activities] list, click **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Create Activity drop-down list](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >The available activity types depend on your [!DNL Target] account. Some activity types might not appear in your list. For example, [!UICONTROL Recommendations] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For information about the various activity types, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) and the [Target activities guide](/help/c-activities/target-activities-guide.md).

   ![Create A/B Test Actity](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   If you prefer to use the Form-Based Experience Composer, select [!UICONTROL Form]. See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >In addition to the VEC and Form-Based Experience Composer, Target offers the Single Page Application VEC and the VEC for Mobile Apps. For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >For troubleshooting information about the VEC, should you have problems, see [Troubleshooting the Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [!UICONTROL [Choose Workplace](/help/administrating-target/c-user-management/property-channel/property-channel.md) option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Your organization has a Target Standard license if you do not see this option.]

1. (Conditional) If you are a [Target Premium customer](/help/c-intro/intro.md#premium), choose a [workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Specify your [activity URL](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), then click **[!UICONTROL Next]**.

   If your account is configured with a default URL, that URL appears by default. You can change from the default to another URL.

   The [!UICONTROL Visual Experience Composer] opens, showing the page specified in the URL.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Type a name for the activity in the space provided.

   ![Name field](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   The following characters are not allowed in an activity name:

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

1. Create any new experiences by changing the elements on the page.

   The [!UICONTROL Visual Experience Composer] displays two tabs on the left side after you create a new activity: Experience A and Experience B. Experience A is the control experience. Your focus will be on the Experience B tab, which you can modify as desired. Experience B is the alternate experience you can add to your test. You can add multiple experiences to the test. You can also delete Experience A from the activity if you don't want to include a default site experience as an option.

   For more information about adding and modifying experiences in the [!UICONTROL Visual Experience Composer], see [Add Experience](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). To modify Experience B, start with Step 3. 

1. Click **[!UICONTROL Targeting]** at the top of the [!UICONTROL Visual Experience Composer] to move to the next step in the three-step guided workflow.

   The flow diagram opens.

   ![A/B Test Targeting step](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   The flow diagram leads you through the steps of choosing the audience for the activity and setting up experiences. 
1. In the [!UICONTROL Audience] box, click the edit icon, then [select the audience](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) for your activity.

   By default, the audience is set to All Visitors. 
   
1. Choose the percentage of qualifying visitors that you want to enter the activity.

   ![Audience percentage](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   For example, you might limit entries to 50% of all visitors or 45% of your "Californians" audience. 

1. Set up your traffic allocation.

   You can show multiple experiences to the same audience. A diagram displays showing your selected audience and the experiences you've added to the activity.

   Choose your desired traffic allocation method:

   * **[!UICONTROL Manual (Default)]**: Specify the percentage of entrants you want to see each experience. You can split the percentages evenly between all experiences, or specify higher or lower percentages for each experience. The total for all experiences must equal 100%.

   * **[!UICONTROL Auto-allocate to best experience]**: Most activity entrants are automatically directed to higher-performing experiences. Some visitors are allocated to all experiences, to maintain exploration of experiences and to recognize changes in performance trends. See [Automated Traffic Allocation](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-target for personalized experiences]**: Target uses advanced machine learning algorithms to automatically target visitors with the best experience to maximize your goals. For more information, see [Auto-Target to Optimize](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

   You can also click **[!UICONTROL Add Experience]** to add another experience to the activity. 

1. When you are satisfied with your audience and experience choices, click **[!UICONTROL Next]** to move to the third step of the three-step guided workflow.

1. Specify the [goals and settings](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) for the activity.

   ![A/B Activity Settings](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Click **[!UICONTROL Save]**.

After you create the activity, the Overview tab shows information about the activity, including a diagram of your activity.

## Training video: Creating A/B Tests (8:36)

This video demonstrates how to create an A/B test using the [!DNL Target] three-step guided workflow.

* Create an A/B activity in Adobe Target 
* Allocate traffic using a manual split or automatic traffic allocation

>[!VIDEO](https://video.tv.adobe.com/v/17391)
