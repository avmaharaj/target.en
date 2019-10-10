---
description: Information about the adobe.target.getOffers() function for at.js. 
keywords: adobe.target.getOffers;getOffers;getoffers;get offers;at.js;functions;function
seo-description: Information about the adobe.target.getOffers(options) function for the Adobe Target at.js JavaScript library.
seo-title: Information about the adobe.target.getOffers() function for the Adobe Target at.js JavaScript library.
solution: Target
subtopic: Getting Started
title: adobe.target.getOffers(options)
topic: Standard
---

# adobe.target.getOffers(options) - at.js 2.x

This function lets you retrieve multiple offers by passing in multiple mboxes. Additionally, multiple offers can be retrieved for all views in active activities.

>[!NOTE]
>
>This function was introduced with at.js 2.x. This function is not available for at.js version 1.*x*.

|Key|Type|Required?|Description|
| --- | --- | --- | --- |
|consumerId|String|No|Default value is client's global mbox if not provided. This key is used to generate the supplemental data ID used for A4T integration. This key is a unique string per visitor.|
|request|Object|Yes|See Requests table below.|
|timeout|Number|No|request timeout. If not specified the default at.js timeout is used.|

## Request

|Field name|Required?|Limitations|Description|
| --- | --- | --- | --- |
|request > id|No||One of `tntId`, `thirdPartyId`, or `marketingCloudVisitorId` is required.|
|Request > id > thirdPartyId|No|Maximum size = 128|||
|Request > experienceCloud|No|||
|Request > experienceCloud > analytics|No||Adobe Analytics integration|
|Request > experienceCloud > analytics > logging|No|The following must be implemented on page:<ul><li>Visitor ID Service</li><li>Appmeasurement.js</li></ul>|The following values are supported:<br>**client_side**: When specified, an analytics payload will be returned to the caller which should be used to send to Adobe Analytics via the Data Insertion API.<br>**server_side**: This is the default value where the Target and Analytics backend will use the SDID to stitch the calls together for reporting purposes.|
|Request > prefetch|No|||
|Request > prefetch > views|No|Maximim count 50<br>Name not blank<br>Name length `<=` 128<br>Value length `<=` 5000<br>Name should not start with "profile"<br>Not allowed names: "orderId", "orderTotal", "productPurchasedId"|Pass in parameters to be used to retrieve relevant views in active activities.|
|Request > prefetch > views > profileParameters|No|Maximim count 50<br>Name not blank<br>Name length `<=` 128<br>Value length `<=` 5000<br>Name should not start with "profile"|Pass in profile parameters to be used to retrieve relevant views in active activities.|
|Request > prefetch > views > product|No|||
|Request > prefetch > views > product -> id|No|Not blank<br>maximum size = 128|Pass in product IDs to be used to retrieve relevant views in active activities.|
|Request > prefetch > views > product > categoryId|No|Not blank<br>maximum size = 128|Pass in product category IDs to be used to retrieve relevant views in activities.|
|Request > prefetch > views > order|No|||
|Request > prefetch > views > order > id|No|Maximum length = 250|Pass in order IDs to be used to retrieve relevant views in in active activities.|
|Request > prefetch > views > order > total|No|Total `>=` 0|Pass in order totals to be used to retrieve relevant views in active activities.|
|Request > prefetch > views > order > purchasedProductIds|No|No blank values<br>Each value's max length 50<br>Concatenated and separated by comma<br>Product IDs total length `<=` 250|Pass in purchased product IDs to be used to retrieve relevant views in active activities.|
|Request > execute|No|||
|Request > execute > pageLoad|No|||
|Request > execute > pageLoad > parameters|No|Maximum count 50<br>Name not blank<br>Name length `<=` 128<br>Value length `<=` 5000<br>Name should not start with "profile."<br>Not allowed names: "orderId", "orderTotal", "productPurchasedId"|Retrieve offers with specified parameters when page loads.|
|Request > execute > pageLoad > profileParameters|No|Maximum count 50<br>Name not blank<br>Name length `<=` 128<br>Value length `<=`256<br>Name should not start with "profile."|Retrieve offers with specified profile parameters when page loads.|
|Request > execute > pageLoad > product|No|||
|Request > execute > pageLoad > product -> id|No|Not blank<br>Maximum size = 128|Retrieve offers with specified product IDs when page loads.|
|Request > execute > pageLoad > product > categoryId|No|Not blank<br>Maximum size = 128|Retrieve offers with specified product category IDs when page loads.|
|Request > execute > pageLoad > order|No|||
|Request > execute > pageLoad > order > id|No|Maximum length = 250|Retrieve offers with specified order IDs when page loads.|
|Request > execute > pageLoad > order > total|No|`>=` 0|Retrieve offers with specified order totals when page loads.|
|Request > execute > pageLoad > order > purchasedProductIds|No|No blank values<br>Each value's max length 50<br>Concatenated and separated by comma<br>Product IDs total length `<=` 250|Retrieve offers with specified purchased product IDs when page loads.|
|Request > execute > mboxes|No|Maximum size = 50<br>No null elements||
|Request > execute > mboxes>mbox|Yes|Not blank<br>No '-clicked' suffix<br>Maximum size = 250<br>Allowed characters: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'`|Name of mbox.|
|Request > execute > mboxes>mbox>index|Yes|Not null<br>Unique<br>`>=` 0|Note that the index does not represent the order in which the mboxes will be processed. Same as in a web page with several regional mboxes, the order in which they will be processed cannot be specified.|
|Request > execute > mboxes > mbox > parameters|No|Maximum count = 50<br>Name not blank<br>Name length `<=` 128<br>Value length `<=` 5000<br>Name should not start with "profile."<br>Not allowed names: "orderId", "orderTotal", "productPurchasedId"|Retrieve offers for a given mbox with the specified parameters.|
|Request > execute > mboxes>mbox>profileParameters|No|Maximum count = 50<br>Name not blank<br>Name length `<=` 128<br>Value length `<=`256<br>Name should not start with "profile."|Retrieve offers for a given mbox with the specified profile parameters.|
|Request > execute > mboxes>mbox > product|No|||
|Request > execute > mboxes > mbox > product > id|No|Not blank<br>Maximum size = 128|Retrieve offers for a given mbox with the specified product IDs.|
|Request > execute > mboxes > mbox > product > categoryId|No|Not blank<br>Maximum size = 128|Retrieve offers for a given mbox with the specified product category IDs.|
|Request > execute > mboxes > mbox > order|No|||
|Request > execute > mboxes>mbox > order > id|No|Maximum length = 250|Retrieve offers for a given mbox with the specified order IDs.|
|Request > execute > mboxes > mbox > order > total|No|`>=` 0|Retrieve offers for a given mbox with the specified order totals.|
|Request > execute > mboxes > mbox > order > purchasedProductIds|No|No blank values<br>Each value's maximum length = 50<br>Concatenated and separated by comma<br>Product ids total length `<=` 250|Retrieve offers for a given mbox with the specified order purchased product IDs.|

## Call `getOffers()` for all views

```
adobe.target.getOffers({
    request: {
      prefetch: {
        views: [{}]
    }
  }
});
```

## Call `getOffers()` to retrieve the latest views with the passed-in parameters and profile parameters

```
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## Call `getOffers()` to retrieve mboxes with parameters and profile parameters passed-in.

```
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## Call getOffers() to retrieve the analytics payload from the client side

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**Response**:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

The payload can then be forwarded to Adobe Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Fetch and render data from multiple mboxes via getOffers() and applyOffers() {#multiple}

at.js 2.x lets you fetch multiple mboxes via the `getOffers()` API. You can also fetch data for multiple mboxes and then use `applyOffers()` to render the data in different locations identified by a CSS selector.

The following example shows a simple HTML page with at.js 2.x implemented:

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

Assume that you have three containers that you want to modify via content received from [!DNL Target]. You can construct a single request for three mboxes in which each mbox has some content to render into the respective container.

The request and rendering code might look like the following example:

```
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

In the `request > prefetch > mboxes` section, there are three different mboxes. If the request completed successfully, you receive the response for each mbox from `response > prefetch > mboxes`. After you have the responses and the locations you want to use for rendering, you can invoke `applyOffers()` to render the content retrieved from [!DNL Target]. In this example we have the following mapping:

* mbox1 > CSS selector #container1
* mbox2 > CSS selector #container2
* mbox3 > CSS selector #container3

This example uses the count variable to construct the CSS selectors. In a real-life scenario you could use a different mapping between the CSS selector and mbox.

Note that this example uses `prefetch > mboxes`, but you could also use `execute > mboxes`. Ensure that if you use prefetch in `getOffers()`, you should also use prefetch in the `applyOffers()` invocation.
