---
title: 比较中小型企业Microsoft 365计划中的安全功能
description: 了解 Defender for Business 与 Defender for Endpoint 之间的差异。 了解每个计划中包含的内容可帮助你为公司做出明智的决策。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
ms.openlocfilehash: d7651e9ec4ec3cfbf3fe8e853b6de1de9e50dae1
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64714672"
---
# <a name="compare-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>将Microsoft Defender 商业版与Microsoft 365 商业高级版进行比较

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

Microsoft 提供各种云解决方案和服务，包括针对中小型企业的几种不同计划。 例如，[Microsoft 365 商业高级版](../../business/microsoft-365-business-overview.md)包括安全和设备管理功能，以及Office应用等生产力功能。 本文旨在帮助阐明Microsoft 365 商业高级版、Microsoft Defender 商业版和Microsoft Defender for Endpoint中包含哪些安全功能（如设备保护）。

从 2022 年 3 月 1 日开始，Microsoft Defender 商业版作为独立产品/服务或Microsoft 365 商业高级版 (的一部分提供) 。

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

**使用本文执行以下操作**：

- [将独立Microsoft Defender 商业版 () 与Microsoft 365 商业高级版进行比较](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium)
- [将 Defender for Business (独立) 与Microsoft Defender for Endpoint企业产品/服务进行比较](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)

**无需有Microsoft 365订阅即可购买和使用Microsoft Defender 商业版。** Microsoft Defender 商业版包含在Microsoft 365 商业高级版中，它作为中小型企业的独立安全解决方案提供。 如果已有Microsoft 365 商业基础版或标准，请考虑添加升级到Microsoft 365 商业高级版或添加Microsoft Defender 商业版以获取更多威胁防护功能。 

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>将Microsoft Defender 商业版中的安全功能与Microsoft 365 商业高级版进行比较

> [!NOTE]
> 本文旨在提供Microsoft Defender 商业版 (作为独立计划) 和包括 Defender for Business) 的Microsoft 365 商业高级版 (中包含的威胁防护功能的高级概述。 本文不适用于服务说明或许可合同文档。 有关详细信息，请参阅[Microsoft 365有关安全&合规性的许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

**从 2022 年 3 月 1 日开始，Defender for Business 将作为Microsoft 365 商业高级版的一部分开始推出。Defender for Business 作为独立产品/服务仍处于预览状态。**

下表比较了 Defender for Business 中的安全功能 (独立) 与Microsoft 365 商业高级版。 

 <br/><br/>

| 功能/功能 | [Microsoft Defender 商业版](mdb-overview.md)<br/> (独立;当前为预览版)  | [Microsoft 365 商业高级版](../../business/microsoft-365-business-overview.md)<br/> (包括 Defender for Business)  |
|:---|:---|:---|
| 电子邮件保护 | 是 <br/>- [使用Microsoft Defender 防病毒进行电子邮件扫描](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md) | 是 <br/>- [Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md) <br/>- [使用Microsoft Defender 防病毒进行电子邮件扫描](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 反垃圾邮件保护 | 是 <br/>- 对于设备 | 是 <br/>- 对于设备<br/>- 对于Microsoft 365电子邮件内容，如邮件和附件 |
| 反恶意软件保护 | 是<br/>- 对于设备 | 是 <br/>- 对于设备<br/>- 对于Microsoft 365电子邮件内容，如邮件和附件 |
| [下一代保护](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/>  (防病毒和反恶意软件保护)  | 是<br/>- Microsoft Defender 防病毒包含在Windows 10和更高版本中  | 是 <br/>- Microsoft Defender 防病毒包含在Windows 10和更高版本中<br/>- 载入设备的下一代保护策略 |
| [减少攻击面](../defender-endpoint/overview-attack-surface-reduction.md) <br/> (Windows 10或更高版本中的 ASR 规则和防火墙保护)  | 是  | 是  |
| [终结点检测和响应](../defender-endpoint/overview-endpoint-detection-response.md) <br/> (基于行为的检测和手动响应操作)  | 是 | 是 |
| [自动调查和响应](../defender-endpoint/automated-investigations.md) | 是 | 是 |
| [威胁和漏洞管理](../defender-endpoint/tvm-dashboard-insights.md) | 是 | 是 |
| 集中管理和报告  | 是  | 是  |
| [API](../defender-endpoint/apis-intro.md) <br/>与自定义应用或报告解决方案集成 ()   | 是 | 是 |


## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>将Microsoft Defender 商业版与Microsoft Defender for Endpoint计划 1 和 2 进行比较

Defender for Business 为中小型企业带来了 Defender for Endpoint 的企业级功能。 

下表比较了 Defender for Business 中的安全功能和功能Microsoft Defender for Endpoint计划 1 和 2。 <br/><br/>

| 功能/功能 | [Defender for Business](mdb-overview.md)<br/> (独立;当前为预览版)  | [Defender for Endpoint 计划 1](../defender-endpoint/defender-endpoint-plan-1.md) | [Defender for Endpoint Plan 2](../defender-endpoint/microsoft-defender-endpoint.md) |
|:---|:---|:---|:---|
| [集中式管理](../defender-endpoint/manage-atp-post-migration.md) <sup>[[1](#fn1)]</sup> | 是 | 是 | 是 |
| [简化的客户端配置](mdb-simplified-configuration.md) | 是 | 否 | 否 |
| [威胁和漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) | 是 | 否 | 是 |
| [攻击面减少功能](../defender-endpoint/overview-attack-surface-reduction.md) | 是 | 是 | 是 |
| [下一代保护](../defender-endpoint/next-generation-protection.md) | 是 | 是 | 是 |
| [终结点检测和响应](../defender-endpoint/overview-endpoint-detection-response.md) | 是 <sup>[[2](#fn2)]</sup> | 否 | 是 |
| [自动调查和响应](../defender-endpoint/automated-investigations.md) | 是 <sup>[[2](#fn2)]</sup> | 否 | 是 |
| [威胁搜寻](../defender-endpoint/advanced-hunting-overview.md) 和六个月的数据保留 | 否 | 否 | 是 |
| [威胁分析](../defender-endpoint/threat-analytics.md) | 是 <sup>[[2](#fn2)]</sup> | 否 | 是 |
| [跨平台支持](../defender-endpoint/minimum-requirements.md) <br/> (Windows、macOS、iOS 和 Android OS)  | 是 <sup>[[3](#fn3)]</sup> | 是 | 是 |
| [Microsoft 威胁专家](../defender-endpoint/microsoft-threat-experts.md) | 否 | 否 | 是 |
| 合作伙伴 API | 是 | 是 | 是 |
| [Microsoft 365 Lighthouse集成](../../lighthouse/m365-lighthouse-overview.md) <br/> (查看客户租户之间的安全事件)  | 是 | 否 | 否 |

 (<a id="fn1">1</a>) Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 或其他工具（如 Microsoft Endpoint Manager () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ）载入和管理设备。

 (<a id="fn2">2</a>) 这些功能针对中小型企业进行了优化。

 (<a id="fn3">3</a>) 在预览计划期间，Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) 支持Windows客户端设备。

## <a name="next-steps"></a>后续步骤

- [请参阅Microsoft Defender 商业版的要求](mdb-requirements.md)
- [获取Microsoft Defender 商业版](get-defender-business.md)
- [了解如何设置和配置Microsoft Defender 商业版](mdb-setup-configuration.md) 
