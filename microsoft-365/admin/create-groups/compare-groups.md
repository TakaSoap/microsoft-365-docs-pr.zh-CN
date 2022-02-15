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
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 组成员将收到组电子邮件，并获取用于对话、文件和日历事件的共享工作区，以及 Stream 和 Planner。
ms.openlocfilehash: cc70fdf534b7240fd914c42f01b2c89843d1372f
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62805828"
---
# <a name="compare-groups"></a>比较组

在 Microsoft 365 管理中心的 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**组**</a>部分中，可创建和管理以下类型的组： 

- **Microsoft 365 组** 用于公司内外用户之间的协作。 它们包括协作服务，如 SharePoint 和 Planner。
- **通讯组** 用于向一组人员发送电子邮件通知。
- **安全组** 用于授予对资源（如 SharePoint 网站）的访问权限。
- **启用邮件的安全组** 用于授予对资源（如 SharePoint）的访问权限，并向这些用户发送电子邮件通知。
- 当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址）时，将使用 **共享邮箱**。
- 创建 **动态通讯组** 的目的是加快组织内电子邮件消息和其他信息的批量发送。

某些组允许动态成员身份或电子邮件。

||Microsoft 365 组|通讯组|安全组|启用邮件功能的安全组|共享邮箱|动态通讯组|
|:----|:----|:----|:----|:----|:----|:----|
|**已启用邮件**|是|是|否|是|是|是|
|**Azure AD 中的动态成员资格**|是|否|是|否|否|否|

所有这些组类型都可以与 Power Automate 一起使用。

## <a name="microsoft-365-groups"></a>Microsoft 365 组

Microsoft 365 组用于公司内外用户之间的协作。 对于每个 Microsoft 365 组，成员将收到组电子邮件并获取用于对话、文件和日历事件的共享工作区，以及 Stream 和 Planner。

只要[管理员启用](manage-guest-access-in-groups.md)了此功能，你就可以将组织外部的人员添加到组中。 还可以允许外部发件人向组电子邮件地址发送电子邮件。

Microsoft 365 组可以 [配置为Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type)中的动态成员身份，从而允许根据用户属性（如部门、位置、标题等）自动添加或删除组成员。

可通过移动应用（如 Outlook for iOS 和 Outlook for Android）访问 Microsoft 365 组。

如果[管理员启用了](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)此功能，则组成员可以作为组或代表组发送电子邮件地址。

Microsoft 365 组不支持与其他Microsoft 365 组或通讯组或安全组进行嵌套。

## <a name="distribution-groups"></a>通讯组

[通讯组](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) 用于向一组人员发送通知。 如果管理员启用，则可以接收外部电子邮件。

通讯组最适用于需要将信息广播给一组人员的情况，例如 "构建 A 中的人" 或 "Contoso 中的每个人"。

可以将通讯组 [升级到 Microsoft 365 组](../manage/upgrade-distribution-lists.md)。

可以将通讯组添加到 Microsoft Teams 中的团队，但只添加成员，而不添加组本身。

Microsoft 365 组不能是通讯组的成员。

## <a name="dynamic-distribution-groups"></a>动态通讯组 

[动态通讯组](/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) 是启用了邮件的组，用于向具有特定属性（如部门或位置）的人员发送邮件。 这些属性是在 Exchange 管理中心而不是 Azure AD 中定义的。

与包含一组已定义成员的常规通讯组不同，每次向动态通讯组发送邮件时，都将根据所定义的筛选器和条件来计算该组的成员列表。电子邮件发送到动态通讯组时，将被传递到组织中所有与为该动态通讯组定义的条件匹配的收件人。

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

如果管理员已授予用户执行该操作的权限，则具有组邮箱权限的用户可以使用或代表邮箱电子邮件地址发送。 这对帮助和支持邮箱尤其有用，因为用户可从“Contoso 支持”或“构建 A 前台”发送电子邮件。

无法将共享邮箱迁移到Microsoft 365组。

## <a name="related-content"></a>相关内容

[了解Microsoft 365 组](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[在 Outlook 中将通讯组列表升级为 Microsoft 365 组](/microsoft-365/admin/manage/upgrade-distribution-lists)

[为什么应将通讯组列表升级至 Outlook 中的组](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
