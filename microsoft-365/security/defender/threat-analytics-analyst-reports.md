---
title: 了解Microsoft 365 Defender中威胁分析的分析师报告部分
ms.reviewer: ''
description: 了解每个威胁分析报告的分析师报告部分。 了解它如何提供有关威胁、缓解措施、检测、高级搜寻查询等的信息。
keywords: 分析报告，威胁分析，检测，高级搜寻查询，缓解，
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection:
- M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 396be53e4c238a8de21082f025762a1a4243b57c
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731133"
---
# <a name="understand-the-analyst-report-in-threat-analytics-in-microsoft-365-defender"></a>了解Microsoft 365 Defender中威胁分析的分析师报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

每个 [威胁分析报告](threat-analytics.md) 包括动态部分和一个名为 _分析师报告_ 的综合书面部分。 若要访问此部分，请打开有关已跟踪威胁的报告，然后选择" **分析师报告** "选项卡。

:::image type="content" source="../../media/threat-analytics/ta_analystreport_mtp.png" alt-text="威胁分析报告的分析师报告部分" lightbox="../../media/threat-analytics/ta_analystreport_mtp.png":::

_威胁分析报告的分析师报告部分_

## <a name="scan-the-analyst-report"></a>扫描分析师报告

分析师报告的每个部分都旨在提供可操作的信息。 虽然报表各不相同，但大多数报表都包含下表中所述的部分。

| 报表部分 | 说明 |
|--|--|
| 摘要 | 威胁概述，包括首次看到威胁时，其动机、值得注意的事件、主要目标以及不同的工具和技术。 可以使用此信息进一步评估如何在行业、地理位置和网络上下文中确定威胁的优先级。 |
| 分析 | 有关威胁的技术信息，包括攻击的详细信息，以及攻击者如何利用新技术或攻击面 |
| 观察到的 MITRE ATT&CK 技术 | 观察到的技术如何映射到 [MITRE ATT&CK 攻击框架](https://attack.mitre.org/) |
| [缓解](#apply-additional-mitigations) | 可以停止或帮助减少威胁影响的推荐。 本部分还包括未作为威胁分析报告的一部分动态跟踪的缓解措施。 |
| [检测详细信息](#understand-how-each-threat-can-be-detected) | Microsoft 安全解决方案提供的特定和通用检测，这些检测可以显示与威胁关联的活动或组件。 |
| [高级搜寻](#find-subtle-threat-artifacts-using-advanced-hunting) | 用于主动识别可能的威胁活动的[高级搜寻查询](advanced-hunting-overview.md)。 大多数查询都提供给补充检测，特别是用于查找无法动态评估为恶意的潜在恶意组件或行为。 |
| References | 在创建报表期间，分析师引用的 Microsoft 和第三方发布。 威胁分析内容基于 Microsoft 研究人员验证的数据。 从公开提供的第三方来源的信息可以清楚地识别出来。 |
| 更改日志 | 报告发布的时间以及对报表进行重大更改的时间。 |

## <a name="apply-additional-mitigations"></a>应用其他缓解措施

威胁分析动态跟踪 [安全更新和安全配置的状态](threat-analytics.md#exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。 此信息在" **公开&缓解** "选项卡中用作图表和表。

除了这些跟踪的缓解措施外，分析师报告还讨论了 _未_ 动态监视的缓解措施。 下面是未动态跟踪的重要缓解措施的一些示例：

- 使用 _.lnk_ 附件或其他可疑文件类型阻止电子邮件
- 随机化本地管理员密码
- 教育最终用户有关网络钓鱼电子邮件和其他威胁向量的信息
- 启用特定 [的攻击面减少规则](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

虽然可以使用" **暴露&缓解** "选项卡来评估安全状况以应对威胁，但这些建议可让你采取其他步骤来改善安全状况。 请仔细阅读分析师报告中的所有缓解指南，并尽可能应用这些指南。

## <a name="understand-how-each-threat-can-be-detected"></a>了解如何检测到每个威胁

分析师报告还提供了来自Microsoft Defender 防病毒和 _终结点检测和响应 (EDR)_ 功能的检测。

### <a name="antivirus-detections"></a>防病毒检测

这些检测在启用[了Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)的设备上可用。 当这些检测发生在已载入到Microsoft Defender for Endpoint的设备上时，它们还会触发警报，以照亮报表中的图表。

>[!NOTE]
>分析师报告还列出了 **一般检测** ，这些检测可以识别各种威胁，以及特定于跟踪威胁的组件或行为。 这些泛型检测不会反映在图表中。

### <a name="endpoint-detection-and-response-edr-alerts"></a>终结点检测和响应 (EDR) 警报

为[载入到](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)Microsoft Defender for Endpoint的设备引发EDR警报。 这些警报通常依赖于由Microsoft Defender for Endpoint传感器收集的安全信号和其他终结点功能（如防病毒、网络保护、篡改防护），这些功能充当强大的信号源。

与防病毒检测列表一样，一些EDR警报旨在一般地标记可能与跟踪的威胁无关的可疑行为。 在这种情况下，报告会将警报明确标识为"泛型"，并且不会影响报表中的任何图表。

### <a name="email-related-detections-and-mitigations"></a>与电子邮件相关的检测和缓解措施

除已从Microsoft Defender for Endpoint获取的终结点数据外，分析师报告还包含了Microsoft Defender for Office 365中的电子邮件相关检测和缓解措施。

阻止的电子邮件尝试信息可让你深入了解你的组织是否是分析报告中应对的威胁的目标，即使攻击在传递或传递到垃圾邮件文件夹之前已被有效阻止。

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>使用高级搜寻查找微妙的威胁项目

虽然检测允许你自动识别和停止跟踪的威胁，但许多攻击活动会留下需要额外检查的细微跟踪。 某些攻击活动表现出的行为也可能正常，因此动态检测这些行为可能会导致操作噪音甚至误报。

[高级搜寻](advanced-hunting-overview.md)提供基于Kusto 查询语言的查询接口，该接口简化了威胁活动的细微指示器的定位。 它还允许你显示上下文信息并验证指示器是否已连接到威胁。

分析师报告中的高级搜寻查询已由 Microsoft 分析师审核，并已准备好在 [高级搜寻查询编辑器](https://security.microsoft.com/advanced-hunting)中运行。 还可以使用查询创建 [自定义检测规则](custom-detection-rules.md) ，以便为将来的匹配触发警报。

>[!NOTE]
> 威胁分析也可在[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)中使用。 但是，它没有 Microsoft Defender for Office 和 Microsoft Defender for Endpoint 之间的数据集成。

## <a name="related-topics"></a>相关主题

- [威胁分析概述](threat-analytics.md)
- [通过高级搜寻主动查找威胁](advanced-hunting-overview.md)
- [自定义检测规则](custom-detection-rules.md)
