---
description: The Visual Experience Composer (VEC) provides a visual interface for editing the experiences on your page in an Experience Targeting (XT) activity.
keywords: create experience;experience create;priority;audience;experience;visual experience composer
seo-description: The Adobe Target Visual Experience Composer (VEC) provides a visual interface for editing the experiences on your page in an Experience Targeting (XT) activity.
seo-title: Create Experience
solution: Target
title: Create Experience
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
---

# Create experience{#create-experience}

The [!UICONTROL Visual Experience Composer] (VEC) provides a visual interface for editing the experiences on your page in an [!UICONTROL Experience Targeting] (XT) activity.

1. Select the elements you want to change and make the desired changes.

   While [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), step one of the three-part guided workflow ([!UICONTROL Experiences]) displays the default [!UICONTROL Experience A] with an [!UICONTROL All Visitors] audience.

   ![All Visitors audience](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Any changes you make now apply to Experience A. In a step below, you'll click **[!UICONTROL Add Experience Targeting]** to create additional experiences.

   As you hover the elements on your page, the elements are highlighted. Any highlighted element can be altered using the VEC. For a list of actions that can be performed on an element to change the experience, see [Visual Experience Composer Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   If you created an mbox on the page using [!DNL Target Classic], that mbox appears as an element that shows the mbox name, and can be modified like any other element.

   >[!NOTE]
   >
   >By default, the VEC does not allow changes to elements containing JavaScript, such as rotating banners. You can select to disable JavaScript to alter those elements using the VEC.

1. To create additional experiences, click **[!UICONTROL Add Experience Targeting]**.

   ![Add Experience Targeting link](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL Choose Audience] dialog box displays. To target an experience to an audience, you must select the audience before you can add an experience.

   The audience library contains audiences that have previously been defined, including some common audiences that are pre-built as a part of [!DNL Target]. You can select an audience from the library or [create a new audience](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >In addition to selecting an existing audience, you can combine multiple audiences to create ad hoc combined audiences rather than creating a new audience. For more information, see [Combining Multiple Audiences](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   When creating an audience, you can select a location (mbox) and specify parameters for that location. Under [!UICONTROL Custom] (Create Audience > Add Rule > Custom), select the mbox, then specify the desired parameters.

   >[!NOTE]
   >
   >Audiences are automatically imported in the background when you open the audience list and the imported audiences are more than 10 minutes old.

1. Select one or more audiences to target with the experience, then click **[!UICONTROL Done]**.

   ![Experience B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   You'll notice that Experience B now displays in the preceding illustration and this experience is targeted to the US Visitors audience.

1. Select the elements you want to change for this experience and make the desired changes, an explained in Step 1 above.

1. Repeat the preceding steps to create additional targeted experiences, as needed.

1. Click **[!UICONTROL Next]** when you are finished designing your experiences.

   The activity diagram displays:

   ![XT Targeting diagram](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >If you deliver an image from a source other than your main page (such as an image hosted on `akamai.net` and delivered on `adobe.com`), that image does not display in the thumbnail of the page shown in the flow diagram.

1. (Conditional) Drag and drop audience/experience pairs while creating or editing XT activities to arrange the pairs in the desired order.

   Visitors are evaluated for experiences in order, from top to bottom.

   ![Move experiences](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL Experience Targeting] assumes that order matters. If a visitor falls into the first audience/experience pair, the first experience is delivered.

   For example, suppose you were not aware that order matters while creating an XT activity. You later realize during testing that visitors that you think should qualify for experiences B or C are instead qualifying for experience A. This could be because the audiences are not mutually exclusive and are not in the proper order (for example, experience A = United States, experience B = San Francisco, and experience C = California). In this scenario, all users from the United States qualify for experience A, even if they are located in San Francisco or elsewhere in California. You can reorder the audience/experience pairs from most restrictive to least restrictive (San Francisco > California > United States) without re-creating the entire activity.

   If you have an [!UICONTROL All Visitors] audience, ensure that it is not the first audience in the diagram. An experience targeted to "All Visitors" can be used as the last experience in the experience targeting activity to "catch" any visitors that have not fallen into any other experience.

## Rename or edit an experience

You can click the [!UICONTROL Edit] icon (three vertical ellipses) on an experience in an XT activity and choose from the following options, as necessary:

* Rename
* Edit

![Rename and Edit options](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Delete an experience

On the **[!UICONTROL Experiences]** page (the first step in the three-step guided workflow), click the three vertical ellipses > **[!UICONTROL Delete]**.

![Delete experience](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicate an experience

You can copy an experience in an XT activity so you can make minor changes to it without having to re-create the experience from scratch.

On the **[!UICONTROL Experiences]** page (the first step in the three-step guided workflow), click the three vertical ellipses > **[!UICONTROL Duplicate]**.

![Duplicate experience](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Training videos:

The following videos contain more information about the concepts discussed in this article.

### From A/B Testing to Experience Targeting

This video describes how to take A/B Testing to the next level with Experience Targeting (XT).

* Describe the three-step guided workflow to configure an XT activity 
* Describe how to deliver location-specific content to audiences located in different geographic areas 
* Describe how to reorder experiences to ensure that the right content is delivered to the right audience

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Activity Types (9:03)

This video explains the activity types available in Target Standard/Premium. Experience Targeting is discussed beginning at 5:15.

* Describe the types of activities included in [!DNL Adobe Target] 
* Select the appropriate activity type to achieve your goals 
* Describe the three-step guided workflow that applies to all activity types

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Using the Visual Experience Composer

This video provides information about using the Visual Experience Composer options.

* Change the content of a page 
* Change the layout of a page

>[!VIDEO](https://video.tv.adobe.com/v/17399)