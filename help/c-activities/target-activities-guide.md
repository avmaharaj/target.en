---
description: Download an interactive PDF that describes the different activity types in Adobe Target (with the exception of Recommendations).
keywords: activities guide;activities;activity;activity types;activity actions
seo-description: Download an interactive PDF that describes the different activity types in Adobe Target (with the exception of Recommendations).
seo-title: Target activity types
solution: Target
title: Target activity types
topic: Standard
uuid: ce2accb4-8330-4431-8d47-8863c54274b5
---

# Target activity types{#target-activity-types}

Download an interactive PDF that describes the different activity types in Adobe Target (with the exception of Recommendations).

>[!NOTE]
>
>For the best experience and to share with others, download the interactive [Adobe Target Activities Guide PDF](/help/assets/activities_guide_82817.pdf).

## What does it do? {#section_4ECAACC68723402EB3649033190E1BBC}

| Activity Type | Details |
|--- |--- |
|![icon](/help/c-activities/assets/icon_ab.png)<br/>Manual A/B Test|Compares two or more experiences to see which best improves conversions throughout a pre-specified test period.  For more information, see  [A/B Test](/help/c-activities/t-test-ab/test-ab.md).|
|![Icon Auto-allocate](/help/c-activities/assets/icon_auto_allocate.png)<br/>Auto-Allocate|Identifies a winner among two or more experiences, and then re-directs traffic to the winner, increasing conversion as the test runs and learns.  For more information, see  [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).|
|![Icon AT](/help/c-activities/assets/icon_auto_target.png)<br/>Auto-Target|Uses advanced machine learning to personalize content and drive conversions by identifying multiple high-performing, marketer-defined experiences, and then serving the most tailored experience to visitors based on their individual customer profiles and past behaviors of similar visitors.  For more information, see  [Auto-Target For Personalized Experiences](/help/c-activities/auto-target-to-optimize.md).|
|![Icon AP](/help/c-activities/assets/icon_ap.png)<br/>Automated Personalization (AP)|Uses advanced machine learning to personalize content and drive conversions by combining specific offers or messages, and then matching different offer variations to visitors, based on their individual customer profiles.  For more information, see [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md).|
|![Icon MVT](/help/c-activities/assets/icon_mvt.png)<br/>Multivariate Testing (MVT)|Compares combinations of offers among elements on a page to see which combination performs the best for a specific audience. Also, identifies which element of the page best improves conversions throughout a pre-specified test period.  For more information, see [Multivariate Test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).|
|![Icon XT](/help/c-activities/assets/icon_xt.png)<br/>Experience Targeting (XT)|Delivers content to a specific audience based on a set of marketer-defined rules and criteria. For more information, see  [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md).|

## Why are you using this? {#section_46A70DD7CE3448749E635DDF5EAFC131}

| Activity Type | Reason |
|--- |--- |
|Manual A/B Test|A highly controlled experiment with traffic measurements, split by percentages rather than by a rule, allowing you to analyze the test data, glean insights about your audience, and determine which experience performs the best.|
|Auto-Allocate|A way to identify a winning experience and adjust traffic allocation to deliver it to visitors as fast as possible, supporting a faster and higher likelihood of conversion.|
|Auto-Target|A way to identify the winners among multiple experiences, and then deliver the most appropriate experience to specific visitors. The targeting adapts over time as visitors' interests change, because the algorithm predicts a visitor's propensity for conversion on a certain experience at a certain time.|
|Automated Personalization (AP)|A way to personalize a set of offers (created or pre-defined, in elements on a single page or across multiple pages) and deliver offer combinations that work the best to attract specific visitors.|
|Multivariate Testing (MVT)|A way to display multiple offers in multiple elements, and then test the resulting unique experiences concurrently against a specific goal , which helps determine which element variation is the most successful, and also potentially reveal which elements have the greatest positive or negative impact on a visitor's interaction.|
|Experience Targeting (XT)|Simply a way to target specific content to a specific audience based on a set of defined allocation rules.|

## What kind of marketer should use this? {#section_A843D663D3E543FFB1A594266B560395}

| Activity Type | The Marketer |
|--- |--- |
|Manual A/B Test|Is knowledgeable in stats.<br/>Has the time to wait until end of test period to analyze results.|
|Auto-Allocate|Has a short time frame.<br/>Needs to identify best experience and deliver quickly.<br/>Wants to be able to "peek" at results as test runs.|
|Auto-Target|Has several eligible experiences.<br/>Wants to match experiences to specific visitors at optimal times based on their dynamic and changing profiles.|
|Automated Personalization (AP)|Has one or more offers.<br/>Wants to create offers combinations that yield optimal personalized experiences for specific visitors across a variety of unique profiles and behaviors.|
|Multivariate Testing (MVT)|Is knowledgeable in stats.<br/>Has one or more offers.<br/>Wants to analyze conversion trends relating to page element interactions.|
|Experience Targeting (XT)|Needs to deliver a specific experience or piece of content to a specific audience.|

## Statistical details {#section_22CF2D07DB054505AB5EC702B99A5BB0}

| Activity Type | Details |
|--- |--- |
|Manual A/B Test|The test compares each challenger experience to a control experience and then ranks the performance of all experiences, identifying both a winning experience, and a losing experience when compared to the control.|
|Auto-Allocate|The test produces a statistical guarantee on a true winner right away, and then directs more traffic towards audiences who have a higher likelihood of conversion with that winning experience.|
|Auto-Target|The optimization mechanism identifies the relevant audience for each experience by showing increases and decreases in lift over time, and before it determines which experience to deliver to which visitor, it is informed by conversions, segments, parameters, and profile scripts. From there, it automatically chooses which algorithm to utilize in order to generate a higher lift and conversion rate.|
|Automated Personalization (AP)|The optimization mechanism constantly adjusts which experiences are delivered to which visitors based on new visitor behavior and past behaviors of similar visitors, with an offer's performance being measured against concurrent control groups.|
|Multivariate Testing (MVT)|The test helps uncover the relative influence that specific elements have on conversion.|
|Experience Targeting (XT)|The method defines rules that target either a specific experience or a specific piece of content to a specific audience. User can make updates at the experience level.|

## Benefits and considerations {#section_56C46ABEF7B945DDA0C1E6D714377123}

| Activity Type | Benefits | Considerations |
|--- |--- |--- |
|Manual A/B Test|A/B Testing allows you to gain a full understanding of how each experience performs, beyond just which experience performs the best.|In an A/B Test, if you look at the test results before the sample size is reached, you risk relying on inaccurate results (you cannot "peek"earlier!).</br>That is because unlike Auto-Allocate, in an A/B test, the traffic distribution remains fixed even after you recognize that some experiences are outperforming others.|
|Auto-Allocate|Auto-Allocate reduces the cost of a typical A/B test because it has a higher overall conversion rate than a manual A/B test. The conversion rate is higher because Auto-Allocate pushes more traffic to the highest performing experience, meaning you can realize the benefit of that winning experience earlier than the end of the test period (you can peek!).|Auto-Allocate identifies the winner but does not differentiate among the losers. If you need to know how each Experience performed, A/B testing is preferable.</br>The Auto-Allocate feature works with only one advanced metric setting , which is "Increment Count and Keep User in Activity."This means that if you do not want to count repeat conversions, you should use A/B testing instead.  Auto- Allocate cannot consume reports in A4T.|
|Auto-Target|With Auto-Target, machine learning is applied to any kind of experience, including multi-page experiences. It also allows you to gain the value of Automated Personalization while using the familiar A/B testing workflow.|With Auto-Target, if you want to change the content of your offers often or frequently, the algorithm will need enough time after each change to exploit what it learns and actually deliver that content to the right visitors.</br>Auto Target cannot consume reports in A4T.|
|Automated Personalization (AP)|With Automated Personalization, you can collect all of your offers in one place, and the algorithm simply figures out the best combination of them. You do not need to specify or build individual experiences. Automated Personalization uses the same machine learning algorithms as Auto-Target.|When you combine multiple offers, a combinatorial explosion occurs resulting in the need for a significant amount of traffic. Automated Personalization's algorithm accounts for a large amount of factors; therefore requiring the most amount of traffic.</br>Automated Personalization cannot consume reports in A4T.|
|Multivariate Testing (MVT)|With Multivariate Testing, you are able to test multiple elements simultaneously.|A Multivariate Test is time consuming , and due to the multiple variables at play, it does not necessarily produce a winning Experience with confidence.</br>It is often challenging to reach the amount of traffic needed to complete the test. Since all Multivariate test experiments are fully factorial, too many changing elements at once can quickly add up to a very large number of possible combinations that must be tested.</br>Even a site with fairly high traffic might have trouble completing a test with more than 25 combinations in a feasible amount of time.|
|Experience Targeting (XT)|With Experience Targeting, you can quickly act on insights deduced from any activity results.</br>For example, if you ran an A/B test where the challenger did not outperform the control, but the results indicate that a very specific segment of visitors actually converted 4x more with the challenger than they did with the control, then you can use Experience Targeting to direct the challenger Experience to that particular segment.|Experience Targeting does not allow you to control the percentage split of an experience across multiple audiences.|