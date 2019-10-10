---
description: Following best practices can help make your experiences work as expected. There are also other tips and limitations that you should be aware of when using the Visual Experience Composer (VEC).
keywords: visual experience composer;visual experience composer best practices;visual experience composer limitations;visual experience composer caveats;vec best practices;vec
seo-description: Following best practices can help make your experiences work as expected. There are also other tips and limitations that you should be aware of when using the Visual Experience Composer (VEC).
seo-title: Visual Experience Composer Best Practices and Limitations
solution: Target
title: Visual Experience Composer Best Practices and Limitations
topic: Classic
uuid: 8d1d199b-b3d7-4edb-ba05-bd97372a0b9e
---

# Visual Experience Composer Best Practices and Limitations{#visual-experience-composer-best-practices-and-limitations}

Following best practices can help make your experiences work as expected. There are also other tips and limitations that you should be aware of when using the Visual Experience Composer (VEC).

By following these best practices, you are less likely to encounter unexpected problems with the experiences you design.

## Best Practices {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

**For mbox.js version 57 and later, and for at.js, place the mbox.js or at.js reference at the top of the `<head>` section of your page.**

If you also use the Visitor API Service, place the visitor API script above mbox.js or at.js.

**For versions of mbox.js before version 57, place the mbox.js code as low as possible in the `<head>` section of your page.**

Place the mbox.js at the end of the `<head>` section, with no additional declarations after it. Otherwise, any script or link tags will be moved into the `<body>` section.

**You can enable the Enhanced Experience Composer at the account level (enabled for all activities created in the account) or at the individual activity level.**

To enable the Enhanced Experience Composer at the account level, click [!UICONTROL Setup > Preferences], then toggle the switch to the On position.

To enable the Enhanced Experience Composer at the activity level while creating an activity in the Visual Experience Composer, click [!UICONTROL Configure > URL], then toggle the switch to the On position.

**You can whitelist certain IP addresses if the Enhanced Visual Experience Composer won't load on secure pages on your site.**

Problems loading the Enhanced Visual Experience Composer can be resolved by whitelisting the following IP addresses. These IP addresses are for Adobe's server used for the Enhanced Experience Composer proxy. They are only required for activity editing. Visitors to your site do not need these IP addresses whitelisted.

United States: 52.55.99.45, 54.80.158.92, and 54.204.197.253

Europe, Middle East, and Africa (EMEA): 52.51.238.221, 52.210.199.44, and 54.72.56.50

Asia-Pacific (APAC): 52.193.67.35, 54.199.198.109, and 54.199.241.57

**Use unique IDs for top-level elements and any other elements that could be good testing/targeting candidates.**

Anything immediately inside the body element should have a unique ID. If new elements are injected into the body and code moves around, at least the parent elements have an easier way to be recognized.

Adobe Target does not require IDs, but using IDs increases the reliability of experiences created with the experience composer. Target uses CSS selectors to modify your content when the experience is delivered. When you edit an experience, the Visual Experience Composer anchors the selector to the closest ancestor with a non-null id attribute to the HTML element being modified. It is, therefore, not advisable to use any mechanism, including JavaScript libraries, that sets or modifies HTML ID attributes. Although those IDs might be available to the Target experience composer for activity creation, if JavaScript modifies IDs, the ID that was used when the experience was created might not be available when the experience runs. If an ID is not available, the selector anchored to the ID fails.

**Name CSS classes so they are easily identifiable.**

When editing CSS classes in the Visual Experience Composer, it is helpful to make the classes easy to identify by using descriptive class names. This helps to ensure that you edit the right CSS classes, and your pages appear as expected.

Don't use the `!important` CSS property when hiding or removing elements.

If the 1!important1 CSS property is present, changes made by target.js during delivery will be overridden by the site's CSS rules.

**Avoid using HTML tables for page layouts.**

Target Standard and Premium uses JavaScript to format a page. It is difficult to modify table-based layouts with JavaScript. Also, table-based layouts might not display the same way in all browsers. For best results, use CSS to create page layouts.

**Minimize the use of iFrames.**

It is a good practice to minimize the use of iFrames, to simplify page and test management. The visual experience composer can apply some actions within an iFrame, but some actions, such as resizing, do not work properly. It is difficult to manage and resize pages that use multiple iFrames. As a result, testing iFrame-heavy pages can create problems.

**Attempt to arrange all dynamic DOM modifications as soon after DOM ready as possible.**

If your modifications fail to apply before the experience application by target.js, content delivery could be broken. This happens only when there is a DOM change in the hierarchy of a targeted element.

**Use only plain text or an image tag in your anchor elements.**

`<a>Anchor Text</a>`

OR

`<a href=""> <img src=""> </img> </a>`

**Avoid block-level elements inside an inline element.**

Block-level elements should not be used inside inline elements like anchor, span, and so on. Doing so causes inline elements to lose their height and width, so the overlay tool in Visual Experience Composer might not work as expected.

**Don't use the base tag in your website to resolve URLs and links.**

The Visual Experience Composer manipulates the website behind the scenes, using a proxy server that updated the links. If you add a base tag, the URLs used by the proxy server are resolved again by the browser and appear broken.

**Using EDIT HTML to manipulate DOM structure can break selectors.**

For example, if you have taken two actions:

* Added a class to Element 1
* Edited the HTML for Element 1

Each change creates a new element in the Visual Experience Composer. Because the second action modifies Element 1,if you delete Element 1, the second action no longer has anything to modify, so the change no longer works.

In other words, if you add an element with text, then in a separate action you edit that element with different text, the code editor shows both actions as separate elements. When you edited the element, you created a new element that modifies the original one you created, containing the edited text. If you then delete the original element, the edited text won't be able to find the element that was edited, and will not display. The second element remains in the list of elements, but it does not affect the page because the element it changes no longer exists.

See [Element Selectors Used in the Visual Experience Composer](../../c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) .

**Use `<b>` and `<i>` tags when styling text elements with the rich-text editor.**

* For bold text, use `<b>` rather than `<strong>`.
* For italic text, use `<i>` rather than `<em>`.

`<strong>` and `<em>` tags might cause unexpected results.

**Be careful when removing form fields.**

Certain form fields might be mandatory for submission. Removing those form fields could impact submissions.

**Do not include `mboxCreate` inside scripts.**

Because `mboxCreate` uses `document.write`, it is not recommended to include `mboxCreate` in scripts. Instead, use `mboxDefine` and `mboxUpdate` for the same purpose.

**Don't update an html snippet using Target Standard if it requires JavaScript code for its initialization.**

When an action (Edit HTML) is performed on page components (such Sliders, Carousels and so on), delivery might appear broken. The Visual Experience Composer performs the action after the page component has been instantiated by JavaScript.

However, when the content of the page is delivered to visitors, the action is applied before instantiation of the component. Because of this, this component's functionality may or may not break at the time of delivery. Functionality depends on the nature of the script used on his page to define the component.

If you test for delivery and it works the first time, it is not guaranteed that it will continue working. There may (or may not) be a race condition.

* If there is a race condition, delivery will work intermittently.
* If there is no race condition, it will always work.

Test your page multiple times to make sure delivery works as expected.

**Don't use a base tag in your website to resolve URLs and links.**

When you use the Enhanced Experience Composer, the website is manipulated behind the scenes by a proxy server that updates all link urls to make them work in the proxy. If you add a base tag, all these URLs are resolved by the browser so they appear broken.

**Important text on the site that might be used for targeting should be kept in HTML code within an element.**

For example, you cannot target Shopping Cart text in the VEC if your code is like the following:

```
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
   Shopping Cart: 
   <span id="HeaderCartQtyTotal">
      0 
  </span> 
  Items 
  <span id="HeaderCartPriceTotal"></span> 
</a>
```

In this example, the entire anchor element is selected in the VEC, which adversely affect other elements if targeting is performed.

**Don't use `top` or `self` variables in JavaScript code.**

When the Enhanced Experience Composer is enabled, the value of the top and self variables are updated to disable iframe busting. Use an X-frame-options header to add iframe busting instead of custom JavaScript codes.

**Always test your website if parameters are added when loading the page.**

For example, to open www.abc.com, the following url parameters are used:

`www.abc.com?mboxEdit=1&mboxDisable=1`

These parameters enable editing in an iframe.

Make sure your website loads as expected after adding parameters like these.

**Make sure your page opens as expected in an iframe.**

Turn OFF iframe busting techniques on your website and check whether it opens as expected within an iframe on a dummy page. For example:

```
<!DOCTYPE 
<html> 
<html> 
<head> 
  <meta charset="utf-8"> 
  <meta name="viewport" content="width=device-width"> 
  <title>JS Bin</title> 
</head> 
<body> 
  <iframe src="https://www.homedepot.com"</iframe> 
</body> 
</html>
```

## Caveats {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Consider the following caveats when using the Visual Experience Composer to design your activity.

**The Move feature does not support z-index.**

Because there is no z-index functionality, the moved element can't be moved on top of another element. See [Limitations](../../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) for more details.

**Rearranging elements affects click tracking.**

If an element marked for click tracking is rearranged, the paths of the rearranged elements are changed. As a result, the element in the location where the original element was before it was rearranged is the one whose clicks are tracked.

This occurs because both the code to deliver the activity content and the code to track clicks is included in one piece of code that is delivered to the page. If you browse to a different page and set up click tracking, then the activity content code and the click tracking code are delivered to that page. If the click-tracking page has a similar page structure to the page where the test is run, then the test content might also appear on the click-tracking page.

**Inserting an element might not work in a `<div>` that is an mbox.**

If an mbox contains an offer, inserting an element may appear as insertBefore and not insertAfter, if the mbox is implemented incorrectly.

**When editing both a parent and child element, edit the parent first.**

If you swap an image action on an element, then edit the text or HTML on its parent element, delivery issues can occur. The best workflow is to edit the parent element before swapping the image on the child element.

**Cannot select page element that includes an mbox as a child element.**

For example, if your page contains:

```
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

The outer div should not be selected in an experience because the mbox hardcoded in the page still makes a call to Target and receives a response. This response interferes with the response intended for the larger page element.

**Proxy IPs may be blocked in customers environment.**

If you are using Enhanced Experienced Composer on a non-live site, such as a staging environment, you might see timeouts and access denied errors if your site blocks RIPs.

**When adding multiple pages, both the experience rail and page rail are opened at the same time. This eventually decreases the width for the Visual Experience Composer to display the site for optimizations. As a result, reflowable sites might start to appear differently than expected in the reduced space.**

The workaround is to collapse the experience rail and page rail by clicking the left chevron icons on top.

## Limitations {#section_F33C2EA27F2E417AA036BC199DD6C721}

**Move feature**

An element cannot be moved outside a container that is followed by a CSS property.

**Only swap offers are available on mboxes.**

Actions such as Edit Class and Rearrange are not allowed inside an mbox. Mbox content is served by mbox.js.

**You should not rearrange and move the same element.**

If an element has been moved to another location, and you select the parent container and try to rearrange the child elements, the moved element is not affected and remains where it is. The rearrangement might not appear as desired.

**Swap Image Action does not work on an Image in a carousel.**

If, for example, your page contains a carousel with six images and you want to swap an image with the second image of the carousel, the Swap Image action won't work.

The workaround is to select the parent container and use the Edit HTML action to edit the HTML of the carousel to update the image source of the desired image.

**Images cannot be resized in an mbox.**

If you swap an image in an mbox element, then try to resize that image according to the mbox element size, the resizing is not permitted.

**After you swap an image, you cannot select the Edit action.**

After you swap the image, you cannot edit the Scene7 URL.

**HTML elements with external source cannot be edited.**

For example: Video, audio tags, embed, iFrames, frames.

**Click tracking does not work for anchor elements that contain anything other than plain text or image tags.**

For example, click tracking does not work if the element contains JavaScript.

**Pages must accept URL parameters for the Visual Experience Composer to work.**

Some sites strip any URL parameters for their pages. However, the Visual Experience Composer requires those parameters.

**While using a script as part of html, any variables and functions that are accessed from outside should be declared under window namespace.**

The script is executed within the scope of target.js after the page loads. Therefore, any variable or function that is declared locally is not accessible from outside the script block.

*Incorrect:*

```
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*Correct:*

```
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

**Inserting an image from the Content library (Scene7) and editing the HTML breaks the image url.**

Add an anchor element inside the 'customHeaderMessage' div with some dummy text:

```
<a href="#"> 
<span> Dummy text </span>
</a>
```

Select this div using the Insert Element action to insert a image as a sibling of this dummy text div. 

After image insertion, it looks like:

```
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Remove the dummy text span.

**The customCode action in the Visual Experience Composer does not work with Internet Explorer 8.**

Due to IE8 limitations when handling script content, target.js does not support this in IE8. As a workaround, if the page contains jQuery and is exposed on the window object globally, target.js can use deliver the customCode action. Ensure that window.jQuery and window.jQuery.fn.prepend are defined.

**Click tracking is supported only on the page on which experiences are created or on the redirected page.**

Although Browse mode is available in Click Track VEC, it can't be used to add click tracking on a page.
