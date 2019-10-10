---
description: Select an experience to be used as control while creating an Automated Personalization (AP) or Auto-Target activity.
keywords: experience;control;automated personalization;auto-target
seo-description: Select an experience to be used as control while creating an Automated Personalization (AP) or Auto-Target activity in Adobe Target.
seo-title: Use a specific experience as control in Adobe Target
solution: Target,Analytics
title: Use a specific experience as control
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
---

# ![PREMIUM](/help/assets/premium.png) Select the control for your Automated Personalization or Auto-Target activity

You can select a randomly served experience or a specific experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

This feature lets you route the control traffic to the relevant experiences, based on the traffic allocation percentage configured in the activity. You can then evaluate the performance reports of the personalized traffic against control traffic to that control.

The options for setting a control in AP and AT activities is a little different than other activity types. In a manual A/B Test, you can change what reporting shows as your control, and lift is calculated based on the conversion rate of that control experience. You can make this change easily because traffic is served randomly to each of the experiences you included in your activity, no matter what the control is initially set to. In other words, selecting the control doesn’t impact how traffic is served. In AP and AT activities, your decision on what to choose as the control does impact how the visitor traffic is served. As a result, you need to think more carefully about your decision.

There are two options available for your control in your AP and AT activities: randomly served experiences or a specific experience.

* **Randomly served**: For a random control, the control percentage of traffic randomly serves all experiences in the activity, without considering that visitor’s profile. You can think of the control as helping answer the question, “If I just randomly serve an experience (or offer) to visitors and don’t consider their profiles, what is the conversion rate for that experience (or offer)?” The control is like an A/B Test within your AI activity. Having this information of the non-personalized conversion rate for each experience or offer can be helpful to understand when analyzing your activity results.

* **Specific experience**: A specific experience control lets you compare your traffic served by Target’s personalization models to a specific marketer-defined experience (for example, your default homepage). With this option, the control percentage of traffic randomly serves traffic for only that one experience.

## Specify a specific experience as control

1. While creating an [AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) or [AT activity](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), configure the experiences as desired.
1. On the [!UICONTROL Targeting] page (step 2 of the three-part guided workflow), select the desired experience as the control.
1. Specify the desired traffic allocation for the control experience and the other experiences.

   For a specific experience control, 10% to 30% is advised.

1. Continue with the [!UICONTROL Goals & Settings] page.

## Known limitations and considerations

Keep the following points in mind when using a specific experience as control:

* Changing the control experience in an already live activity isn't advised. The latest control experience selected is named in reporting (even if older reports are based on another experience).
* Deleting the control experience isn't advised.
* Adding a large number of new offers/experiences to a live activity with a specific experience as the control is not advised.
* In AP activities, including targeting on the control experience that could further constrain who can see that experience isn't advised.
* In AP activities, lift and confidence information is *NOT* available in the offer-level report if a specific experience is selected. Lift and confidence information is available at the overall "targeted" vs. "control" traffic level for the AP activity. Lift and confidence information is available if "random" is selected as the control. This difference is because comparing a specific experience's conversion rate to an offer's conversion rate isn't logical due to the difference in units. The information available in an AT activity is the same, no matter what type of control is selected.
* Because all control traffic goes to a single experience or set of offers when you select the experience as control (compared to random, where the control traffic amount is split over the number of experiences or offers in your activity), you generally do not need as much traffic to flow to the control. 10% is a good place to start.
* If you do one of the following to a live activity with a specific experience as a control, the control is automatically reset to randomly served experiences (instead of the previously selected specific experience):

  * Delete an experience
  * Remove a location or offer (AP only)
  * Exclude an experience, manually, via removing duplicate offers or via an exclusion group (AP only)
  