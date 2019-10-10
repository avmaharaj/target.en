---
description: What you need to know before creating a Recommendations activity.
keywords: Recommendations;settings;preferences;industry vertical;filter incompatible criteria;default host group;thumb base url;recommendations api token
seo-description: What you need to know before creating a Recommendations activity.
seo-title: Plan and Implement Recommendations
solution: Target
title: Plan and Implement Recommendations
title-outputclass: premium
topic: Premium
uuid: 37be7fb3-3686-4dec-9cca-478d28191985
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Plan and Implement Recommendations {#plan-and-implement-recommendations}

What you need to know before creating a Recommendations activity.

## Plan and Implement Recommendations {#concept_02AA644A4C7D4D5CB1D9CADA208CF8D1}

What you need to know before creating a [!DNL Recommendations] activity.

[!DNL Recommendations] requires that you set up the following hierarchy of information:

| Step | Information | Details |
|--- |--- |--- |
|![Step 1](/help/c-recommendations/assets/step1_red.png) |JavaScript library|Each page requires a reference to at.js  version 0.9.1 (or later) or  mbox.js  version 55 (or later). This implementation step is required on all pages where a  Target  activity will be used, and can include keys such as a product or category ID.<BR>For information about at.js, see [at.js Implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md).<br>For more information about mbox.js, see [Mbox.js Implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).|
|![Step 2](/help/c-recommendations/assets/step2_red.png)|Keys|The key determines the type of product or content that displays in your recommendations. For example, the key might be a product category. See [Base the Recommendation on a Recommendation Key](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B).|
|![Step 3](/help/c-recommendations/assets/step3_red.png)|Attributes|Attributes provide more specific information about the products you want to display. For example, you might want to show products within a certain price range, or items that meet an inventory threshold. Attributes can be provided in the mbox or through a [feed](/help/c-recommendations/c-products/feeds.md).<br>See [Inclusion Rules](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_28DB20F968B1451481D8E51BAF947079) and [Entity Attributes](/help/c-recommendations/c-products/entity-attributes.md).|
|![Step 4](/help/c-recommendations/assets/step4_red.png)|Exclusions|Exclusions determine which specific items do not appear in your recommendations.<br>See [Exclusions](/help/c-recommendations/c-products/exclusions.md).|
|![Step 5](/help/c-recommendations/assets/step5_red.png)|Purchase details|Purchase details provide information about purchased items and the order when the purchase has been completed.|

## Base Implementation {#concept_D1154A3FB0FB4467A29AD2BDD21C82D5}

The base implementation requires that you pass parameters to your page that determine which products or services appear in your recommendations.

Before you begin setting up a [!DNL Recommendations] activity, you should understand how product data is provided to [!DNL Recommendations], and decide which method works best for your needs.

There are two methods to provide information about products and services to [!DNL Recommendations]:

| Method | Description |
|--- |--- |
|Pass parameters directly to the page|This method works well for items that change frequently. However, because it requires that changes be made directly to the page, in many organizations, this method requires the involvement of IT and the people who implement the pages.|
|Pass parameters through a Google or CSV feed|This method works well for collections that do not change frequently. It is usually not necessary to change your implementation or other page code to provide product information through a feed. However, the product list remains static, so quick changes are more difficult. For more information, see [Feeds](/help/c-recommendations/c-products/feeds.md).|

These methods can be used separately or together, as in the following examples.

## Example One: Combine Page and Feeds {#section_DF6BAE4BF11548BD9C44D0A426BCF5A7}

One common [!DNL Recommendations] implementation option uses both page parameters and feeds.

This method might be preferred by a retailer who has a relatively set product catalog, but who might want to emphasize specific seasonal items or items that are on sale. Most customers might provide their information primarily through the feed, with only occasional adjustments on the page.

Use a feed to provide information that does not change frequently. Whether using a CSV file or Google feed, use the following parameters:

* Required parameters

    * `entity.id`

* Helpful parameters

    * `entity.name` 
    * `entity.categoryId` 
    * `entity.brand` 
    * `entity.pageUrl` 
    * `entity.thumbnailUrl` 
    * `entity.message`
    * All custom attributes

Once the feed is set up and passed to [!DNL Recommendations], pass parameters on the page for attributes that change frequently, i.e. more often than daily.

* Required parameters

    * `entity.id` 
    * `entity.categoryId`

* Helpful parameters

    * `entity.inventory` 
    * `entity.value`

Priority is given to whichever set of data runs most recently. If you pass the feed first and then update the page parameters, changes that are made in the page parameters will be shown, replacing item information passed in the feed.

## Example Two: Pass All Parameters on the Product (or Content) Details Page {#section_D5A4F69457604CA7AACFD7BFF79B58A9}

If you pass all parameters on the page, you can quickly make updates by updating the page. In some organizations, this requires the involvement of IT or your Web Design team.

This example might be especially useful for a media company, with content that constantly changes.

* Required parameters

    * `entity.id` 
    * `entity.categoryId` 
    * All other attributes

## Sample Code {#section_6E8A73376F30468BB549F337C4C220B1}

For example, you can use the following code in the header section of your product or content pages:

```
function targetPageParams() {
 return {
    "entity": {
       "id": "32323",
       "categoryId": "My Category",
       "value": 105.56,
       "inventory": 329
    }
 }
}
```

For more examples of the code you might use on different types of pages, see [Implementation According to Page Type](../c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC).

## Implementation According to Page Type {#reference_DE38BB07BD3C4511B176CDAB45E126FC}

Page type will influence your [!DNL Recommendations] implementation.

For example, the types of recommendations you want to present may be different on a product page than on a category page or your home page. For each page, you can run specific functions prior to the mbox call to display the appropriate recommendations.

For information about the attributes in the examples, see [Entity Attributes](../c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F).

Valid JSON formatting is required.

The `targetPageParams` function shown below is especially helpful if you are using a tag management solution to implement your pages. [!DNL Adobe Launch] or [!DNL Adobe Dynamic Tag Manager] (DTM) places the at.js/mbox.js reference and the `targetPageParams` function on your page and allows you to configure the values. You should either place that function before your at.js/mbox.js call, or put it in the Extra JavaScript section of your at.js/mbox.js.

## All Pages {#section_A22061788BAB42BB82BA087DEC3AA4AD}

All pages that contain recommendations require either an [!DNL at.js] or [!DNL mbox.js] reference on the page. Add one of the following references to all pages with recommendations:

```
<script src="../at.js /></script>
```

```
<script src="../mbox.js /></script>
```

This implementation requires:

* [!DNL at.js] version 0.9.2 (or later) or [!DNL mbox.js] version 55 (or later)

* [!DNL mbox.js] must include the reference to [!DNL target.js] ( [!DNL at.js] does not require a reference to [!DNL target.js])

For more information about implementing [!DNL at.js], see [How to Deploy at.js](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md#topic_ECF2D3D1F3384E2386593A582A978556).

For more information about implementing [!DNL mbox.js], see [Mbox.js Implementation](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).

For more information about the differences between the two Target Javascript libraries, see [Benefits of at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits).

## Category Page {#section_F51A1AAEAC0E4B788582BBE1FEC3ABDC}

On a category page, you probably want to restrict your recommendations to products or content within that category. To set up a category page, you set up the keys used by the page. For more information about keys, see [Base the Recommendation on a Recommendation Key](../c-recommendations/c-algorithms/create-new-algorithm.md#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B).

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "My Category" 
      } 
   } 
}
```

## Product Page {#section_205B3953C9664125A17CA8574FA6B2A3}

On a product page, you might want to recommend specific items, or items with a particular price or inventory level. For a product page, you might need to set up frequently changing attributes (such as value and inventory), in addition to the keys required for a category page.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "My Category", 
         "value": 105.56, 
         "inventory": 329 
      } 
   } 
}
```

## Cart Page {#section_D37E48700F074556B925D0CA0291405E}

On a cart page, you likely want to exclude some items from your recommendations, such as the items that are already in the cart.

```
<script type="text/javascript">
function targetPageParams() {
   return {
      "excludedIds": [352, 223, 23432, 432, 553]
      }
}
</script>
```

## Thank You Page {#section_C6126A4517A1478693AB7EC2A1D4ACCA}

On the Thank You page, you might want to show the order total, and the order ID, and show the products that were purchased, without recommending additional items. You can implement a second mbox to capture the order information.

* If you are using at.js, see [Track Conversions](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053). 
* If you are using mbox.js, see [Create an Order Confirmation mbox - mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/orderconfirm-create.md#task_0036D5F6C062442788BB55E872816D82).

## Settings {#concept_C1E1E2351413468692D6C21145EF0B84}

Use settings to manage your [!DNL Recommendations] implementation.

To access the [!UICONTROL Recommendations Settings] options, open [!DNL Target] in the [!DNL Adobe Experience Cloud], then click **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

![](assets/recs_settings.png)

The following options are available:

| Setting | Description |
|--- |--- |
|Custom Global Mbox|(Optional) Specify the custom global mbox used to serve [!DNL Target] activities. By default, the global mbox used by [!DNL Target}  is used for [!DNL Recommendations].<br>Note: This option is set on the [!DNL Target] [!UICONTROL Setup] page. Open [!DNL Target], then click [!UICONTROL Setup].|
|Industry Vertical|The industry vertical is used to help categorize your recommendations criteria. This helps members of your team find criteria that make sense for a particular page, such as criteria that are best for the shopping cart page or for a media page.|
|Filter Incompatible Criteria|Enable this option to show only those criteria where the selected page passes the required data. Not every criteria will run correctly on every page. The page or mbox needs to pass in `entity.id` or `entity.categoryId` for the current item/current category recommendations to be compatible. In general, it is best to show only compatible criteria. However, if you want incompatible criteria to be available for the activity, uncheck this option.<br>It is recommended that you disable this option if using a tag management solution.<br>For more information about this option, see [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md).|
|Default Host Group|Select your default host group. None means that your Default Host Group for Reporting setting in [!DNL Target Classic] is used for your default host group.<br>The host group can be used to separate the available items in your catalog for different uses. For example, you can use host groups for Development and Production environments, different brands, or different geographies. By default, preview results in Catalog Search, Collections, and Exclusions are based on the default host group. (You can also select a different host group to preview results, by using the Environment filter.) By default, newly added items are available in all host groups unless an environment ID is specified when creating or updating the item. Delivered recommendations depend on the host group specified in the request.<br>If you don't see your products, make sure that you are using the correct host group. For example, if you set up your recommendation to use a staging environment and you set your host group to Staging, you might need to re-create your collections in the staging environment for the products to show. To see which products are available in each environment, use Catalog Search with each environment. You can also preview the contents of Recommendations collections and exclusions for a selected environment (host group).<br>**Note:** After changing the selected environment, you must click Search to update the returned results.<br>The [!UICONTROL Environment] filter is available from the following places in the [!DNL Target] UI:<ul><li>Catalog Search ([!UICONTROL Recommendations > Catalog Search)</li><li>Create Collection dialog box ([!UICONTROL Recommendations > Collections > Create New])</li><li>Update Collection dialog box ([!UICONTROL Recommendations > Collections > Edit])</li><li>Create Exclusion dialog box ([!UICONTROL Recommendations > Exclusions > Create New])</li><li>Update Exclusion dialog box ([!UICONTROL Recommendations > Exclusions > Edit])</li></ul>For more information, see [Hosts](/help/administrating-target/hosts.md).|
|Thumbnail Base URL|Setting a base URL for your product catalog makes it possible to use relative URLs when specifying thumbnails of your products when passing in your thumbnail URL.<br>For example:<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>sets a URL relative to the thumbnail base URL.|
|Recommendations API Token|Use this token in Recommendations API calls, such as the Download API.|
