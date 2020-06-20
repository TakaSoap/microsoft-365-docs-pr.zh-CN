---
title: 启用或禁用审核日志搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: 如何在安全 & 合规中心中打开或关闭审核日志搜索功能，以启用或禁用管理员在审核日志中搜索的功能。
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819132"
---
# <a name="turn-audit-log-search-on-or-off"></a>启用或禁用审核日志搜索

您（或另一个管理员）必须先启用审核日志记录，然后才能开始搜索审核日志。 当安全 & 合规中心中的审核日志搜索打开时，组织中的用户和管理员活动将记录在审核日志中，并保留90天，且最多为一年，具体取决于分配给用户的许可证。 但是，您的组织可能出于不需要记录和保留审核日志数据的原因。 在这些情况下，全局管理员可能会决定关闭 Microsoft 365 中的审核。

> [!IMPORTANT]
> 如果您在 Microsoft 365 中关闭审核日志搜索，则不能使用 Office 365 管理活动 API 或 Azure Sentinel 来访问您的组织的审核数据。 按照本文中的步骤关闭审核日志搜索意味着，在使用 Security & 合规中心或在 Exchange Online PowerShell 中运行**UnifiedAuditLog** cmdlet 时，搜索审核日志时不会返回任何结果。 这也意味着不会通过 Office 365 管理活动 API 或 Azure Sentinel 提供审核日志。
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>在打开或关闭审核日志搜索之前

- 您必须在 Exchange Online 中向您分配 "审核日志" 角色，才能在 Microsoft 365 组织中打开或关闭审核日志搜索。 默认情况下，此角色在 Exchange 管理中心中的 "**权限**" 页上分配给合规性管理和组织管理角色组。 Microsoft 365 中的全局管理员是 Exchange Online 中的 "组织管理" 角色组的成员。 
    
    > [!NOTE]
    > 必须在 Exchange Online 中向用户分配权限，才能打开或关闭审核日志搜索。 如果您在安全 & 合规中心中向用户分配 "**权限**" 页上的 "审核日志" 角色，则他们将无法打开或关闭审核日志搜索。 这是因为基础 cmdlet 是 Exchange Online cmdlet。 
    
- 有关搜索审核日志的分步说明，请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。 有关 Microsoft 365 管理活动 API 的详细信息，请参阅[microsoft 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。
    
## <a name="turn-on-audit-log-search"></a>启用审核日志搜索

您可以使用安全 & 合规性中心或 PowerShell 在 Microsoft 365 中启用审核日志搜索。 在您打开审核日志搜索后，可能需要几个小时才能在搜索审核日志时返回结果。 您必须在 Exchange Online 中向您分配 "审核日志" 角色，才能启用审核日志搜索。
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>使用安全 & 合规性中心启用审核日志搜索

1. [转到安全 & 合规性中心](https://protection.office.com)并登录。

2. 在 "安全性 & 合规性中心中，转到"**搜索** \> **审核日志搜索**"。

   将显示一个横幅，指出审核必须打开以记录用户和管理员活动。

3. 单击 "**启用审核"**。

    ![单击 "启用审核"](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    标题已更新，指示审核日志正在准备，并且您可以在几个小时内搜索用户和管理活动。

### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 打开审核日志搜索

1. [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 运行以下 PowerShell 命令以在 Office 365 中启用审核日志搜索。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    将显示一条消息，指出可能需要长达60分钟的时间才能使更改生效。
  
## <a name="turn-off-audit-log-search"></a>关闭审核日志搜索

您必须使用连接到 Exchange Online 组织的远程 PowerShell，才能关闭审核日志搜索。 与启用审核日志搜索类似，您必须在 Exchange Online 中将 "审核日志" 角色分配给 "关闭审核日志搜索"。
  
1. [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 运行以下 PowerShell 命令以关闭 Office 365 中的审核日志搜索。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 一段时间后，验证审核日志搜索是否已关闭（已禁用）。 可通过 2 种方法执行此操作：

    - 在 PowerShell 中，运行以下命令：

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      `False` _UnifiedAuditLogIngestionEnabled_属性的值指示已关闭审核日志搜索。 

    - 在 "[安全性 & 合规性中心](https://protection.office.com)中，转到"**搜索** \> **审核日志搜索**"。

      将显示一条横幅，指出必须打开审核才能记录用户和管理员活动。