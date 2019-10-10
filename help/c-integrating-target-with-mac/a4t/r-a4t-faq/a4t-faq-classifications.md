---
description: This topic contains answers to questions that are frequently asked about classifications and using Analytics as the reporting source for Target (A4T).
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
seo-description: This topic contains answers to questions that are frequently asked about classifications and using Analytics as the reporting source for Target (A4T).
seo-title: Classifications - A4T FAQ
solution: Target
title: Classifications - A4T FAQ
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
---

# Classifications - A4T FAQ{#classifications-a-t-faq}

This topic contains answers to questions that are frequently asked about classifications and using Analytics as the reporting source for Target (A4T).

## After using the Classifications Importer to download classifications, how do I match the post-tnt-action value with an activity name? {#section_6045DAC488B248418F430E663C38D001}

You can download the classifications for the A4T/TNT string from the Admin Tools [Classification Importer](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html). The variable is called “TNT” in the export list. The downloaded data includes the friendly names for activities, experiences, and so forth.

This lookup file is useful for customers that receive Adobe’s clickstream data feed. The file provides friendly names for the `post_tnt` and `post_tnt_action` columns.

The string format of the TNT variable is `activityID:experienceID:targettype|event`.

* targettype will always be 0 for A4T. 
* Event = 0 represents an experience entrance. 
* Event = 1 represents an experience visit. 
* Event = 2 represents an activity impression. 
* Event = 32767 represents an activity conversion.

You can import the classification file on a frequent basis from the UI using a [browser import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) or an [FTP import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). You can also engage with Engineering Services to obtain the file as a lookup table along with a clickstream data feed. 
