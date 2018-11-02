---
description: The Adobe Mobile SDK contacts the Target server to get the content along with other data points to show the right experience to the user.
seo-description: The Adobe Mobile SDK contacts the Target server to get the content along with other data points to show the right experience to the user.
seo-title: How Target works in mobile apps
title: How Target works in mobile apps
uuid: ac55ffef-a25d-4a1d-affe-10f44a8d9f0e
index: y
internal: n
snippet: y
---

# How Target works in mobile apps

The Adobe Mobile SDK contacts the Target server to get the content along with other data points to show the right experience to the user.

## Target Locations and Success Metrics {#section_A08AAB0ABA9C4568A5AFD4D27EF1CE74}

A *target location* is also referred to as an mbox. An identified location in the app is enabled for testing or personalization (for example, the welcome message on the home screen). These locations are identified during the test creation process.

A * [success metric](../c-activities/r-success-metrics/r-success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)* is an action performed by the user that identifies if a specific activity was successful (such as signing up, making a purchase, booking a ticket, and so on).

![](assets/mobile-target-location.png)

* **Target Location:** The content that shows below the register button.

  This particular user is offered free shipping until 6 PM. This location can be reused across multiple Target activities to run A/B tests and personalization. 

* **Success Metric:** The action performed by the user where the user taps the register button.

**Understand How Target Works in the SDK**

![](assets/how-target-mobile-works.png)
