---
description: The Adobe Target application and content delivery has been tested across a wide range of browsers and devices.
keywords: Browsers;Prerequisites;Requirements;internet explorer;chrome;firefox;safari;android;surface
seo-description: The Adobe Target application and content delivery has been tested across a wide range of browsers and devices.
seo-title: Supported browsers
solution: Target
subtopic: Getting Started
title: Supported browsers
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
---

# Supported browsers{#supported-browsers}

The [!DNL Adobe Target] application and content delivery has been tested across a wide range of browsers and devices.

For additional important information about TLS, see [TLS (Transport Layer Security) Encryption Changes](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## [!DNL Target] Standard/Premium interface {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

The [!DNL [!DNL Target]] Standard/Premium] interface supports the following browsers and devices:

| Device Type | Browser Version |
|--- |--- |
|Windows|<ul><li>Microsoft Edge</li><li>Google Chrome (Latest, Latest minus 1)</li><li>Mozilla Firefox (Latest, Latest minus 1)</li></ul>|
|Mac|<ul><li>Firefox (Latest, Latest minus 1)</li><li>Chrome (Latest, Latest minus 1)</li></ul>|

## Content delivery {#section_1045A946056441268D40025529918D3D}

Content delivery has been tested across the following browsers and devices:

| Device Type | Browser Version |
|--- |--- |
|Windows|<ul><li>Internet Explorer 9 and 10. Tested in emulation mode.<br>**Note**: at.js 1.3.0 (and later) no longer supports content delivery on Microsoft Internet Explorer 9.</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome (Latest, Latest minus 1)</li><li>Firefox (Latest, Latest minus 1)</li></ul>|
|Mac|<ul><li>Apple Safari (Latest)<br>**Note**: For more information about how Safari handles first- and third-party cookies, see [Target Cookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md).</li><li>Firefox (Latest, Latest minus 1)</li><li>Chrome (Latest, Latest minus 1)</li></ul>|
|Mobile/Tablet|<ul><li>Apple iOS (Latest)</li><li>Android devices and tablets (Android 4 and later)</li><li>Microsoft Surface (Windows 8.1)</li></ul>|

For [!DNL at.js] implementations, [!DNL Target] displays default content in earlier versions of Internet Explorer and possibly in earlier versions of the above-listed browsers. For [!DNL mbox.js] implementations, [!DNL Target] tries to render content but might not be successful.

[!DNL Target] displays default content in browsers not listed above and in browsers using [quirks mode](https://en.wikipedia.org/wiki/Quirks_mode). at.js requires a doctype that renders in standard mode, for example: `<!DOCTYPE html>` .

>[!NOTE]
>
>Adobe Delivery infrastructure is being secured to NOT support TLS 1.0 devices and browsers after September 12, 2018. See [TLS (Transport Layer Security) Encryption Changes](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) to understand the overall impact of this change.
