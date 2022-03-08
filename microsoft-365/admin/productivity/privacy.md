---
title: Microsoft Productivity Score - 隐私
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 如何使用工作效率分数保护隐私。
ms.openlocfilehash: 94e0e1fb3190bc45fb0ad580cd823cb121fb60cf
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320727"
---
# <a name="privacy-controls-for-productivity-score"></a>工作效率分数的隐私控件

生产力分数通过组织对数字转型的Microsoft 365和支持它的技术体验提供见解。  你的组织的分数反映了人员和技术体验指标，可以与类似你组织的基准进行比较。 有关详细信息，请参阅工作效率 [分数概述](productivity-score.md)。

你的隐私对 Microsoft 非常重要。 若要了解如何保护你的隐私，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。 工作效率分数使作为组织的 IT 管理员可以访问隐私设置，以帮助确保你查看的任何工作效率分数信息都是可操作的信息，同时不会损害组织在 Microsoft 中的信任。

在人员体验区域中，指标仅在组织级别可用。 此区域通过查看内容Microsoft 365、移动性、会议、团队合作和通信类别来了解用户如何使用网站。 我们支持多个级别的控制，以帮助你满足内部隐私策略需求。
这些控件可让你：

- 灵活的管理员角色，可控制谁可以看到 Productivity Score 中的信息。
- 选择退出人员体验区域的功能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>灵活的管理员角色，可控制谁可以看到 Productivity Score 中的信息

若要查看整个工作效率分数，你需要是以下管理员角色之一：

- 全局管理员
- Exchange 管理员
- SharePoint 管理员
- Skype for Business 管理员
- Teams 管理员
- 全局读取者
- 报告读取者
- 使用情况摘要报告阅读器

将"报告读取者"或"使用率摘要报告读取者"角色分配给负责变更管理和采用的任何人员，但不一定是 IT 管理员。 通过此角色，他们可以访问管理中心内Microsoft 365分数体验。

"使用率摘要报告读取者"角色必须通过 PowerShell cmdlet 分配，直到它在 2020 年Microsoft 365 管理中心分配。

若要使用 PowerShell 分配使用情况摘要报告读取者角色：

- 运行以下 PowerShell：

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>选择退出人员体验的功能

还可以选择退出工作效率分数的"人员体验"区域。 如果选择退出，则贵组织的任何用户都将无法查看这些指标，并且你的组织将从涉及通信、会议、团队合作、内容协作和移动性的任何计算中删除。 你必须是全局管理员才能选择你的组织退出人员体验报告。

若要选择退出：

1. 在管理中心，转到  >  设置 **Org** >  设置 **生产分数**。
2. 取消选中显示"允许Microsoft 365 **数据以用于用户体验见解"的框**。 若要了解如何在 Intune 配置管理器中修改 Endpoint Analytics 的数据共享设置，请选择" **了解更多信息"**。
3. 选择  **"保存"**。

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="组织设置页面，可在其中选择退出人员体验。":::
