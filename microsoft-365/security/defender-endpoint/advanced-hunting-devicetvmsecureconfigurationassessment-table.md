---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessment 表
description: 了解高级&的 DeviceTvmSecureConfigurationAssessment 表中的威胁和漏洞管理安全评估事件。 这些事件提供设备信息以及安全配置详细信息、影响和合规性信息。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 安全配置， DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056145"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)



>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

`DeviceTvmSecureConfigurationAssessment` 表中的每一行均包含针对来自[威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)的特定安全配置的评估事件。 使用此参考来检查最新的评估结果，并确定设备是否符合要求。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `DeviceId` | string | 服务中设备的唯一标识符 |
| `DeviceName` | string | 设备的完全限定 (FQDN) FQDN |
| `OSPlatform` | string | 在设备上运行的操作系统的平台。 这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。|
| `Timestamp` | datetime |生成记录的日期和时间 |
| `ConfigurationId` | string | 特定配置的唯一标识符 |
| `ConfigurationCategory` | string | 配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件 |
| `ConfigurationSubcategory` | string |配置所属的子类别或子组。 在许多情况下，它用于描述特定的功能。 |
| `ConfigurationImpact` | string | 配置对总体配置评分的影响程度 (1-10) |
| `IsCompliant` | boolean | 指示是否正确配置了配置或策略 |
| `IsApplicable` | boolean | 指示配置或策略是否适用于设备 |
| `Context` | string | 有关配置或策略的其他上下文信息 |
| `IsExpectedUserImpactCompliant` | boolean | 指示应用配置或策略时是否将影响用户 |

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)