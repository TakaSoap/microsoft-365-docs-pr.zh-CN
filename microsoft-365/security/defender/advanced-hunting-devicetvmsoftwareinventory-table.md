---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventory 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventory 表中了解设备中的软件清单。
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
ms.openlocfilehash: a9a17c6e336704cfe09e1c864e9700a4492e8c87
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328017"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

>[!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。


高级`DeviceTvmSoftwareInventory`搜寻架构中的表包含&设备上当前[](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)安装的软件的威胁和漏洞管理清单，包括停止提供支持信息。 例如，可以搜寻涉及使用当前易受攻击的软件版本安装的设备的事件。 使用此参考来构建从该表返回信息的查询。

>[!NOTE]
> `DeviceTvmSoftwareVulnerabilities`和 `DeviceTvmSoftwareInventory` 表已替换表`DeviceTvmSoftwareInventoryVulnerabilities`。 前两个表一起包含更多列，可用于帮助通知 vulnerablity 管理活动或搜寻易受攻击的设备。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `DeviceId` | `string` | 服务中的计算机的唯一标识符 |
| `DeviceName` | `string` | 计算机的完全限定域名 (FQDN) |
| `OSPlatform` | `string` | 计算机上运行的操作系统平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 11、Windows 10 和 Windows 7。 |
| `OSVersion` | `string` | 计算机上运行的操作系统版本 |
| `OSArchitecture` | `string` | 计算机上运行的操作系统的体系结构 |
| `SoftwareVendor` | `string` | 软件供应商的名称 |
| `SoftwareName` | `string` | 软件产品的名称 |
| `SoftwareVersion` | `string` | 软件产品版本号 |
| `EndOfSupportStatus` | `string` | 指示软件产品的生命周期阶段（相对于其指定的停止支持终止 (EOS) 或生命周期 (EOL) 日期 |
| `EndOfSupportDate` | `string` | 软件产品 (EOS) 或生命周期结束 (EOL) 结束日期 |
| `ProductCodeCpe` | `string` | 软件产品的 CPE 或没有 CPE 的"不可用" |


## <a name="related-topics"></a>相关主题

- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [威胁和漏洞管理概述](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)