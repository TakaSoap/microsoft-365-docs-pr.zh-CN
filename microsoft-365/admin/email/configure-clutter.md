---
title: 为您的组织配置邮件筛选
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: '了解如何使用 Exchange PowerShell 为组织中的所有用户或特定用户启用或禁用杂乱功能。 '
ms.openlocfilehash: 069cf7569ebb3654e979100291f6754693b24def
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400132"
---
# <a name="configure-clutter-for-your-organization"></a>为您的组织配置邮件筛选

> [!TIP]
> [重点收件箱](../setup/configure-focused-inbox.md)将替换混乱。 了解详细信息：[更新重点收件箱和我们关于待筛选计划](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
作为管理员，您可能需要在 Microsoft 365 中管理邮件筛选功能。 若要为组织中的用户打开/关闭筛选功能，必须使用 Exchange PowerShell。 （个人可以使用以下说明打开/关闭它：[关闭/打开 Outlook 中的杂乱功能](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)。） 
  
请查看[使用 PowerShell With Exchange online](https://go.microsoft.com/fwlink/?LinkID=402831) ，并[连接到 Exchange online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) ，以了解有关使用 exchange PowerShell 的详细信息。 您需要拥有至少具有 Exchange 服务管理员角色的帐户，并且能够使用 PowerShell 连接到 Exchange Online。 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>使用 Exchange PowerShell 打开杂乱

您可以通过运行 "[设置筛选](https://go.microsoft.com/fwlink/?LinkID=834446)" cmdlet 对邮箱手动启用筛选。 您还可以通过运行 "邮件[筛选](https://go.microsoft.com/fwlink/?LinkID=834759)" cmdlet 来查看组织中邮箱的杂乱设置。 
  
为名为 Allie Bellew 的单个用户打开杂乱的邮件
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>使用 Exchange PowerShell 禁用混乱

您可以通过运行 "[设置筛选](https://go.microsoft.com/fwlink/?LinkID=834446)" cmdlet 对邮箱手动禁用垃圾邮件。 您还可以通过运行 "邮件[筛选](https://go.microsoft.com/fwlink/?LinkID=834759)" cmdlet 来查看组织中邮箱的**杂乱**设置。 
  
对名为 Allie Bellew 的单个用户关闭筛选：
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

如果使用 PowerShell 批量创建用户，则需要对每个用户的邮箱运行[设置混乱](https://go.microsoft.com/fwlink/?LinkID=834446)，以管理杂乱。 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>何时对 web 上的 Outlook 中的用户显示 "杂乱" 开关？
<a name="bkmk_onoff"> </a>

作为管理员，你可以使用 Exchange PowerShell 重新启用筛选。 完成此操作后，将关闭重点收件箱，并再次激活杂乱的垃圾邮件。 
  
 **如果您使用的是 Microsoft 365 商业高级订阅的 web 上的 Outlook：**
  
- 如果用户当前启用了邮件筛选： 
    
  - 出现 "邮件" 设置
    
- 如果用户当前启用了重点收件箱： 
    
  - 杂乱设置不会显示
    
- 如果没有启用 "杂乱" 或 "重点收件箱"： 
    
  - "杂乱" 和 "重点收件箱" 显示为用户的邮件设置中的选项
    
 **如果您使用的是 Outlook.com：**
  
- 如果用户当前启用了邮件筛选： 
    
  - 出现 "邮件" 设置
    
- 如果用户当前启用了重点收件箱： 
    
  - 杂乱设置不会显示
    
- 如果没有启用 "杂乱" 或 "重点收件箱"： 
    
  - "杂乱" 和 "重点收件箱" 显示为用户的邮件设置中的选项
    
- 如果用户在过去某一点启用了重点收件箱：
    
  - 垃圾邮件设置将永远不会出现
    
    无权 
    
  - 将显示 "杂乱" 设置
    
## <a name="related-articles"></a>相关文章
<a name="bkmk_onoff"> </a>

[使用杂乱在 Outlook 中对低优先级邮件进行排序](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[使用杂乱在 OWA 中对低优先级邮件进行排序](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[关闭 Outlook 中的杂乱功能](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

