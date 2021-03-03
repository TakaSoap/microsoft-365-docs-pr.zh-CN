---
title: Microsoft Productivity Score - 隐私
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 如何使用"工作效率分数"保护隐私。
ms.openlocfilehash: b522c40cba746f3a4ede2404cf671607d62a3282
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406556"
---
# <a name="privacy-controls-for-productivity-score"></a>生产力分数的隐私控件

Productivity Score 通过使用 Microsoft 365 和支持它的技术体验，提供对组织数字转型旅程的见解。  你的组织的分数反映了人员和技术体验度量，并可以与类似你组织的基准进行比较。 有关详细信息，请参阅" [生产力分数"概述](productivity-score.md)。

隐私对 Microsoft 非常重要。 若要了解如何保护你的隐私，请参阅 [Microsoft 的隐私声明](https://privacy.microsoft.com/privacystatement)。 工作效率分数使作为组织的 IT 管理员可以访问隐私设置，以帮助确保查看的任何工作效率分数信息都可操作，同时不会损害组织在 Microsoft 中的信任。

在人员体验区域中，指标仅在组织级别可用。 此区域通过查看内容协作、移动性、会议、团队合作和通信的类别来了解用户如何使用 Microsoft 365。 我们支持你使用多个级别的控件，以帮助你满足内部隐私策略需求。
这些控件可让你：

- 灵活的管理员角色，可控制谁可以在"工作效率分数"中查看信息。
- 选择退出人员体验区域的功能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>灵活的管理员角色，控制谁可以在"工作效率分数"中查看信息

若要查看整个工作效率分数，你需要是以下管理员角色之一：

- 全局管理员
- Exchange 管理员
- SharePoint 管理员
- Skype for Business 管理员
- Teams 管理员
- 全局读取者
- 报告读取者
- 使用情况摘要报告阅读器

将"报告读取者"或"使用率摘要报告读取者"角色分配给负责变更管理和采用（但不一定是 IT 管理员）的任何人。 通过此角色，他们可以访问 Microsoft 365 管理中心中完整的工作效率分数体验。

"使用率摘要报告读取者"角色必须经过 PowerShell cmdlet 分配，直到它在 2020 年稍后从 Microsoft 365 管理中心分配。

若要使用 PowerShell 分配使用率摘要报告读取者角色，

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

还可以选择退出"生产力分数"的"人员体验"区域。 如果选择退出，则组织的任何用户都将无法查看这些指标，并且你的组织将从涉及通信、会议、团队合作、内容协作和移动性的任何计算中删除。 你必须是全局管理员才能选择你的组织退出人员体验报告。

若要选择退出：：

1. 在管理中心中，转到 **"设置**   >   **组织设置**  >  **生产力分数"。**
2. 取消选中显示允许 Microsoft  **365 使用情况数据用于用户体验见解的框**。 若要了解如何在 Intune 配置管理器中修改 Endpoint Analytics 的数据共享设置，请选择"**了解更多"。**
3. 选择 **"保存"。**

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="你可以选择退出人员体验的&quot;组织设置&quot;页。":::
