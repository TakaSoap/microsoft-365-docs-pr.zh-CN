---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessmentKB 表
description: 了解高级搜寻架构的 DeviceTvmSecureConfigurationAssessmentKB 表中的威胁&漏洞管理评估的各种安全配置。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， mdatp， microsoft defender atp， wdatp 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， 威胁 & 漏洞管理， TVM， 设备管理， 安全配置， MITRE ATT&CK 框架， 知识库， KB， DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056144"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

高级搜寻架构中的 `DeviceTvmSecureConfigurationAssessmentKB` 表包含有关各种安全配置（例如设备是否已启用自动更新，可通过[威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)进行检查）的信息。 它还包括风险信息、相关的行业基准以及适用的 MITRE ATT&CK 技术和技巧。 使用此参考来构建从该表返回信息的查询。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)。

| 列名称 | 数据类型 | 说明 |
|-------------|-----------|-------------|
| `ConfigurationId` | string | 特定配置的唯一标识符 |
| `ConfigurationImpact` | string | 配置对总体配置评分的影响程度 (1-10) |
| `ConfigurationName` | string | 配置的显示名称 |
| `ConfigurationDescription` | string | 配置的说明 |
| `RiskDescription` | string | 关联风险的说明 |
| `ConfigurationCategory` | string | 配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件|
| `ConfigurationSubcategory` | string |配置所属的子类别或子组。 在许多情况下，它用于描述特定的功能。 |
| `ConfigurationBenchmarks` | string | 推荐相同或类似配置的行业基准的列表 |
| `RelatedMitreTechniques` | string | 与该配置相关的 Mitre ATT&CK 框架技术的列表 |
| `RelatedMitreTactics ` | string | 与该配置相关的 Mitre ATT&CK 框架技巧的列表 |

## <a name="related-topics"></a>相关主题

- [高级搜寻概述](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [了解架构](advanced-hunting-schema-reference.md)
- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
