---
description: Information about using the Visual Experience Composer (VEC).
seo-description: Information about using the Visual Experience Composer (VEC) in Adobe Target.
seo-title: Adobe Target Visual Experience Composer (VEC)
title: Visual Experience Composer (VEC)
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
---

# Visual Experience Composer (VEC){#visual-experience-composer-vec}

Information about using the Visual Experience Composer (VEC).

The VEC is WYSIWYG user interface that lets you easily create and test personalized experiences and offers in the site context. You can create experiences and offers for Target activities by dragging and dropping, swapping, and modifying the layout and content of a web page (or offer) or mobile web page.

The VEC is one of the main features of [!DNL Adobe Target]. The VEC lets marketers and designers create and change content using a visual interface. Many design choices can be made without requiring direct editing of the code. Editing HTML and JavaScript is also possible using the editing options available in the composer.

On the Target **[!UICONTROL Setup]** > **[!UICONTROL Preferences]** tab, you can enter the Default Visual Experience Composer URL.

![Default VEC URL settings](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

This URL determines where you start when you open the VEC. If you do not enter a default, then you start with a blank page when you open the editor, and specify a URL at that time.

>[!NOTE]
>
>Certain browsers, such as Firefox, might block a page from displaying in the VEC if the page contains mixed content (for example, a non-secure page in a secure site). If your page does not display, click the icon next to the URL in the browser address bar and click **[!UICONTROL Disable protection on this page]**. This issue does not affect the display of your pages to site visitors.

Content inside an iframe on the page can't be modified in the VEC. To edit content within an iframe, ensure that the iframe document is Target-enabled, then load that iframe URL in the VEC.

You can use the drop-down menus across the top of the page to view your page as it would appear to different audiences or with different experiences. You can provide a name for each experience in the second drop-down list. For example, if you are testing the location of the Home link in your nav bar, you might name an experience where the Home link appears first something like, "Home link" to make it easier to identify the experiences in the list.

>[!NOTE]
>
>Changes to the structure of a page that affect the locations used in an activity created on that page could cause issues with experience editing. If a location has been changed outside the VEC, Target might not be able to find the location where the content was changed.

As you move your mouse around the page, a context-sensitive box follows the cursor, highlighting the elements on the page.

![VEC highlighted](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

Click a highlighted element for a menu of options available for that element type For example, you can click on an image and select **[!UICONTROL Edit > Text/HTML]** to change the text, or click a button and change the background color. You can use the buttons at the top left of the page to toggle the overlays on and off.

You can also click **[!UICONTROL Browse]**, then navigate to a page that is available from the primary page, such as a shipping page or shopping cart, and test changes on that page. You can also access page elements that are available when you hover, such as flyout menus and mini-carts. When you are finished browsing to the page, click **[!UICONTROL Compose]** to edit the experience. For example, you might want to change the design of a shopping cart drop-down or a carousel of images.

>[!NOTE]
>
>If a hover state depends on JavaScript, make sure **[!UICONTROL Disable JavaScript]** is not selected. JavaScript must be enabled to edit JavaScript elements.

For information about the options available in the VEC, see [Visual Experience Composer Options](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

You can perform some modifications on a page while the page is loading (or after the page fails to load), or you can cancel page loading in the VEC. For more information, see:

* [Edit a page while the page is loading or after the page fails to load](#loading)
* [Cancel loading of a page within the VEC](#cancel-loading)

## Edit a page while the page is loading or after the page fails to load {#loading}

 You can perform many actions before the page loads in the VEC, or even if the page fails to load altogether (for example, custom code is no longer operational).

Some reasons why you might want to access or make edits to a page while it is loading within the VEC or after it fails to load:

* You want to make a simple modification to a page, such as to add custom code or change an experience's name
* You want to copy existing custom code from a page that is no longer accessible
* You know that a page will not load within the VEC, but you want to make simple edits anyway

While the page loads (or after it fails to load), the [!UICONTROL Experiences] panel, [!UICONTROL Modifications] panel, and the settings at the top of the experience (Overlays, Modifications, Configure, and so forth) are all accessible.

The following illustration shows that you can insert custom code or perform other actions while the page is still loading:

![Page loading](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## Cancel loading of a page within the VEC {#cancel-loading}

You can cancel the loading of a page within the VEC to unlock editing of the activity without waiting for the page to load. This feature saves time and helps you make simple edits or insert custom code more efficiently without waiting for the page to load within the VEC.

Some reasons why you might want to cancel page loading within the VEC include:

* You want to make minor edits to existing modifications
* You want to delete one or more existing modifications
* You want to insert or edit custom code
* You mistakenly entered the wrong URL for the page
* You want to enable or disable JavaScript before loading the page in the VEC
* You want to add more template testing rules to the Page Delivery criteria
* You want to override the global Enhanced Experience Composer (EEC) toggle when loading a page via the EEC or iframe-only might depend might vary page to page

After you cancel page loading in the VEC you can switch between experiences in the activity without waiting for the page to load. To see the page within the VEC again, you must click the **[!UICONTOL Reload]** button.

>[!IMPORTANT]
>
>Be aware that when custom code or any modifications are made, by choosing to cancel loading within the VEC, you must ensure that your coding or changes are done properly. Ensure that you perform proper QA to ensure that your custom code and any other modifications are delivered as expected.

To cancel loading of a page within the VEC, click the **[!UICONTROL Cancel Loading]** button while the page is loading. The page will not load in the VEC for this activity during the current editing session.

![Cancel Loading button](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

To continue managing experiences in the current activity or to add new modifications, you must click the **[!UICONTROL Reload]** button.

![Reload button](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>There is a current known issue with this feature that will be fixed in the next release. For more information, see "Cancel loading of a page within the VEC" on the [Known issues and resolved issues](/help/r-release-notes/known-issues-resolved-issues.md#cancel) page.

## Training videos

The following videos contain more information about the concepts discussed in this article.

### Visual Experience Composer (1 of 2) (7:17)

* Change the content of a page 
* Change the layout of a page

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Visual Experience Composer (2 of 2) (7:29)

* Rename and duplicate an experience 
* Create a redirect experience 
* Target an activity to a single URL or a group of URLs 
* Create a multi-page activity 
* Preview and build experience for responsive websites 
* Use overlays to highlight types of elements

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Office hours: Visual Experience Composer

This video is a recording of " [Office Hours](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)," an initiative led by the Adobe Customer Care team.

* How the VEC works 
* How to avoid common issues with the VEC 
* Work-around practices you can use with the VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)