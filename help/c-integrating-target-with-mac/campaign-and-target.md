---
description: Use Target with Adobe Campaign to optimize email content.
keywords: Overview and Reference
seo-description: Use Target with Adobe Campaign to optimize email content.
seo-title: Integrate Target with Adobe Campaign
solution: Target
title: Integrate Target with Adobe Campaign
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
---

# Integrate Target with Adobe Campaign{#integrate-target-with-adobe-campaign}

Use Target with Adobe Campaign to optimize email content.

To optimize your email content--for example, to display different offers for male and female recipients--you can create a redirect offer in Target, then use Adobe Campaign to manage the email offers.

The integration takes place when the email is opened. When the customer opens the email, a call is made to Target and a dynamic version of the content appears. The content consists of a static image supported by all browsers. Target tracks the reaction to the offer at the audience or session level and that data is available in Target reports.

Target can track the following data:

* User agent 
* IP address 
* Geographical location 
* Segment associated with the visitor's ID in Target (subject to legal approval) 
* Data from Campaign Datamart

There are several limitations:

* Because only an image can be used, content cannot be personalized. 
* Tracking is not consolidated in Adobe Campaign. 
* No unified user experience.

  You must use both Target and Campaign to set up different parts of the integration:

    * The rawbox and the experience in Target 
    * The delivery in Campaign

## Before You Begin {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use Adobe Campaign to set up your targeted email offers, set up the following in Target:

* Two or more Target redirect offers

  See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md). 
* A Target activity with an experience for each offer and the desired [success metric](/help/c-activities/r-success-metrics/success-metrics.md).

  See [Redirect to a URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Start the activity in Target before setting up the Campaign portion of the integration.

## Include a Target Offer in an Adobe Campaign Email {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in Adobe Campaign. 
1. In the email properties, click **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]**. 
1. Select the default image from the shared assets. 
1. Specify the location (rawbox). 
1. Add any other decisioning parameters, such as the gender of the recipient. 
1. Preview the email, selecting at least one recipient for each offer (in this case, a male and a female). 
1. In Campaign, define the Target Edge server you are using to control the activity and the name of the tenant. 
1. Specify the external account used for the Experience Cloud so you can access the resources in the Experience Cloud.

For more information, refer to the Adobe Campaign documentation. 
