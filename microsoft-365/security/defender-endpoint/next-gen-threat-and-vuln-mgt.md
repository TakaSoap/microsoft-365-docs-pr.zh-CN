---
title: 威胁和漏洞管理
description: 这一新功能使用基于游戏变化风险的方法来发现、确定终结点漏洞和错误配置并修复这些漏洞和错误配置。
keywords: 威胁&漏洞管理， 威胁和漏洞管理， Microsoft Defender for Endpoint TVM， Microsoft Defender for Endpoint-TVM， 漏洞管理， 漏洞评估， 威胁和漏洞扫描， 安全配置评估， 适用于终结点的 Microsoft Defender， 终结点漏洞， 下一代
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934161"
---
# <a name="threat-and-vulnerability-management"></a>威胁和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

有效识别、评估和修正终结点缺陷是运行正常安全计划并降低组织风险的关键。 威胁和漏洞管理是减少组织风险，强化终结点表面区域和提高组织复原能力的基础结构。

使用传感器实时发现漏洞和错误配置，无需代理或定期扫描。 它根据威胁环境、您组织的检测、易受攻击的设备的敏感信息和业务上下文确定漏洞的优先级。

观看此视频，快速概览威胁和漏洞管理。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>桥接工作流差距

威胁和漏洞管理内置、实时且由云支持。 它与 Microsoft 终结点安全堆栈、Microsoft Intelligent Security Graph 和应用程序分析知识库完全集成。  

漏洞管理是行业首个在修正过程中弥补安全管理和 IT 管理差距的解决方案。 与 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 集成，创建安全任务或票证。

### <a name="real-time-discovery"></a>实时发现

为了发现终结点漏洞和错误配置，威胁和漏洞管理使用相同的无代理内置 Defender for Endpoint 传感器，以减少繁琐的网络扫描和 IT 开销。

它还提供：

- **实时设备清单** - 载入 Defender for Endpoint 的设备会自动将漏洞和安全配置数据报告并推送到仪表板。
- **了解软件和漏洞** - 组织软件清单的光学镜头，以及安装、卸载和修补程序等软件更改。 新发现的漏洞通过针对第一方和第三方应用程序的可操作缓解建议进行报告。
- **应用程序运行时上下文** - 有关应用程序使用模式的可见性，以更好地进行优先顺序和决策制定。
- **配置状态** - 了解组织安全配置或错误配置。 在仪表板中报告的问题以及可操作的安全建议。

### <a name="intelligence-driven-prioritization"></a>智能驱动的优先顺序

威胁和漏洞管理可帮助客户确定优先级，并重点关注对组织构成最紧急且风险最高的漏洞。 它将安全建议与动态威胁和业务上下文融合在一起：

- **在通配符中公开新出现的攻击** - 动态对齐安全建议优先顺序。 威胁和漏洞管理重点关注当前在构成最高风险的新兴威胁中利用的漏洞。
- **精确定位活动漏洞** - 关联威胁和漏洞管理和 EDR 见解，以确定在组织内部的活动泄露中利用的漏洞的优先级。
- **保护高价值资产** - 使用业务关键应用程序、机密数据或高价值用户标识公开的设备。

### <a name="seamless-remediation"></a>无缝修正

威胁和漏洞管理允许安全管理员和 IT 管理员无缝协作以修正问题。

- **发送给 IT 的修正请求** - 根据特定安全建议在 Microsoft Intune 中创建修正任务。 我们计划将此功能扩展到其他 IT 安全管理平台。
- **备用缓解** - 深入了解其他缓解，例如可降低与软件漏洞关联的风险的配置更改。
- **实时修正状态** - 实时监视整个组织中修正活动的状态和进度。

## <a name="threat-and-vulnerability-management-walk-through"></a>威胁和漏洞管理演练

观看此视频，全面演练威胁和漏洞管理。

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>导航窗格 

区域 | 说明
:---|:---
**仪表板**   | 获取组织曝光分数、适用于设备的 Microsoft 安全分数、设备曝光分布、顶级安全建议、最易受攻击的软件、顶级修正活动和最公开设备数据等高级视图。
[**安全性建议**](tvm-security-recommendation.md) | 请参阅安全建议和相关威胁信息列表。 当你从列表中选择一个项目时，将打开一个包含漏洞详细信息的飞出面板、一个打开软件页的链接以及修正和例外选项。 如果你的设备通过 Azure Active Directory 加入，并且你已启用 Defender for Endpoint 中的 Intune 连接，则还可以在 Intune 中打开票证。
[**修正**](tvm-remediation.md) | 请参阅已创建的修正活动和建议例外。
[**软件库存**](tvm-software-inventory.md) | 请参阅组织中易受攻击的软件列表，以及漏洞和威胁信息。
[**漏洞**](tvm-weaknesses.md) | 请参阅组织中 C CV 的常见 (曝光) 列表。
[**活动日程表**](threat-and-vuln-mgt-event-timeline.md) | 查看可能会影响组织风险的事件。

## <a name="apis"></a>API

运行与威胁和漏洞管理相关的 API 调用，以自动执行漏洞管理工作流。 从此 [Microsoft 技术社区博客文章了解更多信息](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615)。

请参阅以下相关 API 文章：

- [支持的 Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [计算机 API](machine.md)
- [建议 API](vulnerability.md)
- [分数 API](score.md)
- [软件 API](software.md)
- [漏洞 API](vulnerability.md)
- [按计算机和软件列出漏洞](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a>另请参阅

- [支持的操作系统和平台](tvm-supported-os.md)
- [威胁和漏洞管理仪表板](tvm-dashboard-insights.md)
- [博客：Microsoft 的威胁&漏洞管理现在可帮助数以千计的客户实时发现、确定漏洞的优先级并修正漏洞](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
