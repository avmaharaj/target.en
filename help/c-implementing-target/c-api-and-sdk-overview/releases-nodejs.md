---
description: Release notes related to Adobe Target's Node.js SDK
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
seo-description: Release notes related to Adobe Target's server-side APIs.
seo-title: Release notes related to Adobe Target's Node.js SDK.
solution: Target
title: Release notes - Target Node.js SDK
topic: Standard
---

# Release notes - Target Node.js SDK

Release notes related to [Adobe Target's Node.js SDK](https://github.com/adobe/target-nodejs-sdk).

## Version 1.0.0 (October 9, 2019)

The following sections provide more information about version 1.0.0 of the Target Node.js SDK:

### Added

* Target View Delivery v1 API support, including Page Load and View prefetch.
* Full support for delivering all types of offers authored in the Visual Experience Composer (VEC).
* Support for prefetching and notifications for performance optimization by caching prefetched content.
* Support for optimizing performance in hybrid [!DNL Target] integrations via `serverState` when [!DNL Target] is deployed both on the server-side and on the client-side.

  We are introducing a setting called `serverState` that contains experiences retrieved via server-side, so that at.js v2.2+ will not make an additional server call to retrieve the experiences. This approach optimizes page load performance.

* Open sourced on GitHub as [Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk).
* New [sendNotifications() API method](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) for sending displayed/clicked notifications to [!DNL Target] for content prefetched via [getOffers()](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers).
* Simplified View Delivery API request building, with internal field auto-completion with defaults (for example, `request.id`, `request.context`, etc.).
* Validation of SDK API method arguments.
* Updated README, samples, and unit tests.
* New CI flow set up using GitHub Actions.
* Added CoC, Contribution guidelines, PR, and issue templates

### Changed

* Project renamed to `target-nodejs-sdk`.
* Major refactoring, replacing Target BatchMbox v2 API with Target View Delivery v1 API.
* [create() API method](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) arguments have been modified, removing redundant nesting (see old method declaration [here](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [getOffers() API method](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) arguments have been modified (see old method declaration [here](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* The `getTargetCookieName()` API method has been replaced with `TargetCookieName` accessor. See [TargetClient utility accessors](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors).
* The `getTargetLocationHintCookieName()` API method has been replaced with `TargetLocationHintCookieName` accessor.  See [TargetClient utility accessors](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors).

### Removed

* Target BatchMbox v2 API support.
* The [getOffer() API method](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) has been removed, use the [getOffers() API method](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) instead.

