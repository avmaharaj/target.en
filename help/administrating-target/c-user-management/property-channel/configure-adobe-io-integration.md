---
description: Information about granting Adobe I/O integrations access to all workspaces with the desired role.
keywords: integration;roles;user permissions;admin console
seo-description: Information about granting existing Adobe I/O integrations access to all workspaces with the desired role in Adobe Target
seo-title: Grant Adobe I/O integrations access to workspaces and assign roles in Adobe Target
solution: Target
subtopic: Getting Started
title: Grant Adobe I/O integrations access to workspaces and assign roles
---

# ![PREMIUM](/help/assets/premium.png) Grant Adobe I/O integrations access to workspaces and assign roles

[!UICONTROL Enterprise Permissions] allows [!DNL Target] customers to use a single organization, but divide it into workspaces for their different teams or workflows.

>[!NOTE]
>
>Properties and Permissions functionality is available as part of the [Target Premium](/help/c-intro/intro.md#premium) solution. They are not available in [!DNL Target Standard] without a [!DNL Target Premium] license.

The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier in 2019. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] provides customers with the following access controls:

* You can choose the workspaces to which the integration can be applied
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

This update supports the following use cases:

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Grant the Adobe I/O integration the access to select workspaces with the appropriate role to allow a central team to make API-driven changes in only a few workspaces.
* Allow each team owning its workspace to have its own integration whenever the team is ready to explore APIs and choose the role accordingly.
* Mix and match any of above scenarios.

**Action Needed**: Those customers who are currently leveraging APIs for CRUD operations on resources (activities, audiences, offers, and reporting) across all workspaces need to grant their existing Adobe I/O integration access to all workspaces with the desired role as per their use case. You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of choice made from the [!UICONTROL Product Role] drop-down list. You can now choose the desired role.

>[!NOTE]
>
>If this action is not performed, after the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. There is no adverse reaction to setting up integrations in advance. The sooner you make this change, the better. Depending on the number of workspaces in your organization, this process takes only a few clicks to add an existing integration into workspaces with the desired role.

**To grant Adobe I/O integrations access to workspaces and to assign roles:**

1. Open the **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Choose product in Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Select the desired workspace (Product Profile).

   ![Select the product profile](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Integrations tab](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Conditional) To add a new integration, click **[!UICONTROL Add Integration]**, select the desired integration, then click **[!UICONTROL Save]**.

1. From the **[!UICONTROL Product Role]** drop-down list, select the desired role for that workspace:

   * [!UICONTROL Approver]
   * [!UICONTROL Editor]
   * [!UICONTROL Observer]

   ![Choose Product Profile role](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
