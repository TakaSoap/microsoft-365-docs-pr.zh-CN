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
description: 如何打开或关闭安全与合规中心&审核日志搜索功能，以启用或禁用管理员搜索审核日志。
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976325"
---
# <a name="turn-audit-log-search-on-or-off"></a>启用或禁用审核日志搜索

默认情况下，Microsoft 365 和 Office 365 企业版组织启用审核日志记录。 这包括具有 E3/G3 或 E5/G5 订阅的组织。 启用审核日志中的搜索时，组织的用户和管理员活动将记录在 审核日志 中，并保留 90 天，最多保留一年，具体取决于分配给用户的许可证。 但是，您的组织可能出于不希望记录和保留数据审核日志的原因。 在这种情况下，全局管理员可能会决定在 Microsoft 365 中关闭审核。

> [!IMPORTANT]
> 如果在 Microsoft 365 中审核日志搜索功能，则你无法使用 Office 365 管理活动 API 或 Azure Sentinel 访问组织的审核数据。 按照本文中的步骤关闭 审核日志 搜索意味着在使用安全 & 合规中心搜索 审核日志 时或在 Exchange Online PowerShell 中运行 **Search-UnifiedAuditLog** cmdlet 时不会返回任何结果。 这也意味着审核日志无法通过 Office 365 管理活动 API 或 Azure Sentinel 提供。
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>打开或审核日志搜索之前

- 您必须在 Exchange Online 中分配有审核日志角色，审核日志 Microsoft 365 组织中启用或关闭搜索。 默认情况下，此角色分配给 Exchange 管理中心中"权限"页上的"合规性管理"和"组织管理"角色组。 Microsoft 365 中的全局管理员是 Exchange Online 中组织管理角色组的成员。 
    
    > [!NOTE]
    > 用户必须获得 Exchange Online 中的权限，才能审核日志或关闭搜索。 如果在安全与合规中心的"权限"页上为用户分配"审核日志"角色&，他们将无法打开或审核日志搜索。 这是因为基础 cmdlet 是 Exchange Online PowerShell cmdlet。 
    
- 有关搜索安全与合规中心的审核日志分步审核日志，请参阅& [搜索](search-the-audit-log-in-security-and-compliance.md)。 有关 Microsoft 365 管理活动 API 详细信息，请参阅 [Microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)管理 API 入门。

- 若要验证审核日志是否打开，可以在 Exchange Online PowerShell 中运行以下命令：

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    `True` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核日志已打开。 
    
## <a name="turn-on-audit-log-search"></a>打开搜索审核日志

如果未审核日志启用搜索，可以在合规中心或通过使用 Exchange Online PowerShell 将其打开。 打开搜索后，可能需要几个小时审核日志才能在搜索时返回审核日志。
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>使用合规中心启用审核日志搜索

1. [转到合规中心](https://protection.office.com) 并登录。

2. 在合规中心，转到 **"搜索**  >  **审核日志搜索"。**

   如果未审核日志启用搜索，则会显示一个横幅，指出必须启用审核才能记录用户和管理员活动。

3. 单击 **"启用审核"。**

    ![单击"启用审核"](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    横幅已更新为说明审核日志准备，并且您可以在几个小时内搜索用户和管理员活动。

### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 启用审核日志搜索

1. [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 运行以下 PowerShell 命令以在 Office 365 中审核日志搜索功能。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    将显示一条消息，指出更改最多可能需要 60 分钟才能生效。
  
## <a name="turn-off-audit-log-search"></a>关闭审核日志搜索

您必须使用 Exchange Online PowerShell 来关闭审核日志搜索。
  
1. [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 运行以下 PowerShell 命令以关闭审核日志搜索。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 一段时间之后，验证审核日志搜索是否 (禁用) 。 可通过 2 种方法执行此操作：

    - 在 Exchange Online PowerShell 中，运行以下命令：

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核日志搜索已关闭。 

    - 在合规 [中心](https://protection.office.com)，转到 **"搜索** \> **审核日志搜索"。**

      将显示一个横幅，指出必须启用审核才能记录用户和管理员活动。
