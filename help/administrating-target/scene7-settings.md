---
description: Target Standard can be integrated with Adobe Dynamic Media Classic (formerly Scene7) to provide Digital Asset Management (DAM) in the Content Library.
seo-description: Target Standard can be integrated with Adobe Dynamic Media Classic (formerly Scene7) to provide Digital Asset Management (DAM) in the Content Library.
seo-title: Dynamic Media Classic integration
solution: Target
subtopic: Getting Started
title: Dynamic Media Classic integration
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
---

# Dynamic Media Classic integration{#scene-settings}

Target Standard can be integrated with Adobe Dynamic Media Classic (formerly Scene7) to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>Integrating Target with Dynamic Media Classic enables delivery of assets (as part of activities) uploaded to the Adobe Experience Cloud assets folder. This integration does not enable access to all assets uploaded in Dynamic Media Classic for delivery in Target activities.

If you already have a Dynamic Media account, you can supply your existing credentials. If you do not have an account, you can request a restricted-use Dynamic Media Classic account at no additional charge from your Adobe representative. This account can be used for purposes restricted for use in Target only. This service is made available to customers for workflows needing image-swap functionality.

If this setting is not configured, the Swap Image offer option within the activity creation workflow is not available. After this setting is configured, the option to swap/change image offers is available in both the [Visual Experience Composer (VEC) and in the Form-Based Experience Composer](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). You can then leverage image offers with images that have been uploaded from the Adobe Experience Cloud for use in Target activities.

If you want to reference a public image URL directly in an offer or custom code during activity creation, you should deploy the image to your own web servers and use your own URL in the code. There is no way to obtain the published URL of an image uploaded into the Experience Cloud to consume directly or outside of targeting workflows using Adobe Target. This functionality is not allowed, as per contract.

Note that the storage URL and the final publish URLs of images from Dynamic Media are different and one must NOT create offers using the storage link of images as delivery will not work in such cases. One must use the image offers capability as explained in our help documentation.

To integrate with Dynamic Media Classic (Scene7), you need to specify some the following information. 

1. Click **[!UICONTROL Setup]** > **[!UICONTROL Scene7 Settings]**.
1. Specify the following Dynamic Media Classic account information:

   **Region:** The region for your Dynamic Media account: North America, Europe, or Asia.

   **Adhoc folder:** The location for content that resides outside the target folder and are manually uploaded to Dynamic Media.

   **Email address:** The email address used to log in to Dynamic Media Classic (Scene7).

   **Password:** The password used to log in to Dynamic Media Classic (Scene7). 
1. Click **[!UICONTROL Submit]**.
