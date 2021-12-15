---
title: 比较 Microsoft Defender for Business 与其他Microsoft 365计划
description: 了解 Defender for Business 和 Defender for Endpoint 之间的差异。 了解每个计划中包括哪些内容可以帮助你为公司做出明智的决策。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 42cd947dec6e954ae675cda233dc4126c2bb2b39
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507430"
---
# <a name="compare-microsoft-defender-for-business-preview-to-microsoft-365-business-premium"></a>比较 Microsoft Defender for Business (预览) 与Microsoft 365 商业高级版

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

Microsoft 提供各种云解决方案和服务，包括针对中小型企业的几个不同计划。 例如[，Microsoft 365 商业高级版](../../business/microsoft-365-business-overview.md)包括安全和设备管理功能，以及工作效率功能，如Office应用。 

**使用本文可：**

- [比较 Microsoft Defender for Business (预览) 与Microsoft 365 商业高级版](#compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium)
- [比较 Defender for Business 与适用于终结点企业产品/服务 Microsoft Defender](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)


**你不必拥有一个 Microsoft 365 订阅，即购买和使用 Microsoft Defender for Business (预览) 。** Microsoft Defender for Business (预览) 是一款适用于中小型企业的独立安全解决方案。 如果你已拥有其他订阅 (如 Microsoft 365 商业基础版 或 Standard) ，请考虑添加 Microsoft Defender for Business，以获得其他威胁防护功能。 

> [!TIP]
> 如果你的公司是小型企业或中型企业 (300 个或更少用户) 并且你要注册 Microsoft Defender for Business 预览计划，请访问 [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview) 。 若要了解更多信息，请参阅[获取 Microsoft Defender for Business。](get-defender-business.md)

## <a name="compare-security-features-in-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>比较 Microsoft Defender for Business 中的安全功能与Microsoft 365 商业高级版

> [!NOTE]
> 本文旨在提供 Microsoft Defender for Business 预览版和预览版 (中包含的威胁防护) Microsoft 365 商业高级版。 本文不用作服务说明或许可合同文档。 有关详细信息，请参阅Microsoft 365[安全与合规&指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

下表比较了 Defender for Business 中的安全特性和功能Microsoft 365 商业高级版 Defender for Business 在预览版中。 当 Defender for Business 普遍可用时，它将包含在 Microsoft 365 商业高级版。 <br/><br/>

| 功能 | [Microsoft Defender for Business](mdb-overview.md) (预览)  | [Microsoft 365 商业高级版](../../business/microsoft-365-business-overview.md) |
|:---|:---|:---|
| 电子邮件保护 | 是 ([电子邮件扫描Microsoft Defender 防病毒) ](../defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus.md) | 是[ (Exchange Online Protection) ](../office-365-security/exchange-online-protection-overview.md) |
| 反垃圾邮件保护 | 是 (设备)  | 是 (电子邮件Microsoft 365，如邮件和附件)  |
| 反恶意软件保护 | 是 (设备)  | 是 (电子邮件Microsoft 365，如邮件和附件)  |
| [下一代保护](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) <br/>  (防病毒和反恶意软件保护)  | 是 (Microsoft Defender 防病毒包括在Windows 10及)   | 是 (Microsoft Defender 防病毒包括在Windows 10及)  |
| [减少攻击面](../defender-endpoint/overview-attack-surface-reduction.md) <br/> (攻击面减少规则和其他保护)   | 是 (内置在攻击面减少规则Windows 10及更高版本中，以及集中管理的功能)  | 是 (和更高版本中内置的攻击面Windows 10规则)  |
| [终结点检测和响应](../defender-endpoint/overview-endpoint-detection-response.md) | 是。 包括： <br/>- 基于行为的检测 <br/>- 手动响应操作 <br/>- 实时响应   | 否 |
| [自动调查和响应](../defender-endpoint/automated-investigations.md) | 是 | 否 |
| [威胁和漏洞管理](../defender-endpoint/tvm-dashboard-insights.md) | 是 | 否 |
| 集中管理和报告 | 是。 你可以载入Windows客户端设备，在 Microsoft 365 Defender 门户 () 中管理它们，或者选择在 Microsoft Endpoint Manager () [https://security.microsoft.com](https://security.microsoft.com) [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 中管理设备。 | 是。 你可以管理Windows客户端设备 [https://admin.microsoft.com](https://admin.microsoft.com) Microsoft 365 管理中心 () 。 设备必须载入 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) Microsoft Endpoint Manager () 。 |
| [API](../defender-endpoint/apis-intro.md) <br/> (，你可以与自定义应用或报告解决方案集成)   | 是 | 是 |



## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>比较 Microsoft Defender for Business 与适用于 Endpoint Plans 1 和 2 的 Microsoft Defender

Defender for Business (预览) 为中小型企业提供 Defender for Endpoint 的企业级功能。 下表比较了 Defender for Business (预览版中的) 和 Microsoft Defender for Endpoint Plans 1 和 2 中的功能。 <br/><br/>

| 功能 | [Defender for Business](mdb-overview.md) (预览)  | [Defender for Endpoint 计划 1](../defender-endpoint/defender-endpoint-plan-1.md) | [Defender for Endpoint Plan 2](../defender-endpoint/microsoft-defender-endpoint.md) |
|:---|:---|:---|
| [集中管理](../defender-endpoint/manage-atp-post-migration.md) <sup>[[1](#fn1)]</sup> | 是 | 是 | 是 |
| [简化的客户端配置](mdb-simplified-configuration.md) | 是 | 否 | 否 |
| [威胁和漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) | 是 | 否 | 是 |
| [攻击面减少功能](../defender-endpoint/overview-attack-surface-reduction.md) | 是 | 是 | 是 |
| [下一代保护](../defender-endpoint/next-generation-protection.md) | 是 | 是 | 是 |
| [终结点检测和响应](../defender-endpoint/overview-endpoint-detection-response.md) | 是 <sup>[[2](#fn2)]</sup> | 否 | 是 |
| [自动调查和响应](../defender-endpoint/automated-investigations.md) | 是 <sup>[[2](#fn2)]</sup> | 否 | 是 |
| [威胁搜寻](../defender-endpoint/advanced-hunting-overview.md) 和 6 个月的数据保留 | 否 | 否 | 是 |
| [威胁分析](../defender-endpoint/threat-analytics.md) | 是 <sup>[[2](#fn2)]</sup> | 否 | 是 |
| [跨平台支持](../defender-endpoint/minimum-requirements.md) <br/> (Windows、macOS、iOS 和 Android OS)  | 是 <sup>[[3](#fn3)]</sup> | 是 | 是 |
| [Microsoft 威胁专家](../defender-endpoint/microsoft-threat-experts.md) | 否 | 否 | 是 |
| 合作伙伴 API | 是 | 是 | 是 |
| [Microsoft 365 Lighthouse集成](../../lighthouse/m365-lighthouse-overview.md) <br/> (查看跨客户租户的安全事件)  | 是 | 否 | 否 |

 (<a id="fn1">1</a>) 在 Microsoft 365 Defender 门户 () 或其他工具（如 Microsoft Endpoint Manager () ）中载入和管理 [https://security.microsoft.com](https://security.microsoft.com) [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 设备。

 (<a id="fn2">2</a>) 这些功能针对中小型企业进行了优化。

 (<a id="fn3">3</a>) 在预览计划Windows，Microsoft 365 Defender支持 ([https://security.microsoft.com](https://security.microsoft.com)) 。

## <a name="next-steps"></a>后续步骤

- [请参阅 Microsoft Defender for Business 预览版 (的要求) ](mdb-requirements.md)

- [了解如何设置和配置 Microsoft Defender for Business (预览) ](mdb-setup-configuration.md) 