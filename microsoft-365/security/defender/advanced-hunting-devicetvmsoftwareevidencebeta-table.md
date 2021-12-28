---
title: 高级搜寻架构中的 DeviceTvmSoftwareEvidenceBeta 表
description: 了解如何使用高级搜寻架构中的 DeviceTvmSoftwareEvidenceBeta 表。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 描述， 威胁 & 漏洞管理， 证据， 软件证据， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareEvidenceBeta
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
ms.openlocfilehash: dd71e4b3554b2cd45b648300f84ec96a73e5116b
ms.sourcegitcommit: f8fbabf1ec7421cd7ad36aa52b8856fb863cf284
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2021
ms.locfileid: "61620538"
---
# <a name="devicetvmsoftwareevidencebeta"></a>DeviceTvmSoftwareEvidenceBeta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

> [!IMPORTANT]
> 该表当前处于 beta 版中，提供该表可让你快速搜寻表明设备上 `DeviceTvmSoftwareEvidenceBeta` 存在软件的证据。

高级 `DeviceTvmSoftwareEvidenceBeta` 搜寻架构中的表包含来自威胁& [与](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 软件证据相关的 [漏洞管理部分的数据](/microsoft-365/security/defender-endpoint/tvm-software-inventory#software-evidence)。 此表允许你查看设备上检测到特定软件位置的证据。 例如，可以使用此表来标识特定软件的文件路径。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `DeviceId` | `string` | 服务中设备的唯一标识符 |
| `SoftwareVendor` | `string` | 软件发布者的名称 |
| `SoftwareName` | `string` | 软件产品的名称 |
| `SoftwareVersion` | `string` | 软件产品版本号 |
| `RegistryPaths` | `dynamic` | 已检测到指示设备上存在软件的证据的注册表路径 |
| `DiskPaths` | `dynamic` | 指示设备上是否存在软件的文件级证据的磁盘路径 |
| `LastSeenTime` | `string` | 此服务上次看到设备的日期和时间 |




## <a name="related-topics"></a>相关主题

- [威胁和漏洞管理概述](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
