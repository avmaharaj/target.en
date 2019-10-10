---
description: Custom parameters are mbox parameters. If you pass any mbox parameters to mboxes, or use the targetPageParams function, those parameters appear here for use in audiences.
keywords: custom parameters;target custom parameters;targetpageparams;targeting mbox parameters
seo-description: Custom parameters are mbox parameters. If you pass any mbox parameters to mboxes, or use the targetPageParams function, those parameters appear here for use in audiences.
seo-title: Custom parameters in Adobe Target
solution: Target
title: Custom parameters
topic: Standard
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
---

# Custom parameters{#custom-parameters}

Custom parameters are mbox parameters. If you pass any mbox parameters to mboxes, or use the targetPageParams function, those parameters appear here for use in audiences.

For more information, see [Pass parameters to a global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

When creating a custom audience based on an mbox parameter, `mboxParameter` no longer prompts you for `mboxName`. mbox name is now optional. This change lets you use parameters from multiple mboxes or reference a parameter that has not yet been recorded on the edge.

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Name the audience.
1. Click **[!UICONTROL Add Rule]** > **[!UICONTROL Custom]**.

   To select the desired parameter:

   * While creating a new audience, select a parameter name from the list, start typing the first characters of the desired parameter name, or type the full name of the desired parameter name. 
   * If you remember the mbox name, but not the parameter name, use the checkbox to filter on a known mbox passing the desired parameter.

   Using either method, there is no link between the mbox and the parameter. The audience will work on the basis of parameter across all mboxes that pass that parameter.

   If you edit an existing audience, the filtering criteria displays with the mbox name that was supplied during creation.

1. Choose an evaluator:

   * Contains (case insensitive)
   * Does not contain (case insensitive)
   * Equals

   ![Custom parameter audience](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. Enter each value in a new line.
1. (Optional) Click **[!UICONTROL Add Rule]** and set up additional rules for the audience.
1. Click **[!UICONTROL Save]**.

The audience's [definition details pop-up card](../../../c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) shows the parameter name in the Rules section. There is no reference to the mbox used for filtering.

>[!NOTE]
>
>For custom audiences created before the Target 18.5.1 release (May, 22, 2018), mbox names will not display in the audience's definition pop-up card. You must re-save the custom audience to get the mbox name to be shown in the card.

## Considerations {#considerations}

* Audiences and activities are evaluated for a specific mbox. For example, if the global mbox passes a certain parameter, but the regional mbox does not, the activity/audience targeting that parameter will not be qualified for on the regional mbox.

## Training video: Creating Audiences

This video includes information about using audience categories.

* Create audiences 
* Define audience categories

>[!VIDEO](https://video.tv.adobe.com/v/17392)