---
title: 高级搜寻架构中的 DeviceTvmSoftwareVulnerabilitiesKB 表
description: 在高级搜寻架构的 DeviceTvmSoftwareVulnerabilitiesKB 表中，了解由威胁和漏洞管理跟踪的软件漏洞。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构， 参考， kusto， 表格， 列， 数据类型， 描述， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， CVSS， DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 545e2a3ba12924d364facda14a7a564ead212f30
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531083"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



高级搜寻架构中的 `DeviceTvmSoftwareVulnerabilitiesKB` 表包含漏洞列表，[威胁和漏洞管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)会针对这些漏洞对设备进行评估。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `CveId` | `string` | 通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符 |
| `CvssScore` | `string` | 通用漏洞评分系统 (CVSS) 下分配给安全漏洞的严重性评分 |
| `IsExploitAvailable` | `boolean` | 指示该漏洞的攻击代码是否公开可用 |
| `VulnerabilitySeverityLevel` | `string` | 基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别 |
| `LastModifiedTime` | `datetime` | 上次修改项或相关元数据的日期和时间 |
| `PublishedDate` | `datetime` | 向公众公开漏洞的日期 |
| `VulnerabilityDescription` | `string` | 漏洞和相关风险的描述 |
| `AffectedSoftware` | `string` | 受漏洞影响的所有软件产品列表 |

## <a name="related-topics"></a>相关主题

- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [威胁和漏洞管理概述](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)