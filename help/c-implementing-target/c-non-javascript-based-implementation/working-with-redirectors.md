---
description: Use a Redirector similarly to how you use an mbox in your tests.
keywords: Implementation;mbox.js non javascript;redirector;costs per click;revenue per click
seo-description: Use a Redirector similarly to how you use an mbox in your tests.
seo-title: Work with redirectors
solution: Target
subtopic: Getting Started
title: Work with redirectors
topic: Standard
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
---

# Work with redirectors{#work-with-redirectors}

Use a Redirector similarly to how you use an mbox in your tests.

Redirectors are created with a special Redirector URL that loads a Redirector mbox (Redirector) into your account. Use this Redirector similarly to how you use an mbox in your tests. Submit the Redirector URL to your Ad Network as the ad's destination link.

Use the Redirector to do the following:

* Track clicks from your display ads to your site 
* Create a single centralized report to track clicks to display ads on multiple ad networks 
* Vary display ad destinations

  For example the same banner lands on your home page, category page and product page. 

* Find which landing page leads to the most conversions

For help deciding the right setup see [Non-JavaScript-Based Implementations](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4). 

## Create a Redirector {#task_76608B0F73FC45C4A9F125B894DCF821}

Before you can use a redirector, you must create it.

1. Determine the ad's destination variations, including the default destination.
1. Create the Redirector URL.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Where `yourclientcode` is your company's client code. Your company's client code is all lower case and has no special characters.

     * **at.js**: Your client code is available at the top of the [!UICONTROL Setup > Implementation > Edit at.js Settings] page of the [!DNL Target] interface.

     * **mbox.js**: Your client code is available at the top of the [!UICONTROL Setup > Implementation > Edit Mbox.js Settings] page.

   * `redirectorlink_456` is the name of the Redirector mbox that appears in your account to use in campaigns and tests.

      Redirectors function differently from other mboxes, but appear just as any other mbox in your account. Name the redirector so it is easily distinguished them from the standard type mboxes in your account.  As best practice, begin the mbox name with 'redirectorlink'.

   * Where `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` is the default destination.

     This must be URL encoded and must be an absolute reference. You can use the [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) to quickly encodes your URLs.|


1. Validate the Redirector.
   1. Insert the Redirector URL into a browser and refresh.
   1. Log in to your account, refresh your mbox list and verify the new Redirector is listed as an mbox.
1. If you will test different destinations for one ad, create [Redirect Offers](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) for each version.
1. Create the campaign.

   See [Non-JavaScript-Based Implementations](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) for the right setup to meet your goals. 
1. Complete QA on the campaign.

   Create a dummy page with an `<a href>` containing the Redirector URL. Example:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Verify that all experiences, default content, and reports act as expected on all browser types, for all of your environments.

   >[!NOTE] {class="- topic/note "}
   >
   >* Redirectors are not supported by Offer Preview or Browse for mbox. Preview experiences directly in a browser. 
   >* `mboxDebug` does not work with Redirectors . 

1. Submit the full Redirector URL to your Display Ad Network as the ad destination.

## Use a Redirector to Pass Costs per Click and Revenue Per Click {#concept_3078EF48E9C44B34992D62AAB9628853}

Information about using a redirector to pas costs per click and revenue per click.

### Passing Costs per Click {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Use a redirector to pass the costs per click.

>[!NOTE]
>
>Best practice is to determine the cost value using the **Score per visit** engagement metric.

Add `&mboxPageValue=-value` to the URL. Note the negative value.

Example: For a .10 cents cost per click:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### Passing Revenue per Click {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Use a redirector to pass the revenue per click.

>[!NOTE]
>
>Best practice is to determine the revenue value using the **Score per visit** engagement metric.

Add `&mboxPageValue=value` to the URL.

Example: For a .10 cents revenue per click.

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```