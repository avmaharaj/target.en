---
description: Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.
keywords: implement;implementing;implementation;adobe launch;launch;race;redirect;experience platform launch
seo-description: Adobe Experience Platform Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.
seo-title: Implement Target using Adobe Launch
title: Implement Target using Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
---

# Implement Target using Adobe Launch{#implement-target-using-adobe-launch}

Adobe Experience Platform Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.

## Implement Target using Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch is the next-generation tag management platform from Adobe and is the preferred method to implement Adobe Target. Launch gives customers a simple way to deploy and manage all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences. 

The following table lists the various sources where you can get more information about Launch:

| Resource | Details |
|--- |--- |
|[Implementing Target using the Adobe Target Extension Tutorial](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html)|This tutorial provides step-by-step instructions to implement Adobe Target in a website with Launch. Topics include adding the at.js JavaScript library, firing the global mbox, adding parameters, and integrating with other solutions. This article is part of a larger tutorial that shows you how to implement Adobe Launch, as well as the other Adobe Experience Cloud solutions.|
|[Adobe Launch Documentation](https://docs.adobe.com/content/help/en/launch/using/intro/get-started/quick-start.html)|Information about deploying and managing all of the analytics, marketing, and advertising tags necessary to power relevant customer experiences.|
|[Adobe Target Extension Documentation](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/target-extension/overview.html)|Information about implementing Target using Launch.|

## Advantages of Implementing at.js Using the Target Launch Extension {#section_48B3F938B6F8491DAF798E0DB54EF304}

The following advantages apply only if you use Adobe Launch to implement at.js. For this reason we strongly suggest that you use Adobe Launch rather than DTM or a manual implementation of at.js.

* **Solves Analytics and Target Race Condition:** Because the Analytics call could be fired before the Target call, the Target call is not stitched to the Analytics call. This can lead to incorrect data. Starting with 0.6.0, the Target Launch extension ensures that the Analytics beacon call waits until the Target call completes, successfully or not. This should solve the data inconsistency customers might have experienced. 
* **Prevents Incorrect Redirect Offer Handling:** If you have Target and Analytics on the page, and there is a redirect offer executed by Target, you might experience a situation in which the Analytics tracker fires a request when it shouldn’t (because the user is being redirected to a different URL). If you implement Target and Analytics via Launch, you’ll not experience this issue. Using Launch, Target instructs Analytics to abort the Analytics beacon request.
