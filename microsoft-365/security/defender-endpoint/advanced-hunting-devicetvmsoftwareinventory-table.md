---
title: 高级搜寻架构中的 DeviceTvmSoftwareInventory 表
description: 在高级搜寻架构的 DeviceTvmSoftwareInventory 表中了解设备中的软件清单。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 软件， 清单， 漏洞， CVE ID， OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056269"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

高级 `DeviceTvmSoftwareInventory` 搜寻架构中的表包含&网络中设备上[](next-gen-threat-and-vuln-mgt.md)当前安装的软件的威胁和漏洞管理清单，包括停止提供支持信息。 例如，可以搜寻涉及使用当前易受攻击的软件版本安装的设备的事件。 使用此参考来构建从该表返回信息的查询。

>[!NOTE]
>和 `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` 表已替换 `DeviceTvmSoftwareInventoryVulnerabilities` 表。 前两个表一起包含可用于帮助通知漏洞管理活动的更多列。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `OSPlatform` | string | 在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。 |
| `OSVersion` | string | 在设备上运行的操作系统的版本 |
| `OSArchitecture` | string | 在设备上运行的操作系统的体系结构 |
| `SoftwareVendor` | string | 软件供应商的名称 |
| `SoftwareName` | string | 软件产品的名称 |
| `SoftwareVersion` | string | 软件产品版本号 |
| `EndOfSupportStatus` | string | 指示软件产品的生命周期阶段（相对于其指定的 EOS (停止) 或生命周期结束 (EOL) 日期 |
| `EndOfSupportDate` | string | 在软件产品 (EOS) 或生命周期结束 (EOL) 终止支持 |



## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)

