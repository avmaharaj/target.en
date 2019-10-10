---
description: Information about the adobe.target.trackEvent(options) function for at.js. 
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
seo-description: Information about the adobe.target.trackEvent(options) function for the Adobe Target at.js JavaScript library.
seo-title: Information about the adobe.target.trackEvent(options) function for the Adobe Target at.js JavaScript library.
solution: Target
subtopic: Getting Started
title: adobe.target.trackEvent(options)
topic: Standard
---

# adobe.target.trackEvent(options)

This function fires a request to report user actions, such as clicks and conversions. It does not deliver activities in the response.

These event-tracking mbox calls can then be used to define metrics in activities. For more information, see [Success Metrics](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) and [Track Conversions](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

Here are the API details:

| Key | Type | Required | Description |
|--- |--- |--- |--- |
|mbox|String|Yes|Mbox name|
|selector|String|No|CSS selectors used to find the HTML elements. The event listeners will be attached to found elements.|
|type|String|No|Represents a registered event type. It can be both HTML known events like: click, mousedown ,etc., as well as custom HTML events.|
|preventDefault|Boolean|No|Indicates whether to use `event.preventDefault()` in the event listener callback. Defaults to false.<br>**Note**: Only `form[submit] and `a[click]` are supported. Other scenarios are not supported due to complexity and huge amount of scenarios to support.|
|params|Object|No|Mbox parameters. An object of key-value pairs that has the following structure:<br>`{ "param1": "value1", "param2": "value2"}`|
|timeout|Number|No|Timeout in milliseconds.<br>If not specified, default value is used:<br>`...timeoutInSeconds: 0.15...}`|
|success|Function|No|A callback function used to signal that event has been reported.|
|error|Function|No|A callback function used to signal that event could not be reported.|

## Example

```
<a href="https://asite.com">click me!</a> 
```

plus javaScript code to assign `trackEvent`:

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

Or:

```
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>In case the mandatory fields are not set, no request is executed, and an error is thrown.