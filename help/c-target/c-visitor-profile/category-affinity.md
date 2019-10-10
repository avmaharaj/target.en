---
description: The category affinity feature automatically captures the categories a user visits and then calculates the user's affinity for the category so it can be targeted and segmented on. This helps to ensure that content is targeted to visitors who are most likely to act on that information.
keywords: affinity;category affinity
seo-description: The category affinity feature in Adobe Target automatically captures the categories a user visits and then calculates the user's affinity for the category so it can be targeted and segmented on. This helps to ensure that content is targeted to visitors who are most likely to act on that information.
seo-title: Use category affinity in Adobe Target
solution: Target
title: Category affinity
topic: Standard
uuid: b81d9c91-a222-4768-9ac8-359f9ab9ca2d
---

# Category affinity{#category-affinity}

The category affinity feature automatically captures the categories a user visits and then calculates the user's affinity for the category so it can be targeted and segmented on. This helps to ensure that content is targeted to visitors who are most likely to act on that information.

## Passing category affinity information into Target {#section_B0C8E46EEBAC4549AD90352A47787D04}

Whenever a user visits your site, profile parameters specific to the visitor are recorded in the [!DNL Target] database. This data is tied to the user's cookie. One particularly useful parameter is `user.categoryId`, an mbox parameter assigned on a product page. As the visitor continues to browse, or returns for another session, the categories of products a particular user views can be recorded. You can also record category information by passing it as the mbox parameter `user.categoryId` in any mbox (including a nested mbox), as a URL parameter `user.categoryId`, or in Target page parameters with a global mbox. See your account representative for more details.

Separate categories with a comma to include an item in multiple categories. For example:

* `user.categoryId=clothing,shoes,nike,running,nike clothing,nike shoes,nike running shoes`

Based on the frequency and recency of visits to your product categories, the category affinity (if any) a user has is recorded. Category affinity can be used to target populations for your activities.

You can use `user.categoryAffinities[]` in a profile script to return an array of the affinities that a visitor has populated.

>[!IMPORTANT]
>
>The `user.categoryId` attribute used for Adobe Target's category affinity algorithm is distinct from the `entity.categoryId` attribute used for Adobe Target Recommendations' product and content recommendations. `user.categoryId` is required to track a user's favorite category. `entity.categoryId` is required to base recommendations on the current page's or current item's category. Pass both values to Adobe Target if you want to use both capabilities.

## Business case for category affinity {#section_D6FF913E88E6486B8FBCE117CA8B253B}

A visitor's activity in one session, such as which category he or she views the most often, can be used for targeting in subsequent visits. Each category page a visitor views during a session is captured, and his or her "favorite" category is calculated based on a recency and frequency model. Then, every time the visitor returns to the home page, the hero image area can be targeted to show content related to that user's favorite category.

## Example of using category affinity {#section_A4AC0CA550924CB4875F4F4047554C18}

Suppose you sell musical instruments online and want to target sales promotions on bass guitars to visitors who have already expressed interest in guitars in the past. Using category affinity, you can create offers that display only to visitors with this category affinity.

## Category affinity algorithm {#section_8B86C7FF50294208866ABF16F07D5EB9}

The category affinity algorithm works as follows:

* 10 points for the first category viewed
* 5 points for each category clicked after the first
* When a new category is clicked, 1 is subtracted from all previously clicked categories
* If a category was already clicked (seen), clicking it again won't subtract 1 from all other categories
* If a sixth new category is clicked, the lowest scored category of the first five categories is dropped from the calculation
* At end of session, divide all values by 2

### Example: category affinity algorithm

For example, viewing the `mens-clothing` category, then `accessories`, then `jewelry`, then `accessories` again in a session results in affinities of:

* `accessories`: 9 (+5 – 1 + 5)

* `mens-clothing`: 8 (+10 – 1 – 1)

* `jewelry`: 5 (+5)

When the session ends, and the user later returns to the site, the scores are halved:

* `accessories`: 4.5 (9/2)

* `mens-clothing`: 4 (8/2)

* `jewelry`: 2.5 (5/2)

Assuming the user then views, in order, `jewelry`, `accessories`, `beauty`, `shoes`, and `womens-clothing`:

* `accessories`: 6.5 (4.5 + 5 – 1 – 1 - 1)

* `womens-clothing`: 5 (+5)

* `jewelry`: 4.5 (2.5 + 5 – 1 – 1 - 1)

* `shoes`: 4 (+5 – 1)

* `beauty`: 3 (+5 – 1 - 1)

* `mens-clothing` is dropped after the final click of `womens-clothing` as the lowest-scoring category with a score of 1 (4 – 1 – 1 - 1)

When the session ends, and the user later returns to the site, the scores are halved:

* `accessories`: 3.3 (6.5/2)

* `womens-clothing`: 2.5 (5/2)

* `jewelry`: 2.3 (4.5/2)

* `shoes`: 2 (4/2)

* `beauty`: 1.5 (3/2)

## Use category affinity for targeting {#concept_5750C9E6C97A40F8B062A5C16F2B5FFC}

Information to help you use a [!UICONTROL Category Affinity] audience for targeting in an activity. 

This section contains the following information:

* [Create an Audience to Use Category Affinity](../../c-target/c-visitor-profile/category-affinity.md#section_A27C600BBA664FE7A74F8FE076B78F40) 
* [Use the Category Affinity Audience in an Activity](../../c-target/c-visitor-profile/category-affinity.md#section_91526B942D1B4AEBB8FCDF4EBFF931CF)

## Create an audience to use category affinity {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. From the **[!UICONTROL Audiences]** list, click **[!UICONTROL + Create Audience]**.

   Or

   To copy an existing audience, from the Audiences list, hover over the desired audience, then click the Copy icon. You can then edit the audience to create a similar audience. 

1. Type a descriptive audience name. 
1. Click **[!UICONTROL + Add Rule]** > **[!UICONTROL Visitor Profile]**. 
1. From the **[!UICONTROL Visitor Profile]** drop-down list, select **[!UICONTROL Category Affinity]**.

   ![Visitor Profile > Category Affinity](assets/affinity.png)

1. Select the desired category:

    ![Category Affinity > Category](/help/c-target/c-visitor-profile/assets/affinity-category.png)

    Categories include:

    * Favorite Category 
    * First Category 
    * Second Category 
    * Third Category 
    * Fourth Category 
    * Fifth Category

1. Chose the Evaluator:

    * Contains (case insensitive) 
    * Does Not Contain (case insensitive) 
    * Equals

1. Specify each new value in a separate line (for example, "shoes"). 
1. Click **[!UICONTROL Save]**.

## Use the category affinity audience in an activity {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

You can use Category Affinity audiences in any activity. During the three-step guided workflow, on the Target step, choose the desired audience. 
