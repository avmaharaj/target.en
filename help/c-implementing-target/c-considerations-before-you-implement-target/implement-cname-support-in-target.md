---
description: Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in Adobe Target.
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate
seo-description: Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in Adobe Target.
seo-title: CNAME and Adobe Target
solution: Target
title: CNAME and Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
---

# CNAME and Adobe Target {#cname-and-adobe-target}

Information about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Target]. To best handle ad blocking issues, or ITP-related cookie policies, a CNAME is used so calls are made to a domain owned by the customer rather than a domain owned by Adobe.

Perform the following steps to request CNAME support in [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. Create CNAME records (see instructions below). 

   Upon receiving the ticket, a FPSSL specialist should provide you with a pair of CNAME records. These records must be configured on your company's DNS server before Adobe can purchase the certificate on your behalf. 

   The CNAMES will be similar to the following example:

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. When these CNAMES are in place, Adobe will work with DigiCert to purchase and install a certificate on Adobe's production servers.

1. After completing the preceding tasks, you must update the `serverDomain` to the new CNAME in at.js.
