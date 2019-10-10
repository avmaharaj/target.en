---
description: The Visual Experience Composer (VEC) for Single Page Apps (SPAs) enables marketers to create tests and personalize content on SPAs in a do-it-yourself fashion without continuous development dependencies. The VEC can be used to create activities on most popular frameworks, such as React and Angular.
keywords: spa vec;react;angular;react.js;spa visual experience composer;spa experience composer options;single page apps;single-page-app;spa;mobile experience options;target view
seo-description: The Visual Experience Composer (VEC) for Single Page Apps (SPAs) in Adobe Target enables marketers to create tests and personalize content on SPAs in a do-it-yourself fashion without continuous development dependencies. The VEC can be used to create activities on most popular frameworks, such as React and Angular.
seo-title: Single Page App (SPA) Visual Experience Composer
solution: Target
title: Single Page App (SPA) Visual Experience Composer
topic: Standard
uuid: 4dcd6d9c-b2e3-4759-a2e0-3696c572faba
---

# Single Page App (SPA) Visual Experience Composer {#single-page-app-spa-visual-experience-composer}

In [!DNL Adobe Target], the [!UICONTROL Visual Experience Composer] (VEC) gives marketers a do-it-yourself capability to create activities and personalize experiences that can be dynamically delivered on traditional Multi Page Applications via Adobe Target's global mbox. However, this relies on retrieving offers on page-load or subsequent server calls, which introduces latency, as shown in the diagram below. This approach does not work well with Single Page Applications (SPAs) because it degrades the user experience and application performance.

![Traditional lifecycle vs. SPA lifecycle](/help/c-experiences/assets/trad-vs-spa.png)

With the newest release, we now introduce the VEC for SPAs. The VEC for SPAs enables marketers to create tests and personalize content on SPAs in a do-it-yourself fashion without continuous development dependencies. The VEC can be used to create [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT) activities on popular frameworks, such as React and Angular.

## Adobe Target Views and Single Page Applications

The Adobe Target VEC for SPAs takes advantage of a new concept called Views: a logical group of visual elements that together make up an SPA experience. A SPA can, therefore, be considered as transitioning through views, instead of URLs, based on user interactions. A View can typically represent a whole site or grouped visual elements within a site. 

To explain further about what Views are, let’s navigate this hypothetical online e-commerce site implemented in React and explore some example Views. Click the links below to open this site in a new browser tab.

**Link: [Home Site](https://target.enablementadobe.com/react/demo/#/)**

![home site](/help/c-experiences/assets/home.png)

When we navigate to the home site, we can immediately see a hero image that promotes an Easter sale as well as the newest products selling on the site. In this case, a View can be defined as the entire home site. This is handy to note as we will expand on this more in the Implementing Adobe Target Views section below.

**Link: [Product Site](https://target.enablementadobe.com/react/demo/#/products)**

![product site](/help/c-experiences/assets/product-site.png)

As we become more interested in the products, we decide to click the Products link. Similar to the home site, the entirety of the products site can be defined as a View. We can name this View "products" just like the path name in `https://target.enablementadobe.com/react/demo/#/products`.

![product site 2](/help/c-experiences/assets/product-site-2.png)

In the beginning of this section, we defined Views as the whole site or even a group of visual elements on the site. As shown above, the four products shown on the site can also be grouped and considered as a View. If we wanted to name this View, we can name it "products".

![product site 3](/help/c-experiences/assets/product-site-3.png)

We decide to click on the Load More button to explore more products on the site. The website URL does not change in this case. But a View here can represent only the second row of products shown above. The View name can be called "PRODUCTS-PAGE-2".

**Link: [Checkout](https://target.enablementadobe.com/react/demo/#/checkout)**

![check-out page](/help/c-experiences/assets/checkout.png)

Because we liked some products shown on the site, we decided to buy a couple. Now, on the checkout site we are given some options to choose normal delivery or express delivery. Because a View can be any group of visual elements on a site, we can name this "View Delivery Preferences". 

Furthermore, the Views concept can be extended much further than this. If marketers want to personalize content on the site depending on which delivery preference is selected, a View can be created for each delivery preference. In this case, when we select Normal Delivery, the View can be named "Normal Delivery". If Express Delivery is selected, the View can be named "Express Delivery". 

Now, marketers might want to run an A/B Test to see whether changing the color from blue to red when Express Delivery is selected can boost conversions as opposed to keeping the button color blue for both delivery options. 

## Implementing Adobe Target Views

Now that we have covered what Adobe Target Views are, we can leverage this concept in Target to empower marketers to run A/B and XT tests on SPAs via the VEC. This will require a one-time developer setup. Let’s go through the steps to set this up.

1. Install at.js 2.x.

   First, we need to install at.js 2.x. This version of at.js was developed with SPAs in mind. Previous versions of at.js and mbox.js do not support Adobe Target Views and the VEC for SPA.

   ![Implementation details dialog box](/help/c-experiences/assets/imp-200.png)

   Download the at.js 2.x via the Adobe Target UI located in [!UICONTROL Setup > Implementation]. at.js 2.x can also be deployed via [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). However, the Adobe Target Extensions are not currently up to date and supported.

1. Implement at.js 2.x’s newest function: [triggerView()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) on your sites.

   After defining the Views of your SPA where you want to run an A/B or XT test, implement at.js 2.x’s `triggerView()` function with the Views passed in as a parameter. This allows marketers to use the VEC to design and run the A/B and XT tests for those Views defined. If the `triggerView()` function is not defined for those Views, the VEC will not detect the Views and thus marketers cannot use the VEC to design and run A/B and XT tests.

   **`adobe.target.triggerView(viewName, options)`**

   |Parameter|Type|Required?|Validation|Description|
   | --- | --- | --- | --- | --- |
   |viewName|String|Yes|1. No trailing spaces.<br>2. Cannot be empty.<br>3. View name should be unique for all pages.<br>4. **Warning**: View name should not start or end with '`/`'. This is because the customer would generally extract the View name from URL path. For us, "home" and "`/home`" are different.<br>5. **Warning**: Same view should not be consecutively triggered multiple times with the  `{page: true}` option.|Pass in any name as a string type that you want to represent your View. This View name displays in the [!UICONTROL Modifications] panel of the VEC for marketers to create actions and run their A/B and XT activities.|
   |options|Object|No|||
   |options > page|Boolean|No||**TRUE**: Default value of page is true. When `page=true`, notifications will be sent to the Edge servers for incrementing impression count.<br>**FALSE**: When `page=false`, notifications will not be sent for incrementing impression count. This should be used when you want to only re-render a component on a page with an offer.|

   Now let’s go through some example use cases on how to invoke the `triggerView()` function in React for our hypothetical e-commerce SPA:

   **Link: [Home Site](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   As marketers, if we want to run A/B tests on the whole home site, then we might want to name the view "home" that can be extracted from the URL:

   ```
   function targetView() {
     var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash

     viewName = viewName || 'home'; // view name cannot be empty

     // Sanitize viewName to get rid of any trailing symbols derived from URL
     if (viewName.startsWith('#') || viewName.startsWith('/')) {
       viewName = viewName.substr(1);
     }
  
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }

   // react router v4
   const history = syncHistoryWithStore(createBrowserHistory(), store);
   history.listen(targetView);

   // react router v3
   <Router history={hashHistory} onUpdate={targetView} >
   ```

   **Link: [Products Site](https://target.enablementadobe.com/react/demo/#/products)**

   Now, let’s look at an example that is a little bit more complicated. Let’s say as marketers, we would like to personalize the second row of the products by changing the price label color to red after a user clicked on the Load More button.

   ![react products](/help/c-experiences/assets/react4.png)

   ```
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }

   class Products extends Component {
     render() {
       return (
         <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
       );
     }

     handleLoadMoreClicked() {
       var page = this.state.page + 1; // assuming page number is derived from component’s state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **Link: [Checkout](https://target.enablementadobe.com/react/demo/#/checkout)**

   ![react checkout](/help/c-experiences/assets/react6.png)

   If marketers want to personalize content on the site depending on which delivery preference is selected, a View can be created for each delivery preference. In this case, when we select Normal Delivery, the View can be named "Normal Delivery". If Express Delivery is selected, the View can be named "Express Delivery". 

   Now, marketers might want to run an A/B test to see whether changing the color from blue to red when Express Delivery is selected can boost conversions as opposed to keeping the button color blue for both delivery options.  

   ```
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }

   class Checkout extends Component {
     render() {
       return (
         <div onChange={this.onDeliveryPreferenceChanged}>
           <label>
             <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
             <span> Normal Delivery (7-10 business days)</span>
           </label>

           <label>
             <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
             <span> Express Delivery* (2-3 business days)</span>
           </label>
         </div>
       );
     }
     onDeliveryPreferenceChanged(evt) {
       var selectedPreferenceValue = evt.target.value;
       targetView(selectedPreferenceValue);
     }
   }
   ```

1. Launch A/B or XT activities via the VEC.

   When `adobe.target.triggerView()` is implemented on your SPA with View names passed in as parameters, the VEC will be able to detect these views and allow users to create actions and modifications for their A/B or XT activities.

   >[!NOTE]
   >
   >The VEC for SPAs is really the same VEC that you use on regular web pages, but some additional capabilities are available when you open a single page app with `triggerView()` implemented.

  There are two major improvements to the [Modifications](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) panel and Actions for the VEC that allow the VEC to work well with SPAs.

   **Modifications Panel**

   The [!UICONTROL Modifications] panel, as shown below, captures the actions created for a particular view. Notice that all actions for a View are grouped under that View.

   **Actions** 

   Clicking an action highlights the element on the site where this action will be applied. Each VEC action created under a View has the following icons, as shown below: Information, Edit, Clone, Move, and Delete.

   ![Modifications](/help/c-experiences/assets/modifications.png)

   The following table describes each action:

   |Page|Description|
   | --- | --- |
   |Information|Displays the details of the action.|
   |Edit|Allows you to edit the properties of the action directly.|
   |Clone|Clone the action to one or more Views that exist on the [!UICONTROL Modifications] panel or to one or more Views that you have browsed and navigated to in the VEC. The action doesn’t have to necessarily exist in the [!UICONTROL Modifications] panel.<br>**Note**: After a clone operation is made, you need to navigate to the View in the VEC via [!UICONTROL Browse] to see whether the cloned action was a valid operation. If the action cannot be applied to the View, you will see an error.|
   |Move|Moves the action to a Page Load Event or any other View that already exists in the modifications panel.<br>[!UICONTROL Page Load Event] – any actions corresponding to the page load event are applied on the initial page load of your web application.<br>**Note** After a move operation is made, you need to navigate to the View in the VEC via Browse to see whether the move was a valid operation. If the action cannot be applied to the View, you will see an error|
   |Delete|Deletes the action.|

   >[!NOTE]
   >
   >You can perform many actions before the page loads in the VEC, or even if the page fails to load altogether. Actions that cannot be edited before the site loads are disabled in the UI.

   **Example 1**

   Let’s refer to the example above where we created a Home view. Our goal is two-fold for this view:

   1. Change the Add to Cart and the Like button to a lighter blue color. This should be in a “Page Load” because we are changing components of the header.
   1. Change the "Latest Products for 2019" label to "Hottest Products for 2019" with the text color changed to purple.

   To execute these goals, in the VEC, click [!UICONTROL Compose] and apply those changes on the Home view.

   ![Example 1](/help/c-experiences/assets/example1.png)

   **Example 2**

   Let’s refer to the example above where we created a PRODUCTS-PAGE-2 view. Our goal is to change the "Price" label to "Sale Price" with the label color as red.

   1. Click [!UICONTROL Browse], then click the [!UICONTROL Products] link at the header. 
   1. Click [!UICONTROL Load More] once to get to the second row of products. 
   1. Click [!UICONTROL Compose].
   1. Apply actions to change the text label to "Sale Price" and the color to red.

   ![Example 2](/help/c-experiences/assets/example2.png)

   **Example 3**

   Lastly, as mentioned before, Views can be defined at a granular level. Views can be a state or even an option from a radio button. Previously we have created Views as CHECKOUT-EXPRESS and CHECKOUT-NORMAL. Our goal is to change the button color to red for the CHECKOUT-EXPRESS view.

   1. Click [!UICONTROL Browse].
   1. Add couple of products to the cart.
   1. Click the cart icon at the top right corner.
   1. Click Checkout your Order.
   1. Click on the Express Delivery radio button.
   1. Click [!UICONTROL Compose].
   1. Change the "Pay" button to read "Complete the Order" button and change the color to red.

   ![Example 3](/help/c-experiences/assets/example3.png)

   >[!NOTE]
   >
   >The CHECKOUT-EXPRESS view will not show up in the modification panel until you click the Express Delivery radio button. This is because the `triggerView()` function is triggered when the Express Delivery radio button is selected and this is only when VEC knows that there is a View to show in the modification panel.

## Deep dive into at.js and SPAs

**How can I retrieve views for the latest audience data hydrated by actions after the initial page load on my SPA?**

The typical workflow of at.js 2.x is when your site loads, all of your views and actions are cached so that subsequent user actions on your site won’t trigger server calls to retrieve offers. If you want to retrieve views depending on the most up-to-date profile data that might have been updated depending on subsequent user actions, you can call `getOffers()` and `applyOffers()` with the latest audience user or profile data passed.

For example, consider that you are a telecom company and you have an SPA that uses at.js 2.x. As a business, you want to achieve the following objectives:

* For a logged out or anonymous user, show the latest company promotion, such as showing a “First month free” hero offer on `http://www.telecom.com/home`.
* For a logged in user, show an upgrade promotional offer for users whose contracts are coming up, such as “You are eligible for a free phone!” on `http://www.telecom.com/loggedIn/home`.

Now, your developers name views and call `triggerView()` in the following manner:

* For `http://www.telecom.com/home` the view name is "Logged Out Home"
  * `triggerView(“Logged Out Home”)` is invoked.
* For `http://www.telecom.com/loggedIn/home` the view name is "Logged In Home"
  * `triggerView(“Logged In Home”)` is invoked on route change.

Your marketers then run the following A/B activities through the VEC:

* A/B activity with the “First Month Free” offer for audiences with the parameter “`loggedIn= false`” to be shown in `http://www.telecom.com/home`, where the view name is Logged Out Home.
* A/B activity with the “You are eligible for a free phone!” offer for audiences with the parameter “`loggedIn=true`” to be shown in `http://www.telecom.com/loggedIn/home`, where the view name is Logged In Hero Offer.

Now, lets consider this user flow:

1. An anonymous logged-out user lands on your page.
1. Because you are using at.js 2.x, you pass in the parameter “`loggedIn = false`” on page-load to retrieve all views present in active activities that qualify for when the audience has parameter “`loggedIn = false`”. 
1. at.js 2.x then retrieves the Logged Out Home view and action to show the “First Month Free” offer and stores it in cache.
1. When `triggerView(“Logged Out Home”)` is invoked, the “First Month Free” offer is retrieved from cache and the offer is shown without a server call.
1. The user now clicks “Log in” and provides his or her credentials. 
1. Because your website is an SPA, you do not conduct a full page load and instead route your user to `http://www.telecom.com/loggedIn/home`.

Now, here is the problem. The user logs in and we encounter `triggerView(“Logged In Home”)` because we placed this code on route change. This tells at.js 2.x to retrieve the view and actions from cache, but the only view that exists in cache is Logged Out Home. 

So, how can we then retrieve our Logged In View and show the “You are eligible for a free phone!” offer? And since all subsequent actions on your site will be from a logged-in-user perspective, how can you make sure all subsequent actions result in personalized offers for logged-in users?

You can use the new `getOffers()` and `applyOffers()` functions supported in at.js 2.x:

```
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

Pass the response of `getOffers()` to `applyOffers()` and now all views and actions associated with “loggedIn = true” will update the at.js cache. 

In other words, at.js 2.x supports a way to retrieve views, actions, and offers with the most up-to-date audience data in an on-demand fashion.

**Does at.js 2.x support A4T for Single Page Applications?**

Yes, at.js 2.x supports A4T for SPA via the `triggerView()` function given that you have implemented Adobe Analytics and the Experience Cloud Visitor ID Service. See the diagram below with step-by-step descriptions.

![Target Flow](/help/c-experiences/assets/atjs-spa-flow.png)

|Step|Description|
| --- | --- |
|1|`triggerView()` is called in the SPA to render a view and apply actions to modify visual elements associated to the view.|
|2|Targeted content for the view is read from the cache.|
|3|Targeted content is revealed as quickly as possible without flicker of default content.|
|4|Notification request is sent to the Target Profile Store to count the visitor in the activity and increment metrics.|
|5|Analytics data sent to Data Collection Servers.|
|6|Target data is matched to Analytics data via the SDID and is processed into the Analytics reporting storage. Analytics data can then be viewed in both Analytics and Target via A4T reports.|

>[!NOTE]
>If you don’t want to send notifications to Adobe Analytics for impression counting every time a view is triggered, pass in `{page: false}` to the `triggerView()` function so that impression counting is not inflated when a view is triggered multiple times for a component that re-renders constantly. For example:
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## Supported activities

|Activity Type|Supported?|
| --- | --- |
|[A/B Test](/help/c-activities/t-test-ab/test-ab.md)|Yes|
|[Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md)<br>in A/B Test and Experience Targeting (XT) activities|Yes|
|[Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)|Yes|
|[Experience Targeting](/help/c-activities/t-experience-target/experience-target.md)|Yes|
|[Multivariate Test](/help/c-activities/c-multivariate-testing/multivariate-testing.md)|No|
|[Auto-Target](/help/c-activities/auto-target-to-optimize.md)|No|
|[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md)|No|
|[Recommendations](/help/c-recommendations/recommendations.md)|No|

**If we installed at.js 2.x and implemented `triggerView()` on our sites, how do we run Auto-Target A/B activities because the SPA VEC doesn't support Auto-Target?**

If you want to use Auto-Target A/B activities, you can move all of your actions to be executed on Page Load Event in the VEC. Hover over each action, and click the [!UICONTROL Move to Page Load Event] button. After this is done, in the next step, you can select Auto-Target for the traffic allocation method.

## Supported integrations

|Integration|Supported?|
| --- | --- |
|[Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md)|Yes|
|[Experience Cloud Audiences](/help/c-integrating-target-with-mac/mmp.md)|Yes|
|[Customer Attributes](/help/c-target/c-visitor-profile/working-with-customer-attributes.md)|Yes|
|[AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md)|Yes|

## Supported features {#supported-features}

|Feature|Supported?|
| --- | --- |
|[Workspaces and Properties](/help/administrating-target/c-user-management/property-channel/property-channel.md)|Yes|
|[QA Links](/help/c-activities/c-activity-qa/activity-qa.md)|Yes|
|[Form-based Experience Composer](/help/c-experiences/form-experience-composer.md)|No|
|[Custom Code](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)|Yes|
|[VEC options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)|All|
|[Click-tracking](/help/c-activities/r-success-metrics/click-tracking.md)|Yes|
|[Multi-Activity Delivery](/help/c-experiences/c-visual-experience-composer/multipage-activity.md)|Yes|

## Page Delivery settings for the SPA VEC {#page-delivery-settings}

[!UICONTROL Page Delivery] settings let you configure rules to determine when a Target activity should qualify and execute for an audience. 

To access the [!UICONTROL Page Delivery] options from within the VEC's three-part guided activity-creation workflow, from the **[!UICONTROL Experiences]** step, click **[!UICONTROL Configure]** (the gear icon) > **[!UICONTROL Page Delivery]**.

![Page Delivery options dialog box](/help/c-experiences/assets/page-delivery.png)

For example, as defined by the [!UICONTROL Page Delivery] settings shown above, a Target activity qualifies and executes when a visitor lands directly on `https://www.adobe.com` *or* when a visitor lands on any URL that contains `https://www.adobe.com/products`. This works perfectly for any multi-page application in which every interaction with the page invokes a page reload, for which at.js retrieves the activities that qualify for the URL that the user navigates to.

However, because SPAs work differently, the [!UICONTROL Page Delivery] settings must be configured in a way that allows all actions to be applied to the Views as defined in the SPA VEC activity. 

### Example use-case

Consider this example use-case:

![SPA VEC Modifications panel](/help/c-experiences/assets/page-delivery-example.png)

The following changes were made:

* Changed the background color in the Home view, which is located under the URL: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* Changed the button color in the Products view, which is located under the URL: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).

With the example above in mind, what would happen when we configure [!UICONTROL Page Delivery] settings to only include: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/) in an SPA with at.js 2.*x*?

![Page Delivery dialog box](/help/c-experiences/assets/spa-page-delivery.png)

The following illustration shows the Target Flow -  Page Load request in at.js 2.*x*:

![Target Flow - at.js 2.0 Page Load Request](/help/c-experiences/assets/page-load-request.png)

**User Journey #1**

* A user navigates directly to [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* at.js 2.*x* makes a query to the Edge to see if any activity needs to execute for the URL: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* In step 6, the Target Edge returns the actions for the Home and Products view so that they are cached within the browser.

**Result**: The user sees the green background color in the Home view. When the user then navigates to [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products), the blue background color of the button is seen because the action is cached in the browser under the Products view. 

Note: The user navigating to [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products) did not trigger a page load.

**User Journey #2**

* A user navigates directly to [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* at.js 2.*x* makes a query to the Edge to see if any activity needs to execute for the URL: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* There are no activities qualified for [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Because there are no activities qualified, there are no actions and Views to be cached for at.js 2.*x* to trigger from.

**Result**: Even if you have defined `triggerView()` for the Products View and made an action to the Products View through the SPA VEC, you will not see the expected action since you did not create a rule that included [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products) in the Page Delivery settings.

### Best Practice

You can see that managing the user journey can be quite difficult as users can land on any URL of your SPA and navigate to any other page. Therefore, it is best to specify a Page Delivery rule that includes the base URL so that it includes your entire SPA. In this way, you don’t need to think about all the different journeys and paths that a user might take to get to a page on which you want to show an A/B Test or Experience Targeting (XT) activity.

For example, in order to resolve the issue faced above, we can specify the base URL in the Page Delivery settings as such:

![Page Delivery dialog box](/help/c-experiences/assets/conclusion.png)

This ensures that wherever a visitor lands on the SPA and navigates to either the Home or Page View will see the actions applied.

Now, whenever you add an action to a View in the SPA VEC, we will show you the following pop-up message to remind you to think about the [!UICONTROL Page Delivery] rules. 

![Page Delivery Settings message](/help/c-experiences/assets/pop-up-message.png)

This message displays when you add the first action to a View for every new activity you create. This message helps ensure that everyone in your organization learns how to apply these [!UICONTROL Page Delivery] rules correctly.

## Training video: Using the VEC for SPAs in Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

See [Using the Visual Experience Composer for Single Page Application (SPA VEC) in Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) for more information.
