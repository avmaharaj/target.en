---
description: Target Standard and Premium use a modified version of the Adobe Target mbox.js file.
keywords: Implementation;Mbox;mbox.js;download mbox.js;configure mbox.js
seo-description: Target Standard and Premium use a modified version of the Adobe Target mbox.js file.
seo-title: Download mbox.js
solution: Target
subtopic: Getting Started
title: Download mbox.js
topic: Standard
uuid: b2a46321-cac7-4924-92dd-a80b50e27cee
---

# Download mbox.js{#download-mbox-js}

Target Standard and Premium use a modified version of the Adobe Target mbox.js file.

To use the [!DNL Adobe Target] [!UICONTROL Visual Experience Editor], you must include an additional line of JavaScript as part of your [!DNL mbox.js] file. 

1. Click **[!UICONTROL Setup]** > **[!UICONTROL Implementation]** in [!DNL Target Standard].
1. Click **[!UICONTROL Download mbox.js]** and follow the prompts to save the file.
1. (Conditional) If you use [!DNL mbox.js] version 60 or later, you can configure the library to automatically hide page content by default until mboxes load to reduce flicker on responsive sites.

   For more information, see "Suppress page-load flicker" in [mbox.js Advanced Settings](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C). 

1. Create the [!DNL mbox.js] reference on the website.

   Beginning with [!DNL mbox.js] version 57, the [!DNL mbox.js] reference can be placed anywhere within the `<head>` section of the page.

   >[!IMPORTANT]
   >
   >If you use a version of [!DNL mbox.js] prior to version 57, the reference must be the last item in the `<head>` section of your pages. If the reference is not the last item, serious display or performance issues could result. See [What mbox.js does](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) for more information.

1. Upload the saved [!DNL mbox.js] file to the location in your hosting environment that you specified in the code.
