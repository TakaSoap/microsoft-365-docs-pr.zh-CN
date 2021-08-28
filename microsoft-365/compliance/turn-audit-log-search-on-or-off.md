---
title: 打开或关闭审核
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
description: 如何打开或关闭审核日志搜索功能Microsoft 365 合规中心启用或禁用管理员搜索审核日志。
ms.openlocfilehash: 793c76d45f2cd7aed43a959dfcb94edeb9869310
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58575320"
---
# <a name="turn-auditing-on-or-off"></a>打开或关闭审核

默认情况下，将为企业组织和企业组织启用Microsoft 365 Office 365日志记录。 但是，在组织Microsoft 365或Office 365时，应验证组织的审核状态。 有关说明，请参阅本文 [中的验证组织的](#verify-the-auditing-status-for-your-organization) 审核状态部分。 

启用 Microsoft 365 合规中心 中的审核时，组织的用户和管理员活动将记录在 审核日志 中，并保留 90 天，最多保留一年，具体取决于分配给用户的许可证。 但是，贵组织可能出于不希望记录并保留数据审核日志的原因。 在这种情况下，全局管理员可能会决定关闭审核Microsoft 365。

> [!IMPORTANT]
> 如果关闭审核Microsoft 365，则你无法通过 Office 365 管理活动 API 或 Azure Sentinel 访问组织的审核数据。 按照本文中的步骤关闭审核意味着在使用 Microsoft 365 合规中心 搜索 审核日志 或在 Exchange Online PowerShell 中运行 **Search-UnifiedAuditLog** cmdlet 时不会返回任何结果。 这也意味着审核日志无法通过 Office 365管理活动 API 或 Azure Sentinel 提供。
  
## <a name="before-you-turn-auditing-on-or-off"></a>打开或关闭审核之前

- 必须分配有"审核日志"角色Exchange Online在组织中启用或Microsoft 365审核。 默认情况下，此角色分配给管理中心中"权限"页上的"合规性管理"Exchange组。 Microsoft 365中的全局管理员是组织中组织管理角色Exchange Online。

    > [!NOTE]
    > 用户必须分配有权限Exchange Online才能启用或关闭审核。 如果在用户权限页上为用户分配审核日志Microsoft 365 合规中心，他们将无法启用或关闭审核。  这是因为基础 cmdlet 是一个Exchange Online PowerShell cmdlet。

- 有关搜索搜索列表的审核日志， [请参阅搜索](search-the-audit-log-in-security-and-compliance.md)审核日志。 有关管理活动 API Microsoft 365，请参阅 Microsoft 365 管理[API 入门](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="verify-the-auditing-status-for-your-organization"></a>验证组织的审核状态

若要验证是否为组织启用审核，可以在[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中运行Exchange Online命令：

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

`True` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核已打开。 值 `False` 表示未启用审核。

## <a name="turn-on-auditing"></a>启用审核

如果未为组织启用审核，可以在 Microsoft 365 合规中心或通过使用 PowerShell Exchange Online审核。 在打开审核后，可能需要几个小时才能在搜索查询时返回审核日志。
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>使用合规中心启用审核

1. 转到 <https://compliance.microsoft.com> 并登录。

2. 在页面的左侧导航窗格中，Microsoft 365 合规中心审核 **"。**

   如果未为组织启用审核，则会显示横幅，提示你开始录制用户和管理员活动。

   ![审核页上的横幅。](../media/AuditingBanner.png)

3. 单击" **开始录制用户和管理员活动"** 横幅。

   更改最多可能需要 60 分钟才能生效。

### <a name="use-powershell-to-turn-on-auditing"></a>使用 PowerShell 启用审核

1. [连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行以下 PowerShell 命令以启用审核。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    将显示一条消息，指出更改最多可能需要 60 分钟才能生效。
  
## <a name="turn-off-auditing"></a>关闭审核

您必须使用 Exchange Online PowerShell 来关闭审核。
  
1. [连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行以下 PowerShell 命令以关闭审核。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 一段时间后，确认审核已关闭， (禁用) 。 可以通过两种方式来执行此操作：

    - 在 Exchange Online PowerShell 中，运行以下命令：

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核已关闭。

    - 转到 **"审核**"页面中Microsoft 365 合规中心。

      如果未为组织启用审核，则会显示横幅，提示你开始录制用户和管理员活动。
