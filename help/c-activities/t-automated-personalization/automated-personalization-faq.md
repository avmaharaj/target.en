---
description: List of frequently asked questions (FAQs) about Automated Personalization (AP).
keywords: troubleshooting;frequently asked questions;FAQ;FAQs;automated personalization
seo-description: List of frequently asked questions (FAQs) about Automated Personalization (AP).
seo-title: Automated Personalization FAQ
solution: Target
title: Automated Personalization FAQ
title-outputclass: premium
topic: Premium
uuid: 4c8aadd3-75c3-4388-b838-e62576dfb955
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Automated Personalization FAQ{#automated-personalization-faq}

List of frequently asked questions (FAQs) about Automated Personalization (AP).

## Can I specify a specific experience to be used as control?

You can select an experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

This feature lets you route the entire control traffic to a specific experience, based on the traffic allocation percentage configured in the activity. You can then evaluate the performance reports of the personalized traffic against control traffic to that one experience.

For more information, see [Use a specific experience as control](/help/c-activities/t-automated-personalization/experience-as-control.md).

## How can I compare Automated Personalization to a default experience? {#section_46C1A620A2384C2C8392D6716DD18495}

There is no turn-key option of comparing AP to a default experience. However, as a workaround, if a default offer or experience exists as part the overall activity, to understand its baseline performance you can click the “Control” segment in the reports and locate that particular offer in the resulting offer-level report. The conversion rate recorded for this offer can be used to compare with the conversation rate of the entire “Random Forest” segment. This helps to compare how the machine is doing compared to the default offer.

## What are best practices to set up an Automated Personalization activity? {#section_E155B26282BE49B58EA2683413D11DE6}

* If you are looking to personalize a lower-traffic page, or you want to make structural changes to the experience you are personalizing, consider using Auto-Target in place of Automated Personalization. See [Auto-Target For Personalized Experiences](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3). 
* Consider completing an A/B activity between the offers and locations you are planning to use in your Automated Personalization activity to ensure the location(s) and offers have an impact on the optimization goal. If an A/B activity fails to demonstrate a significant difference, Automated Personalization likely will also fail to generate lift.

    * If an A/B…N test shows no statistically significant differences between experiences, likely the offers you are considering are not sufficiently different from each other, the locations you selected do not impact the success metric, or the optimization goal is too far in the conversion funnel to be affected by your chosen offers.

* Make sure to use the [Traffic Estimator](../../c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) so you can have a sense of how long it will take for personalization models to build in your Automated Personalization activity. 
* Decide on the allocation between control and targeted before beginning the activity based on your goals.

  There are three scenarios to consider based on the goal of your activity and the type of control you’ve selected:

  * **Random Experiences as your control and your activity goal is to test the effectiveness of the personalization algorithm**: If your goal is to evaluate the personalization algorithm, then you’ll want to have a more accurate picture of your lift. You also would want to likely compare to what the conversion rate for your experiences/offers would be if you simply did an A/B Test (a randomly served control). In that situation, using a 50% allocation to a control of randomly served experiences is recommended.
  * **“Random Experiences” as your control and your activity goal is to maximize personalized traffic**: If you are comfortable with the algorithm and want to have the maximum amount of traffic personalized, a 10% to 30% allocation to control is recommended. The tradeoff here is the accuracy you’ll be able to see in your lift information (as the confidence intervals of your control traffic will be larger because there is less traffic flowing to them).
  * **Specific Experience as your control, with either goal type**: If you want to compare a specific marketer-driven experience to the personalization models, a 10% to 30% allocation to control is recommended. When you select only one experience as a control, then that traffic isn’t spread across every offer/experience in the activity.

* Targeting rules should be used as sparingly as possible because they can interfere with the model's ability to optimize. 
* Reporting groups can limit the success of your Automated Personalization activity. They should only be used under specific conditions.

    * Use reporting groups only if the following conditions are met: (1) you plan on replacing/adding new offers while the activity is running, (2) the offers in the reporting group appeal to the same visitors, and (3) the offers in that reporting group have about the same overall response rate. 
    * There is no personalization between offers in a reporting group: the offers are all treated as the same by the personalization model. 
    * Never put all offers in an activity into a single reporting group. This decision will cause all offers to be uniformly randomly served to all visitors in the activity.

## What are some limits in Automated Personalization? {#section_08BA09ED51B547299963C94FE6417CFA}

Target has a hard limit of 30,000 experiences, but it functions at its best when fewer than 10,000 experiences are created.

## How is offer-level targeting implemented? {#section_9D7A86EA93D74E9B8C81072A681263A4}

When each visitor arrives, the set of possible offers the visitor can see is determined by the offer-level targeting rules. Then, the algorithm chooses the offer that the model predicts will have the best expected revenue or chance of conversion from among those offers. Note that offer targeting impacts the efficacy of Target's machine learning algorithms and, as a result, should be used as sparingly as possible.

## My activity isn't showing any lift. What is going on? {#section_BFA07C8C258F45318F73A461B8F32737}

There are four factors required for an AP activity to generate lift:

* The offers in each location need to be different enough to influence visitors. 
* The locations need to be somewhere that makes a difference to the optimization goal. 
* There must be enough traffic and statistical power in the activity to detect the lift. 
* The personalization algorithm must work well.

The best course of action is to first make sure the content and locations that make up the activity experiences truly make a difference to the overall response rates using a simple, non-personalized A/B test. Be sure to compute the sample sizes ahead of time to ensure there is enough power to see a reasonable lift and run the A/B test for a fixed duration without stopping it or making any changes. If an A/B test results show statistically significant lift on one or more of the experiences, then it is likely that a personalized activity will work. Of course, personalization can work even if there are no differences in the overall response rates of the experiences. Typically, the issue stems from the offers/locations not having a large enough impact on the optimization goal to be detected with statistical significance.

For more information, [Troubleshooting Automated Personalization](../../c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

## How is Automated Personalization allocating my activity's traffic? {#section_4369364F77804E0D9B78BEE551DA5659}

Automated Personalization routes visitors to the experience that has the highest forecasted success metric based on the most recent [Random Forest](../../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA) models built for each model. This forecast is based on the visitor's specific information and visit context.

For example, assume an AP activity had two locations with two offers each. In the first location, Offer A has a forecasted conversion rate of 3% for a specific visitor, and Offer B has a forecasted conversion rate of 1%. In the second location, Offer C has a forecasted conversion rate of 2% for the same visitor, and Offer D has a forecasted conversion rate of 5%. Therefore, Automated Personalization would serve this visitor an experience with Offer A and Offer D.

## When should I stop my Automated Personalization activity? {#section_C51F3DAB8887463BB147373F6FE06B93}

Automated Personalization can be used as "always on" personalization that will constantly optimize. Especially for evergreen content, there is no need to stop your Automated Personalization activity. If you want to make substantial changes to the content that aren't similar to offers currently in your Automated Personalization activity, the best practice is to start a new activity so that other users reviewing reports will not confuse or relate past results with different content.

## How long should I wait for models to build? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

The length of time it takes for models to build in your activity typically depends on the traffic to your selected activity location(s) and your activity success metric. Use the [Traffic Estimator](../../c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) to determine the expected length of time it will take for models to build in your activity.

## One model is built within my activity. Are the visits to that experience personalized? {#section_51EA953C6D1D4A3185FC9DD290D66621}

No, there must be at least two models built within your activity for personalization to begin.

## When can I look at the results of my Automated Personalization activity? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

You can begin to look at the results of your Automated Personalization activity once you have at least two experiences with models built (green checkmark) for the experience that have models built.

## How can I decrease the amount of time needed for models to build in my activity? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

Review your activity setup and see if there are any changes you are willing to make to improve the speed at which models will build.

* Is your success metric far down the sales funnel from your activity experiences? A lower activity conversion rate will increase the traffic requirements needed for models to build, as a minimum number of conversions is required. 
* If your success metric is set to RPV, can you change to conversion? Conversion activities tend to require less traffic to build models. 
* Are there some experiences you can drop from your activity? Decreasing the number of experiences in an activity will speed up the amount of time to build models. 
* Is there a higher-traffic page there this activity would be more successful? The more traffic and conversions in your activity locations, the quicker models will build.

## Why are visitors seeing experiences for an AP activity that they shouldn't see? {#section_41CECEAE0881446A8D9F3B016857914B}

Automated Personalization activities are evaluated once per session. If there were active sessions that have qualified for a particular experience and now new offers have been added to it, users will see the new content along with the previously shown offers. Because they have previously qualified for those experiences, they would still see them for the duration of the session. If there's a desire to evaluate this at every single page visit, you should change to the Experience Targeting (XT) activity type. 
