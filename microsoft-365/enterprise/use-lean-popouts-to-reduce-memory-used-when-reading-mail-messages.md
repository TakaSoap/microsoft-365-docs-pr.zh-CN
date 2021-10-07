---
title: 使用斜弹出式弹出窗口减少阅读邮件时所使用的内存
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: 本文包含有关使用精简弹出窗口来提高邮件下载性能Outlook 网页版。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aaacacc0c1db418181690a5a4691bd251180d97c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188981"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>使用斜弹出式弹出窗口减少阅读邮件时所使用的内存

本文包含用于提高邮件下载性能Outlook 网页版。 本文是 Network [planning and performance tuning for Office 365的一](./network-planning-and-performance.md)部分。
  
作为Office 365管理员、全局管理员或用户管理员，你可以配置Outlook 网页版 以提供精简弹出窗口，即 Microsoft Edge 或 Internet Explorer 中某些电子邮件的较小、内存占用较少的版本。  当为用户配置斜弹出Outlook 网页版，将加载服务器端呈现的组件以优化性能。
  
> [!NOTE]
> 自 2018 年 3 月起，精简弹出窗口不适用于指定使用权限限制的邮件，例如信息权限管理 (IRM) 。
  
这些功能将继续在主窗口中工作，但在精简弹出窗口中不可用：
  
- Outlook 外接程序
  
- Skype for Business状态
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>为组织内部所有用户配置Office 365弹出窗口
  
1. [连接远程Exchange Online PowerShell 进行连接](/powershell/exchange/connect-to-exchange-online-powershell)。
  
2. 运行带 LeanPopoutEnabled 参数的 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet，如下所示：

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  例如，若要为组织中所有用户启用精简弹出窗口：
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  若要禁用组织中所有用户的精简弹出窗口：：

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
