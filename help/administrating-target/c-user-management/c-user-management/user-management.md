---
description: You can add users and manage their permissions in the Adobe Admin Console.
keywords: add user;manage user;user permissions
seo-description: You can add users and manage their permissions in the Adobe Admin Console.
seo-title: Users
solution: Target
subtopic: Getting Started
title: Users
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
---

# Users{#users}

You can add users and manage their permissions in the Adobe Admin Console.

>[!NOTE]
>
>[!UICONTROL Properties] and [!UICONTROL Permissions] functionality is available as part of the [!DNL Target] Premium solution. They are not available in [!DNL Target] Standard without a [!DNL Target] Premium license.
>You can tell whether your organization has a Standard or Premium license by clicking the [!UICONTROL Setup] link at the top of the [!DNL Target] UI.
>
>**[!DNL Target] Standard Customers**: If you see the [!UICONTROL Users] tab ([!UICONTROL Setup > Users]), your organization has a [!DNL Target] Standard license. [!DNL Target Standard customers should follow the instructions in this article to add users and assign permissions in the [!DNL Adobe Admin Console].
>
>**[!DNL Target] Premium Customers**: If you see the [!UICONTROL Properties] tab ([!UICONTROL Setup > Properties]), your organization has a [!DNL Target] Premium license. [!DNL Target] Premium customers should follow the instructions in [Enterprise user permissions](/help/administrating-target/c-user-management/property-channel/property-channel.md) and [Configure enterprise permissions](/help/administrating-target/c-user-management/property-channel/properties-overview.md) to add users and assign permissions in the [!DNL Adobe Admin Console].

Only system admin users can add users and manage their permissions. The system admin role is assigned at the [!DNL Experience Cloud] level. [!DNL Experience Cloud] roles are separate from the roles managed in each solution.

When you get started with [!DNL Adobe Target], you will find IDs (ending in Adobe.com) pre-populated in your [!DNL Adobe Experience Cloud] account. These IDs are for members of Adobe teams so that they can assist you with your new account and with your use of [!DNL Adobe Target], should you need help. To get assistance, reach out to your Adobe teams in the usual way.

You will not see the new user listed on the [!UICONTROL Users] page until the user logs in using his or her Adobe Experience Cloud account and then logs in to [!DNL Target Standard/Premium] by clicking the [!DNL Target] card.

By default all [!DNL Target] users start with observer permissions.

System admin users are identified in the Users list. Contact one of those system admin users if you need your access level changed.

## Access the Adobe Admin Console {#access}

For tasks performed in the Adobe Admin Console, access the console by following these steps:

1. Go to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.

   Or

   If you are already logged in to the Experience Cloud, go to [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com), then click the [!UICONTROL App] icon in the top navigation bar > click **[!UICONTROL Admin]** on the right side. 

1. (Conditional) If you have access to the [!DNL Admin Console for Enterprise] for more than one organization, click the user avatar in the right corner or the top navigation bar, then select the desired organization.

## Add Users {#add-users}

All user management must be performed in the [!DNL Adobe Admin Console for Enterprise]. However, all of your existing users in [!DNL Target] will be migrated from [!DNL Target] to the [!DNL Admin Console for Enterprise].

1. [In the Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), click **[!UICONTROL Users]** > **[!UICONTROL Users]** to create new users or to edit existing users. 
1. Follow the instructions in [Manage Users and Groups in the Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) in the *Enterprise User Guide*.

## Create User Groups {#user-groups}

You can create user groups, such as Developers, Analysts, Marketers, Executives, etc., and then assign privileges across multiple Adobe products and workspaces. Assigning a new team member all the appropriate privileges across different Adobe products can be as easy as adding them to a specific user group.

1. [In the Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), click **[!UICONTROL Users]** > **[!UICONTROL User Groups]** to create new user groups or to edit existing groups. 
1. Follow the instructions in [Manage Users and Groups in the Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) in the *Enterprise User Guide*.

## Specify Roles and Permissions {#roles-permissions}

Only system admins can set user roles in [!DNL Target]. For example, a Standard approver user cannot change an observer to an approver, without also having Experience Cloud Admin rights.

System admin users must add users to the system. Users are not automatically added. They are invited by email from the Experience Cloud and must confirm their email addresses before their accounts are registered.

1. [In the Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), click **[!UICONTROL Products]**, then select the name of the desired product.

   ![Products tab](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Click the name of the desired configuration. 
1. Click **[!UICONTROL Users]**.

   The [!UICONTROL Users] tab displays all of the users in that workspace.

   ![configuration users](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. Select the desired permissions role (Observer, Editor, or Approver) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   | Role | Description |
   |--- |--- |
   |Observer|Can view activities, but cannot create or edit them.|
   |Editor|Can create and edit activities before they are live, but cannot approve the launch of an activity.|
   |Approver|Can create, edit, and activate or stop activities.|

For more information, see [Manage Product Permissions and Roles in the Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) in the *Enterprise User Guide*.

## Training video: How to Configure Target Workspaces

Learning objectives:

* Access the Adobe Admin Console from the Adobe Target interface (three ways)
* Configure a workspace in the Adobe Admin Console
    * Add users to workspaces
    * Add properties to workspaces
* Understand default workspaces

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
