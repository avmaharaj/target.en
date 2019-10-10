---
description: To use Target Standard or Target Premium, add one line of code to call mbox.js.
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
seo-description: To use Target Standard or Target Premium, add one line of code to call mbox.js.
seo-title: mbox.js implementation
solution: Target
subtopic: Getting Started
title: mbox.js implementation
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
---

# mbox.js implementation{#mbox-js-implementation}

To use Target Standard or Target Premium, add one line of code to call mbox.js.

 You can use either of two library references: [!DNL mbox.js] or [!DNL at.js]. [Benefits of at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) explains the differences between the two libraries.

>[!NOTE]
>
>The mbox.js library is still supported, but there will be no feature updates. All customers should migrate to at.js. For more information, see [Migrate to at.js from mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

The single reference to [!DNL mbox.js] on each page provides the libraries needed for all of your activities. [!DNL mbox.js] calls [!DNL Target] from every page that references the [!DNL mbox.js] file. This enables [!DNL Target] to do the following:

* Deliver Target activities 
* Track clicks 
* Track most success metrics

>[!TIP]
>
>To simplify implementation, you could reference [!DNL mbox.js] in your global header.

You do not need to maintain different activity-specific versions of the file. 

1. Reference [!DNL mbox.js] in the `<head>` section of each page on your site.

   `<script src="/ *`directory`*/ *`scripts`*/mbox.js"></script>`

   Where ` *`directory`*/ *`scripts`*` is the directory where you saved your [!DNL mbox.js] file after downloading it. 
If you already have mboxes on your page from a legacy implementation, these mboxes can still be used in the new interface. The updated [!DNL mbox.js] file is still required, but these mboxes can be selected for activities and edited using the [!UICONTROL Visual Experience Composer].