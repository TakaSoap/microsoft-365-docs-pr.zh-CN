---
title: 为第一个事件准备安全状况
description: 为Microsoft 365 Defender中的第一个事件设置Microsoft 365租户的安全状况。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
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
ms.openlocfilehash: 0dbff9e88ed00dd8aa08fd64543266c3aef75d79
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664075"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>为第一个事件准备安全状况

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

准备事件处理涉及为组织网络设置足够的保护，防止发生不同类型的安全事件。 为了降低安全事件的风险，国家标准与技术研究所 (NIST) 建议采取多种安全做法，包括风险评估、强化主机安全性、安全配置网络和防止恶意软件。

Microsoft 365 Defender可以帮助解决事件预防的几个方面：

- 实现[零信任](/security/zero-trust/)框架
- 使用 [Microsoft 安全分数](microsoft-secure-score.md)分配分数来确定安全状况
- 通过[威胁和漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)中的漏洞评估来防止威胁
- 了解最新的安全威胁，以便通过[威胁分析为它们](threat-analytics.md)做好准备

## <a name="step-1-implement-zero-trust"></a>步骤 1. 实现零信任

[零信任](/security/zero-trust/)是一种集成的安全理念和端到端策略，可考虑任何新式环境的复杂性质，包括移动员工以及用户、设备、应用程序和数据（无论他们身在何处）。 通过提供单个玻璃窗格以一致的方式管理所有检测，Microsoft 365 Defender可以使安全运营团队更容易实现零信任的[指导原则](/security/zero-trust/#guiding-principles-of-zero-trust)。

Microsoft 365 Defender的组件可以通过集成来自Microsoft Defender for Endpoint的数据来显示已实施的规则的冲突，以便为零信任建立条件访问策略 或其他移动安全供应商，作为设备符合性策略和基于设备的条件访问策略实现的信息源。

设备风险直接影响该设备的用户可以访问的资源。 根据特定条件拒绝对资源的访问是零信任的主题，Microsoft 365 Defender提供确定信任级别条件所需的信息。 例如，Microsoft 365 Defender可以通过"威胁和漏洞管理"页提供设备的软件版本级别，而条件访问策略则限制具有过时或易受攻击版本的设备。

自动化是实现和维护零信任环境的关键部分，同时也减少了可能导致事件响应 (IR) 事件的警报数。 Microsoft 365 Defender的组件可以自动化，例如 (Microsoft 365 Defender门户) 中的事件调查、通知操作，甚至创建支持票证（例如在 [ServiceNow](https://microsoft.service-now.com/sp/) 中）的[修正操作](m365d-autoir.md)。

## <a name="step-2-determine-your-organizations-security-posture"></a>步骤 2. 确定组织的安全状况

接下来，组织可以使用Microsoft 365 Defender中的 [Microsoft 安全分数](microsoft-secure-score.md)来确定当前的安全状况，并考虑有关如何改进它的建议。 分数越高，组织执行的安全建议和改进操作就越多。 安全评分建议可跨不同的产品进行，并允许组织提高分数。

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Microsoft 365 Defender门户中的&quot;Microsoft 安全评分&quot;页" lightbox="../../media/first-incident-prepare/first-incident-secure-score.png":::

## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>步骤 3. 评估组织的漏洞暴露情况

防止事件有助于简化安全操作工作，以专注于持续的关键和重要的安全事件。 软件漏洞通常是导致数据盗窃、数据丢失或业务运营中断的攻击的可预防入口点。 如果未发生任何攻击，则安全操作必须努力在其组织中实现并保持可接受的 [漏洞暴露](../defender-endpoint/tvm-exposure-score.md) 级别。

若要检查软件修补进度，请访问 Defender for Endpoint 中 [的威胁和漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)页面，可通过"**更多资源**"选项卡从Microsoft 365 Defender访问该页面。

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Microsoft 365 Defender门户中的&quot;威胁和漏洞&quot;页" lightbox="../../media/first-incident-prepare/first-incident-vulnerability.png":::

## <a name="4-understand-emerging-threats"></a>4. 了解新出现的威胁

在Microsoft 365 Defender门户中使用[威胁分析](threat-analytics.md)来随时了解当前的安全威胁环境。 Microsoft 安全专家研究人员创建报告，详细描述最新的网络威胁，以便了解这些威胁如何影响Microsoft 365订阅、设备和用户。 这些报表可以包括：

- 活动威胁执行组件及其活动
- 热门和新的攻击技术
- 严重漏洞
- 常见攻击面
- 流行的恶意软件

威胁分析还会查看配置和警报，以确定你的风险程度以及是否有适用于报表的活动警报。

可以实施新出现的威胁的建议，以加强安全状况并最大程度地减少攻击面。

请在计划中腾出时间定期检查Microsoft 365 Defender门户的威胁[分析](threat-analytics.md)部分。 有关详细信息，请参阅[Microsoft 365 Defender的示例安全操作](incidents-overview.md#example-security-operations-for-microsoft-365-defender)。

## <a name="next-step"></a>后续步骤

了解如何 [对事件进行会审和分析](first-incident-analyze.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [调查事件](investigate-incidents.md)
- [管理事件](manage-incidents.md)
