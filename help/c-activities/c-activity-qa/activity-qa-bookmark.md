---
description: Information to help you use the Adobe Target QA bookmarklet to force Target to release you from QA mode.
keywords: qa;preview;bookmarklet;preview links
seo-description: Information to help you use the Adobe Target QA bookmarklet to force Target to release you from QA mode.
seo-title: Activity QA bookmarklet for Adobe Target
solution: Target
title: Activity QA bookmarklet
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
---

# Activity QA bookmarklet{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

Because [QA mode](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) is sticky, after you browse a website in QA mode, your [!DNL Target] session must expire or you need to have [!DNL Target] release you from QA mode before you can view your site like a typical visitor. Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser's Bookmarks Toolbar:

```
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

The bookmarklet should then appear on the toolbar for re-use.

>[!NOTE]
>
>The process to create a bookmarklet varies by browser type and version. Consult your browser's help or search on the Internet for specific directions.

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value. 

For example:

`https://www.mysite.com/?at_preview_token=` 
