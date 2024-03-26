---
title: "Delete user data in Microsoft Planner"
f1.keywords:
- NOCSH
ms.author: ryany
author: efrene
manager: pamgreen
ms.date: 08/14/2019
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
search.appverid:
- MET150
description: "In order to ensure that a user is deleted from Microsoft Planner, you delete that user in the Microsoft 365 admin center. "
---

# Delete user data in Microsoft Planner

> [!IMPORTANT]
>
> This article applies to:
>
> - Basic plans in the Planner app in Teams
> - All plans in other Planner endpoints (including Planner web, Planner mobile, and Planner connectors)
>
> It does not apply to To Do lists and premium plans in the Planner app in Teams. Learn more about the Planner app in Teams here: [Manage the Planner app for your organization in Microsoft Teams](/microsoftteams/manage-tasks-app)

In order to ensure that a user is deleted from Microsoft Planner, you delete that user in the Microsoft 365 admin center. Once the user is deleted, their telemetry information is deleted in Microsoft Planner and their user name changed to "Former user." If you want to delete information other than user name and telemetry, you'll need to access the relevant plans and do this method manually.

## To delete a user from Planner

As the Microsoft 365 admin, go to the Microsoft 365 admin center and delete the user following the steps in [Delete a user from your organization](https://support.office.com/article/delete-a-user-from-your-organization-d5155593-3bac-4d8d-9d8b-f4513a81479e).

This process will delete the user from Microsoft Entra ID as well. You have 30 days to restore the account before the user's data is permanently deleted.

> [!IMPORTANT]
> If you delete the user from Microsoft Entra first, you will not be able to export the user's plans from Microsoft Planner. Make sure to export the plans from Microsoft Planner first if you intend to also delete the user from your organization.

## What gets deleted automatically

Once the user is deleted, their telemetry and user name are deleted, as follows:

- **All telemetry data is deleted.**    This happens every time a user is deleted from Microsoft Entra ID.
- **The user's name and User.Id are deleted.**    Microsoft Planner stores the user's name and User.Id against the TaskUserID. When a user is deleted, Microsoft Planner retains the TaskUserID, but deletes the user's name and User.Id. This enables Microsoft Planner to:

  - Rename the user to "Former user." All deleted users will be renamed "Former user."
  - Keep information on "task created by", "task assigned to", and "task completed by" under the name "Former user."

## To delete specific user data

Since Microsoft Planner is a collaborative tool in which much of the work is shared, deleting a user doesn't delete any plans, tasks, or content that the user was involved with or referenced by. If you want to remove or redact data included in plans and tasks, you can manually edit the plan.

To edit plans, do one of the following:

- **Grant yourself permissions to the group containing the user's personal data.**    This is most useful when the user's data is somewhere the user themself doesn't have access to.
- **Change the user's password and sign in as the user.**   This works best for plans that the user participated in.

    > [!IMPORTANT]
    > Changing the user's password and signing in as them only works if you do it before you delete the user from your organization.

Once you have permissions or are signed in as the user, you can change or remove any plan, task, or other content that should no longer reference the user.

## Related articles

[Export user data from Microsoft Planner](export-user-data.md)
