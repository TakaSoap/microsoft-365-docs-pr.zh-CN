---
title: 高级搜寻架构Microsoft 365 Defender中的命名更改
description: 跟踪并查看高级搜寻架构中的命名更改表和列
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 数据， 命名更改， 重命名
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5006347ad8f4487c904fc6df4934bbaf612a1bdf
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60664232"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高级搜寻架构 - 命名更改

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高级 [搜寻架构](advanced-hunting-schema-tables.md) 会定期更新以添加新表和列。 在某些情况下，重命名或替换现有列名称以改进用户体验。 请参阅本文，查看可能会影响查询的命名更改。

命名更改将自动应用于保存在安全中心的查询，包括自定义检测规则使用的查询。 无需手动更新这些查询。 但是，您需要更新以下查询：
- 使用 API 运行的查询
- 保存在安全中心外部的查询

## <a name="december-2020"></a>2020 年 12 月

| 表名 | 原始列名称 | 新列名称 | 更改原因
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | 客户反馈 |

## <a name="january-2021"></a>2021 年 1 月

| 列名称 | 原始值名称 | 新值名称 | 更改原因
|--|--|--|--|
| `DetectionSource` | MCAS | Microsoft Cloud App Security | 重新品牌 |
| `DetectionSource` | WindowsDefenderAtp| EDR| 重新品牌 |
| `DetectionSource` | WindowsDefenderAv | 防病毒 | 重新品牌 |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | 重新品牌 |
| `DetectionSource` | CustomerTI | 自定义 TI | 重新品牌 |
| `DetectionSource` | OfficeATP | Microsoft Defender for Office 365 | 重新品牌 |
| `DetectionSource` | MTP | Microsoft 365 Defender | 重新品牌 |
| `DetectionSource` | AzureATP | Microsoft Defender for Identity | 重新品牌 |
| `DetectionSource` | CustomDetection | 自定义检测 | 重新品牌 |
| `DetectionSource` | AutomatedInvestigation |自动调查 | 重新品牌 |
| `DetectionSource` | ThreatExperts | Microsoft 威胁专家 | 重新品牌 |
| `DetectionSource` | 第三方 TI | 第三方传感器 | 重新品牌 |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender for Endpoint | 重新品牌 |
|`ServiceSource` |Microsoft 威胁防护 | Microsoft 365 Defender | 重新品牌 |
| `ServiceSource` | Office 365 ATP |Microsoft Defender for Office 365 | 重新品牌 |
| `ServiceSource` |Azure ATP |Microsoft Defender for Identity | 重新品牌 |

`DetectionSource` 在 [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。 `ServiceSource` 在 [AlertEvidence 和](advanced-hunting-alertevidence-table.md) [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。 

## <a name="february-2021"></a>2021 年 2 月

1. 在 [EmailAttachmentInfo 和](advanced-hunting-emailattachmentinfo-table.md) [EmailEvents](advanced-hunting-emailevents-table.md) 表中，和 列 `MalwareFilterVerdict` `PhishFilterVerdict` 已替换为 `ThreatTypes` 列。 和 `MalwareDetectionMethod` `PhishDetectionMethod` 列也替换为 `DetectionMethods` 列。 通过简化，可以在新列下提供详细信息。 映射如下所示。

    | 表名 | 原始列名称 | 新列名称 | 更改原因
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | 包括更多检测方法 |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 包括更多威胁类型 |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | 包括更多检测方法 |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 包括更多威胁类型 |


2. 在 `EmailAttachmentInfo` 和 `EmailEvents` 表中， `ThreatNames` 添加了 列以提供有关电子邮件威胁详细信息。 此列包含"垃圾邮件"或"钓鱼邮件"等值。

3. 在 [DeviceInfo 表中](advanced-hunting-deviceinfo-table.md) ， `DeviceObjectId` 列已根据客户反馈 `AadDeviceId` 替换为该列。

4. 在 [DeviceEvents](advanced-hunting-deviceevents-table.md) 表中，修改了几个 ActionType 名称，以更好地反映操作的说明。 可在下方找到更改的详细信息。

    | 表名 | 原始 ActionType 名称 | 新的 ActionType 名称 | 更改原因
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | 客户反馈 |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | 客户反馈 |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | 客户反馈 |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | 客户反馈 |

## <a name="march-2021"></a>2021 年 3 月

`DeviceTvmSoftwareInventoryVulnerabilities`该表已被弃用。 将 替换为 `DeviceTvmSoftwareInventory` 和 `DeviceTvmSoftwareVulnerabilities` 表。

## <a name="may-2021"></a>2021 年 5 月

`AppFileEvents`该表已被弃用。 `CloudAppEvents`该表包含以前在表中的信息 `AppFileEvents` ，以及云服务中的其他活动。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)