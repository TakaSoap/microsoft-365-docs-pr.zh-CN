---
title: 'Microsoft 365 网络评估 (预览版) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: 'Microsoft 365 网络评估 (预览版) '
ms.openlocfilehash: 3d80130dbf9ca41342bc1a01fe3ce992303efb48
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200743"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 网络评估 (预览版) 

在 Microsoft 365 管理中心的网络连接中， **网络评估** 将许多网络性能指标的聚合提取到企业网络外围运行状况的快照中，由 0-100 中的点值表示。 网络评估告诉你客户负责网络设计对 Office 365 用户体验有多大影响。 网络评估的作用范围为整个租户和每个地理位置，用户将从该位置连接到你的租户，从而为 Microsoft 365 管理员提供一种简单的方法来即时了解企业网络运行状况的 gestalt，并快速深入到任何全球办公地点的详细报告。

网络评估点值是一天编译的平均 TCP 延迟、下载速度和 UDP 连接质量指标。 Microsoft 拥有的网络的性能指标将从这些度量中排除，以确保评估结果明确且特定于企业网络。

![网络评估价值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

非常低的网络评估价值表明 Microsoft 365 客户端将在连接到租户或维护响应前的用户体验时遇到严重问题，而较高的值表示配置正确的网络，且持续的性能问题很少。 80% 的值表示一个正常的基准，即您不应预期收到有关 Microsoft 365 连接或由于网络性能导致的响应的定期用户意见。 由于进行了重复的网络连接改进，因此此值将随用户体验的增加而增加。

| 网络评估 | 预期的用户体验 |
| :----------------- | :----------------------- |
| 100                | 最好                     |
| 80                 | 满足建议    |
| 60                 | 可以接受               |
| 40                 | 用户可能会遇到问题 |
| 20                 | 用户可能会抱怨       |
| 0                  | 网络问题讨论的常见主题 |

>[!IMPORTANT]
>网络洞察力、Microsoft 365 管理中心中的性能建议和评估当前处于预览状态，并且仅适用于已在功能预览计划中注册的 Microsoft 365 租户。

## <a name="network-assessment-panel"></a>网络评估面板

每个网络评估（无论是属于租户还是特定办公室位置）都将显示一个面板，其中包含有关评估的详细信息。 此面板显示评估的条形图，以百分比表示，并作为每个组件工作负荷的总积分，包括仅收到度量数据的工作负荷。 对于 "办公室位置网络评估"，我们还将显示与 quintiles 中的每五个中的 Microsoft 365 客户的百分比相比较，报告与您的办公室位置相同的城市内的数据。

![示例网络评估值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

面板中的 **评估细目** 显示了每个组件工作负荷的评估。

**评估历史记录**显示了最近30天的评估和基准。 您还可以使用 "历史记录" 选项卡报告最长为两年的任意办公地点的指标历史记录。通过 "历史记录" 选项卡，可以选择要报告的属性，并选择报告时间范围可以突出显示网络更新项目的影响，并查看对网络评估的改进。

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>租户网络评估和 office 位置网络评估

网络评估可衡量办公室的网络外围位置到 Microsoft 网络的设计。 最好在每个办公室位置对网络周边进行改进。

我们在网络性能概述页面上显示了整个 Microsoft 365 租户的网络评估值，这是所有办公地点的网络评估的加权平均值。 在该位置的 "摘要" 页上，每个检测到的 office 位置也有一个特定的网络评估值。

## <a name="exchange-online"></a>Exchange Online

对于 Exchange Online，测量来自客户端计算机到 Exchange 服务前向的 TCP 延迟。 这可能会受到网络通过客户 LAN 和 WAN 传输的距离的影响。 它还可能受到网络中间设备或服务的影响，这些服务会延迟连接或导致发送数据包。 并受最近的 Exchange 服务前盖的距离的影响。 中间 (也称为第50个百分点值或 P50 度量值) 在前三天的所有度量值中采用。

将使用下表进行 Exchange Online 评估。 阈值之间的任何 TCP 延迟数均以线性方式在频带内分配点。

| TCP 延迟   | Points |
| :------------ | :----- |
| 10ms 或更低  | 100    |
| 25ms          | 80     |
| 100毫秒         | 60     |
| 200ms         | 40     |
| 300ms         | 20     |
| 350ms 或更多 | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

对于 SharePoint Online，可供用户从 SharePoint 或 OneDrive 访问文档的下载速度进行度量。 这可能受客户端计算机和 Microsoft 网络之间网络线路上的可用带宽的影响。 通常，在复杂网络设备的瓶颈或较差的 Wlan 区域中存在的网络拥塞也会受到影响。 下载速度以每秒兆字节数度量，每秒大约为每秒额定的电路10秒。 每秒的兆字节数很有用，因为您可以直接在1秒内看到可以下载的大小文件。 第25个百分点 (也称为 "P25" 度量值，) 在前三天的所有度量中采用。 第25个百分点值有助于降低随着时间的推移不同拥塞的影响。

使用下表进行 SharePoint Online 评估。 阈值之间的任何下载速度编号都在频带中线性分配点。

| 下载速度 | Points |
| :------------- | :----- |
| 20MBps 或更多 | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

对于 Microsoft 团队，网络质量是指 UDP 延迟、UDP 抖动和 UDP 数据包丢失。 UDP 可用于 Microsoft 团队的呼叫和会议音频和视频媒体连接。 这可能受到与延迟和下载速度相同的因素的影响，除了网络的 UDP 支持中的连接间隙之外，因为 UDP 是分别配置为更常见的 TCP 协议。 中间 (也称为第50个百分点值或 P50 度量值) 在前三天的所有度量值中采用。 

我们根据从1到5的比例计算来自这些 UDP 度量值的平均意见得分。 然后，我们将其映射到 Microsoft 团队网络评估的0-100 点刻度。  总体正常大于87.5 点，总体差低于50磅。

## <a name="related-topics"></a>相关主题

[Microsoft 365 管理中心中的网络连接 (预览版) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 网络性能见解 (预览版) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 网络连接测试工具 (预览) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 网络连接位置服务 (预览) ](office-365-network-mac-location-services.md)
