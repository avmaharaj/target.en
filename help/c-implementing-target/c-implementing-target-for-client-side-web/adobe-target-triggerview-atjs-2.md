---
description: Information about the adobe.target.triggerView (viewName, options) function for at.js. 
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;functions;function;viewName;viewname;view name
seo-description: Information about the adobe.target.triggerView (viewName, options) function for the Adobe Target at.js JavaScript library.
seo-title: Information about the adobe.target.triggerView (viewName, options) function for the Adobe Target at.js JavaScript library.
solution: Target
subtopic: Getting Started
title: adobe.target.triggerView (viewName, options)
topic: Standard
---

# adobe.target.triggerView (viewName, options) - at.js 2.x

This function can be called whenever a new page is loaded or when a component on a page is re-rendered. `adobe.target.triggerView()` should be implemented for single page applications (SPAs) in order to use the Visual Experience Composer (VEC) to create A/B Tests and Experience Targeting (XT) activities. If `adobe.target.triggerView()` is not implemented on the site, the VEC cannot be utilized for SPA. For more information, see [Single Page Application implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>This function was introduced with at.js 2.x. This function is not available for at.js version 1.*x*.

|Parameter|Type|Required?|Description|
| --- | --- | --- | --- |
|viewName|String|Yes|Pass in any name as a string type that you want to represent your view. This view name appears in the [!UICONTROL Modifications] panel of the VEC for marketers to create actions and run their A/B and XT activities.|
|options|Object|No||
|options > page|Boolean|No|**TRUE:** Default value of page is true. When page=true, notifications are sent to the [!DNL Target] backend for incrementing impression count.<br>If no activity experience or activity metric is associated with the view, no notification is sent.<br>**FALSE:** When page=false, notifications are not sent for incrementing impression count. This should be used when you want to only re-render a component on a page with an offer.|

## Example: True

`triggerView()` call to send a notification to the Target backend for incrementing activity impressions and other metrics.

```
adobe.target.triggerView("homeView")
```

## Example: False

`triggerView()` call to not have notifications sent to the Target backend for impression counting.

```
adobe.target.triggerView("homeView", {page: false})
```
