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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解 Microsoft 365 组。
ms.openlocfilehash: b3bc0c30f4ac292da7af46678fc742854984db12
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925346"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>面向管理员的 Microsoft 365 组概述

Microsoft 365 组是推动 Microsoft 365 所有团队合作的基础成员身份服务。 使用 Microsoft 365 组，你可以向一组人员授予对共享资源集合的访问权限。 这些资源包括：

- 共享 Outlook 收件箱
- 共享日历
- SharePoint 文档库
- A Planner
- OneNote 笔记本
- Power BI
- 如果 (Yammer 对象创建组，Yammer) 
- 团队 (组是否从 Teams) 
- 如果 (Project 网页应用，路线图) 

对于 Microsoft 365 组，不必手动为其中每个资源分配权限。 向组添加人员会自动授予他们所需的权限。

任何用户都可以创建组，除非你 [将组创建限制为一组特定的人员](manage-creation-of-groups.md)。 如果限制组创建，则无法创建组的用户将无法创建 SharePoint 网站、规划人员或团队。 这些服务要求创建它们的人能够创建组。 用户仍然可以参与组活动，例如，在 Planner 中创建任务或使用 Teams 聊天，但如果他们是组的成员。

组具有以下角色：

- **所有者** - 组所有者可以添加或删除成员，并且具有独特的权限，如从共享收件箱中删除对话或更改有关组的不同设置。 组所有者可以重命名组、更新说明或图片等。
- **Members** - 成员可以访问组内的所有内容，但无法更改组设置。 默认情况下，团队成员可以邀请来宾加入你的组，但你可以 [控制该设置](manage-guest-access-in-groups.md)。
- **来宾** - 组来宾是组织外部的成员。

只有全局管理员、用户管理员和组管理员可以在 Microsoft 365 管理中心创建和管理组。 你不能是委派管理员（例如代表管理员的顾问）。

作为管理员，您可以：

- [指定可以创建组的人](manage-creation-of-groups.md)
- [为组织中的组创建命名策略](groups-naming-policy.md)
- [选择创建组时要使用哪个域](choose-domain-to-create-groups.md)
- [管理对组的来宾访问](manage-guest-access-in-groups.md)
- [在删除 (](restore-deleted-group.md) 30 天内恢复已删除) 

如果你希望采用更自动化的方式来管理 Microsoft 365 组的生命周期，可以使用过期策略以特定时间间隔使组过期。 组的所有者将在组过期前 30、15 和 1 天收到一封电子邮件，允许他们根据需要续订组。 请参阅 [：Microsoft 365 组过期策略](office-365-groups-expiration-policy.md)。

可以从 Microsoft 365 管理中心或 [PowerShell 管理组](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel)。

如果您具有许多用户（如大型企业或企业中的用户），则您可能有许多用户出于各种目的创建组。 我们强烈建议你查看 [Microsoft 365](plan-for-groups-governance.md) 组中管理规划的最佳实践。

## <a name="group-limits"></a>组限制

以下限制适用于 Microsoft 365 组：

|最大值...|值|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|管理员可以创建的组|最多默认租户限制为 500 K|
|成员数目|超过 1，000 个，但只有 1，000 个可以同时访问组对话。 <br>在 Outlook 中访问日历和大型组的对话时，用户可能会注意到延迟。|
|用户可以成为其成员组数|7,000|
|文件存储|每个订阅用户 1 TB + 10 GB + 已购买任何其他存储。 你可以购买无限量的额外存储空间。|
|组邮箱大小|50 GB|

组织可以拥有的默认最大 Microsoft 365 组数为 500，000。 若要超出默认限制，必须联系 Microsoft 支持部门。 有关 Microsoft 365 组限制详细信息，请参阅 [Microsoft 365 组 - 管理员帮助](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

当你拥有有关组使用情况的可操作信息时，管理 Microsoft 365 组会更有效。 Microsoft 365 管理中心有一个报告工具，可用于查看存储用途、你拥有的活动组数以及用户如何使用组。 有关详细信息，请参阅： [管理中心中的 Microsoft 365](../activity-reports/office-365-groups.md) 报告。

## <a name="sensitivity-labels"></a>敏感度标签

可以创建组织中用户在创建 Microsoft 365 组时可以设置的敏感度标签。 使用敏感度标签，可以配置： 

- 隐私 (公共或专用) 
- 外部用户访问
- 非托管设备访问

例如，可以创建一个称为"高度机密"的标签，并指定使用此标签创建的任何组都是私有组，不允许外部用户。 当贵组织的用户在组创建期间选择此标签时，该组将设置为专用组，并且不允许组成员向组中添加外部用户。

> [!IMPORTANT]
> 如果当前正在使用分类标签，则启用敏感度标签后，创建组的用户将无法再使用这些标签。 

有关创建、管理和使用敏感度标签的信息，请参阅使用敏感度标签保护 [Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

## <a name="which-microsoft-365-plans-include-groups"></a>哪些 Microsoft 365 计划包含组？

任何具有 Exchange Online 和 SharePoint Online 的 Microsoft 365 订阅都将支持组。 这包括商业基础版和商业高级版计划，以及企业版 E1、E3 和 E5 计划。 组负责授权创建组 (也称为组"组织者"的组) 。 只要组织者具有希望组具有的任何功能的正确许可证，该许可证就会传达到组。

> [!NOTE]
> 有关 Microsoft 365 服务系列和计划的更多详细信息，请参阅 [Microsoft 365 计划选项](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。

如果你有仅 Exchange 计划，仍可以在 Outlook 中获取组的共享收件箱和共享日历功能，但无法获取文档库、Planner 或其他任何功能。

Microsoft 365 组使用 Azure Active Directory。 你获取的组功能取决于你拥有哪个 Azure Active Directory 订阅，以及分配给组组织者的许可证。

> [!IMPORTANT]
> 对于所有组功能，如果你有 Azure AD Premium 订阅，则用户可以加入组，无论他们是否分配有 AAD P1 许可证。 不强制执行许可。
> 我们将定期生成使用情况报告，告知您哪些用户缺少许可证，并且需要为其分配一个许可证，以便符合许可要求。 例如，假设用户没有许可证，并且他们被添加到强制执行命名策略的组中。 该报告将标记他们需要许可证。

## <a name="related-articles"></a>相关文章

[了解 Microsoft 365 组](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[将通讯组列表升级到 Microsoft 365 组](../manage/upgrade-distribution-lists.md)

[使用 PowerShell 管理 Microsoft 365 组](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
