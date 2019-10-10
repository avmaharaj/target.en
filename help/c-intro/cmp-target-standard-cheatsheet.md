---
description: A list of frequently asked questions about using the features in Adobe Target, along with information and links for more information.
keywords: Target Standard;faq;frequently asked questions;cheat sheet;cheatsheet
seo-description: A list of frequently asked questions about using the features in Adobe Target, along with information and links for more information.
seo-title: Target optimization and personalization FAQ
solution: Target
title: Target optimization and personalization FAQ
topic: Advanced
uuid: b6052939-6ed4-4c90-b118-77b6fe42b0af
---

# Target optimization and personalization FAQ{#target-optimization-and-personalization-faq}

A list of frequently asked questions about using the features in Adobe Target, along with information and links for more information.

## General Information {#section_CE5713B5AAC341C9A75586C107797FA3}

**How can I see how other customers have leveraged Adobe Target for better results?**

Here are just some of our [customer success stories](https://www.adobe.com/in/marketing-cloud/target/resources.html#x). See how customers like you have leveraged Target to improve optimization and personalization to achieve business goals.

Note that some of these case studies have leveraged capabilities from Adobe Target Premium.

**Where can I learn about the latest Target features?**

See our [Release Notes](../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) to check out the details on the latest release. Information about all of our [past releases](../r-release-notes/release-notes-for-previous-releases.md) is also available online.

**Does Adobe have a Community/Forum where I can find answers and more information about Target?**

Check out the [Target Community Forum](../cmp-resources-and-contact-information.md#concept_9C203A8AED054DFFA9A504811DB6BA42), where we help customers, but more importantly, we like Adobe Target practitioners like yourself to help each other. After all, a community and forum's success relies on active participation by its members. Become a part of the community and contribute and seek answers to your questions.

**Which browsers does Target support?**

Please read our [Supported Browsers](../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100) matrix for more details. Notice that there are two aspects: the Target Standard/Premium Experience Cloud interface support and the end-user browser support on desktop/devices.

## Target JavaScript Libraries (at.js and mbox.js) {#section_C2AC78DFDAD84981A8C84DF20893E340}

**Which implementation JavaScript file should I use, at.js or mbox.js?**

at.js is our latest and greatest JavaScript library. mbox.js is our older version. See [Benefits of at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) to understand the differences between the two libraries. All new customers should use at.js.

All existing mbox.js customers should migrate to at.js. Learn more about the steps involved in [migrating from mbox.js to at.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA) before making the transition.

## Activities {#section_CB95B3BF9934445DB98E8A7E22FC2CF6}

**Can I perform a statistically rigorous activity to find a winning and losing experience while using a control experience?**

Use [A/B Testing](../c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977) (Manual Targeting option) along with the [Sample Size Calculator](../c-activities/t-test-ab/sample-size-determination.md#section_286EB6E671184239BB1552F0387DAEB5) for best results.

**How do I know when to stop an activity?**

Stopping activities prematurely can result in wrong conclusions. Be aware of [common pitfalls and ensure practices to avoid them](../c-activities/t-test-ab/common-ab-testing-pitfalls.md#section_DF01A97275E44CA5859D825E0DE2F49F). See also, [How long should you run an A/B Test](/help/c-activities/t-test-ab/sample-size-determination.md)?

**How can I perform an activity if the time-window is small?**

**Can I optimize for my goal as I test?**

Use our [reports to determine the winning experience](../c-activities/automated-traffic-allocation/determine-winner.md#concept_5741A89ED7224E1285A3BC34B2CCD0F9).

**Can I perform an activity with a level of personalization as an integral part of the activity?**

Check out [A/B Testing with the Auto-Target](../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3) option.

**How can I know which type of activity best fits my needs?**

Read the [Target Activities Guide](../c-activities/target-activities-guide.md#concept_D974B0918EB74B3B8CB07ACD32BF37A1) to understand the scenarios where each of the options provided by Adobe Target makes sense.

Be sure to also consider [Recommendations activities](../c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

**How can I discover which combinations of elements on my page contribute to its success and to what degree each element helps?**

Check out our [Full Factorial Multivariate (MVT) activities](../c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) with Element contribution analysis to see if it meets your needs.

Note that the traffic requirement increases with MVT activities.

**Can I run an activity spanning multiple pages where the page structure is different?**

**Can I apply offers at different locations (for example, the checkout funnel)?**

Try out the [Multipage Activity feature](../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) that lets you use multiple pages within experiences.

**How can I ensure that once a goal (Primary or Secondary) has been reached, a user never enters the activity again and instead sees a different activity going forward?**

This is easy to achieve by using the [Advanced Settings](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_E2FE441AFB324E498793ABB025ED9974) option available with every goal. You have options to decide what should happen after user reaches the goal and how you want the counting to be incremented.

So, in this case, you might choose "Increment Count, Release User & Bar from Reentry" along with "Default/Other Activity Content" to achieve the objective. Check out other options as well.

**I have created multiple goals in my activity. Can I create a chain of goals as a funnel for reporting and analysis purposes?**

**For example, I want to consider Goal B when the user has achieved Goal A so that I can track numbers for a particular funnel.**

Target has a robust way to achieve this with our Metrics Dependency feature. Simply [add dependencies on other success metrics](../c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B). You have options like "Reached" and "Not Reached," along with ability to combine metrics in multiple ways to create any combination you want.

**How can I be clear as to how to set up an activity to achieve my objectives?**

This is where [goals](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) come in.

You should start by knowing what you want to optimize on. Is it Revenue, Conversion, or Engagement? Each of these options is available in the goals section. And for each of these, you can further define which action a user would take on your site to qualify that the goal has been reached.

This is made possible by the Primary Goal setting in Step 3 of the three-part guided workflow. You can add additional goals as well, which can help you for better reporting

**Can I schedule an activity to start and end at a fixed time?**

Use the [Scheduling feature in the Goals and Settings](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) step of the three-part activity workflow by specifying the start and end dates.

Remember to activate the activity. Only live activities adhere to the specified schedule. After the end date is reached, the activity goes into the Ended state.

**Can I make a change to just the Targeting step and not go through the entire three-step guided workflow for editing?**

You can easily do that by [directly entering the desired step of your choice from the Activity Overview page](../c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0) and then exiting from that step by using the Save and Close option.

**Can I stay on a particular step, keep modifying the activity (offer text or custom code, for example), and then perform QA in another tab?**

This is also possible. Simply [use the Save option available to make incremental changes without leaving the step](../c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0).

**How can I preview and QA an activity I just created?**

Use our [powerful QA Mode feature](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) to perform QA. You can share links with your QA team and also test the activity end-to-end, including reporting, to be fully sure that after the activity is live, it works as intended and as tested.

**How can I use Target's decisioning power to receive an experience/offer that can be used in Single Page Applications (SPAs) or server-side integrations?**

Use the power of [form-based activities](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) with [JSON offers](../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D) to meet your goal.

**I have set up two activities. How do I know which one a visitor will end up seeing?**

**Can I set the priority order of a few activities?**

Use the Priority setting available on Step 3 of the Target three-part guided workflow (Goals and Settings Page) to [define the priority of the activities](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC).

There are two options:

* Default, with three levels (Low / Medium / High)
* Custom, with a range from 0 to 999. For Custom, enable the Fine-Grained Priorities feature ( Setup > Preferences).

## Audiences {#section_FA6314777ABC46D8B198D6F388051460}

**Can I create an audience segment in an activity that is specific to the activity? I do not feel that such an audience should be created in the Audience Library because there is no re-use factor.**

Start using our [Activity-Only Audience feature](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) to define audiences that are local to the activity.

**How can I target users based on their locations?**

Try out [Geo audiences](../c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670). Read about the accuracy levels of this feature.

**Can I target users based on some of the attributes on the page in the session?**

The best way would be to use mboxes and [custom audiences](../c-target/c-audiences/c-target-rules/custom-parameters.md#concept_C4C6E00D7C5A4BE9B72D471DB2E3027B) to deliver the right experience.

**Can I deliver experiences based on visitor attributes across multiple visits?**

**Can I randomly split the traffic in two buckets?**

Try the [Profile Scripts feature](../c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2). It is a powerful way to personalize experiences, although it requires you to write code.

**Can I start an activity with a fewer number of visitors?**

Use the percentage allocation controls available from [Step 2 of the Target three-part guided workflow (Targeting page)](../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) to decide how you want to go about setting up the activity.

**I also have Adobe Analytics and want to leverage it with Target. What key capabilities do I get by integrating the two solutions?**

Check out following aspects of the product:

* [Analytics for Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)
* [Customer Attributes](../c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)
* [Audiences](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

## Experiences {#section_5959536B8D6A4BEA8FAA1273338F3451}

**Can I run an activity on multiple pages where the page structure is common?**

Check out [Template Rules](../c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) to include many similar structured pages to the activity while still creating the experience on the single URL provided.

**I am tired of the "allow your browser to load scripts" message when I attempt to load my page in the Visual Experience Composer (VEC). How can I avoid this?**

This is because your site has mixed content—it’s a site that fetches both HTTP and HTTPS resources. Request that your IT team move to HTTPS completely.

Until this happens, follow the instructions in [Enabling Mixed Content in Your Browser](../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md#concept_46D022D50280468C9EF6D5DF6EFC911C) to allow your browser to load mixed content. This is a security feature of most modern browsers.

**Can I try the Visual Experience Composer (VEC) on my site even though the Target at.js library has yet not been deployed?**

Try loading the page with the [Enhanced Experience Composer](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D).

**Why is my site not loading within the Visual Experience Composer (VEC)?**

Try out the [troubleshooting information](../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4) outlined in our help page. Reach out to [Adobe Support](../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) if none of these approaches work.

We also have [form-based approach](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) which can unblock you.

Also read when and why the [Enhanced Experience Composer](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) can be useful. You might have to reach out to your IT department to [whitelist Adobe's proxy servers](../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6) as well.

**I have a responsive site. While creating an activity, how can I be sure that I am considering key devices?**

Try out the [Mobile Viewports](../c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5) feature. Note that it works only when the Enhanced Experience Composer is enabled.

**I have multiple domains. One of the domains needs the Enhanced Experience Composer enabled, while others need it to be disabled. How can I do this?**

You can always use [Enhanced Experience Composer option at the activity level](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) to override the default setting ( Setup > Preferences).

**Why don't I see an option to swap images?**

Reach out to Adobe to [ensure that your account is set up for Scene7](../administrating-target/scene7-settings.md#task_37AD0768EFBA4E588955FE3D5DD670A5). Once provisioned, you will be able to swap an image with another image with ease.

**I want to test between two different experiences, for example Flat discount versus Percentage discount, but I want to target the experiences properly (show different locale text or different currency for people coming from different countries). How can I do this?**

You can easily achieve this with our [Multiple Experience Versions feature](../c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md#task_0138112E283A4A5B9F8AB9AAF2FBC2FF). Note the nuances around delivery in such tests

**How can I see what modifications I made in Visual Experience Composer (VEC)?**

We always show your changes in the [Code Editor](../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5). The Modifications tab shows the CSS Selector or mbox you applied to your offer.

Note that the CSS Selector is a Sizzle Selector. You can use this section to make minor modifications or delete certain offers quickly.

**I want to deliver JavaScript as part of the experiment/activity to either make modifications on the fly for some dynamic elements or simply to send a call to a 3rd-party solution. How can I do this?**

One of the ways is to use the [Custom Code Editor](../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5). Go ahead and put your JavaScript in the section and it will get delivered. You have the option to deliver it in the head or at the top of the body, depending on your needs.

**Why can't I go past the log-in page within the Visual Experience Composer (VEC) or to a page buried deep within for which I don't have a specific URL?**

Use the Compose and Browse features to navigate to the page of choice and start creating your experience.

![](assets/vec2.png)

**How can I go to the experience of my choice from Step 2 of the Target three-part guided workflow (Targeting page)?**

Click the thumbnail in front of the experience name on Step 2 and you will land on the experience of your choice.

![](assets/thumbnail_experiences.png)

**I am a former Target Classic user. Can I leverage my mboxes for certain use cases?**

Use [form-based approach](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) to create activities.

**Can I ensure that same experience is delivered consistently across all devices a user might have?**

Check out our [Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) that allows you to deterministically and probabilistically link multiple devices of a user through the power of a Co-op .

If you are in the Co-op, a simple flag on the Goals and Settings page enables the feature. Reporting also changes to now reflect People instead of Visitors. Talk to your Adobe contact for more on this feature as this is not available in all regions.

**Why am I not seeing the desired offer/experience and am instead seeing some other activity?**

Use our [debugger](../c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA) and check for [activity collisions](../c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E).

## Offers {#section_A547B1EAD0B34FD38D3B87AAF62E3963}

**I do not want to try minor changes, but instead want to test a brand new, completely different page.**

**I want to direct users to a landing page, for example, a new launch.**

**How can I do this?**

We have [Redirect URL feature](../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) that lets you redirect users to the page of choice (with or without the current query parameters).

**Why is content delivery not happening in my QA process?**

It's possible that your site might have dynamic IDs, duplicate IDs, or dynamic classes on elements. You might have to evaluate the site preference options at the account level (or at activity level if the issue is specific to a domain or a page). See [CSS Selectors](../administrating-target/r-target-account-preferences/target-account-preferences.md#section_8155EDBF449E4198863235F94D1EA872).

**Why am I not seeing the desired offer/experience and am instead seeing some other activity?**

Use our [debugger](../c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA) and check for [activity collisions](../c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E).

**Can I use Target's decisioning power to receive an experience/offer that can be used in Single Page Applications (SPAs) or server-side integrations?**

Use the power of [form-based activities](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) with [JSON offers](../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D) to meet your goal.

## Reports (Including Analytics for Target—A4T) {#section_8AECC69BEEB7422E894E7EC44A50BA0A}

**I also have Adobe Analytics and want to leverage it with Target. What key capabilities do I get by integrating the two solutions?**

Check out following aspects of the product:

*   [Analytics for Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)
    
*   [Customer Attributes](../c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)
    
*   [Audiences](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)
    

**Can I slice and dice the reporting on multiple user segments?**

This is where the [Audiences for Reporting feature](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_13119392051044FBA6387D9B3B1C43CF) available on the Goals and Settings page in Step 3 of the three-part guided activity workflow comes in.

You have the option to add 50 such segments and also the application point (Activity Entry or a specific metric) to have a powerful way to slice and dice.

Note that Target collects the data in this regard from the time you add these audiences, so if you miss adding segments before running the test, you are out of luck.

**I cannot define audiences prior to running the activity. I find this aspect of reporting audiences in Target activities restrictive.**

**What can I do to make this process easier?**

This is where [Analytics for Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) is handy. If you have Adobe Analytics, simply choose the source as Analytics, which eliminates this restriction. Now you can perform analysis on any audience at any point and you don't need to define the reporting audiences up front.

**Can I perform offline reporting calculations?**

Use the [Export Reports to CSV and Download Order Details to CSV options](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) on the Reports page to download the desired reporting data.

**Can I change the control experience for evaluating reports or change the counting methodology from Visitors to Visits?**

Make these changes using the [Settings gear on the reports page](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA). Read more about these settings to understand how the calculations vary.

**How should I interpret reports?**

We have tried to make reports as intuitive as possible with features like [confidence Interval bars, lift bounds, significance/confidence and multiple metric selections, table and graph views, running averages, and more](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) to allow for powerful, yet easy, report analysis. Obviously, you can look into Analytics if you are using [Analytics for Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) activities for further analysis on audiences.

## Response Tokens {#section_C2A7118B4B62482A9D630C2212112A3D}

**Can I perform an integration with a 3rd-party system, such as Google Analytics or ClickTale, to pass the activity information delivered to an end-user for analysis?**

We have a solution for that too with our [Response Tokens feature](../administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4).

## Troubleshooting {#section_6B8B4DC62AE34066A8C55915E9EC6C19}

**How can I know the availability status of Adobe Target?**

Use the [Adobe System Status page](../r-release-notes/system-status-updates.md#concept_5CBDF506BEFA40E483CC7DE0DA915EAD) to view the status of Adobe products and Experience Cloud solutions, including Target. This page helps you determine whether problems you might encounter are due to system updates or routine maintenance.

**Do you have a troubleshooting guide?**

We are sorry to hear that you are having problems. Check out [Troubleshooting Target](../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) for links to many troubleshooting topics.

## Target Mobile Apps {#section_07BA89F2C38747158ECD5B153274AEAF}

**We have a mobile SKU. Can I create mobile activities?**

For optimization and personalization on mobile, you need to use [form-based activities](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) along with the [Adobe SDK](../c-target-mobile-app/mobile-enable-target-in-sdk.md#task_FCA99AD0785A44E995468776AE76FE91). Check out more details about [Target for mobile apps](../c-target-mobile-app/target-mobile-app.md#concept_80126FF457724DE788CE37264A047559).

## Target APIs {#section_714E85EFF6E3400389EF2E40D538E1DA}

**Where can I learn more about Target APIs?**

We have exhaustive documentation around APIs. See [Delivery APIs, NodeJS SDK, and Recommendations APIs documentation](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).