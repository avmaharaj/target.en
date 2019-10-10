---
description: When you click on a page element in the Visual Experience Composer (VEC), a menu shows the options that are available for that element type.
keywords: visual experience composer options;experience composer options;experience options;edit text;edit html;edit text/html;edit background color;background color;insert element;edit link;link;visual experience composer link;edit css class;css class;swap offer;offer swap;swap image;image swap;remove item;item remove;hide item;item hide;rearrange;move element;element move;resize element;element resize;element;expand selection;navigate to this link;navigate link;link navigate;navigate;link;undo;redo;undo/redo
seo-description: When you click on a page element in the Adobe Target Visual Experience Composer (VEC), a menu shows the options that are available for that element type.
seo-title: Adobe Target Visual Experience Composer (VEC) options
solution: Target
title: Visual Experience Composer Options
topic: Standard
uuid: efd672ae-c684-455f-8ec1-0efcfe1e9534
---

# Visual Experience Composer Options{#visual-experience-composer-options}

When you click a page element in the Visual Experience Composer (VEC), a menu shows the options that are available for that element type. In addition, a DOM path displays at the bottom of the page that lets you easily navigate through the page structure.

## VEC Options

The various Visual Experience Composer (VEC) actions are grouped appropriate menu options to make your job quicker and more efficient:

![VEC options menu](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>The available options depend on the activity type you are editing.

### Edit

The following options are available:

#### Text/HTML {#edit-text-html}

Change the HTML code for the element, such as the text for a text area, button, or link.

In addition to HTML code, you can edit and inject custom JavaScript.

Several rich text formatting options are available when editing text and HTML for [!UICONTROL A/B] and [!UICONTROL Experience Targeting] activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML.

The following HTML5 tags can be nested:

|Tag|Allowed Nested Tags|
| --- | --- |
|`<a>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>`|
|`<ins>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`|
|`<del>`|`<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>`|
|`<label>`|`<p>`|

#### Background Color

Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent.

**Note:** This option is not available for an element where a background image is set. 

#### Styles {#styles}

Use the [!UICONTROL Styles] panel to view or edit the value of existing styles for the selected element. You can also add additional styling.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] panel displays on the right side of the VEC. The panel contains a list of styles that lets you edit or add to the selected element. A real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

![Styles panel](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

As you apply different styles, you can always revert your changes by clicking the [!UICONTROL Revert] icon that displays at the top right corner of the [!UICONTROL Styles] panel after you make a change to any section. Note that clicking the [!UICONTROL Revert] icon reverts all changes on the current section's panel.

Expand each section to edit or add styles, as explained below. To save your changes, click the Back icon at the top of the panel to return to the panel's main display, then click **[!UICONTROL Save]**. 

Note that blue dots on the main panel and next to each option on the various section panels indicate that you have made changes to the corresponding styles. This makes it easy for you to review your changes before clicking [!UICONTROL Save].

>[!NOTE]
>
>Quick actions for layout changes, background color, resizing, and move are also available as separate actions in the VEC menu. These options can be leveraged as separate actions or you can use the Styles menu, as explained here.

* **Background**

  Change the background color and image.

  * Color (specify the color code or use the color picker)
  * Image (select an image from the image picker)
  * Image source (specify an external URL)
  * Attachment
    * Click the top drop-down list to select scroll, fixed, or local
    * Click the bottom drop-down list to select repeat, repeat-x, repeat-y, no-repeat, space, or round
  * Clip
    * Click the top drop-down list to select border-box, padding-box, content-box, or text
    * Click the bottom drop-down list to select auto audio or audio

* **Typography**

  Change the typography of an element. Typography edits are quick and easy. 

  Although the rich text editor (Edit Text/HTML) is available for fine tuning, quick actions to make changes to the entire element is available via this option. If you want to apply typography changes to only a part of the text (not to the full text), use the [rich text editor](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md). 

  You can edit the following typography styles:

  * Font size
  * Font weight
  * Font style
  * Color (specify the color code or use the color picker)
  * Word spacing
  * Line height
  * Text alignment

* **Margin**

  Change the margin for the selected element. You can change the left, right, bottom, and top margins.

  Click the drop-down icon for each margin to choose from the following options:

  * Auto 
  * Value (drag the slider to set the margin or specify the number of pixels for each margin)

  Margin supports positive and negative values.

  Target also supports other size units, such as rem, pc, em, etc. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **Padding**

  Change the padding for the selected element. You can change the left, right, bottom, and top padding.

  Drag the slider to set the padding or specify the number of pixels for padding.

  Padding supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **Border**

  Click the border icons at the top of the panel to change the selected element's border.

  You can edit the following styles for each border (top, right, bottom, and left):

  * Border style (none, hidden, dotted, dashed, solid, or double)
  * Border color (specify the color code or use the color picker)
  * Border width (drag the slider to select a border width or specify the width in pixels)

  Border supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **Position**

  Move the selected element from its current position. You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

  Click the [!UICONTROL Static] drop-down list to choose from the following position options:

  * Static
  * Relative
  * Absolute
  * Sticky
  * Fixed

  Click the drop-down icon for each position to choose from the following options:

  * Auto 
  * Value (drag the slider to position the element or specify the number of pixels you want to move the element)

  Position supports positive and negative values.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **Size**

  Change the selected element's width and height.

  Click the drop-down icon next to [!UICONTROL Width] and [!UICONTROL Height] to choose from the following options:

  * Auto 
  * Value (drag the slider to size the element or specify the number of pixels for each dimension)

* **Filter**

  Drag the slider for each filter option or specify the desired percentage:

  * Sepia
  * Contrast
  * Brightness
  * GrayScale
  * Blur
  * Opacity
  * Invert
  * Hue-rotate
  * Saturate

* **CSS Editor**

  The real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

  The CSS Editor displays any changes that you make in the Styles panel. As shown in the illustration below, the font size, top border, and image size have been changed:

  ![CSS editor with changes](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Notice the blue dots next to the [!UICONTROL Typography], [!UICONTROL Border], and [!UICONTROL Size] options in the preceding illustration. These dots indicate that you have made changes to these sections. If you open these section panels, blue dots display next to the specific options that you changed.

  You can type your own code if your desired style is not available by default in the [!UICONTROL Styles].

  Be aware that the CSS Editor shows details for the current session only. If you save changes and then reopen the editor, details about your previous change do not display in the editor, even if you select the same element again.

  >[!Important]
  >
  >You can apply a background image using the CSS Editor, but it might cause flicker. Test your changes before deployment.

#### CSS Class

Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space.

Available for [!UICONTROL A/B], [!UICONTROL Automated Personalization], and [!UICONTROL Multivariate Test] activities.

#### Link

Change the URL in the link.

Use Edit Link to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the [!UICONTROL Visual Experience Composer] to apply the action on the other image element.

### Insert Before

The following options are available:

#### Image, HTML, and Text

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert Before] and choose whether you want to insert an image, HTML, or text. The inserted element appears before the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

#### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Insert After

The following options are available:

#### Image, HTML, and Text

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert After] and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

#### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Replace With

The following options are available:

#### Image

Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target.

During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL.

For example, the initial URL might look like the following example:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

After activity syncing, the delivery URL might look like the following example:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations supports Replace With in DIV, SECTION, and ARTICLE tags.

**Note:** Swapping images requires an Adobe Scene7 Publishing System Account.

#### HTML Offer

Select a different offer from the [!UICONTROL Content Library].

**Note:** HTML Offers are stored on [!DNL Target] servers.

An HTML offer can be up to 256 KB in size.

#### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md).

#### Experience Fragment

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Layout

The following options are available:

#### Rearrange

Drag the element to another location inside the same parent element or DIV. Other elements shift location to make space for the rearranged element.

**Note:** Click tracking does not work on rearranged items.

#### Resize

Resize an element on your page. When you select [!UICONTROL Resize], a handle appears in the bottom right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio.

**Note:** Inline elements cannot be resized.

#### Move {#move}

Move elements on your page. Unlike the [!UICONTROL Rearrange] option, [!UICONTROL Move] does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support for making sure moved elements are not hidden behind other elements.)

In some cases, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. An element cannot be moved outside of a container that has following CSS property: `overflow: hidden`.

#### Hide

Hide the element. The white space remains, but the content is removed.

#### Remove

Remove the element. The white space behind the image is removed and the space where the element was is collapsed.

**Note:** Items within a "classic" mbox (an mbox created within a Target Classic campaign) cannot be removed using this option.

### Expand Section

Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times.

### Navigate to Link

Open the destination of the link.

### Undo/Redo

Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone.

## Considerations {#considerations}

* If an offer contains HTML content, see "How at.js renders offers with HTML content" in [How at.js works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render) for more information.

## Navigate elements using the DOM path {#dom-path}

When you click an element on the page, the VEC options menu displays. In addition, when you click an element, the corresponding DOM path displays at the bottom of the page. 

![DOM path](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

You can use the DOM path to quickly see information about the selected element (type, ID, and class) and move up or down the DOM path to select the desired element.

When you hover over the DOM path, a blue box highlights the corresponding element in the VEC. When you click the element, an orange box highlights the element and the VEC options menu displays, as explained above.

You can easily navigate to any parent, sibling, or child element within the VEC using the DOM path.

The DOM path feature is also available when setting up [click tracking](/help/c-activities/r-success-metrics/click-tracking.md).