---
description: Use Activity Settings to manage the objective, priority, and duration of your activities.
keywords: Goal &Settings;objective;priority;duration
seo-description: Use Activity Settings to manage the objective, priority, and duration of your activities.
seo-title: Activity settings
solution: Target
subtopic: Multivariate Test
title: Activity settings
topic: Standard
uuid: d317e63a-ba1f-4c0e-ab90-c6181b8b45fd
---

# Activity settings{#activity-settings}

Use Activity Settings to manage the objective, priority, and duration of your activities.

1. Enter notes about the activity's objective.

   Type any information about your activity that is useful to keep on hand for yourself or other team members. Drag to resize the [!UICONTROL Objective] field. 
1. Set the activity priority.

   Depending on your settings, the UI and options for [!UICONTROL Priority] vary. You can use the legacy settings of Low, Medium, or High, or you can enable fine-grained priorities from 0 to 999.

   The priority is used if multiple activities are assigned to the same location with the same audience. If two or more activities are assigned to the location, the activity with the highest priority displays.

   If this option is not enabled in [!UICONTROL Setup] (the default), specify a priority: Low, Medium, or High.

   To enable fine-grained priorities, click [!UICONTROL Setup], then toggle the [!UICONTROL Enable Fine-Grained Priorities] option to the "On" position.

   If this option is enabled, specify a value between 0 and 999:

   * 0 = Low 
   * 999 = High

   For activities created in previous versions of [!DNL Target Standard/Premium], Low priority is converted to 0, Medium is converted to 5, and High is converted to 10. You can adjust these values as necessary.

   >[!NOTE]
   >
   >Before you can disable this option after using fine-grained priories, all priorities must be set back to 0, 5, and 10.

1. Set the duration of the activity.

   You can manually activate and deactivate the activity, or specify a date and time for delivery of the activity. The time control uses a 24-hour clock, with 00:00 being midnight. The time zone is set to the time zone configured in your browser. To use a different time zone, set your browser to another time zone and restart the browser.

   >[!NOTE]
   >
   >Scheduling an activity controls the delivery time frame of the activity; however, the activity must be explicitly activated before it can be delivered according to the specified schedule.

The [!UICONTROL Goal & Settings] page includes additional settings that vary based on the type of activity you are creating. For more information on these settings, refer to your activity type:

* [A/B Test](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) 
 * [Automated Personalization](../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) 
* [Experience Targeting](../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) 
* [Multivariate Test](../c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) 
* [Recommendations](../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## Training video: Activity Settings

This video includes information about activity settings.

* Enter an objective for your activity 
* Set the priority level of your activities 
* Schedule activity start and end times 
* Add audiences for reporting to create report filters 
* Enter notes for your activities

   >[!VIDEO](https://video.tv.adobe.com/v/17381) 
