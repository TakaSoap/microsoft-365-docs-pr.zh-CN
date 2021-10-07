---
title: 为组织配置待筛选邮件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: '了解如何使用 PowerShell 为组织中所有用户或特定用户启用或禁用待筛选Exchange功能。 '
ms.openlocfilehash: 5037e7cb6518ca90f3d12c183fcff3c838c29907
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165080"
---
# <a name="configure-clutter-for-your-organization"></a>为组织配置待筛选邮件

> [!TIP]
> [重点收件箱](../setup/configure-focused-inbox.md) 将替换待筛选邮件。 了解更多信息 [：更新重点收件箱和待筛选邮件计划](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
作为管理员，您可能必须管理待筛选邮件功能Microsoft 365。 若要为组织的用户打开/关闭待筛选邮件功能，必须使用 Exchange PowerShell。  (个人可以使用以下说明将其打开/关闭：关闭/打开待筛选邮件[Outlook。](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
  
请参阅将[PowerShell](/powershell/exchange/exchange-online-powershell)与 Exchange Online 一连接 Exchange Online [PowerShell，](/powershell/exchange/connect-to-exchange-online-powershell)详细了解如何Exchange PowerShell。 您需要具有至少具有 Exchange 服务管理员角色且能够使用 PowerShell Exchange Online帐户。 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>使用 PowerShell 启用待筛选Exchange功能

可以通过运行 [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet 手动为邮箱启用待筛选邮件功能。 您还可以通过运行 [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet 查看组织中邮箱的待筛选邮件设置。 
  
为名为 Allie Bellew 的单个用户打开待筛选邮件功能
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>使用 PowerShell Exchange待筛选邮件功能

可以通过运行 [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet 手动禁用邮箱的待筛选邮件功能。 您还可以通过运行[Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet 查看组织中邮箱的待筛选邮件设置。 
  
关闭名为 Allie Bellew 的单个用户的待筛选邮件功能：
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

如果使用 PowerShell 批量创建用户，则需要针对每个用户的邮箱运行 [Set-Clutter](/powershell/module/exchange/set-clutter) 以管理待筛选邮件。 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>何时对用户显示待筛选邮件打开/关闭Outlook 网页版？
<a name="bkmk_onoff"> </a>

作为管理员，您可以使用 PowerShell 重新启用待筛选Exchange功能。 完成此操作后，重点收件箱将关闭，待筛选邮件功能将再次处于活动状态。 
  
 **如果你将 Outlook 网页版订阅Microsoft 365 商业高级版：**
  
- 如果用户当前已启用待筛选邮件功能： 
    
  - 将显示待筛选邮件设置
    
- 如果用户当前已启用重点收件箱： 
    
  - 不会显示待筛选邮件设置
    
- 如果"待筛选邮件"或"重点收件箱"均未启用： 
    
  - 待筛选邮件和重点收件箱均显示为用户邮件邮箱中的设置
    
 **如果你使用的是 Outlook.com：**
  
- 如果用户当前已启用待筛选邮件功能： 
    
  - 将显示待筛选邮件设置
    
- 如果用户当前已启用重点收件箱： 
    
  - 不会显示待筛选邮件设置
    
- 如果"待筛选邮件"或"重点收件箱"均未启用： 
    
  - 待筛选邮件和重点收件箱均显示为用户邮件邮箱中的设置
    
- 如果用户在过去某一时间点启用重点收件箱：
    
  - 永远不会显示待筛选邮件设置
    
    否则， 
    
  - 将显示待筛选邮件设置
    
## <a name="related-content"></a>相关内容

[使用待筛选邮件对邮件中的低优先级Outlook (](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)文章) \
[使用待筛选邮件对 OWA 邮件](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) 中的低优先级邮件进行排序 (文章) \
[关闭待筛选邮件Outlook (](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)文章) 
