---
title: 面向管理员的 Microsoft 365 组概述
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 通过Microsoft 365组，你可以向一组人员Microsoft 365共享资源集合，从而推动整个团队的团队合作。
ms.openlocfilehash: 5aaf7598f3591efb330618f0be98ea3376816eca
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165732"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>面向管理员的 Microsoft 365 组概述

Microsoft 365组是跨组织推动所有团队合作的基础Microsoft 365。 使用Microsoft 365组，您可以向一组人员授予对共享资源集合的访问权限。 这些资源包括：

- 共享Outlook收件箱
- 共享日历
- 文档SharePoint库
- A Planner
- OneNote 笔记本
- Power BI
- Yammer (组是否从组创建Yammer) 
- 如果 (创建组，团队将Teams) 
- 如果 (Web Project，路线图) 
- Stream

使用Microsoft 365组，不必手动为其中每个资源分配权限。 向组添加人员会自动授予他们所需的权限。

除非将组创建限制为一组特定的人员，否则 [任何用户都可以创建组](../../solutions/manage-creation-of-groups.md)。 如果限制组创建，则无法创建组的用户将无法创建 SharePoint 网站、规划人员、团队、Outlook 组日历、Stream 组、Yammer 组、OneDrive 中的共享库或共享 Power BI 工作区。 这些服务要求创建它们的人能够创建组。 用户仍然可以参与组活动，例如，在 Planner 中创建任务Teams聊天，但如果他们是组的成员。

组具有以下角色：

- **所有者** - 组所有者可以添加或删除成员，并且具有独有权限，例如从共享收件箱中删除对话或更改有关组的不同设置。 组所有者可以重命名组、更新说明或图片等。
- **Members** - 成员可以访问组内的所有内容，但无法更改组设置。 默认情况下，团队成员可以邀请来宾加入你的组，但你可以 [控制该设置](manage-guest-access-in-groups.md)。
- **来宾** - 组来宾是组织外部的成员。

只有全局管理员、用户管理员和组管理员才能在"组<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">"Microsoft 365 管理中心。</a> 你不能是委派管理员（例如代表管理员的顾问）。

作为管理员，您可以：

- [指定可以创建组的人](../../solutions/manage-creation-of-groups.md)
- [为贵组织的组创建命名策略](../../solutions/groups-naming-policy.md)
- [创建组时选择使用哪个域](../../solutions/choose-domain-to-create-groups.md)
- [管理对组的来宾访问](manage-guest-access-in-groups.md)
- [在删除 (](restore-deleted-group.md) 30 天内恢复已删除) 

如果更希望采用自动化的方式来管理组Microsoft 365，可以使用过期策略以特定时间间隔使组过期。 组所有者将在组到期前 30、15 和 1 天收到一封电子邮件，允许他们根据需要续订组。 请参阅[：Microsoft 365组过期策略](../../solutions/microsoft-365-groups-expiration-policy.md)。

可以从组管理组，Microsoft 365 管理中心[PowerShell 管理](../../enterprise/manage-microsoft-365-groups-with-powershell.md)组。

如果您有很多用户（例如，在大型企业或企业中）中，则您可能有许多用户出于各种目的创建组。 我们强烈建议您查看规划Microsoft 365[组以](../../solutions/collaboration-governance-overview.md)获得最佳方案。

## <a name="group-limits"></a>组限制

以下限制适用于Microsoft 365组：

|最大值...|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|管理员可以创建的组|最多默认租户限制为 500 K|
|成员数目|超过 1，000 个，但只有 1，000 个用户可以同时访问组对话。 <br>用户在访问日历和日历中大型组的对话时可能会注意到Outlook。|
|用户可以是其中一个成员的组数|7,000|
|文件存储|每个订阅用户 1 TB + 10 GB + 已购买任何其他存储。 你可以购买无限量的额外存储空间。|
|组邮箱大小|50 GB|

组织可以拥有的默认Microsoft 365数是 500，000。 若要超出默认限制，必须联系 Microsoft 支持部门。 有关组限制Microsoft 365，请参阅Microsoft 365组 -[管理员帮助](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

当你拥有Microsoft 365组使用情况的可操作信息时，管理你的组会更有效。 该Microsoft 365 管理中心有一个报告工具，可用于查看存储用途、你拥有的活动组数以及用户如何使用组。 有关详细信息[Microsoft 365请参阅管理中心中的](../activity-reports/office-365-groups.md)报告。

## <a name="sensitivity-labels"></a>敏感度标签

可以创建敏感度标签，组织中用户在创建组时可设置Microsoft 365标签。 使用敏感度标签，可以配置： 

- 隐私 (公共或私有) 
- 外部用户访问
- 非托管设备访问

例如，可以创建一个称为"高度机密"的标签，并指定用此标签创建的任何组都是私有组，不允许外部用户。 当贵组织的用户在组创建期间选择此标签时，该组将设置为专用组，并且不允许组的成员向该组添加外部用户。

> [!IMPORTANT]
> 如果当前正在使用分类标签，则启用敏感度标签后，创建组的用户将无法再使用这些标签。 

有关创建、管理和使用敏感度标签的信息，请参阅使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint[网站中的内容](../../compliance/sensitivity-labels-teams-groups-sites.md)。

## <a name="which-microsoft-365-plans-include-groups"></a>哪些Microsoft 365计划包括组？

任何Microsoft 365和 Exchange Online SharePoint 订阅都将支持组。 这包括商业基础版和商业高级版计划，以及 Enterprise E1、E3 和 E5 计划。 组负责授权创建组 (也称为组"组织者"的组) 。 只要组织者拥有所需的组具有的任何功能的正确许可证，该许可证就会传达给组。

> [!NOTE]
> 有关服务系列Microsoft 365和计划的更多详细信息，请参阅Microsoft 365[计划选项。](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

如果你有仅 Exchange 计划，你仍然可以获取 Outlook 中的组的共享收件箱和共享日历功能，但你无法获取文档库、Planner 或其他任何功能。

Microsoft 365组使用Azure Active Directory。 你获取的组功能取决于Azure Active Directory订阅，以及分配给组组织者的许可证。

> [!IMPORTANT]
> 对于所有组功能，如果你有 Azure AD Premium订阅，则用户可以加入组，无论他们是否分配有 AAD P1 许可证。 不强制执行许可。
> 我们将定期生成使用情况报告，告知你哪些用户缺少许可证，并且需要为其分配的许可证符合许可要求。 例如，假设用户没有许可证，他们将被添加到强制执行命名策略的组。 报告将标记你需要许可证。

## <a name="related-content"></a>相关内容

[Learn about Microsoft 365 Groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (article) \
[Upgrade distribution lists to Microsoft 365 Groups](../manage/upgrade-distribution-lists.md) (article) \
[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article) \
[SharePoint Online 限制 (](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)文章) \
[在 Microsoft Stream 中组织组](/stream/groups-channels-organization) 和频道 (文章) 
