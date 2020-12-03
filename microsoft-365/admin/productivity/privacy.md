---
title: Microsoft 工作效率分数-隐私
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
description: 使用效率分数保护隐私的方式。
ms.openlocfilehash: db123042761b07ed64dd2dd94e783d65205e1460
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561504"
---
# <a name="privacy-controls-for-productivity-score"></a>用于提高工作效率的隐私控制分数

通过使用 Microsoft 365 和支持 it 的技术体验，工作效率分数可深入了解您的组织的数字转换旅程。  贵组织的分数反映了人员和技术体验指标，可以与类似于您的组织的基准进行比较。 有关更多详细信息，请查看 [工作效率分数概述](productivity-score.md)。

你的隐私对 Microsoft 很重要。 若要了解我们如何保护你的隐私，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。 生产效率分数为你的组织的 IT 管理员提供了对隐私设置的访问权限，以帮助确保你查看的任何工作效率分数信息可操作，同时不会损害你的组织在 Microsoft 中的信任。

在 "人员体验" 区域内，指标仅在组织级别可用。 此区域通过查看内容协作、移动性、会议、团队合作和通信的类别，了解用户如何使用 Microsoft 365。 我们为你启用了多个级别的控件，以帮助你满足内部隐私策略需求。
这些控件为您提供了：

- 灵活的管理员角色，可控制谁可以查看工作效率分数中的信息。
- 退出 "人员体验" 区域的功能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>灵活的管理员角色，可控制谁可以查看工作效率分数中的信息

若要查看整个生产效率分数，您需要具有以下管理员角色之一：

- 全局管理员
- Exchange 管理员
- SharePoint 管理员
- Skype for Business 管理员
- Teams 管理员
- 全局读取者
- 报告读取者
- 使用率摘要报告读者

将报告读者或使用情况摘要报告读者角色分配给负责更改管理和采用的任何人，但不一定是 IT 管理员。 通过此角色，他们可以访问 Microsoft 365 管理中心内的完全工作效率得分。

必须通过 PowerShell cmdlet 分配使用率摘要报告读者角色，才能将其分配给2020中稍后的 Microsoft 365 管理中心。

若要将使用率摘要报告读者角色分配给 PowerShell，请执行以下操作：

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


## <a name="capability-to-opt-out-of-people-experiences"></a>能够退出人员体验

您还可以选择退出 "人员体验" 工作效率分数区域。 如果你选择退出，你的组织中的任何人都无法查看这些指标，并且你的组织将从涉及通信、会议、团队合作、内容协作和移动性的任何计算中删除。

选择加入：

1. 在管理中心中，转到 "**设置**   >   **组织设置**"，然后在 "**服务**" 选项卡下选择 "**报告**"。
2. 取消选中 "  **允许将 Microsoft 365 使用率数据用于人们体验见解**" 的复选框。 若要了解如何在 Intune 配置管理器中修改终结点分析的数据共享设置，请选择 " **了解详细信息**"。
3. 选择 "  **保存**"。

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="&quot;组织设置&quot; 页，您可以在其中选择 &quot;人员&quot; 体验。":::