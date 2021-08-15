---
title: 比较组
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 组成员将获得组电子邮件和用于对话、文件和日历事件的共享工作区，以及 Stream 和 Planner。
ms.openlocfilehash: a831ef11817af47ed1007600a1eb70bddd341b3ae474c11d0b2326a9e4debf89
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53826515"
---
# <a name="compare-groups"></a>比较组

在 Microsoft 365 管理中心的 **组** 部分中，可创建和管理以下类型的组： 

- **Microsoft 365 组** 用于公司内部和外部用户之间的协作。 它们包括协作服务，如 SharePoint 和 Planner。
- **通讯组** 用于向一组人员发送电子邮件通知。
- **安全组** 用于授予对资源（如 SharePoint 网站）的访问权限。
- **启用邮件的安全组** 用于授予对资源（如 SharePoint）的访问权限，并向这些用户发送电子邮件通知。
- 当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址）时，将使用 **共享邮箱**。

某些组允许动态成员身份或电子邮件。

||Microsoft 365 组|通讯组|安全组|启用邮件功能的安全组|共享邮箱|
|:----|:----|:----|:----|:----|:----|
|**已启用邮件**|是|是|否|是|是|
|**Azure AD 中的动态成员资格**|是|否|是|否|否|

所有这些组类型都可以与 Power Automate 一起使用。

## <a name="microsoft-365-groups"></a>Microsoft 365 组

Microsoft 365 组用于公司内部和外部用户之间的协作。 对于每个 Microsoft 365 组，成员将获得组电子邮件和用于对话、文件和日历事件的共享工作区、流和规划器。

只要[管理员启用](manage-guest-access-in-groups.md)了此功能，你就可以将组织外部的人员添加到组中。 还可以允许外部发件人向组电子邮件地址发送电子邮件。

可[为 Azure Active Directory中的动态成员身份](/azure/active-directory/users-groups-roles/groups-change-type)配置 Microsoft 365 组，以便根据部门、位置、职衔等等用户属性自动添加或删除组成员。

可通过移动应用（如 Outlook for iOS 和 Outlook for Android）访问 Microsoft 365 组。

如果[管理员启用了](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)此功能，则组成员可以作为组或代表组发送电子邮件地址。

Microsoft 365 组不支持与其他 Microsoft 365 组、通讯组或安全组嵌套。

## <a name="distribution-groups"></a>通讯组

[通讯组](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) 用于向一组人员发送通知。 如果管理员启用，则可以接收外部电子邮件。

通讯组最适用于需要将信息广播给一组人员的情况，例如 "构建 A 中的人" 或 "Contoso 中的每个人"。

通讯组可[升级到 Microsoft 365 组](../manage/upgrade-distribution-lists.md)。

通讯组可添加到 Microsoft Teams 中的团队中。

Microsoft 365 组不能是通讯组成员。

## <a name="security-groups"></a>安全组

[安全组](../email/create-edit-or-delete-a-security-group.md) 用于授予对 Microsoft 365 资源（如 SharePoint）的访问权限。 它们可以简化管理，因为只需管理组，而不是单独将用户添加到每个资源。

安全组可以包含用户或设备。可将创建设备安全组用于移动设备管理服务（如 Intune）。

可为[ Azure Active Directory 中的动态成员身份配置](/azure/active-directory/users-groups-roles/groups-change-type)安全组，以便根据部门、位置或职衔等用户属性自动添加或删除组成员或设备；或设备属性（如操作系统版本）。

可以将安全组添加到团队中。

Microsoft 365 组不能是安全组成员。

## <a name="mail-enabled-security-groups"></a>启用邮件的安全组

启用邮件的安全组的功能与常规安全组相同，不同之处在于它们无法通过 Azure Active Directory 动态管理，并且不能包含设备。

它们包括向组中的所有成员发送邮件的功能。

可以将启用邮件的安全组添加到团队中。

## <a name="shared-mailboxes"></a>共享邮箱

当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址、接待台或其他可能由多个用户共享的其他功能）时，将使用[共享邮箱](../email/create-a-shared-mailbox.md)。

如果管理员已启用共享邮箱，则共享邮箱可以接收外部电子邮件。

共享邮箱包括可用于协作的日历。

如果管理员已授予用户执行该操作的权限，具有组邮箱权限的用户可以作为或代表邮箱电子邮件地址发送。 这对帮助和支持邮箱尤其有用，因为用户可从 "Contoso 支持" 或 "构建 A 接待台" 发送电子邮件。

暂无法将共享邮箱迁移到 Microsoft 365 组中。 

## <a name="related-content"></a>相关内容

[了解 Microsoft 365 组](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[在 Outlook 中将通讯组列表升级为 Microsoft 365 组](/microsoft-365/admin/manage/upgrade-distribution-lists)

[为什么应将通讯组列表升级至 Outlook 中的组](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
