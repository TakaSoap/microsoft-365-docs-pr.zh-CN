---
title: 搜索暴露的设备
description: 了解如何危险和漏洞管理安全管理员、IT 管理员和 SecOps 协作。
keywords: 适用于 Endpoint-tvm 方案的 Microsoft Defender， 适用于终结点的 Microsoft Defender， tvm， tvm 方案， 减少威胁 & 漏洞暴露， 减少威胁和漏洞， 改进安全配置， 提高 Microsoft 设备安全分数， 增加威胁 & 漏洞 Microsoft 设备安全分数， Microsoft 设备安全分数， 曝光分数， 安全控制
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3e413b511f080c23d76e616d83de0cb70a2f966f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210825"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>搜寻公开的设备 - 危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>使用高级搜寻查找具有漏洞的设备

高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。 你可以主动检查网络中的事件来找到威胁指示器和实体。 通过灵活的数据访问，可以不受限制地搜寻已知威胁和潜在威胁。 [详细了解高级搜寻](advanced-hunting-overview.md)

### <a name="schema-tables"></a>架构表

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - 设备上安装的软件清单，包括其版本信息和停止支持状态。

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - 设备上发现的软件漏洞以及可解决每个漏洞的可用安全更新列表。

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - 公开披露漏洞的知识库，包括攻击代码是否公开可用。

- [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - 威胁漏洞管理评估事件，指示设备上各种安全配置的状态。

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - 威胁和漏洞管理用于评估&各种安全配置的知识库;包括到各种标准和基准的映射

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>检查高严重性警报中涉及的设备

1. 从导航 **门户** 的左侧导航窗格中转到搜寻高级 \> Microsoft 365 Defender。

2. 向下滚动到 TVM 高级搜寻架构，以熟悉列名称。

3. 输入以下查询：

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
let DeviceWithHighAlerts = AlertInfo
| where Severity == "High"
| project Timestamp, AlertId, Title, ServiceSource, Severity
| join kind=inner (AlertEvidence | where EntityType == "Machine" | project AlertId, DeviceId, DeviceName) on AlertId
| summarize HighSevAlerts = dcount(AlertId) by DeviceId;
let DeviceWithCriticalCve = DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId;
DeviceWithCriticalCve
| join kind=inner DeviceWithHighAlerts on DeviceId
| project DeviceId, DeviceName, NumOfVulnerabilities, HighSevAlerts
```

## <a name="related-topics"></a>相关主题

- [威胁漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [安全性建议](tvm-security-recommendation.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)
- [为角色配置危险和漏洞管理访问](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [高级搜寻概述](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [所有高级搜寻表](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
