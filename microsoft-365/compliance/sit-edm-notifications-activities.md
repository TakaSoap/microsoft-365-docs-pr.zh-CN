---
title: 创建精确数据匹配活动通知
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何为精确数据匹配活动创建通知。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1033b6cd84f84db65f49f95e008e20eada63ca64
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914592"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>创建精确数据匹配活动通知

当 [使用精确数据匹配 (EDM) 创建自定义敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) 时，在 [审核日志](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log) 中会创建大量活动。 可以使用 [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet 创建通知，让你了能这些活动何时开始：

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
 创建 EDM 活动通知的功能仅可用于 World Wide 和 GCC 云。

## <a name="pre-requisites"></a>先决条件

所使用帐户必须为下列之一：

- 全局管理员
- 合规性管理员
- Exchange Online 管理员

若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。

这些订阅中包含基于 EDM 的分类:

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 合规
- Microsoft E5/A5 信息保护和治理

有关 DLP 许可的详细信息，请参阅 [适用于安全与合规性的 Microsoft 365 许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

## <a name="configure-notifications-for-edm-activities"></a>配置 EDM 活动通知

1. 连接到[安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 使用想要为其创建通知的活动运行 `New-ProtectionAlert` cmdlet。  例如，如果希望在 **UploadDataCompleted** 操作发生时收到通知，请运行:

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    对于 **UploadDataFailed**，可以运行：
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>相关文章

- [了解基于确切数据匹配的敏感信息类型](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)