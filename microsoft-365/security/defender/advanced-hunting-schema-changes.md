---
title: Microsoft 365 Defender高级搜寻架构中的命名更改
description: 跟踪和查看命名更改高级搜寻架构中的表和列
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、Microsoft 365 Defender、microsoft 365、m365、搜索、查询、遥测、架构参考、kusto、表、数据、命名更改、重命名
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
ms.openlocfilehash: 4e58bb3d8c8cc7c507c4136abcabeb7e42b6827d
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "64731496"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高级搜寻架构 - 命名更改

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高级搜寻架构](advanced-hunting-schema-tables.md)会定期更新，以添加新的表和列。 在某些情况下，将重命名或替换现有列名称以改善用户体验。 请参阅本文，查看可能会影响查询的命名更改。

命名更改会自动应用于保存在Defender for Cloud中的查询，包括自定义检测规则使用的查询。 无需手动更新这些查询。 但是，需要更新以下查询：
- 使用 API 运行的查询
- 保存在Defender for Cloud以外的其他位置的查询

## <a name="december-2020"></a>2020 年 12 月

| 表名 | 原始列名 | 新列名 | 更改原因
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | 客户反馈 |
| [EmailEvents](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | 客户反馈 |

## <a name="january-2021"></a>2021 年 1 月

| 列名称 | 原始值名称 | 新值名称 | 更改原因
|--|--|--|--|
| `DetectionSource` | Defender for Cloud Apps | Microsoft Defender for Cloud Apps | 品牌重塑 |
| `DetectionSource` | WindowsDefenderAtp| EDR| 品牌重塑 |
| `DetectionSource` | WindowsDefenderAv | 防病毒 | 品牌重塑 |
| `DetectionSource` | WindowsDefenderSmartScreen |  SmartScreen | 品牌重塑 |
| `DetectionSource` | CustomerTI | 自定义 TI | 品牌重塑 |
| `DetectionSource` | OfficeATP | Microsoft Defender for Office 365 | 品牌重塑 |
| `DetectionSource` | MTP | Microsoft 365 Defender | 品牌重塑 |
| `DetectionSource` | AzureATP | Microsoft Defender for Identity | 品牌重塑 |
| `DetectionSource` | CustomDetection | 自定义检测 | 品牌重塑 |
| `DetectionSource` | AutomatedInvestigation |自动调查 | 品牌重塑 |
| `DetectionSource` | ThreatExperts | Microsoft 威胁专家 | 品牌重塑 |
| `DetectionSource` | 第三方 TI | 第三方传感器 | 品牌重塑 |
| `ServiceSource` | Microsoft Defender ATP| Microsoft Defender for Endpoint | 品牌重塑 |
|`ServiceSource` |Microsoft 威胁防护 | Microsoft 365 Defender | 品牌重塑 |
| `ServiceSource` | Office 365 ATP |Microsoft Defender for Office 365 | 品牌重塑 |
| `ServiceSource` |Azure ATP |Microsoft Defender for Identity | 品牌重塑 |

`DetectionSource` 在 [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。 `ServiceSource` 在 [AlertEvidence](advanced-hunting-alertevidence-table.md) 和 [AlertInfo 表中](advanced-hunting-alertinfo-table.md) 可用。 

## <a name="february-2021"></a>2021 年 2 月

1. 在 [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) 和 [EmailEvents](advanced-hunting-emailevents-table.md) 表中 `MalwareFilterVerdict`，列和 `PhishFilterVerdict` 列已被列替换 `ThreatTypes` 。 列 `MalwareDetectionMethod` 和 `PhishDetectionMethod` 列也被 `DetectionMethods` 列替换。 通过这种精简，我们可以在新列下提供详细信息。 下面提供了映射。

    | 表名 | 原始列名 | 新列名 | 更改原因
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | 包括更多检测方法 |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 包括更多威胁类型 |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | 包括更多检测方法 |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | 包括更多威胁类型 |


2. `EmailAttachmentInfo`在和`EmailEvents`表中，添加了该`ThreatNames`列以提供有关电子邮件威胁的详细信息。 此列包含垃圾邮件或网络钓鱼等值。

3. 在 [DeviceInfo](advanced-hunting-deviceinfo-table.md) 表中 `DeviceObjectId` ，列已根据客户反馈替换 `AadDeviceId` 为列。

4. 在 [DeviceEvents 表中](advanced-hunting-deviceevents-table.md) ，修改了多个 ActionType 名称，以便更好地反映操作的说明。 可在下面找到更改的详细信息。

    | 表名 | 原始 ActionType 名称 | 新建 ActionType 名称 | 更改原因
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | 客户反馈 |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | 客户反馈 |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | 客户反馈 |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | 客户反馈 |

## <a name="march-2021"></a>2021 年 3 月

该 `DeviceTvmSoftwareInventoryVulnerabilities` 表已被弃用。 替换它是 `DeviceTvmSoftwareInventory` 和 `DeviceTvmSoftwareVulnerabilities` 表。

## <a name="may-2021"></a>2021 年 5 月

该 `AppFileEvents` 表已被弃用。 该 `CloudAppEvents` 表包含曾经在表中 `AppFileEvents` 的信息，以及云服务中的其他活动。

## <a name="related-topics"></a>相关主题
- [高级搜寻概述](advanced-hunting-overview.md)
- [了解架构](advanced-hunting-schema-tables.md)
