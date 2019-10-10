---
description: Frequently Asked Questions about Adobe Target for mobile apps.
keywords: mobile app;frequently asked questions;faq;target mobile app
seo-description: Frequently Asked Questions about Adobe Target for mobile apps.
seo-title: Frequently asked questions about Adobe Target for mobile apps
title: Adobe Target for mobile apps FAQ
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
---

# Target for mobile apps FAQ

List of frequently asked questions about [!DNL Target] for mobile apps.

## Should I use [!DNL Adobe Experience Platform Launch] to deploy the SDK, or can I deploy the SDK without using [!DNL Launch]?

The SDK is available on the [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). If you don't use [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), you must manage your own settings file and manage it in your app.

## Can the Visual Experience Composer (VEC) for mobile apps be used with React-Native support for the Adobe Experience Platform SDK v5?

The [VEC for Native Mobile Apps](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md) currently doesn't support the React native app. You must use the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).  

## Does the Mobile SDK integration allow for roll-out of new mobile functionality? Can I turn the feature flag on and off without new code deployments?  

Yes, you can use our mobile SDK to roll out features gradually.  

## For more complex logic, should I develop directly in the app instead of using the Mobile VEC? If so, which development language should I use?

Currently, the VEC supports common use cases such as changing the image, text, color, etc. For more advanced use cases, such as personalizing the app layout, you must insert the [!DNL Target] request/location (mbox) in the code and use the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) to design the experiences and allocate traffic. Our mobile SDK supports Java, Objective C, and Swift. It depends on your team's preference and resources to choose the language.  

## Which SDKs are available today?

The Adobe Experience Platform Mobile SDKs currently support iOS, Android, and React. For more information, see the [Adobe Experience Cloud Platform Mobile SDKs guide](https://aep-sdks.gitbook.io/docs/).

## What is the frequency of the location-based feature, in terms of verification about the latitude and longitude?

See the [Adobe Places documentation](https://placesdocs.com/places-services-by-adobe-documentation/) for more information.

## Which native classes do mobile "Views" support? Do they support any NSObject derived class (or any Android Object) or just NSViewController and Activities?

For more information, visit the Android documentation for the [manual way of declaring views](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md#views). 

## Do I need at.js for the Adobe Experience Platform Mobile SDKs to work?

No, you don’t need at.js to use the mobile SDKs. at.js is the [!DNL Target] JavaScript library for websites. The Adobe Experience Platform Mobile SDKs are for mobile apps.

## Is Target Mobile a functionality of Adobe Target Premium Product SKU only?

For Adobe Target Standard customers, you can use our Mobile SDKs for A/B Test and Experience Targeting (XT) activities only. If you want to use Recommendations or AI-powered features in the mobile app, you need an [Adobe Target Premium](/help/c-intro/intro.md#premium) license.

## Can I leverage audiences from Adobe Audience Manager (AAM) in the VEC for Mobile Apps? 

Yes, Adobe Experience Platform Mobile SDKs are built for [Audience Manager](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html), [Analytics](https://docs.adobe.com/content/help/en/analytics/landing/home.html), [Campaign](https://docs.adobe.com/content/help/en/campaign-standard/using/campaign-standard-home.html), and Target. Your audiences in Audience Manager are shared with [!DNL Target].

## Is there a mobile app integration between Adobe Experience Manager (AEM) and Target mobile activities?

It is on our roadmap but there is no timeline yet. Currently, you can share JSON [Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) from AEM to Target and there might be potential to then use them in a mobile app activity.  

## Can I add more images using the VEC or only change existing images?

You can currently change existing images only.
