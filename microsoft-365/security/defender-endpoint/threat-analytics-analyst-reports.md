---
title: 了解威胁分析中的分析员报告部分。
ms.reviewer: ''
description: 威胁分析报告的报告部分如何提供有关威胁、缓解、检测、高级搜寻查询等的信息。
keywords: 分析员报告， 威胁分析， 检测， 高级搜寻查询， 缓解，
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337f9a94b651adffc7360cb88b3d68c9c8167c0a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468096"
---
# <a name="the-analyst-report-in-threat-analytics"></a>威胁分析中的分析员报告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

每个 [威胁分析报告包括](threat-analytics.md) 动态部分和一个称为分析员报告的综合书面 _部分_。 若要访问此部分，请打开关于跟踪的威胁的报告，然后选择"分析 **员报告"** 选项卡。

:::image type="content" source="images/ta-analyst-report-small.png" alt-text="威胁分析报告的分析员报告部分" lightbox="images/ta-analyst-report-small.png":::

_威胁分析报告的分析员报告部分_

## <a name="scan-the-analyst-report"></a>扫描分析员报告

分析员报告的每个部分旨在提供可操作的信息。 虽然报告各不相同，但大多数报告包含下表中描述的部分。

<br>

****

|"报告"部分|说明|
|---|---|
|执行摘要|威胁概述，包括首次看到威胁时、其动机、值得注意的事件、主要目标以及不同的工具和技术。 可以使用此信息进一步评估如何在行业、地理位置和网络上下文中确定威胁的优先级。|
|分析|有关威胁的技术信息，包括攻击的详细信息以及攻击者如何利用新技术或攻击面|
|MITRE ATT&观察到的 CK 技术|观察技术如何映射到 [MITRE ATT&CK 攻击框架](https://attack.mitre.org/)|
|[缓解](#apply-additional-mitigations)|推荐可以停止或帮助降低威胁的影响。 本部分还包括未作为威胁分析报告的一部分动态跟踪的缓解。|
|[检测详细信息](#understand-how-each-threat-can-be-detected)|Microsoft 安全解决方案提供的特定和通用检测，可显示与威胁关联的活动或组件。|
|[高级搜寻](#find-subtle-threat-artifacts-using-advanced-hunting)|[用于主动识别](advanced-hunting-overview.md) 可能的威胁活动的高级搜寻查询。 大多数查询都用于补充检测，尤其是用于找到无法动态评估为恶意的潜在恶意组件或行为。|
|References|Microsoft 和分析师在报告创建期间引用的第三方出版物。 威胁分析内容基于 Microsoft 研究人员验证的数据。 公开提供的、第三方源的信息会明确标识。|
|更改日志|报告的发布时间和对报告进行重大更改的时间。|
|

## <a name="apply-additional-mitigations"></a>应用其他缓解

威胁分析动态跟踪 [安全更新和安全配置的状态](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。 此信息在缓解选项卡中作为图表 **和表格** 提供。

除了这些跟踪的缓解之外，分析员报告还将讨论未 _动态_ 监视的缓解。 下面是未动态跟踪的重要缓解的一些示例：

- 阻止带有 _.lnk_ 附件或其他可疑文件类型的电子邮件
- 随机化本地管理员密码
- 向最终用户就网络钓鱼电子邮件和其他威胁矢量进行培训
- 打开特定 [攻击面减少规则](attack-surface-reduction.md)

虽然可以使用"缓解 **"选项卡评估** 针对威胁的安全状态，但这些建议可让你采取其他步骤改善安全状况。 仔细阅读分析员报告中的所有缓解指南，并尽可能应用它们。

## <a name="understand-how-each-threat-can-be-detected"></a>了解如何检测每个威胁

分析员报告还提供来自Microsoft Defender 防病毒 _和终结点检测和响应_ (EDR) 检测。

### <a name="antivirus-detections"></a>防病毒检测

这些检测在已打开[Microsoft Defender 防病毒设备上可用](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)。 当这些检测发生在已载入到 Microsoft Defender for Endpoint 的设备上时，它们还会触发警报，以点亮报告中的图表。

> [!NOTE]
> 除特定于跟踪的威胁的组件或行为外，分析员报告还列出了可标识各种威胁的通用检测。 这些常规检测不会在图表中反映出来。

### <a name="endpoint-detection-and-response-edr-alerts"></a>终结点检测和响应 (EDR) 警报

EDR Microsoft [Defender for Endpoint 的设备将引发警报](onboard-configure.md)。 这些警报通常依赖于 Microsoft Defender for Endpoint 传感器收集的安全信号以及其他终结点功能 (例如防病毒、网络保护、防篡改保护) 用作强大的信号源。

与防病毒检测列表一样，某些EDR警报旨在一般标记可能未与跟踪威胁关联的可疑行为。 在这种情况下，报告将清楚地将警报标识为"通用"，并且它并不影响报告中的任何图表。

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>使用高级搜寻查找细微的威胁项目

虽然检测允许你自动识别和停止跟踪的威胁，但许多攻击活动留下需要额外检查的细微跟踪。 某些攻击活动呈现的行为也是正常的，因此动态检测它们可能会导致操作干扰甚至误报。

[高级搜寻](advanced-hunting-overview.md) 提供基于 Kusto 查询语言的查询接口，可简化威胁活动的细微指示器的定位。 它还允许你显示上下文信息并验证指示器是否已连接到威胁。

分析员报告中的高级搜寻查询已经过 Microsoft 分析师审查，可随时在高级搜寻 [查询编辑器中运行](https://security.microsoft.com/advanced-hunting)。 您还可以使用查询创建自定义 [检测规则，](custom-detection-rules.md) 以触发将来匹配项的警报。

## <a name="related-topics"></a>相关主题

- [威胁分析概述](threat-analytics.md)
- [使用高级搜寻主动查找威胁](advanced-hunting-overview.md)
- [自定义检测规则](custom-detection-rules.md)
