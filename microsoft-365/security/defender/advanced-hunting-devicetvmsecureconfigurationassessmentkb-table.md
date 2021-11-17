---
title: 高级搜寻架构中的 DeviceTvmSecureConfigurationAssessmentKB 表
description: 在高级搜寻架构的 DeviceTvmSecureConfigurationAssessmentKB 表中了解有关由威胁和漏洞管理评估的各种安全配置的信息。
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 365 Defender， microsoft 365， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表格， 列， 数据类型， 描述， 威胁 & 漏洞管理， TVM， 设备管理， 安全配置， MITRE ATT&CK 框架， 知识库， KB， DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: bf65634e38d7676eaef20386b3effa828aa46f4b
ms.sourcegitcommit: bd43f08b4719ba984ea6712227508d4a281148cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2021
ms.locfileid: "61035978"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint


高级 `DeviceTvmSecureConfigurationAssessmentKB` 搜寻架构中的表包含威胁和漏洞管理检查的各种安全 [&的信息](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。 它还包括风险信息、相关的行业基准以及适用的 MITRE ATT&CK 技术和技巧。

此表不返回事件或记录。 我们建议使用此表加入 [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) 表，以查看返回的评估中有关 `ConfigurationId` 安全配置的文本信息。

例如，当您查询表时，您可能希望查看评估结果中提供 `DeviceTvmSecureConfigurationAssessment` `ConfigurationDescription` 的安全配置的 。 通过联接此表以使用 和 项目 ， `DeviceTvmSecureConfigurationAssessment` 可以看到 `ConfigurationId` 此信息 `ConfigurationDescription` 。

有关高级搜寻架构中其他表的信息，请参阅[高级搜寻参考](advanced-hunting-schema-tables.md)。

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
| `Tags` | string | 表示用于标识或分类安全配置的各种属性的标签 |
| `RemediationOptions` | string | 用于降低或解决任何关联风险的建议操作 |

可以尝试此示例查询返回相关配置元数据以及表中具有不兼容防病毒配置的设备上 `DeviceTvmSecureConfigurationAssessment` 的信息：

```kusto
// Get information on devices with antivirus configurations issues
DeviceTvmSecureConfigurationAssessment
| where ConfigurationSubcategory == 'Antivirus' and IsApplicable == 1 and IsCompliant == 0
| join kind=leftouter (
    DeviceTvmSecureConfigurationAssessmentKB
    | project ConfigurationId, ConfigurationName, ConfigurationDescription, RiskDescription, Tags, ConfigurationImpact
) on ConfigurationId
| project DeviceName, OSPlatform, ConfigurationId, ConfigurationName, ConfigurationCategory, ConfigurationSubcategory, ConfigurationDescription, RiskDescription, ConfigurationImpact, Tags
```

## <a name="related-topics"></a>相关主题

- [主动搜寻威胁](advanced-hunting-overview.md)
- [了解查询语言](advanced-hunting-query-language.md)
- [使用共享查询](advanced-hunting-shared-queries.md)
- [跨设备、电子邮件、应用和标识进行查寻](advanced-hunting-query-emails-devices.md)
- [了解架构](advanced-hunting-schema-tables.md)
- [应用查询最佳做法](advanced-hunting-best-practices.md)
- [威胁和漏洞管理概述](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)