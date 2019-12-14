---
title: 高级搜寻架构中的 AlertEvents 表
description: 在高级搜寻架构的 AlertEvents 表中，了解警报生成事件
keywords: 高级搜寻, 威胁搜寻, 网络威胁搜寻, 搜索, 查询, 遥测, 架构参考, kusto, 表格, 列, 数据类型, 说明, alertevents, 警报, 严重性, 类别
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910818"
---
# <a name="alertevents"></a>AlertEvents

**适用于：**
- Microsoft 威胁防护

[!include[Prerelease information](prerelease.md)]

[高级搜寻](advanced-hunting-overview.md)架构中的 `AlertEvents` 表包含有关 Microsoft Defender ATP 警报的信息。 使用此参考来构建从此表返回信息的查询。

有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `AlertId` | string | 警报的唯一标识符 |
| `EventTime` | datetime | 记录事件的日期和时间 |
| `MachineId` | string | 服务中的计算机的唯一标识符 |
| `ComputerName` | string | 计算机的完全限定域名 (FQDN) |
| `Severity` | string | 指示警报所标识的威胁指示器或违反活动的潜在影响（高、中或低） |
| `Category` | string | 由警报标识的威胁指示器或违反活动的类型 |
| `Title` | string | 警报的标题 |
| `FileName` | string | 录制操作所应用到的文件的名称 |
| `SHA1` | string | 录制操作所应用到的文件的 SHA-1 |
| `RemoteUrl` | string | 连接到的 URL 或完全限定域名 (FQDN) |
| `RemoteIP` | string | 连接到的 IP 地址 |
| `ReportId` | long | 基于重复计数器的事件标识符。 要标识唯一事件，此列必须与 ComputerName 和 EventTime 列一起使用 |
| `Table` | string | 包含事件详细信息的表 |

## <a name="related-topics"></a>相关主题
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备和电子邮件搜寻威胁](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
