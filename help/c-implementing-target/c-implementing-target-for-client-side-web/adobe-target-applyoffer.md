---
description: Information about the adobe.target.applyOffer() function for at.js. 
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;functions;function
seo-description: Information about the adobe.target.applyOffer(options) function for the Adobe Target at.js JavaScript library.
seo-title: Information about the adobe.target.applyOffer() function for the Adobe Target at.js JavaScript library.
solution: Target
subtopic: Getting Started
title: adobe.target.applyOffer(options)
topic: Standard
---

# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

This function is for applying the response content.

>[!NOTE]
>
>`applyOffer` requires the `mbox` parameter. If no mbox name is specified, an error occurs.

The options parameter is mandatory and has the following structure:

| Key | Type | Required | Description |
|--- |--- |--- |--- |
|mbox|String|Yes|Mbox name<br>With at.js 1.3.0 (and later) Target enforces that the mbox key is used. This key has been required in the past, but Target now enforces its use to ensure that Target has proper validation and customers are using the function correctly.|
|selector|String or DOM Element|No|HTML element or CSS selector used to identify the HTML element where Target should place the offer content. If selector is not provided, Target assumes that the HTML element we should use is HTML HEAD.|
|offer|Array|Yes|An array actions that should be applied to the element.|

## Example {#section_D8D6A17B73DE4542937CDB687193A5CC}

The following example shows how to use `getOffer` and `applyOffer` together:

```
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```