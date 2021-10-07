---
title: 使用适用于终结点威胁分析的 Microsoft Defender 跟踪和响应新出现的威胁
ms.reviewer: ''
description: 了解新出现的威胁和攻击技术以及如何阻止它们。 评估其对组织的影响，并评估组织的恢复能力。
keywords: 威胁分析， 风险评估， 操作系统缓解， 微代码缓解， 缓解状态
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 805f61d5a7a00056f204b77c4550672ac17982b7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199641"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a>通过威胁分析跟踪和响应新出现的威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

随着更复杂的对手和新威胁的频繁和普遍出现，必须能够快速：

- 评估新威胁的影响
- 查看抵御威胁或暴露给威胁的恢复能力
- 确定可以采取的停止或包含威胁的操作

威胁分析是一组来自专家 Microsoft 安全研究人员的报告，涉及最相关的威胁，包括：

- 活动威胁参与者及其活动
- 热门和新的攻击技术
- 关键漏洞
- 常见攻击面
- 流行的恶意软件

每个报告都提供威胁的详细分析和有关如何防御该威胁的广泛指导。 它还包含来自你的网络的数据，指示威胁是否处于活动状态以及是否具有适用的保护。

观看此简短视频，详细了解威胁分析如何有助于跟踪和阻止最新威胁。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a>查看威胁分析仪表板

威胁分析仪表板是获取与组织最相关的报告的最大起点。 它总结了以下各节中的威胁：

- **最新威胁**：列出最新发布的威胁报告，以及具有活动警报和已解决警报的设备数量。
- **高影响威胁**：列出对组织影响最大的威胁。 本部分按具有活动警报的设备数量对威胁进行排名。
- **威胁摘要**：通过显示具有活动警报和已解决警报的威胁数，显示跟踪的威胁的总体影响。

从仪表板中选择威胁以查看该威胁的报告。

![威胁分析仪表板的图像。](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a>查看威胁分析报告

每个威胁分析报告提供三个部分的信息： **概述**、分析 **员报告** 和 **缓解**。

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>概述：快速了解威胁、评估其影响并审查防御

" **概述** "部分提供详细分析员报告的预览。 它还提供了突出显示威胁对组织的影响以及通过错误配置和未修补的设备暴露的图表。

![威胁分析报告的概述部分的图像。 ](images/ta-overview.png)
_威胁分析报告的概述部分_

#### <a name="assess-the-impact-to-your-organization"></a>评估对组织的影响

每个报告都包括旨在提供有关威胁的组织影响的图表：

- **具有警报的设备**：显示受威胁影响的当前不同设备的数量。 如果至少有一个警报与该威胁关联，则设备分类为"活动";如果与设备上的威胁关联的所有警报已解决，则将其分类为"已解决"。 
- **具有随着时间的警报的设备**：显示随着时间的推移具有 **活动** 和已解决警报的不同设备的数量。 已解决的警报数指示组织响应与威胁关联的警报的有多快。 理想情况下，图表应显示几天内解决的警报。

#### <a name="review-security-resilience-and-posture"></a>查看安全恢复和状态

每个报告都包括一些图表，这些图表概述了组织对给定威胁的复原能力：

- **安全配置** 状态：显示已应用有助于缓解威胁的建议安全设置的设备数量。 如果设备已 **应用** 所有跟踪 _设置，则_ 被视为安全设备。
- **漏洞修补状态**：显示已应用安全更新或修补程序以解决威胁所利用漏洞的设备数量。

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>分析员报告：从 Microsoft 安全研究人员获取专家见解

转到" **分析员报告** "部分，阅读详细的专家撰写。 大多数报告都提供攻击链的详细说明，包括映射到 MITRE ATT&CK 框架的策略和技术、详细的建议列表和强大的 [威胁](advanced-hunting-overview.md) 搜寻指南。

[详细了解分析员报告](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>缓解：查看缓解列表和设备的状态

在 **"缓解"** 部分，查看特定可操作建议的列表，这些建议可帮助你提高组织应对威胁的复原能力。 跟踪的缓解列表包括：

- **安全更新**：部署安全更新程序或漏洞修补程序
- **Microsoft Defender 防病毒设置**
  - 安全智能版本
  - 云端保护
  - PUA 保护 (可能不需要) 应用程序
  - 实时保护

本节中的缓解信息包含来自 危险和漏洞管理[](next-gen-threat-and-vuln-mgt.md)的数据，其中还提供了报告中各个链接的详细深化信息。

![威胁分析报告的缓解部分的图像。](images/ta-mitigations.png)

_威胁分析报告的缓解部分_

## <a name="additional-report-details-and-limitations"></a>其他报告详细信息和限制

使用报告时，请牢记以下事项：

- 数据的范围基于基于角色的访问控制 (RBAC) 作用域。 你将看到可以访问 的组中 [设备的状态](machine-groups.md)。
- 图表仅反映跟踪的缓解。 查看报告概述，了解图表中未显示的其他缓解功能。
- 缓解不保证完全恢复。 提供的缓解反映了改进恢复能力所需的最佳可能操作。
- 如果设备尚未将数据传输到服务，则被视为"不可用"。
- 防病毒相关的统计信息基于Microsoft Defender 防病毒设置。 具有第三方防病毒解决方案的设备可能显示为"公开"。

## <a name="related-topics"></a>相关主题

- [使用高级搜寻主动查找威胁](advanced-hunting-overview.md)
- [了解分析员报告部分](threat-analytics-analyst-reports.md)
- [评估和解决安全漏洞和曝光](next-gen-threat-and-vuln-mgt.md)
