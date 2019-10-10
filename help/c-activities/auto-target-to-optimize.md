---
description: Auto-Target uses advanced machine learning to select from multiple high-performing marketer-defined experiences, and serves the most tailored experience to each visitor based on his or her individual customer profile and the behavior of previous visitors with similar profiles, in order to personalize content and drive conversions.
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
seo-description: Auto-Target uses advanced machine learning to select from multiple high-performing marketer-defined experiences, and serves the most tailored experience to each visitor based on his or her individual customer profile and the behavior of previous visitors with similar profiles, in order to personalize content and drive conversions.
seo-title: Auto-Target
solution: Target
title: Auto-Target
title-outputclass: premium
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Auto-Target{#auto-target}

[!UICONTROL Auto-Target] uses advanced machine learning to select from multiple high-performing marketer-defined experiences to personalize content and drive conversions. Auto-Target serves the most tailored experience to each visitor based on his or her individual customer profile and the behavior of previous visitors with similar profiles. 

>[!NOTE]
>
>[!UICONTROL Auto-Target] is available as part of the [!DNL Target Premium] solution. This feature is not available in [!DNL Target Standard] without a [!DNL Target Premium] license. For more information about the advanced features this license provides, see [Target Premium](/help/c-intro/intro.md).

While [creating an A/B activity using the three-step guided workflow](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72), you can choose to allocate traffic using the [!UICONTROL Auto-Target For Personalized Experiences] option:

![Auto target for personalized experiences option](/help/c-activities/assets/auto-target-ui-new.png)

## Overview {#section_972257739A2648AFA7E7556B693079C9}

The [!UICONTROL Auto-Target] option within the A/B activity flow lets you harness machine-learning to personalize based on a set of marketer-defined experiences in one click. [!UICONTROL Auto-Target] is designed to deliver maximum optimization, compared to traditional A/B testing or Auto Allocate, by determining which experience to display for each visitor. Unlike an A/B activity in which the objective is to find a single winner, [!UICONTROL Auto-Target] automatically determines the best experience for a given visitor (based on his or her profile and other contextual information) to deliver a highly personalized experience.

Similarly to Automated Personalization, [!UICONTROL Auto-Target] uses a Random Forest algorithm, a leading data science ensemble method, to determine the best experience to show to a visitor. Because [!UICONTROL Auto-Target] can adapt to changes in visitor behavior, it can be run perpetually to provide lift. This is sometimes referred to as "always-on" mode.

Unlike an A/B activity in which the experience allocation for a given visitor is sticky, [!UICONTROL Auto-Target] optimizes the specified business goal over each visit. Like in [!UICONTROL Auto Personalization], [!UICONTROL Auto-Target], by default, reserves part of the activity's traffic as a control group to measure lift. Visitors in the control group are served a random experience in the activity.

There are a few important notes to keep in mind when using [!UICONTROL Auto-Target]:

* You cannot switch a specific activity from [!UICONTROL Auto-Target] to Automated Personalization, and vice-versa. 
* You cannot switch from Manual traffic allocation (traditional A/B Test) to [!UICONTROL Auto-Target], and vice-versa after an activity is live. 
* When using hosts and environments (host groups), models are built for the "Production" environment only. All environments contribute data to build models for "Production" campaigns. 
* You must use a minimum of two experiences.

## Terminology {#section_A309B7E0B258467789A5CACDC1D923F3}

The following terms are useful when discussing [!UICONTROL Auto-Target]:

|  Term  | Definition  |
|---|---|
|  Multi-armed bandit  | A multi-armed bandit approach to optimization balances exploratory learning and exploitation of that learning.  |
|  Random Forest  |Random Forest is a leading machine learning approach. In data-science speak, it is an ensemble classification, or regression method, that works by constructing a large number of decision trees based on visitor and visit attributes. Within Target, Random Forest is used to determine which experience is expected to have the highest likelihood of conversion (or highest revenue per visit) for each specific visitor. For more information about Random Forest in Target, see [Random Forest Algorithm](../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA).  |
|  Thompson Sampling  |The goal of Thompson Sampling is to determine which experience is the best overall (non-personalized), while minimizing the “cost” of finding that experience. Thompson sampling always picks a winner, even if there is no statistical difference between two experiences. For more information, see [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling).  |

## How [!UICONTROL Auto-Target] Works {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Learn more about the data and algorithms underlying [!UICONTROL Auto-Target] and Automated Personalization at the links below:

| Term | Details |
|--- |--- |
|[Random Forest Algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md)|Target's main personalization algorithm used in both [!UICONTROL Auto-Target] and Automated Personalization is Random Forest. Ensemble methods like Random Forest use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms. The Random Forest algorithm in the automated personalization system is a classification, or regression method, that operates by constructing a multitude of decision trees at training time.|
|[Uploading Data For Target's Personalization Algorithms](/help/c-activities/t-automated-personalization/algo-random-forest.md)|There are several ways to input data for [!UICONTROL Auto-Target] and Automated Personalization models.|
|[Data Collection for Target's Personalization Algorithms](/help/c-activities/t-automated-personalization/ap-data.md)|Target's personalization algorithms automatically collect a variety of data.|

## Determining Traffic Allocation {#section_AB3656F71D2D4C67A55A24B38092958F}

Depending on the goal of your activity, you might choose a different traffic allocation between control and personalized experiences. Best practice is to determine this goal before you make your activity live.

The [!UICONTROL Custom Allocation] drop-down list lets you choose from the following options:

* Evaluate Personalization Algorithm 
* Maximize Personalization Traffic 
* Custom Allocation

![Allocation Goal drop-down list](/help/c-activities/assets/split-new.png)

| Activity Goal | Suggested Traffic Allocation | Tradeoffs |
|--- |--- |--- |
|**Evaluate Personalization Algorithm (50/50)**: If your goal is to test the algorithm, use a 50/50 percent split of visitors between the control and the targeted algorithm. This split gives the most accurate estimate of the lift. Suggested for use with “random experiences” as your control.|50% Control / 50% Personalized Experience split|<ul><li>Maximizes accuracy of lift between control and personalized</li><li>Relatively fewer visitors will have a personalized experience</li></ul>|
|**Maximize Personalization Traffic (90/10)**: If your goal is to create an “always on” activity, put 10% of the visitors into the control to ensure there is enough data for the algorithms to continue learning over time. Note the tradeoff here is that in exchange for personalizing a larger proportion of your traffic, you will have less precision in what the exact lift is. No matter your goal, this is the recommended traffic split when using a specific experience as the control.|Best practice is to use a 10% - 30% Control / 70% - 90% Personalized Experience split|<ul><li>Maximizes number of visitors who have a personalized experience</li><li>Maximizes lift</li><li>Less accuracy as to what the lift is for the activity</li></ul>|
|**Custom Allocation**|Manually split the percentage as desired.|<ul><li>You might not achieve the desired results. If you are unsure, follow the suggestions for either of the preceding options</li></ul>|

To adjust the Control percentage, click the icons in the Allocation column. You cannot decrease the control group to less than 10%.

![Change Auto-Target traffic allocation](/help/c-activities/assets/auto-target-control.png)

You can [select a specific experience to use as control](/help/c-activities/t-automated-personalization/experience-as-control.md) or you can use the Random experience option.

## When should you choose [!UICONTROL Auto-Target] over Automated Personalization? {#section_BBC4871C87944DD7A8B925811A30C633}

There are several scenarios where you might prefer to use [!UICONTROL Auto-Target] over Automated Personalization:

* If you want to define the entire experience rather than individual offers that will be automatically combined to form an experience. 
* If you want to leverage the full set of Visual Experience Composer (VEC) features not supported by [!UICONTROL Auto Personalization]: the custom code editor, multiple experience audiences, and more. 
* If you want to make structural changes to your page in different experiences. For example, if you wanted to rearrange the order of elements on your home page, [!UICONTROL Auto-Target] would be more appropriate to use than Automated Personalization.

## What does [!UICONTROL Auto-Target] Have in Common with Automated Personalization? {#section_2A601F482F9A44E38D4B694668711319}

**The algorithm optimizes for a favorable outcome for each visit.**

* The algorithm predicts a visitor's propensity for conversion (or estimated revenue from conversion) in order to serve the best experience. 
* A visitor is eligible for a new experience upon the end of an existing session (unless the visitor is in the control group, in which case the experience that visitor is assigned on his or her first visit remains the same for subsequent visits). 
* Within a session, the prediction doesn’t change, to maintain visual consistency.

**The algorithm adapts to changes in visitor behavior.**

* The multi-arm bandit ensures the model is always "spending" a small fraction traffic to continue to learn throughout the life of the activity learning and to prevent over-exploitation of previously learned trends. 
* The underlying models are rebuilt every 24 hours using the latest visitor behavior data to ensure Target is always exploiting changing visitor preferences. 
* If the algorithm can't determine winning experiences for individuals, it automatically switches to showing the overall best-performing experience while still continuing to look for personalized winners. The best-performing experience is found using [Thompson sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

**The algorithm continually optimizes for a single goal metric.**

* This metric could be conversion-based or revenue-based (more specifically Revenue per Visit).

**The algorithm does not support using [!DNL Analytics] as a data-source or a reporting endpoint.**

**Target automatically collects information about visitors to build the personalization models.**

* For more information about the parameters used in [!UICONTROL Auto-Target] and Automated Personalization, see [Automated Personalization Data Collection](../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**Target automatically uses all Experience Cloud shared audiences to build the personalization models.**

* You don't have to do anything specific to add audiences to the model. For information about using Experience Cloud Audiences with Target, see [Experience Cloud Audiences](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

**Marketers can upload offline data, propensity scores, or other custom data to build personalization models.**

* Learn more about [uploading data for Auto-Target and Automated Personalization](../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

## How Does [!UICONTROL Auto-Target] differ from Automated Personalization? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL Auto-Target] frequently requires less traffic than Automated Personalization for a personalized model to build.**

Although the amount of traffic *per experience* required for [!UICONTROL Auto-Target] or [!UICONTROL Auto Personalization] models to build are the same, there are usually more experiences in an Automated Personalization activity than an [!UICONTROL Auto-Target] activity. For example, if you had an [!UICONTROL Auto Personalization] activity where you've created two offers per location with two locations, there would be four (2 = 4) total experiences included in the activity (with no exclusions). Using [!UICONTROL Auto-Target], you could set experience 1 to include offer 1 in location 1 and offer 2 in location 2, and experience 2 to include offer 1 in location 1 and offer 2 in location 2. Because [!UICONTROL Auto-Target] allows you could choose to have multiple changes within one experience, you can reduce the number of total experiences in your activity.

For [!UICONTROL Auto-Target], simple rules of thumb can be used to understand traffic requirements:

* **When Conversion is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 7,000 visits and 350 conversions. 
* **When Revenue per Visit is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 1,000 conversions per experience. RPV usually requires more data to build models due to the higher data variance that typically exists in visit revenue compared to conversion rate.

**[!UICONTROL Auto-Target] has full-fledged setup functionality.**

* Because [!UICONTROL Auto-Target] is embedded in the A/B activity workflow, [!UICONTROL Auto-Target] benefits from the more mature and full-fledged Visual Experience Composer (VEC). You can also leverage [QA links](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) with [!UICONTROL Auto-Target].

**[!UICONTROL Auto-Target] provides an extensive online testing framework.**

* The multi-arm bandit is part of a larger online-testing framework that allows our data-scientists and researchers to understand the benefits of their continual improvements in real-world conditions. 
* In the future, this test bed will allow us to open our machine learning platform to our data-savvy clients so that they can bring in their own models to augment Target's models.

## Reporting and [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

For more information, see [Auto-Target Summary Report](../c-reports/auto-target-summary-report.md#concept_E2171F7B57C1417DAAD7E7909A3FB073) in the [Reports](../c-reports/reports.md#concept_B5077F5503AA4C98901AA99EDCE6CDE6) section.

## Auto-Target Frequently Asked Questions {#section_5C120A2B11D14D9BAF767BBAB50FED23}

**What are best practices to set up an [!UICONTROL Auto-Target] activity?**

* Decide if the business value of a Revenue per Visit (RPV) success metric is worth the additional traffic requirements. RPV typically needs at least 1,000 conversions per experience for an activity to work versus conversion.
* Decide on the allocation between control and personalized experiences before beginning the activity based on your goals.
* Determine if you have sufficient traffic to the page where your [!UICONTROL Auto-Target] activity will run for personalization models to build in a reasonable amount of time.
  * If you are testing the personalization algorithm, you shouldn’t change experiences or add/remove profile attributes while the activity is live.

* Consider completing an A/B activity between the offers and locations you are planning to use in your [!UICONTROL Auto-Target] activity to ensure the location(s) and offers have an impact on the optimization goal. If an A/B activity fails to demonstrate a significant difference, [!UICONTROL Auto-Target] likely will also fail to generate lift.

  * If an A/B test shows no statistically significant differences between experiences, it is likely the offers you are considering are not sufficiently different from each other, the locations you selected do not impact the success metric, or the optimization goal is too far in the conversion funnel to be affected by your chosen offers.

* Try not to make substantial changes to the experiences during the course of the activity.

**Do the check marks indicating a model is built for that experience update if the report date range changes?**

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.

**If a visitor does NOT see the [!UICONTROL Auto-Target] activity and converts, does the conversion count in my activity?**

No, only visitors who qualify for and view the [!UICONTROL Auto-Target] activity are counted in reporting.

**My [!UICONTROL Auto-Target] activity doesn’t seem to be generating any lift. What is going on?**

There are four factors required for an [!UICONTROL Auto-Target] activity to generate lift:

* The offers need to be different enough to influence visitors.
* The offers need to be located somewhere that makes a difference to the optimization goal.
* There must be enough traffic and statistical “power” in the test to detect the lift.
* The personalization algorithm must work well.

The best course of action is to first make sure the content and locations that make up the activity experiences truly make a difference to the overall response rates using a simple, non-personalized A/B test. Be sure to compute the sample sizes ahead of time to ensure there is enough power to see a reasonable lift and run the A/B test for a fixed duration without stopping it or making any changes.

If an A/B test's results show statistically significant lift on one or more of the experiences, then it is likely that a personalized activity will work. Of course, personalization can work even if there are no differences in the overall response rates of the experiences. Typically, the issue stems from the offers/locations not having a large enough impact on the optimization goal to be detected with statistical significance.

**When should I stop my [!UICONTROL Auto-Target] activity?**

[!UICONTROL Auto-Target] can be used as “always on” personalization that will constantly optimize. Especially for evergreen content,there is no need to stop your [!UICONTROL Auto-Target] activity.

If you want to make substantial changes to the content in your [!UICONTROL Auto-Target] activity, the best practice is to start a new activity so that other users reviewing reports will not confuse or relate past results with different content.

**How long should I wait for models to build?**

The length of time it takes for models to build in your [!UICONTROL Auto-Target] activity typically depends on the traffic to your selected activity location(s) and your activity success metric.

For [!UICONTROL Auto-Target], simple rules of thumb can be used to understand traffic requirements:

* **When Conversion is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 7,000 visits and 350 conversions.
* **When Revenue per Visit is your success metric:** 1,000 visits and at least 50 conversions per day per experience, and in addition the activity must have at least 1,000 conversions per experience. RPV usually requires more data to build models due to the higher data variance that typically exists in visit revenue compared to conversion rate.

**One model is built in my activity. Are the visits to that experience personalized?**

No, there must be at least two models built within your activity for personalization to begin.

**When can I start to look at the results of my [!UICONTROL Auto-Target] activity?**

You can begin to look at the results of your [!UICONTROL Auto-Target] test after you have at least two experiences with models built (green checkmark) for the experience that have models built.

**Can I specify a specific experience to be used as control?**

You can select an experience to be used as control while creating an [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) or [Auto-Target](/help/c-activities/auto-target-to-optimize.md) (AT) activity.

This feature lets you route the entire control traffic to a specific experience, based on the traffic allocation percentage configured in the activity. You can then evaluate the performance reports of the personalized traffic against control traffic to that one experience.

For more information, see [Use a specific experience as control](/help/c-activities/t-automated-personalization/experience-as-control.md).

## Troubleshooting [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

Sometimes activities don't go as expected. Here are some potential challenges you may face while using [!UICONTROL Auto-Target], and some suggested solutions.

**My [!UICONTROL Auto-Target] activity is taking too long to build models.**

There are several activity setup changes that can decrease the expected time to build models, including the number of experiences in your [!UICONTROL Auto-Target] activity, the traffic to your site, and your selected success metric.

**Solution:** Review your activity setup and see if there are any changes you are willing to make to improve the speed at which models will build.

* If your success metric is set to RPV, can you change to conversion? Conversion activities tend to require less traffic to build models. You will not lose activity data if you change the success metric from RPV to conversion.
* Is your success metric far down the sales funnel from your activity experiences? A lower activity conversion rate will increase the traffic requirements needed for models to build, as a minimum number of conversions is required.
* Are there some experiences you can drop from your activity? Decreasing the number of experiences in an activity will lessen the amount of time to build models.
* Is there a higher-traffic page on which this activity would be more successful? The more traffic and conversions in your activity locations, the quicker models will build.

**My [!UICONTROL Auto-Target] activity isn't generating any lift.**

There are four factors required for an AP activity to generate lift:

* The offers need to be different enough to influence visitors.
* The offers need to be located somewhere that makes a difference to the optimization goal.
* There must be enough traffic and statistical “power” in the test to detect the lift.
* The personalization algorithm must work well.

**Solution:** First, make sure that your activity is personalizing traffic. If models aren't built for all of the experiences, your [!UICONTROL Auto-Target] activity is still randomly serving a significant portion of visits to attempt to build all models as quickly as possible. If models aren't built, [!UICONTROL Auto-Target] is not personalizing traffic.

Next, make sure the offers and the activity locations truly make a difference to the overall response rates using a simple, non-personalized A/B test. Be sure to compute the sample sizes ahead of time to ensure there is enough power to see a reasonable lift and run the A/B test for a fixed duration without stopping it or making any changes. If an A/B test results show statistically significant lift on one or more of the experiences, then it is likely that a personalized activity will work. Of course, personalization can work even if there are no differences in the overall response rates of the experiences. Typically, the issue stems from the offers/locations not having a large enough impact on the optimization goal to be detected with statistical significance.

**Any metric dependent on conversion metric never converts.**

This is expected.

In an [!UICONTROL Auto-Target] activity, once a conversion metric (whether optimization goal or post goal) is converted, the user is released from the experience and the activity is restarted.

For example, there is an activity with a conversion metric (C1) and an additional metric (A1). A1 is dependent on C1. When a visitor enters the activity for the first time, and the criteria for converting A1 and C1 are not converted, metric A1 is not converted due to the success metric dependency. If the visitor converts C1 and then converts A1, A1 is still not converted because as soon as C1 is converted, the visitor is released.

## Training video: Understanding Auto-Target Activities

This video explains how to set up an [!UICONTROL Auto-Target] A/B activity.

After completing this training, you should be able to:

* Define [!UICONTROL Auto-Target] testing 
* Compare and contrast [!UICONTROL Auto-Target] to Automated Personalization 
* Create [!UICONTROL Auto-Target] activities

>[!VIDEO](https://video.tv.adobe.com/v/18558)