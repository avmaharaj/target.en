---
description: Release notes related to Adobe Target's server-side APIs and SDKs
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
seo-description: Release notes related to Adobe Target's server-side APIs.
seo-title: Release notes related to Adobe Target's server-side APIs.
solution: Target
title: Release notes - Target server-side APIs
topic: Standard
---

# Release notes - Target server-side APIs

Release notes related to the [Adobe Target server-side APIs](https://developers.adobetarget.com/api/delivery-api/).

## V1/delivery (October 9, 2019)

An entirely new delivery API endpoint has been released.

* New [documentation](https://developers.adobetarget.com/api/delivery-api/) is available.
* One endpoint to retrieve experiences for one or more mboxes.
* Retrieve VEC-created activities via the API.
  
  The response that contains VEC-created activities has selectors that can be used to pre-hide only portions of your page that need to be personalized. This helps to optimize your page's [First Contentful Paint metric](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html), which is an important KPI for your business to achieve a high score in the [Google PageRank](https://en.wikipedia.org/wiki/PageRank) system.

* Support for an entirely new object called Views that is used for [Single Page Applications](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) (SPAs) and [mobile applications](/help/c-target-mobile-app/target-mobile-app.md).
* Support for prefetching of views and mboxes to optimize for performance via caching.
* Support for sending notifications for prefetched views and mboxes.

>[!IMPORTANT]
>
>The legacy [/v1/mbox and /v2/batchmbox API documentation](https://developers.adobetarget.com/api/legacy-api/index.html) can still be accessed. However, new features will be developed in the new delivery API and will not be back-ported to the legacy APIs.
