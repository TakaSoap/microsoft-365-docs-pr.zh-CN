---
title: Microsoft 365 Defender 高级搜寻架构中的命名更改
description: 跟踪和查看高级搜寻架构中的命名更改表和列
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 数据， 命名更改， 重命名， Microsoft 威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066865"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高级搜寻架构 - 命名更改

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高级 [搜寻架构](advanced-hunting-schema-tables.md) 会定期更新以添加新的表和列。 在某些情况下，将重命名或替换现有列名称，以改进用户体验。 请参阅本文，查看可能会影响查询的命名更改。

命名更改将自动应用于保存在安全中心的查询，包括自定义检测规则使用的查询。 无需手动更新这些查询。 但是，您需要更新以下查询：
- 使用 API 运行的查询
- 保存在安全中心外部的其他地方的查询

## <a name="december-2020"></a>2020 年 12 月

| 表名 | 原始列名称 | 新列名称 | 更改原因
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | 客户反馈 |

## <a name="january-2021"></a>2021 年 1 月

| 列名称 | 原始值名称 | 新值名称 | 更改原因
|--|--|--|--|
| `DetectionSource` | MCAS |    Microsoft Cloud App Security | 重新品牌 |
| `DetectionSource` | WindowsDefenderAtp|   EDR| 重新品牌 |
| `DetectionSource` | WindowsDefenderAv | 防病毒 | 重新品牌 |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | 重新品牌 |
| `DetectionSource` | CustomerTI |  自定义 TI | 重新品牌 |
| `DetectionSource` | OfficeATP | Microsoft Defender for Office 365 | 重新品牌 |
| `DetectionSource` | MTP   | Microsoft 365 Defender | 重新品牌 |
| `DetectionSource` | AzureATP |    Microsoft Defender for Identity | 重新品牌 |
| `DetectionSource` | CustomDetection   | 自定义检测 | 重新品牌 |
| `DetectionSource` | AutomatedInvestigation |自动调查 | 重新品牌 |
| `DetectionSource` | ThreatExperts | Microsoft 威胁专家 | 重新品牌 |
| `DetectionSource` | 第三方 TI | 第三方传感器 | 重新品牌 |
| `ServiceSource` | 每个租户| Microsoft Defender for Endpoint | 重新品牌 |
|`ServiceSource` |Microsoft 威胁防护   | Microsoft 365 Defender | 重新品牌 |
| `ServiceSource` | Office 365 ATP  |Microsoft Defender for Office 365 | 重新品牌 |
| `ServiceSource` |Azure ATP    |Microsoft Defender for Identity | 重新品牌 |

`DetectionSource` 在 [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。 `ServiceSource` 在 [AlertEvidence 和](advanced-hunting-alertevidence-table.md) [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。 
## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)