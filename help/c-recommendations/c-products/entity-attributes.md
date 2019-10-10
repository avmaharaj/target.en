---
description: Use entity attributes to pass product or content information to Recommendations.
keywords: entity;entity attributes;pass information to Recommendations;behavioral data;data counter;define relative URL;display inventory level;define price;define profit margin;custom attributes
seo-description: Use entity attributes to pass product or content information to Recommendations.
seo-title: Entity attributes
solution: Target
title: Entity attributes
title-outputclass: premium
topic: Premium
uuid: 27672881-a79c-4271-9a61-defddb9a5249
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Entity attributes{#entity-attributes}

Use entity attributes to pass product or content information to Recommendations.

## Available variables

The following list describes the available variables.

### `entity.id`

Singe value only.

This required parameter identifies the product. This alphanumeric ID must be the same across all [!DNL Adobe Experience Cloud] products that are used, including [!DNL Analytics], for the various products to recognize the item and share data about it.

`entity.id` values must not contain slashes, ampersands, question marks, percentage symbols, commas, or other punctuation characters that require URL encoding when passed in a REST API call. Hyphens and underscores are permitted. Including invalid punctuation in an `entity.id` value causes some [!DNL Recommendations] functionality to fail.

Example: `'entity.id=67833'`

### `entity.name`

Single-value only.

The product name that is displayed on the Web site when the product is recommended.

Example: `'entity.name=Giants& vs& Rockies& 5/12'`

### `entity.categoryId`

Supports multi-value (comma-delimited list).

Category of the current page. This can include multiple categories, such as a cardigans sub-subsection (i.e. womens, womens:sweaters, womens:sweaters:cardigans). Multiple categories should be separated by commas.

`categoryId` is limited to 250 characters.

>[!NOTE]
>
>To show a recommendation based on a category in a [!UICONTROL Category] page, only one `categoryId` can be passed into the mbox used to display that particular recommendation. The value of the `categoryId` must match exactly the value of `entity.categoryId` passed on the [!UICONTROL Product Detail] page.

Examples:

* Example Product Detail Page: womens, womens:sweaters, womens:sweaters:cardigans
* Example Category Page Sweaters: womens:sweaters
* Example Category Page Cardigans: womens:sweaters:cardigans

For category-based recommendations, a comma is used to separate category value. Any values separated by commas become categories. You can also define subcategories by using a different separator, such as a colon (:), to separate subcategories within the category value.

For example, in the following code the Womens category is divided into several subcategories:

```
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

For the mbox delivery, the longest attribute name is used for the key. If there is a tie, the last attribute is used. In the example above, the category key is Womens:Outerwear:Jackets:Caban .

### `entity.brand`

Single-value only.

Displays an item's brand name.

Example: `'entity.brand=brandxyz'`

### `entity.pageUrl`

Single-value only.

Defines the relative URL of the page where the item can be purchased.

Example: `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### `entity.thumbnailUrl`

Single-value only.

Defines the relative URL to the thumbnail image that displays with the item.

Example: `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### `entity.message`

Single-value only.

A message about the product that is displayed in the recommendation, such as "on sale" or "clearance." The message is typically more verbose than the product name. Use to define additional information to display with the product in the template.

Example: `'entity.message=Family&nbsp;special'`

### `entity.inventory`

Single-value only. Requires an integer or long value.

Displays the inventory level of the item.

Example: `'entity.inventory=1'`

**Empty Inventory Attribute Handling:** For delivery, if you have an inclusion rule, collection rule, or criteria setting with `entity.inventory` > 0 or `entity.inventory` = 0 and the product has inventory not set, [!DNL Target] evaluates this to TRUE and includes products where the inventory is not set. This was done by default so that products with inventory that is not set show up in recommendation results.

Similarly, if you have a global exclusion rule with `entity.inventory` = 0 and `entity.inventory` is not set, [!DNL Target] evaluates this rule to be TRUE and excludes the product.

**Known issue:** Product Search is inconsistent with delivery for not-set inventory value attributes. For example for a rule with `entity.inventory` = 0 , Product Search will not display products where the inventory value is not set.

### `entity.value`

Single-value only.

Defines the price or value of the item.

Example: `'entity.value=15.99'`

### `entity.margin`

Single-value only.

The profit margin or other value of the item.

Example: `'entity.margin=1.00'`

### `entity.<custom>`

Supports multi-value (JSON array).

Define up to 100 custom variables that provide additional information about the item. You can specify any unused attribute name for each custom attribute. For example, you might create a custom attribute called `entity.genre` to define a book or movie. Or, a ticket vendor might create attributes for an event venue for a secondary performer, such as a visiting team in a sporting event or an opening act in a concert.

Restrictions:

* You cannot use predefined entity attribute names for custom entity attributes.
* The attribute entity.environment is reserved by the system and cannot be used for custom entity attributes. Attempts to pass entity.environment using targetPageParams , feed, or API will be ignored.

Examples:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Custom entity attributes support multiple values. See [Custom entity attributes](/help/c-recommendations/c-products/custom-entity-attributes.md#limits) for character and value limits. 

Example: `'entity.secondary=["band1",&nbsp;"band2"]'`

>[!NOTE]
>
>Multi-value custom entity attributes require valid JSON arrays. For correct syntax information, see Custom Entity Attributes.

### `entity.event.detailsOnly`

Single-value only.

Used to prevent an mbox call from incrementing behavioral data counters for an algorithm.

Example: `'entity.event.detailsOnly=true'`

In the examples below, the first mbox call will update the catalog and behavioral data. The second mbox call will update only the catalog.

```
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

## Use entity attributes

>[!NOTE]
>
>Provided entity attribute values expire after 61 days. This means that you should ensure that the latest value of each entity attribute is passed to Target Recommendations at least once per month for each item in your catalog.

Recommendations sends the `productId` or `productPurchasedId` (referred to as `entity.id` in the code) that is used in the algorithms.

>[!NOTE]
>
>`entity.id` must match the `productPurchasedId` sent to the order confirmation page and the `productId` used in Adobe Analytics product reports).

Most predefined parameters accept only a single value, with new values overwriting old values. The `categoryId` parameter can accept a comma-delimited list of values for each category containing that product. New `categoryId` values do not overwrite existing values but instead are appended during entity update (250-character limit).

In general, the display information mbox might look like the following example. Change the details in bold to refer to your products.

>[!NOTE]
>
>All entity parameter attributes are case sensitive.

```
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id= 
<b>67833</b>', 
 
'entity.name= 
<b>GIANTS VS ROCKIES 5/12</b>', 
 
'entity.categoryId= 
<b>BASEBALL, GIANTS, SF BAY AREA</b>', 
 
'entity.pageUrl= 
<b>../baseball/giants-tix/giantsvrockies5.12.2000-67833</b>', 
 
'entity.venue= 
<b>AT&T PARK</b>', 
 
'entity.secondary= 
<b>ROCKIES</b>', 
 
'entity.thumbnailUrl= 
<b>../baseball/giants-tix/giants-136px.gif</b>', 
 
'entity.message= 
<b>FAMILY SPECIAL</b>', 
 
'entity.value= 
<b>15.99</b>', 
 
'entity.inventory= 
<b>1</b>' 
 
); 
 
</script>
```

>[!NOTE]
>
>Relative URLs are preferred for `pageUrl` and `thumbnailUrl` rather than absolute URLs because recommendations receive data being sent from all environments on your site. Using relative URLs avoids hardcoded links to a staging or development server.

If the mbox is on a product page, you can include both the product ID and category ID. The selected algorithm determines which displays. The product ID is used for affinity algorithms and the category ID is used for category algorithms. 

## Related topics:

* [Custom Entity Attributes](../../c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
