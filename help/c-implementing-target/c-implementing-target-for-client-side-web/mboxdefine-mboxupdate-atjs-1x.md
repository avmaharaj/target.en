---
description: Information about the mboxDefine() and mboxUpdate() functions for at.js. 
keywords: mboxDefine;mboxdefine;mbox define;mboxUpdate;mboxupdate;mbox update;at.js;functions;function
seo-description: Information about the mboxDefine() and mboxUpdate() functions for the Adobe Target at.js JavaScript library.
seo-title: Information about the mboxDefine() and mboxUpdate() functions for the Adobe Target at.js JavaScript library.
solution: Target
subtopic: Getting Started
title: mboxDefine() and mboxUpdate() - at.js 1.x
topic: Standard
---

# mboxDefine() and mboxUpdate() - at.js 1.x

Define and update an mbox in Adobe Target.

>[!NOTE]
>
>These functions are available for at.js versions 1.*x* only. These functions were deprecated with the release of at.js 2.x. These functions return default content if used with at.js 2.x.

`mboxDefine()` and `mboxCreate()` are tied to HTML DIV elements where the offer should be displayed. These HTML DIV elements should have the `mboxDefault` class. If the HTML elements won't have this class attached, you could see some noticeable flicker.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Creates an internal mapping between a nodeId and an mbox name, but does not execute the request. Used in conjunction with `mboxUpdate()`. Built into [!DNL at.js]mostly to ease the transition from [!DNL mbox.js]to [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Executes the request and applies the offer to the element identified by the `nodeId` in the `mboxDefine()`. Can also be used to update an mbox initiated by `mboxCreate`. Built into [!DNL at.js] mostly to ease the transition from [!DNL mbox.js] to [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` could be replaced by [adobe.target.getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) and [adobe.target.applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) using the selector option.

## Example {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
