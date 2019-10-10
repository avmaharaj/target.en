---
description: The Mobile Visual Experience Composer (VEC) supports setting up of click tracking goals for Target activities.
keywords: Mobile App VEC;mobile visual experience composer;mobile experience composer options;mobile experience options;target view;clicks;click tracking;track
seo-description: The Mobile Visual Experience Composer (VEC) supports setting up of click tracking goals for Adobe Target activities.
seo-title: Set up click tracking in the Mobile App VEC
solution: Target
title: Set up click tracking in the Mobile App VEC
topic: Standard
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
---

# Set up click tracking in the Mobile App VEC{#set-up-click-tracking-in-the-mobile-vec}

The Mobile App VEC supports setting up of click tracking goals for [!DNL Target] activities.

1. When setting your goals on the Goals & Settings page for your activity , select the [!UICONTROL Conversion] success metric.

   ![](assets/mobile-vec-clicktrack1.png)

1. For the action, select **[!UICONTROL Clicked an Element]**, then click **[!UICONTROL Select Elements]**.

   Your mobile app opens in the Mobile Visual Experience Composer (VEC).

   ![](assets/mobile-vec-clicktrack2.png)

1. Select any elements that you want to track.

   See the [!UICONTROL Considerations] section below for tips on selecting elements.

   ![](assets/mobile-vec-clicktrack3.png)

1. Click the check mark at the top of the screen to save your selections.

You can also edit and change the click selections or delete them if you need to start fresh.

![](assets/mobile-vec-clicktrack4.png)

When an activity entrant clicks a selected element, that click is counted as a conversion.

## Considerations {#considerations}

There are several things to consider when selecting elements:

* When more than one element is selected and if a visitor clicks any one of these elements, the click is counted. To count each click separately, set up individual success metrics for each element.  
* Click events are sent to Target as soon as the user clicks the element. 
* In the Mobile App VEC, only those elements that have a click handler attached are allowed to be selected. 
* You can browse to any section of the app, but make sure that [views](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#target-views) are defined for the section where you are selecting elements for click tracking. 
* While editing an activity, if the device is already selected in Step 1, you don't need to select the device again. However, if you land directly on the click-track page, you will be shown the device selection screen to select an authorized device.
* A Modifications panel displays in the Mobile App VEC that displays the elements you have set up for click-tracking.

  ![Modifications panel showing click-tracking
](/help/c-target-mobile-app/c-mobile-visual-experience-composer/assets/click-track-modifications-panel.png)