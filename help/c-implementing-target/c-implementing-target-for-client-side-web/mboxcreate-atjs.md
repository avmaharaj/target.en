---
description: Information about the mboxCreate(mbox,params) function for at.js. 
keywords: mboxCreate;mboxcreate;mbox create;at.js;functions;function
seo-description: Information about the mboxCreate(mbox,params) function for the Adobe Target at.js JavaScript library.
seo-title: Information about the mboxCreate(mbox,params) function for the Adobe Target at.js JavaScript library.
solution: Target
subtopic: Getting Started
title: mboxCreate(mbox,params) - at.js 2.x
topic: Standard
---

# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

Executes a request and applies the offer to the closest DIV with mboxDefault class name.

>[!NOTE]
>
>This function is available for at.js versions 1.*x* only. This function was deprecated with the release of at.js 2.x. This function returns default content if used with at.js 2.x.

This function is built into [!DNL at.js] mostly to ease the transition from [!DNL mbox.js] to [!DNL at.js]. A newer alternative to `mboxCreate()` is `adobe.target.getOffer()`/ `adobe.target.applyOffer()` or the Angular directive.

## Example

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Notes

`mboxCreate()` now uses the "json" endpoint instead of the "standard" endpoint and fires asynchronously. Because of this:

* [Debugging](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) is a little different. 
* Avoid offer code requiring synchronous, blocking calls.

  For example, offers that set JavaScript variables that are used by site code or other mboxes that come later on the page.
  
* Be sure to have a `<div class="mboxDefault"></div>`before invoking `mboxCreate()`, because [!DNL at.js] will not add one for you. 

* Empty, top-of-page `mboxCreate()` functions are not recommended as a global mbox.

  The auto-created global mbox in [!DNL at.js] is a better option because it fires from the `<head>` and can return content earlier.