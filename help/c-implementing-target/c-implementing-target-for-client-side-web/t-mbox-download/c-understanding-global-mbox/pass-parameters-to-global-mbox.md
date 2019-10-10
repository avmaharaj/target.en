---
description: The JavaScript targetPageParams function is used to pass parameters to the global mbox. This is needed in any scenario where additional targeting/context information is to be passed into Target.
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
seo-description: The JavaScript targetPageParams function is used to pass parameters to the global mbox. This is needed in any scenario where additional targeting/context information is to be passed into Target.
seo-title: Pass Parameters to a global mbox
solution: Target
subtopic: Getting Started
title: Pass Parameters to a global mbox
topic: Standard
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
---

# Pass Parameters to a global mbox{#pass-parameters-to-a-global-mbox}

The JavaScript targetPageParams function is used to pass parameters to the global mbox. This is needed in any scenario where additional targeting/context information is to be passed into Target.

 For example, in a Recommendations activity, use the parameters to represent the current product or category that is being viewed.

The code to call the JavaScript function must come before the global mbox on the page, whether the global mbox is fired as a part of mbox.js or is manually included in the page code.

>[!NOTE]
>
>If you want to add parameters to all mboxes on the page, not just to the global mbox, use the [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) function (at.js only).

You can pass in parameters to `target-global-mbox` using the `targetPageParams()` function in any of the following ways:

* An array 
* A JSON object 
* An ampersand-delimited list

Use these three methods to verify that the parameters are being passed correctly. You might also be able to verify the passing of parameters using the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html).

You must define the JavaScript function before adding the global mbox to the page. The name must be `targetPageParams`.

**Query String**

```
p1=v1&p2=v2&p3=hello%20world
```

* Name: `targetPageParams` 
* Return value: a "&" delimited parameters, with URL encoded parameter values.

  Example:

  In this example, p3 has the value `hello world`, which is URL encoded.

The following is an example of how the code for the page might look:

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

This example sends the following data to the mbox edge:

* p1=v1 
* p2=v2 
* p3=hello world

**Array**

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 

```

Values do not need to be URL encoded. For example, if a value contains a space, there is no need to encode the space.

This example sends the following data to the mbox edge:

* a=1 
* b=2 
* c=hello world

**JSON**

JSON is a powerful way to pass parameters. Target uses the JSON object keys to flatten complicated structures into simple parameters.

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 

```

Values do not need to be URL encoded. For example, "San Francisco" does not require the space to be encoded. A space suffices.

This example sends the following data to the mbox edge:

* a=1 
* b=2 
* `profile.age`=26 
* `profile.country.city`=San Francisco