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
ms.openlocfilehash: 8686c7c86249a408fe8d4fda14c2ae23a168cafe
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999402"
---
# <a name="privacy-controls-for-productivity-score"></a>用于提高工作效率的隐私控制分数

工作效率分数可帮助组织使用可帮助你评估和改进人员和技术体验的指标来转换工作的完成情况。 它可帮助您了解您的组织的工作方式，并提供可帮助您专注于启用改进体验的指标。  您还可以将指标连接到操作，以帮助您更新技能和系统，以便每个人都可以完成其最佳工作。 分数将反映您的组织的绩效，还使您能够安全地将您的成绩与其他组织（如你的公司）进行比较。  有关更多详细信息，请查看 [工作效率分数概述](productivity-score.md)。

你的隐私对我们非常重要。 若要了解我们如何保护你的隐私，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。 工作效率分数提供了有关组织中的人员如何与控件合作以确保信息在不会影响您在 Microsoft 中放置的信任的过程中的关键信息。

在 "人员体验" 区域内，在组织级别提供指标，并将所有用户包括在 Microsoft 365 租户中。 此区域通过查看内容协作、移动性、会议、团队合作和通信的类别，了解用户如何使用 Microsoft 365。 为帮助你推动培训和认知，以帮助你的产品可能需要支持的一组人员，我们还向你提供有关各个级别的信息。 虽然我们提供了这一级别的透明度，但我们还为你启用了多个级别的控件，以帮助你满足内部隐私策略需求。
以下控件为您提供了：

- 灵活的管理员角色，可控制谁可以查看工作效率分数中的信息。
- 能够取消识别用户级指标。
- 能够退出人员体验。
- 退出 "人员体验" 区域的功能

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>灵活的管理员角色，可控制谁可以查看工作效率分数中的信息

若要查看整个工作效率评分（包括租户级指标和每用户详细信息），您的角色应为以下管理员角色之一：

- 全局管理员
- Exchange 管理员
- SharePoint 管理员
- Skype for Business 管理员
- Teams 管理员
- 全局读取者
- 报告读取者

将报告读者角色分配给负责更改管理和采用的任何人。 通过此角色，他们可以访问完整的体验，包括租户级指标和每用户级别的详细信息。

"人员体验报表" 包含每个用户的活动详细信息，每个类别的详细信息页面。 分配名为使用率摘要报告读取器的自定义角色。 (可从) 2020 年10月29日开始，仅支持人员体验的聚合指标的访问。 必须通过 PowerShell cmdlet 分配此角色，才能将其分配给11/15/2020 上的 Microsoft 管理中心。

若要将使用率摘要报告读者角色分配给 PowerShell，请执行以下操作：

- 运行以下 PowerShell：

```powershell
Connect-AzureAD
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="生产率报告中的 &quot;通信&quot; 页面。":::

## <a name="de-identification-of-user-level-metrics"></a>对用户级指标的取消标识

若要使为所有报告匿名收集的数据，您必须是全局管理员。 此操作将隐藏所有报告中的可识别信息（如用户、组和网站名称），包括工作效率分数和 Microsoft 365 使用率。

1. 在管理中心中，转到 " **设置**   >   **组织设置** "，在 " **服务** " 选项卡下，选择 " **报告** "。
2. 选择 "  **报告** "，然后选择  **显示用户、组和网站名称的匿名标识符，以提高工作效率的分数和使用情况报告** 。 此设置既适用于使用情况报告，也适用于模板应用。
3. 选择 "  **保存更改** "。

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="将用户信息设为匿名的报告。":::

## <a name="capability-to-opt-out-of-people-experiences"></a>能够退出人员体验

当工作效率分数通常可用时，您还可以选择不在工作效率分数方面的人员体验。 如果选择退出，则组织中的任何人都无法查看这些指标，并且您的组织将从涉及通信、会议、团队合作、内容协作和移动性的任何计算中删除。

1. 在管理中心中，转到 " **设置**   >   **组织设置** "，在 " **服务** " 选项卡下，选择 " **报告** "。
2. 选择 "  **报告** "，然后取消选中 "  **允许将 Microsoft 365 使用率数据用于人们体验见解** " 的复选框。 若要了解如何在 Intune 配置管理器中修改终结点分析的数据共享设置，请单击 " **了解更多** "。
3. 选择 "  **保存更改** "。

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="&quot;组织设置&quot; 页，您可以在其中选择 &quot;人员&quot; 体验。":::