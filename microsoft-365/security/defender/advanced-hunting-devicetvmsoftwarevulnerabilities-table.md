---
title: 高级搜寻架构中的 DeviceTvmSoftwareVulnerabilities 表
description: 了解设备上发现的软件漏洞，以及可解决高级搜寻架构的 DeviceTvmSoftwareVulnerabilities 表中每个漏洞的可用安全更新列表。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 描述， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: c217c060c3d0b570c6da5bfbd47c72cb8cdfca2b
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60700321"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

>[!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

高级 `DeviceTvmSoftwareVulnerabilities` 搜寻架构中的表包含已安装 [软件&](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 漏洞的威胁和漏洞管理列表。 此表还包括操作系统信息、CVE ID 和漏洞严重性信息。 例如，您可以使用此表来搜寻涉及其软件中具有严重漏洞的设备的事件。 使用此参考来构建从该表返回信息的查询。

>[!NOTE]
> 和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。 前两个表一起包含更多列，可用于帮助通知 vulnerablity 管理活动或搜寻易受攻击的设备。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服务中的计算机的唯一标识符 |
| `DeviceName` | string | 计算机的完全限定域名 (FQDN) |
| `OSPlatform` | string | 计算机上运行的操作系统平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 11、Windows 10 和 Windows 7。 |
| `OSVersion` | string | 计算机上运行的操作系统版本 |
| `OSArchitecture` | string | 计算机上运行的操作系统的体系结构 |
| `SoftwareVendor` | string | 软件供应商的名称 |
| `SoftwareName` | string | 软件产品的名称 |
| `SoftwareVersion` | string | 软件产品版本号 |
| `CveId` | string | 通用漏洞披露 (CVE) 系统下分配给安全漏洞的唯一标识符 |
| `VulnerabilitySeverityLevel` | string | 基于 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别 |
| `RecommendedSecurityUpdate` | string | 软件供应商提供的用于解决漏洞的安全更新的名称或说明 |
| `RecommendedSecurityUpdateId` | string | 适用安全更新的标识符或相应指南或知识库的标识符 (KB) 文章 |



## <a name="related-topics"></a>相关主题

- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [威胁和漏洞管理概述](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)