---
title: 仪表板见解 - 危险和漏洞管理
description: 仪表板危险和漏洞管理 SecOps 和安全管理员解决网络安全威胁，并构建组织的安全恢复能力。
keywords: Microsoft Defender for Endpoint-tvm， Microsoft Defender for Endpoint-tvm dashboard， 威胁 & 漏洞管理， 危险和漏洞管理， 基于风险的威胁 & 漏洞管理， 安全配置， 适用于设备的 Microsoft 安全分数， 曝光分数
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 63d994ce521f3915daea6a585f64c407fd241eee
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963211"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>仪表板见解 - 危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

威胁和漏洞管理是 Defender for Endpoint 的一个组件，可为安全管理员和安全运营团队提供独特的价值，包括：

- 与终结点漏洞相关的实时终结点检测和响应（EDR）见解
- 事件调查期间有价值的设备漏洞上下文
- 内置修正过程通过Microsoft Intune和Microsoft Endpoint Configuration Manager

可以使用 危险和漏洞管理 门户中的 Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">功能</a>：

- 查看设备的曝光分数和 Microsoft 安全分数，以及顶级安全建议、软件漏洞、修正活动和公开的设备
- 将EDR见解与终结点漏洞关联并处理它们
- 选择修正选项进行会审并跟踪修正任务
- 选择例外选项并跟踪活动异常

> [!NOTE]
> 过去 30 天内未处于活动状态的设备不会在反映组织的 危险和漏洞管理 曝光分数和 Microsoft 设备安全分数的数据中考虑。

观看此视频，快速概览仪表板危险和漏洞管理内容。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>威胁和漏洞管理仪表板

:::image type="content" source="../../media/tvmdashboard.png" lightbox="../../media/tvmdashboard.png" alt-text="设备的威胁和漏洞管理仪表板。":::

<br>

****

|领域|说明|
|---|---|
|**选定的设备组 (#/#)**|按危险和漏洞管理组筛选想要在仪表板和卡片中查看的数据。 在筛选器中选择的内容将应用于整个危险和漏洞管理页。|
|[**风险评分**](tvm-exposure-score.md)|查看组织设备面临的威胁和漏洞的当前状态。 有几个因素会影响组织的曝光评分：在设备中发现的缺点、设备被泄露的可能性、设备对组织的价值，以及设备发现的相关警报。 目标是降低组织的曝光分数，以更安全。 若要降低分数，需要修正安全建议中列出的相关安全配置问题。|
|[**设备的 Microsoft 安全功能分数**](tvm-microsoft-secure-score-devices.md)|查看组织的操作系统、应用程序、网络、帐户和安全控制的安全状态。 目标是修正相关的安全配置问题，以增加设备的分数。 选择条形将你访问" **安全建议"** 页。|
|**设备曝光分布**|查看基于其曝光级别公开的设备数。 选择圆环图中的某个部分以转到"设备"列表页，并查看受影响的设备名称、曝光级别、风险级别和其他详细信息，如域、操作系统平台、其运行状况、上次查看时间及其标记。|
|**首要安全建议**|请参阅已排序的安全建议，这些建议根据组织的风险暴露及其需要的紧急程度进行排序和确定优先级。 选择 **"显示** 更多"以查看列表中的其余安全建议。 对于 **具有例外** 的建议列表，选择"显示例外"。|
|**最易受攻击的软件**|使用在网络设备上安装的易受攻击的软件的堆栈排名列表，以及这些软件如何影响组织曝光分数，实时了解组织的软件清单。 选择一个项目了解详细信息或 **显示详细信息** ，以查看软件清单页中的其余易受 **攻击的软件** 列表。|
|**首要修正活动**|跟踪根据安全建议生成的修正活动。 可以选择列表中的每个项目以查看"修正"页中的详细信息，或选择"显示更多"以查看其余修正活动和活动异常。|
|**最公开的设备**|查看公开的设备名称及其曝光级别。 从列表中选择设备名称以转到设备页面，可在其中查看警报、风险、事件、安全建议、已安装的软件以及发现的与公开的设备关联的漏洞。 选择 **"显示** 更多"以查看公开设备列表的其余部分。 从设备列表中，你可以管理标记、启动自动调查、启动实时响应会话、收集调查包、运行防病毒扫描、限制应用执行和隔离设备。|
|

有关整个门户中使用的图标详细信息，请参阅 [适用于终结点的 Microsoft Defender 图标](portal-overview.md#microsoft-defender-for-endpoint-icons)。

## <a name="related-topics"></a>相关主题

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [风险评分](tvm-exposure-score.md)
- [设备的 Microsoft 安全功能分数](tvm-microsoft-secure-score-devices.md)
- [安全性建议](tvm-security-recommendation.md)
- [软件库存](tvm-software-inventory.md)
- [活动日程表](threat-and-vuln-mgt-event-timeline.md)
