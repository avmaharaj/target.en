---
description: Information about additional resources to help you learn about Target features and how to contact Adobe should you need help with Target.
keywords: contact;legal;technical support;tech support;support;service;capability;billing;feedback
seo-description: Information about additional resources to help you learn about Target features and how to contact Adobe should you need help with Target.
seo-title: Resources and Contact Information
solution: Target
title: Resources and Contact Information
topic: Standard
uuid: 3a7fb747-f7b9-4956-9a0e-4c5679110783
---

# Resources and Contact Information{#resources-and-contact-information}

Information about additional resources to help you learn about Target features and how to contact Adobe should you need help with Target.

## Target Community Forum {#concept_9C203A8AED054DFFA9A504811DB6BA42}

The Target Community is your one-stop shop for everything Adobe Target. 

The Community lets you:

* Learn more about what Target has to offer 
* Connect with your peers and Adobe Experts 
* Vote or submit an idea of your own for a future Target Release

Visit the [Target Community Forum](https://forums.adobe.com/community/experience-cloud/marketing-cloud/target) to get started. 

## Target Basics Webinar Series {#concept_11902FAC95C64479AABE020557A7EEE4}

Registration information and links to previous sessions of the Target Basics Webinar Series, a Customer Success Webinar Series brought to you by the Community.

[Click here to watch past sessions or to learn more about upcoming sessions and registration information](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html).


## Adobe Customer Care Office Hours {#concept_58EA30379D3B48C4848BA2A8C464A5B7}

"Office Hours" is an initiative led by the Adobe Customer Care team. These sessions are designed to inform as well as help participants troubleshoot problems, and provide tips and tricks to be successful with the Adobe Experience Cloud solutions, including Target.

To sign up for upcoming sessions and to watch recorded sessions, see [Adobe Customer Care Office Hours](https://helpx.adobe.com/customer-care-office-hours.html).

Current recorded Target sessions include:

| Topic / Runtime / Recording Date | What you will learn |
|--- |--- |
|[Visual Experience Composer (VEC)](https://helpx.adobe.com/customer-care-office-hours/target/visual-experience-composer.html)<br>50:23<br>December 2017|You will learn:<ul><li>How the VEC works</li><li>How to avoid common issues with the VEC</li><li>Work-around practices you can use with the VEC</li></ul>For more information in this guide, see [Experiences](/help/c-experiences/experiences.md).|
|[Adobe Target: Analytics/Target Integration (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)<br> 40:33<br>January 2018|You will learn:<ul><li>How to set up and validate that the integration is working </li><li>How the integration works</li><li>Learn about the ideal reports to use in Analytics</li><li>Answers to common questions about A4T</li></ul>For more information in this guide, see [Adobe Analytics as the Reporting Source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).|
|[at.js: Advantages and Implementation Best Practices](https://helpx.adobe.com/customer-care-office-hours/target/at-js-advantages-implementation-best-practices.html)<br>26:43<br>April 2018|You will learn: <ul><li>How the at.js library works</li><li>The advantages of at.js over mbox.js</li><li>How at.js manages flicker</li><li>Error handling in at.js</li><li>Debugging methodologies</li><li>Known issues and future roadmap</li></ul>For more information in this guide, see [at.js Implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md).|

>[!NOTE]
>
>The publish date lets you know when the session was recorded. Some features might have changed and additional functionality added since the publish date.

In addition it sessions about Target, there are other sessions for other Adobe solutions, including Analytics, Campaign, Adobe Experience Manager (AEM), Primetime, Adobe Core Services, Audience Manager, and more. 

## Contact Adobe Client Care {#reference_ACA3391A00EF467B87930A450050077C}

Client Care is prepared to help you solve any issues that might arise. This page contains the information you need when contacting Client Care to expedite a resolution.

### Basic Information {#section_CC8B206F58D6495C9372D5C0D4055CF6}

If you encounter issues or have questions when using Target, you have a number of options

For questions, you can ask the Adobe Target experts in the [Experience Cloud community](https://forums.adobe.com/community/experience-cloud/marketing-cloud/target) or ask us on Twitter at [@AdobeExpCare](https://twitter.com/adobeexpcare).

For technical issues or to log a bug you can contact Customer Care. To contact Customer Care by telephone, call 1-800-497-0335. Toll free numbers outside the United States can be found on the [Adobe Digital Marketing Customer Care Regional Phone Numbers](https://helpx.adobe.com/contact/dma-external/DMACustomeCareRegionalPhoneNumbers.html) page. When asked to select an option for your product, press 3 to contact the Target team.

E-mail Customer Care at [!DNL tt-support@adobe.com].

For the quickest triage of your issue, please have the following basic information ready when you are contacting us:

|Information|Details|
| --- | --- |
|Summary|Brief summary of the overall issue|
|Account information|Company Name<br>Admin Number<br>Campaign Name<br>Type of Campaign<br>Report Suite/Report Suite ID (if regarding a Target to SiteCatalyst integration)|
|Steps to reproduce|Include as much detail as possible, including any URLs needed to duplicate as well as the expected result.<br>Include enough detail that somebody unfamiliar with Target should be able to follow the directions and reproduce the problem.|
|Priority|P1 (most important) to P4 (least important).|
|Business impact|What is the impact to your business? For example, is this issue causing revenue loss or rendering the product unusable, and is there a viable workaround?|
|Expectations|What do you expect to happen?|

Also prepare information related to the specific issue. For example, one of the most common problems received by Client Care is that mboxes load too slowly. For this issue, helpful data includes:

* A Firebug trace showing the repeatable slowness to a URL or host.

  A gomez report with one or two outlying requests is not enough data to analyze or troubleshoot the issue. 
* A screenshot of a traceroute from the machine running the firebug TO 70.42.13.100.

  This is very important. The EDGE networks are worldwide so it is very difficult to determine where the client is being sent. For example, if you can reproduce the issue from your desktop in your office, say "I can reproduce this from my desktop and I am homed to EDGE 20." 
* Your client code and the mbox name (if you have it). 
* The number of mboxes embedded in the page.

  Is it a single mbox of many on the page that is slow? 
* How repeatable is the slowness with the given mbox on the given page?

  Providing a Firebug trace shows Client Care a one-time case scenario. If you can provide statistical data, such as "the lowest I've seen is 300ms, highest I've seen is 1.1 seconds and I've tested 50 times," it will help to facilitate a solution. 
* Information regarding anything unusual about your campaigns.

  Is there a high number of segments? (For example, do you update segments 3 to 4 times per hour in the admin interface?) This information helps Client Care understand the interaction between the admin interfaces and the edges for this campaign. Frequent updates to the campaign mean frequent reloads from the central server, which can force more remote calls or cache reloads. 
* Any other data you think might be helpful.

### In Case of an Outage {#section_2CB3BC53E4C641F38D50949E2E7A2886}

If you suspect there is an outage, first check the [Experience Cloud System Status page](https://status.adobe.com) ( [!DNL https://status.adobe.com]) This has a record of all outages, incidents and maintenance for Experience Cloud Solutions, including Target, and includes latest updates from our Tech Ops team. If you still require assistance, please ensure you know the following in addition to the information listed above when you contact Customer Care:

* Time outage started 
* Explanation of what is occurring 
* Scope 
* Expectation of resolution (ETA, severity, and so on)

## Contact and Legal Information {#concept_34A1CA16F2244D42930BB77846A5ABBB}

Information to help you contact Adobe and to understand the legal issues concerning your use of this product and documentation.

### Help & Technical Support {#section_354AC2658BA84A2A96E64C5B2C43B73B}

The Adobe Experience Cloud Customer Care team is here to assist you and provides a number of mechanisms by which they can be engaged:

* [Check the Experience Cloud help pages for advice, tips, and FAQs](https://helpx.adobe.com/marketing-cloud.html) 
* [Ask us a quick question on Twitter @AdobeExpCare](https://twitter.com/adobeexpcare) 
* [Log an incident in our customer portal](https://customers.omniture.com/login.php) 
* [Contact the Customer Care team directly](https://helpx.adobe.com/marketing-cloud/contact-support.html) 
* [Check availability and status of Experience Cloud Solutions](https://status.adobe.com/)

To receive advance notifications about upcoming product enhancements, sign up for the Adobe Priority Product Update:

[Adobe Priority Product Update](https://www.adobe.com/subscription/priority-product-update.html)

### Service, Capability & Billing {#section_FA4F5274FDFE4DF7BB079E575877DFC2}

Dependent on your solution configuration, some options described in this documentation might not be available to you. As each account is unique, please refer to your contract for pricing, due dates, terms, and conditions. If you would like to add to or otherwise change your service level, or if you have questions regarding your current service, please contact your Account Manager.

### Feedback {#section_8154D6D712054220A90D85FA8E92933E}

We welcome any suggestions or feedback regarding this solution. Enhancement ideas and suggestions for the Analytics suite [can be added to our Customer Idea Exchange](https://my.omniture.com/login/?r=%2Fp%2Fsuite%2Fcurrent%2Findex.html%3Fa%3DIdeasExchange.Redirect%26redirectreason%3Dnotregistered%26referer%3Dhttp%253A%252F%252Fideas.omniture.com%252Ft5%252FAdobe-Idea-Exchange-for-Omniture%252Fidb-p%252FIdeaExchange3).

### Legal {#section_A6E1844D4AC2485CADBF6D05116E3D59}

* © 2019 Adobe Systems Incorporated. All Rights Reserved.
* Published by Adobe Systems Incorporated.

[Terms of Use](https://www.adobe.com/go/marketingcloud_terms_of_use) | [Privacy Center](https://www.adobe.com/privacy.html)

Adobe and the Adobe logo are either registered trademarks or trademarks of Adobe Systems Incorporated in the United States and/or other countries. A trademark symbol (®, ™, etc.) denotes an Adobe trademark.

All third-party trademarks are the property of their respective owners. Updated Information/Additional Third Party Code Information available at [https://www.adobe.com/go/thirdparty](https://www.adobe.com/products/eula/third_party/). 
