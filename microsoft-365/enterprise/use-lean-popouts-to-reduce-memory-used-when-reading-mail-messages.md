---
title: 使用斜弹出式弹出窗口减少阅读邮件时所使用的内存
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: 本文包含有关在 Web 上使用斜弹出式Outlook下载性能的信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925252"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>使用斜弹出式弹出窗口减少阅读邮件时所使用的内存

本文包含用于改进 Web 上邮件Outlook下载性能的信息。 本文是 Network [planning and performance tuning for Office 365项目的一](./network-planning-and-performance.md)部分。
  
作为Office 365管理员，可以在 Web 上配置 Outlook 以提供精简弹出窗口，即 Microsoft Edge或 Internet Explorer 中某些电子邮件的较小、内存占用较少的版本。 当为 Web 上的Outlook精简弹出窗口时，将加载服务器端呈现的组件以优化性能。
  
> [!NOTE]
> 截至 2018 年 3 月，精简弹出窗口不适用于指定使用权限限制的邮件，例如信息权限管理 (IRM) 。
  
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