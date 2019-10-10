---
description: Information about how to safely deploy at.js to a non-production environment.
seo-description: Information about how to safely deploy at.js to a non-production environment.
seo-title: Deploy at.js to a Non-Production Environment
title: Deploy at.js to a Non-Production Environment
uuid: 7f1adc43-35b4-442c-bb06-feab60604a87
---

# Deploy at.js to a non-production environment{#deploy-at-js-to-a-non-production-environment}

Information about the techniques to safely deploy at.js to a non-production environment.

## Deploy to DTM Staging

If you use DTM, you can easily save at.js in your Adobe Target Tool configuration.

After you have saved the library, use the DTM Switch tool to test it against your production code. This will also make it easy for your Adobe consultants to support you.

For more information, see [Option 3: Implement Target Manually with the Target JavaScript Library Hosted by DTM](https://docs.adobe.com/content/help/en/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html) in the *Best Practices for Implementing Adobe Target using Dynamic Tag Management* guide.

## Use "Requestly" Chrome extension to map to another file

>[!NOTE]
>
>In addition to the following information, you can use the [Adobe Target VEC Helper browser extension](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) for Google Chrome.

[Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) is a free Chrome extension that lets you redirect requests to an alternate URL.

You deploy at.js to a URL, and then use Requestly to map your current mbox.js file URL to the new at.js URL. Then, any time your website tries to load mbox.js, it loads at.js instead. This approach also make it easier for Adobe to provide support.

## Deploy to a development, staging, or QA environment

If you host mbox.js in your codebase and are able to easily make updates to your code environments, deploy at.js to one of your lower environments.

For better support from Adobe, deploy the file to an environment that Adobe can access.

## Use Charles or Fiddler to map to a local file

[Charles Web Debugging Proxy](https://www.charlesproxy.com/) is an application available for Mac and Windows whose Map Local feature can be used to map the loading of your production mbox.js file to a local copy of at.js. A free trial version is available for download for Mac and Windows.

[Fiddler](https://www.telerik.com/fiddler) is a similar tool available as a free download for Windows.

## Deploy to another tag manager environment

If you are using another tag manager, it probably has a way to deploy at.js safely without impacting your production traffic.