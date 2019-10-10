---
description: Information about the targetPageParamsAll() function for at.js. 
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;page params;page parameters;at.js;functions;function
seo-description: Information about the targetPageParamsAll() function for the Adobe Target at.js JavaScript library.
seo-title: Information about the targetPageParamsAll() function for the Adobe Target at.js JavaScript library.
solution: Target
subtopic: Getting Started
title: targetPageParamsAll()
topic: Standard
---

# targetPageParamsAll()

This method allows you to attach parameters to all mboxes from outside of the request code.

This is very useful for including the same set of parameters on multiple mbox calls. The function needs to be defined by the customer. It should return an array of parameters that will be passed to all mbox requests on the page. This function can be defined before at.js is loaded or in **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

You can pass in parameters to target-global-mbox using the targetPageParamsAll() function in any of the following ways:

* An ampersand-delimited list 
* An array 
* A JSON object

## Examples

Ampersand-delimited list (values must be URL encoded):

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Array (values do not need to be URL encoded):

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (values do not need to be URL encoded):

```
targetPageParamsAll = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
``` 
