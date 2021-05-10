---
title: 为第一个事件准备安全状态
description: 为 Microsoft 365 Defender 中的第一个事件设置租户Microsoft 365状态。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 76bead8fd855e4119db6297d2ab1a3d08d64a48c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297160"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>为第一个事件准备安全状态

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

准备事件处理涉及为组织网络设置来自不同类型的安全事件的充分保护。 为降低安全事件的风险，美国国家标准和技术协会 (NIST) 推荐了几种安全做法，包括风险评估、强化主机安全、安全配置网络以及预防恶意软件。 

Microsoft 365Defender 可帮助解决事件防护的几个方面： 

- 实现零 [信任](https://docs.microsoft.com/security/zero-trust/) 框架
- 使用 Microsoft 安全分数分配分数来确定 [安全状态](microsoft-secure-score.md)
- 通过威胁和漏洞管理中的漏洞评估 [防止威胁](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- 了解最新的安全威胁，以便你可以为它们做好准备

## <a name="step-1-implement-zero-trust"></a>步骤 1. 实现零信任

[零](https://docs.microsoft.com/security/zero-trust/) 信任是一种集成的安全理念和端到端策略，它考虑任何现代环境的复杂性质，包括移动工作人员以及用户、设备、应用程序和数据，无论他们位于何处。 通过提供单一的窗格以一致的方式管理所有终结点检测，Microsoft 365 Defender 可以使安全运营团队更轻松地实施零信任指导原则。 [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) 

Microsoft 365 Defender 的组件可以显示违反为建立零信任条件访问策略而实施的规则，通过将来自 Microsoft Defender for Endpoint (MDE) 或其他移动安全供应商的数据集成为设备合规性策略和基于设备的条件访问策略实现的信息源。 

设备风险直接影响该设备的用户可访问的资源。 基于特定条件拒绝访问资源是零信任的主要主题，Microsoft 365 Defender 提供确定信任级别条件所需的信息。 例如，Microsoft 365 Defender 可以通过"威胁和漏洞管理"页提供设备的软件版本级别，而条件访问策略限制具有过时或易受攻击的版本的设备。

自动化是实施和维护零信任环境的重要部分，同时还减少了可能导致发生 IR 事件或 IR 事件 (警报) 数量。 Microsoft 365 Defender 的组件可以自动化，例如修正操作[ (称为](m365d-autoir.md)Microsoft 365 安全中心) 中的事件调查、通知操作，甚至是创建支持票证（如[在 ServiceNow](https://microsoft.service-now.com/sp/)中）。

## <a name="step-2-determine-your-organizations-security-posture"></a>步骤 2. 确定组织的安全状态

接下来，组织可以使用 Microsoft 365 Defender 中的[Microsoft](microsoft-secure-score.md)安全分数来确定你当前的安全状况，并考虑如何改进它的建议。 分数越高，组织采取的安全建议和改进措施就越高。 安全分数建议可以跨不同的产品进行，并允许组织进一步提升分数。 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft 安全中心中的 Microsoft 安全分数示例":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>步骤 3. 评估组织的漏洞暴露

预防事件有助于简化安全操作工作，以重点关注进行中的关键和重要的安全事件。 软件漏洞通常是攻击的可阻止入口点，可能导致数据盗窃、数据丢失或业务运营中断。 如果没有攻击在进行中，则安全操作必须努力在组织中实现并保持可接受的漏洞暴露级别。 [](../defender-endpoint/tvm-exposure-score.md)

若要检查软件修补进度，请访问 Defender [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) for Endpoint 中的"威胁和漏洞管理"页，可通过"更多资源"选项卡从 Microsoft 365 Defender **访问** 该页面。

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft 安全中心中的威胁和漏洞页面示例"::: 
 
## <a name="4-understand-emerging-threats"></a>4. 了解新出现的威胁

在[安全中心](threat-analytics.md)Microsoft 365威胁分析，及时获得最新的安全威胁环境。 专家 Microsoft 安全研究人员创建报告，详细说明最新的网络威胁，以便你了解它们可能会Microsoft 365订阅、设备和用户。 这些报告可能包括：

- 活动威胁参与者及其活动
- 热门和新的攻击技术
- 关键漏洞
- 常见的攻击面
- 流行恶意软件

你可以实施新兴威胁的建议，以强化安全状况并最大限度地减少攻击面区域。

安排时间，定期查看安全中心中Microsoft 365分析[](threat-analytics.md)"部分。

## <a name="next-step"></a>后续步骤

[![步骤 1：了解如何对事件分类和分析](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

了解如何 [对事件进行会审和分析](first-incident-analyze.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
