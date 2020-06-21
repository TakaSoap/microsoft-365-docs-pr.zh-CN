---
title: 面向管理员的 Microsoft 365 组概述
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解 Microsoft 365 组。
ms.openlocfilehash: 14bc1211aaa65fb2daeebdb22729fce10154f204
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780405"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>面向管理员的 Microsoft 365 组概述

Microsoft 365 组是促进跨 Microsoft 365 的所有团队合作的基础成员身份服务。 使用 Microsoft 365 组，您可以向一组用户授予对要共享的协作资源集的访问权限。 这些资源包括：

- 共享 Outlook 收件箱
- 共享日历
- SharePoint 文档库
- Planner
- OneNote 笔记本
- Power BI
- Yammer （如果组是从 Yammer 创建的）
- 团队（如果组是从团队创建的）
- 路线图（如果您有适用于 web 的项目）

对于 Microsoft 365 组，您无需手动分配对每个资源的权限，因为向该组添加人员会自动向他们授予对组所提供的工具所需的权限。

除非您将[组创建限制为一组特定的用户](manage-creation-of-groups.md)，否则任何用户都可以创建组。 请注意，如果限制组创建，无法创建组的用户将无法创建 SharePoint 网站、规划者或团队。 这些服务要求创建组的人员能够创建组。 用户仍可以参与组活动，例如，在 Planner 中创建任务或使用团队聊天，前提是该组的成员。

组具有以下角色：

- **所有者**-组所有者可以添加或删除成员，并具有独特的权限，如从共享收件箱中删除对话的功能或更改有关组的不同设置。 组所有者可以重命名组、更新说明或图片等。
- **成员**-成员可以访问组中的所有内容，但不能更改组设置。 默认情况下，组成员可以邀请来宾加入你的组，但你可以[控制该设置](manage-guest-access-in-groups.md)。
- **来宾**组来宾是来自组织外部的成员。

只有全局管理员、用户管理员和组管理员才能在 Microsoft 365 管理中心中创建和管理组。 你不能是委派管理员（例如代表管理员的顾问）。

作为管理员，您可以执行以下操作：

- [指定可以创建组的用户](manage-creation-of-groups.md)
- [为组织中的组创建命名策略](groups-naming-policy.md)
- [选择创建组时要使用的域](choose-domain-to-create-groups.md)
- [管理对组的来宾访问](manage-guest-access-in-groups.md)
- [恢复已删除的组](restore-deleted-group.md)（在删除后的30天内）

如果您更喜欢管理 Microsoft 365 组生命周期的一种更自动化的方法，则可以使用过期策略在特定时间间隔内使组过期。 组的所有者将在组过期前收到一封电子邮件，以允许他们轻松地续订组（如果仍需要）。 请参阅： [Microsoft 365 组过期策略](office-365-groups-expiration-policy.md)。

你可以从 Microsoft 365 管理中心或[使用 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)管理你的组。

如果您有大量用户（例如在大型公司或企业中），则可能会有许多用户出于各种目的创建组。 强烈建议您查看[Microsoft 365 组中的治理计划](plan-for-groups-governance.md)，以获得最佳实践。

## <a name="group-limits"></a>组限制

以下限制适用于 Microsoft 365 组：

|最大 .。。|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|管理员可以创建的组|最高为500,000 名的默认租户限制|
|成员数目|1000以上，但只有1000可以同时访问组对话。 <br>用户可能会注意到在 Outlook 中访问大型组中的日历和对话时的延迟。|
|用户可以是其成员的组的数目|1,000|
|文件存储|每个订阅用户 1 tb + 10 GB + 购买的任何附加存储空间。 您可以购买无限量的额外存储空间。|
|组邮箱大小|50 GB|

组织可拥有的 Microsoft 365 组的默认最大数量为500000，但可以按请求增加。 有关 Microsoft 365 组限制的详细信息，请参阅[microsoft 365 组-管理员帮助](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

在具有有关组使用的可操作信息时，管理 Microsoft 365 组会更有效。 Microsoft 365 管理中心有一个报告工具，可让你查看存储使用情况、拥有的活动组数以及你的用户使用组的数量。 有关详细信息，请参阅： [Microsoft 365 Reports in admin center](../activity-reports/office-365-groups.md) 。

## <a name="sensitivity-labels"></a>敏感度标签

您可以创建您的组织中的用户在创建 Microsoft 365 组时可以设置的敏感度标签。 使用灵敏度标签，您可以配置： 

- 隐私（公用或专用）
- 外部用户访问
- 非托管设备访问

例如，可以创建一个名为 "*高度机密*" 的标签，并指定使用此标签创建的任何组都是私有的，并且不允许外部用户。 如果组织中的用户在创建组的过程中选择此标签，则组将设置为 "私人"，并且不允许组成员将外部用户添加到组中。

> [!IMPORTANT]
> 如果你当前正在使用分类标签，则在启用灵敏度标签后，创建组的用户将无法再使用这些标签。 

有关创建、管理和使用敏感度标签的信息，请参阅[使用敏感度标签保护 Microsoft 团队、microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

## <a name="which-microsoft-365-plans-include-groups"></a>哪些 Microsoft 365 计划包括组？

任何具有 Exchange Online 和 SharePoint Online 的 Microsoft 365 订阅都将支持组。 其中包括业务重点和业务高级计划，以及企业版 E1、E3 和 E5 计划。 该组将接受创建组的人员（也称为组的 "组织者"）的许可。 只要组织者具有对您希望组拥有的任何功能的正确许可证，该许可证就会传递到组。

> [!NOTE]
> 有关 Microsoft 365 服务系列和计划的更多详细信息，请参阅[microsoft 365 计划选项](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。

如果您具有仅 Exchange 计划，您仍可以在 Outlook 中获取组的共享收件箱和共享日历功能，但不会获取文档库、计划程序或任何其他功能。

Microsoft 365 组适用于 Azure Active Directory （AAD）。 你获取的组功能取决于你拥有的 Azure Active Directory 订阅以及分配给组组织者的许可证。

> [!IMPORTANT]
> 对于所有组功能，如果你有 Azure AD Premium 订阅，则用户可以加入组，无论是否为其分配了 AAD P1 许可证。 不强制实施许可。
> 我们将定期生成使用情况报告，告诉你缺少许可证的用户，并且需要向其分配一个许可证以符合许可要求。 例如，假设用户没有许可证，并将其添加到强制实施命名策略的组中。 报告将标记，表明他们需要许可证。

## <a name="related-articles"></a>相关文章

[了解 Microsoft 365 组](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[将通讯组列表升级到 Microsoft 365 组](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Microsoft 365 组](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
