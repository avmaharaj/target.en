---
description: Information about Adobe Target server-side delivery APIs, Node.js SDK, and Target Recommendations APIs.
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
seo-description: Information about Adobe Target server-side delivery APIs, Node.js SDK, and Target Recommendations APIs.
seo-title: Information about Adobe Target server-side delivery APIs, Node.js SDK, and Target Recommendations APIs.
solution: Target
title: Server Side implement Target
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
---

# Server Side: implement Target{#server-side-implement-target}

Information about [!DNL Adobe Target] server-side delivery APIs, Node.js SDK, and [!DNL Target Recommendations] APIs.

The following process occurs in a server-side implementation of [!DNL Target]:

1. A client device makes a request for an experience through your server.
1. Your server sends that request to [!DNL Target].
1. [!DNL Target] sends the response back to your server.
1. Your server makes the decision on which experience to deliver to the client device for it to render.

The experience does not need to display in a browser. The experience can display in an email or kiosk, via a voice assistant, or through some other non-visual experience or non-browser-based device. Because your server sits between the client and [!DNL Target], this type of implementation is also ideal if you need greater control and security or have complex backend processes that you want to run on your server.

The following sections provide more information about the various APIs and the NodeJS SDK:

## Server Sice Delivery APIs

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Throught the [!DNL Target] Delivery API, you can:

* Deliver experiences across web, including SPAs, and mobile channels as well as non-browser based IoT devices, such as connected TVs, kiosks, or in-store digital screens.
* Deliver experiences from any server-side platform or application that can make HTTP/s calls.
* Deliver consistent and personalized experiences to a visitor regardless of which channel or devices the visitor used to engage with your business.
* Cache experiences for a visitor within a session on your server so that multiple API calls can be avoided, which achieves better performance.
* Seamlessly integrate with [!DNL Adobe Experience Cloud] products, such as [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM), and the [!DNL Experience Cloud ID Service] from the server side.

## Node.js SDK

Link: [Node.js SDK](https://github.com/adobe/target-nodejs-sdk)

The Node.js SDK is a sophisticated software development kit that removes the complexities of managing cookies, sessions, and integrating with [!DNL Experience Cloud] products, such as [!DNL Analytics], [!DNL Experience Cloud Visitor ID Service], and [!DNL Audience Manager]. Behind the scenes, the Node.js SDK uses the `/rest/v1/delivery` API. Here are some notable features that are supported in the Node.js SDK:

* **Support for prefetch and notifications that allow you to optimize for performance via caching:** You can use the Node.js SDK to retrieve experiences and cache them locally on your Node.js server with the purpose of minimizing server calls to [!DNL Target] and optimizing your application performance.
* **Ability to retrieve VEC-created activities:** Retrieve VEC-created activities on the server-side. The response that contains VEC-created activities has selectors that can be used to pre-hide only portions of your page that need to be personalized. This helps optimize your page's [First Contentful Paint metric](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html), which is an important KPI for your business to achieve a high score in the [Google PageRank](https://en.wikipedia.org/wiki/PageRank) system.

## Target Recommendations APIs

Link: [Target Recommendations APIs](https://developers.adobetarget.com/api/recommendations)

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
