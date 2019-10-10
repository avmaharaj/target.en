---
description: Information about Content Security Policy (CSP) directives you should add when using Adobe Target at.js 2.1 or later.
keywords: content security policy;csp;at.js;whitelist;flicker;pre-hide;pre-hiding;prehiding
seo-description: Information about Content Security Policy (CSP) directives you should add when using Adobe Target at.js 2.1 or later.
seo-title: Content Security Policies (CSP)
solution: Target
subtopic: Getting Started
title: Content Security Policy (CSP) directives
topic: Standard
---

# Content Security Policy (CSP) directives

If you are using [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) for your Target implementation, you should add the following CSP directives when using [at.js 2.1 or later](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` with `*.tt.omtrdc.net` whitelisted. Necessary to allow the network request to the [!DNL Target] edge.
* `style-src unsafe-inline`. Required for pre-hiding and flicker control.
* `script-src unsafe-inline`.  Required to allow JavaScript execution that might be part of an HTML offer.
