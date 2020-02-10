---
title: 管理审核日志保留策略
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 审核日志保留策略是 Microsoft 365 中的新高级审核功能的一部分。 通过审核日志保留策略，可指定组织中审核日志的保留时间。
ms.openlocfilehash: 00e3ba527ee72fced0d264457375210e138b006e
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862380"
---
# <a name="manage-audit-log-retention-policies"></a>管理审核日志保留策略

可在安全与合规中心创建和管理审核日志保留策略。 审核日志保留策略是 Microsoft 365 中的新高级审核功能的一部分。 通过审核日志保留策略，可指定组织中审核日志的保留时间。 可将审核日志保留长达一年时间。 可以根据以下标准创建策略：

- 一个或多个 Microsoft 365 服务中的所有活动

- 所有用户或特定用户执行的特定活动（在特定服务中）

- 优先级，用于指定当组织中有多个策略时优先使用哪个策略

## <a name="default-audit-log-retention-policy"></a>默认审核日志保留策略

Microsoft 365 中的高级审核功能为所有组织提供默认审核日志保留策略。 此策略将所有 Exchange、SharePoint 和 Azure Active Directory 审核记录保留一年。 此默认策略将保留审核记录，其中包含**工作负载**属性（活动发生的服务）的 **AzureActiveDirectory**、**Exchange** 或 **SharePoint** 的值。 无法修改默认策略。 请参阅本文的[详细信息](#more-information)部分，以获取默认策略中包含的每个工作负载的记录类型列表。

> [!NOTE]
> 默认审核日志保留策略仅适用于分配了 Office 365 或 Microsoft 365 E5 许可证或具有 Microsoft 365 E5 合规版加载项许可证的用户执行的活动审核记录。 如果你的组织中有非 E5 用户，则其相应的审核记录将保留 90 天。

## <a name="before-you-begin"></a>准备工作

- 必须在安全与合规中心为你分配了“组织配置”角色，这样才能创建或修改审核保留策略。

- 在组织中，你最多可以拥有 50 个审核日志保留策略。

- 若要将审核日志保留超过 90 天，必须为生成审核日志的用户分配 Office 365 或 Microsoft 365 E5 许可证，或者该用户必须具有 Microsoft 365 E5 合规版加载项许可证。

- 所有自定义审核日志保留策略（由组织创建）都优先于默认保留策略。 例如，如果为保留期短于一年的 Exchange 邮箱活动创建审核日志保留策略，则 Exchange 邮箱活动的审核记录将在自定义策略指定的较短期限内保留。

## <a name="create-an-audit-log-retention-policy-in-the-security--compliance-center"></a>在安全与合规中心创建审核日志保留策略

1. 转到 [https://protection.office.com](https://protection.office.com)，然后使用在安全与合规中心分配了“组织配置”角色的用户帐户登录。 

2. 在安全与合规中心的左侧窗格中，单击“**搜索**” > “**审核日志搜索**”。

    此时将显示“**审核日志搜索**”页面。

    ![“审核日志搜索”页面](media/AuditLogRetentionPolicy1.png)

3. 单击“**新建保留策略**”，然后在弹出页面上填写以下字段：

    ![审核日志保留策略弹出页面](media/AuditLogRetentionPolicy2.png)

   a. **名称**：审核日志保留策略的名称。 此名称必须在你的组织中保持唯一。
   
   b. **说明**：可选，但有助于提供有关策略的信息，例如记录类型或工作负载、策略中指定的用户以及期限。

   c. **记录类型**：将为其应用策略的审核记录类型。 如果选择多个记录类型，则不能选择活动，因为该策略将应用于所选记录类型的所有活动。 此外，如果将此属性留空，则必须在“**用户**”框中选择用户。

   d. **活动**：使用此框从所选的记录类型中选择活动。 你可以选择要为其应用策略的特定活动。 如果未选择特定活动，则该策略将应用于所选记录类型的所有活动。

   e. **用户**：选择一个或多个要为其应用策略的用户。 如果将此框留空，则该策略将应用于所有用户。 如果将“**记录类型**”留空，则必须选择用户。

   f. **期限**：保留符合策略条件的审核日志的时间。

   g. **优先级**：此值确定处理组织中的审核日志保留策略的顺序。 该值越大，表示优先级越高。 例如，优先级值为 **5** 的策略将优先于优先级值为 **0** 的策略。 如前文所述，任何自定义审核日志保留策略都优先于组织的默认策略。

6. 单击“**保存**”以创建新的审核日志保留策略。 

目前，不会指示已成功创建保留策略。 有关查看审核日志保留策略的属性，请参阅下一节。

## <a name="create-an-audit-log-retention-policy-in-powershell"></a>在 PowerShell 中创建审核日志保留策略

你还可以使用 Office 365 安全与合规中心 PowerShell 来创建审核日志保留策略。 

1. [连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

2. 运行以下命令以创建审核日志保留策略。 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```
    
    本示例使用以下设置创建名为“Microsoft Teams 审核策略”的审核日志保留策略：

   - 策略说明。

   - 保留所有 Microsoft Teams 活动（由 *RecordType* 参数定义）。

   - 将 Microsoft Teams 审核日志保留一年。

   - 优先级为 100。

下面是创建审核日志保留策略的另一个示例。 此策略将用户 admin@contoso.onmicrosoft.com 的“用户登录”活动的审核日志保留六个月。

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

有关详细信息，请参阅 [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy)。

## <a name="view-audit-log-retention-policies"></a>查看审核日志保留策略

目前，查看自定义审核日志保留策略的唯一方法是在安全与合规中心 PowerShell 中使用 **Get-UnifiedAuditRetentionPolicy** cmdlet。 下面是一个示例命令，用于显示组织中的审核日志保留策略的设置（在上一步中配置）。 此命令从最高优先级到最低优先级对策略进行排序。

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> 目前，**Get-UnifiedAuditLogRetentionPolicy** cmdlet 不会返回组织的默认审核日志策略。

有关详细信息，请参阅 [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy)。

## <a name="more-information"></a>详细信息

- 使用安全与合规中心 PowerShell 中的 **Set-UnifiedAuditLogRetentionPolicy** cmdlet 可修改现有审核日志保留策略。 有关详细信息，请参阅 [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/set-unifiedauditlogretentionpolicy)。

- 使用安全与合规中心 PowerShell 中的 **Remove-UnifiedAuditLogRetentionPolicy** cmdlet 可删除审核日志保留策略。 最长可能需要 30 分钟才能完全删除策略。 有关详细信息，请参阅 [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/remove-unifiedauditlogretentionpolicy)。

- 如前文所述，Azure Active Directory，Exchange 和 SharePoint 中针对操作的审核记录将保留一年。 下表列出了默认审核日志保留策略中包括的所有记录类型（针对每个服务）。 这意味着具有此记录类型的任何操作的审核日志都将保留一年，除非自定义审核日志保留策略对特定的记录类型、操作或用户具有优先权。 括号中显示了每种记录类型的枚举值（在审核记录中显示为 RecordType 属性值）。

   |AzureActiveDirectory |Exchange  |SharePoint|
   |:---------|:---------|:---------|
   |AzureActiveDirectory (8)|ExchangeAdmin (1)|ComplianceDLPSharePoint (11)|
   |AzureActiveDirectoryAccountLogon (9)|ExchangeItem (2)|ComplianceDLPSharePointClassification (33)|
   |AzureActiveDirectoryStsLogon (15)|Campaign (62)|Project (35)|
   ||ComplianceDLPExchange (13)|SharePoint (4)|
   ||ComplianceSupervisionExchange (68)|SharePointCommentOperation (37)|
   ||CustomerKeyServiceEncryption (69)|SharePointContentTypeOperation (55)|
   ||ExchangeAggregatedOperation (19)|SharePointFieldOperation (56)|
   ||ExchangeItemAggregated (50)|SharePointFileOperation (6)|
   ||ExchangeItemGroup (3)|SharePointListOperation (36)|
   ||InformationBarrierPolicyApplication (53)|SharePointSharingOperation (14)|
   ||||
