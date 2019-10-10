---
description: Introduction to Target Recommendations activities that automatically display products or content that might interest your customers based on previous user activity or other algorithms. Recommendations help direct customers to relevant items they might otherwise not know about.
keywords: Recommendations;intro;introduction;webinar;demo
seo-description: Introduction to Adobe Target Recommendations activities that automatically display products or content that might interest your customers based on previous user activity or other algorithms. Recommendations help direct customers to relevant items they might otherwise not know about.
seo-title: Introduction to Recommendations activities in Adobe Target
solution: Target
title: Introduction to Recommendations
title-outputclass: premium
topic: Premium
badge: premium
---

# ![PREMIUM](/help/assets/premium.png) Introduction to Recommendations

The text in this article comes from the *Introduction to Recommendations* webinar, which you can view in its entirety below.

The *Introduction to Recommendations* webinar includes an in-depth exploration of how to leverage the value of [!DNL Adobe Target Recommendations]. Find out how this [!DNL Target] activity automatically displays products or content that might interest your customers by optimizing real-time suggestions based on previous visits. Further, dive into the [!DNL Target] UI for a step-by-step overview of how to build a [!DNL Recommendations] activity.

## Introduction

We all know about the kinds of recommendations we see in retail. Increasingly, customers expect these kind of recommendations and use them as a starting point to explore other available options. If you think about your own shopping behavior, these kind of recommendations work really well. Nearly everyone among us has bought a product we saw first in a recommendation somewhere, whether that was in a store or on a digital property.

The following illustration shows a recommendation that displays accessories that are commonly purchased with a new phone, including charging stations, cases, and headphones.

![Recommendation showing accessories others have purchased with a new phone.](/help/c-recommendations/assets/intro-1.png)

But what we don’t always think about is how digital-first brands are raising the bar of customer expectations. Increasingly, the way we consume media and content is driven by personalized recommendations. Think about the first thing you see when you open Netflix, Spotify, or YouTube. These brands start the customer experience with recommendations. In a world where more alternatives are available than ever, it’s critical that you can identify the most relevant content for your customer at the point of interaction.

![Recommendation showing digital-first brands](/help/c-recommendations/assets/intro-2.png)

Marketers use [!DNL Adobe Target] to drive personalized experiences across a wide variety of industries, customer types, and channels.

[!DNL Adobe Target] delivers personalized content everywhere.

![Illustration showing how Target delivers recommendations in various places](/help/c-recommendations/assets/intro-3.png)

* **Publishing**: Web publishers use [!DNL Target Recommendations] to recommend articles to site visitors and drive increased engagement.
* **Video Tutorials**: [!DNL Adobe Creative Cloud] uses [!DNL Target] to recommend video tutorials to Photoshop users in the Photoshop application.
* **Gaming**: Gaming companies use [!DNL Target] to recommend games and content to users on their consoles.
* **B2B Sales**: [Business-to-business companies use Target to recommend videos, whitepapers, and blog posts to B2B prospects; deliver downloads; and provide help to existing customers](https://theblog.adobe.com/testing-shifts-high-gear-intel).

* **Travel**: [A German travel booker uses Target to recommend hotels and more to travelers](https://2017.summit.adobe.com/na/sessions/summit-online/online-2017/#17608).

* **Retail**: [A leading B2B retailer uses Target to recommend top categories and products to return visitors in the browser and in its mobile app](https://theblog.adobe.com/optimization-personalization-b2b-powerhouse-grainger/).

These are just a few of the ways customers use Target to deliver personalized recommendations.

What makes for great recommendations?

![Illustration showing the three elements that make great recommendations](/help/c-recommendations/assets/intro-4.png)

Great recommendations should be relevant and personalized. This means you need three things to drive relevance and personalization:

* **Marketer controls** to help drive relevance of the items that are recommended. As a marketer, you bring valuable context to the table and you know what attributes of your products or content are relevant for a recommendations model to consider. If you’re running a video site, you know that users might be interested in seeing movies from the same director, but probably don’t care about seeing movies that were produced by the same studio. [!DNL Target] empowers you with controls that allow you to enhance your algorithms with this domain knowledge.
* **Sophisticated models** to make sense of millions of items in your catalog and interaction events. [!DNL Target] has sophisticated machine learning capabilities built over a decade of experience and we handle billions of recommendations per year.
* **User context** to ensure that recommendations are timely and relevant to your users. You don’t want to recommend the video that someone just watched or the shirt that someone just added to their cart. Target’s rich user profile can be used in recommendations to ensure personalization.

## Implement Target Recommendations

Start with a strategy.

![Illustration showing recommendations strategy](/help/c-recommendations/assets/intro-5.png)

* **What items do you want to recommend?** First, think about what items you want to recommend. This could be products, videos, or content.
* **Where do you want to show recommendations?** Next, think about where you want to make recommendations. Broadly what channels (web, mobile, in-store, a kiosk, and so forth). What parts of the customer journey will contain recommendations? What pages on your site will contain recommendations?
* **How will you determine if recommendations are successful?** Suppose that you have an experience without recommendations and an experience with recommendations, or you have two different types of recommendations. How would you determine which experience was a better experience for your customers? Some metrics might be more difficult than others to measure. For example, the impact of recommendations on Customer Lifetime Value is often difficult to directly get to. So it is often easier to get to a less abstract metric and one that is more concrete, for example, revenue per visit, average order value, or number of clicks. In some cases you might be looking to minimize a metric, for example, the number of support calls.

After you come up with your strategy, you are ready to start the implementation of [!DNL Target Recommendations].

There are three broad steps involved in creating your recommendations implementation:

![Illustration showing the steps to create your recommendations implementation](/help/c-recommendations/assets/intro-6.png)

1. Teach [!DNL Target] about your context or products.
1. Capture user behavior.
1. Get recommendations with the right context.

### Teach [!DNL Target] about your context or products

When you start with [!DNL Recommendations], you pass information about every item you want to recommend. [!DNL Target] offers several integration options to create your catalog.

![Illustration showing how to teach Target about your context or products](/help/c-recommendations/assets/intro-7.png)

The simplest, and most frequently used method is to send a CSV file on a daily or weekly basis from your product information management system or from your content management system. But you can also pass information on the data layer from your page using the [!DNL Adobe Target] Javascript library, leverage our APIs to pass information directly from your source system, or use our [!DNL Adobe Analytics] integration if you are already passing catalog data to [!DNL Analytics].

Sometimes, you might want to use multiple options together, for example, passing most data daily via a CSV file and passing inventory updates more frequently via an API.

Your IT department will usually be involved in helping set this step up.

Whichever method you choose, you should include metadata about each item in three categories:

![Illustration showing metadata information for your catalog](/help/c-recommendations/assets/intro-8.png)

* Data that you want to display to the user receiving the recommendation. For example, the name of the movie and a thumbnail image URL.
* Data that is useful for applying marketing and merchandising controls. For example, the rating of the movie so that you do not recommend NC-17 movies.
* Data that is useful for determining the similarity of items to other items. For example, the genre of the movie or the actors that are in the movie.

### Capture user behavior

Next, you should add tags or leverage you existing [!DNL Analytics] implementation to track the conversion events (such as views and purchases) that drive [!DNL Target] algorithms.

![Illustration showing how to capture user behavior](/help/c-recommendations/assets/intro-9.png)

You need to ensure that [!DNL Target] is aware of the items that your users are viewing and purchasing. If purchasing isn’t relevant to your context, you might want to track a different type of conversion event, for example, downloading a PDF, completing a survey, subscribing to a newsletter, watching a video, and so forth.

If you are already using [!DNL Target] to run A/B Tests activities on your site, you might have already completed this step. Or if you are already using [!DNL Adobe Analytics] to report on site visits and conversion behavior, you can use [!DNL Analytics] as your behavioral datasource. If not, it’s easiest to set this up using a tag manager such as [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). It’s also possible to send offline or in-app interactions to [!DNL Target] via real-time API.

### Get recommendations with the right context

Pass information about the user and context at the point of interaction to [!DNL Target] to return relevant and personalized recommendations.

![Illustration showing how to get recommendations with the right context](/help/c-recommendations/assets/intro-10.png)

Besides user behavior in aggregate, you need to pass [!DNL Target] the specific context where recommendations are being shown. This includes information about the page and information from the user profile. [!DNL Target] uses this information to make personalized recommendations. For example, on a retail website, you want to know the product and product category that the visitor is currently viewing. You also want to know information about that user (favorite brand, favorite product category, loyalty tier, and so forth). This information is important so that [!DNL Target] can filter items and improve the personalization of recommendations.

## Build your first Recommendations activity

What is a [!DNL Recommendations] activity?

![Illustration showing the parts that make a good recommendations activity](/help/c-recommendations/assets/intro-11.png)

A [!DNL Recommendations] activity is made up of the following components:

* **Audience**: Who should see these recommendations?
* **Criteria**: What items should be recommended?
* **Design**: How should the recommended items be displayed?

![Illustration showing what makes up a recommendations activity: Audiences, Criteria, and Designs](/help/c-recommendations/assets/intro-12.png)

Out of the box, [!DNL Target] includes 14 built-in audiences, 42 built-in criteria, and 10 built-in design templates. You can customize each of these items or add your own. We’ve had previous [webinars about building audiences](https://landing.adobe.com/acs/2018/na/adobe-target/registration.html) in [!DNL Target]. This section focuses on defining the criteria, which define which items will be recommended.

Target uses the concept of the criteria card. A criteria card is like a recipe for personalization.

![Criteria card illustration](/help/c-recommendations/assets/intro-13.png)

It is important to choose or create the right criteria to achieve the personalization results you desire. A criteria is like a funnel that takes you from your entire catalog to your final set of recommendations.

![Funnel illustration](/help/c-recommendations/assets/intro-14.png)

The following sections describe the various parts of this funnel and how they work in [!DNL Target]:

### Static filters (collections and exclusions)

Static filters are broadly applicable rules related to catalog attributes that you don't expect to change frequently.

![Collections and exclusions illustration](/help/c-recommendations/assets/intro-16.png)

For example, in a content context, you might want to include all movies in recommendations, but exclude movies rated NC-17. In a retail context, you might have multiple brands in different parts of the world, but you want to recommend only products available in the United States. You might also want to exclude products from a regional private label.

These are all catalog attributes that are broadly applicable that you might want to use in multiple recommendations and you don't expect them to change frequently.

### Algorithm (recommendation key and logic)

The next step is to choose a recommendation key and logic. This is where you decide what is the basis for your recommendation.

![Algorithm illustration](/help/c-recommendations/assets/intro-17.png)

The first thing you need to choose is the recommendation key. The recommendation key is what you are "looking up" to choose the recommendation. This is what you are basing your recommendation on. 

You might base your recommendation on:

* The item the visitor is currently viewing
* The category the visitor is currently viewing
* The item the visitor last purchased or added to the shopping cart
* A custom attribute related to a visitor or an item

Based on these keys, you then choose the desired recommendation logic:

* Items with similar attributes
* The most-viewed items in a particular category
* Customers who bought this item also bought these items
* A custom attribute

Out of the box, [!DNL Target] includes a portfolio of algorithms.

![Portfolio of algorithms illustration](/help/c-recommendations/assets/intro-15.png)

* **Popularity-based algorithms** include Most Viewed and Top Sellers.
* **Content-based algorithms** include Content Similarity.
* **Item-based collaborative filtering algorithms** include Viewed/Viewed, Viewed/Bought, and Bought/Bought. Note that "bought" can be any conversion.
* **Personalized algorithms** include Recently Viewed, Site Affinity, and profile-enhanced collaborative filtering.
* **Bring-your-own algorithms** let you use your own custom algorithms.

### Online business rules

The last step is applying online business rules. This is where you empower your algorithms with domain knowledge and current context based on what the visitor is doing on your digital property.

![Online-business rules illustration](/help/c-recommendations/assets/intro-18.png)

For example, in the content context, you might want to exclude movies that the visitor has previously watched, recommend movies by the same director, or boost movies in the same genre. In the retail context, you might want to exclude out-of-stock products, show items in a price range of $5 to $500, or boost items from the same brand.

## Demo

After you complete the tasks illustrated in the recommendation funnel describe above, you are left with your final recommendation. To watch an in-product demonstration inside [!DNL Target], the demo begins at 21:00 in the *Adobe Target Basics Webinar*, linked to below.

## Adobe Target Basics Webinar: Introduction to Recommendations {#intro-to-recs}

[Introduction to Recommendations](https://forums.adobe.com/external-link.jspa?url=https%3A%2F%2Fadobecustomersuccess.adobeconnect.com%2Fp8gt31drhs3e%2F%3FOWASP_CSRFTOKEN%3D4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)