---
title: 'Microsoft 365 网络见解 (预览) '
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
description: 'Microsoft 365 网络见解 (预览) '
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055469"
---
# <a name="microsoft-365-network-insights-preview"></a>Microsoft 365 网络见解 (预览) 

**网络见解** 是从 Microsoft 365 租户收集的性能指标，仅可供租户中的管理用户查看。 Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance> .

见解旨在帮助您设计办公地点的网络外围。 每个见解都提供有关用户访问租户的每个地理位置的特定常见问题的性能特征的实时详细信息。

每个办公室位置可能会显示六个特定的网络见解：

- [回程网络出口](#backhauled-network-egress)
- [网络中介设备](#network-intermediary-device)
- [为附近客户检测到更好的性能](#better-performance-detected-for-customers-near-you)
- [使用非最佳 Exchange Online 服务前端](#use-of-a-non-optimal-exchange-online-service-front-door)
- [使用非最佳 SharePoint Online 服务前端](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [从 SharePoint 前端下载速度较低](#low-download-speed-from-sharepoint-front-door)
- [中国用户最佳网络出口](#china-user-optimal-network-egress)

可能会为租户显示两个租户级别的网络见解。 这些也显示在 producvitivy 分数页面中：

- [受连接问题影响的 Exchange 采样连接](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [受连接问题影响的 SharePoint 采样连接](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
>Microsoft 365 管理中心中的网络见解、性能建议和评估目前处于预览状态，仅适用于已在功能预览计划注册的 Microsoft 365 租户。

## <a name="backhauled-network-egress"></a>回程网络出口

如果网络见解服务检测到从给定用户位置到网络出口的距离大于 500 英里 (800 千米) ，则将显示此见解，指示 Microsoft 365 流量正在回流到常见的 Internet 边缘设备或代理。

在某些摘要视图中，此见解缩写为"出口"。

![回程网络出口](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>应用场景

这标识了办公室位置和网络出口之间的距离超过 500 英里 (800 千米) 。 办公室位置由混淆的客户端计算机位置标识，网络出口位置使用反向 IP 地址标识到位置数据库。 如果计算机上禁用了 Windows Location Services，则办公地点可能不准确。 如果反向 IP 地址数据库信息不准确，则网络出口位置可能不准确。

此见解的详细信息包括办公室位置、位置中租户用户总数的估计百分比、当前网络出口位置、出口位置的相关性、位置与当前出口点之间的距离、首次检测到条件的日期以及解决条件的日期。

### <a name="what-should-i-do"></a>该怎么办？

为获得此见解，我们建议网络出口更接近办公地点，以便连接性可以最佳地路由到 Microsoft 的全局网络和最近的 Microsoft 365 服务前端。 通过关闭到用户办公室位置的网络出口，还可以在未来提高性能，因为 Microsoft 未来将同时扩展网络接入点和 Microsoft 365 服务前端入口。

若要详细了解如何解决此问题，请参阅[Office 365](microsoft-365-network-connectivity-principles.md)网络连接原则中的本地出口网络连接。 [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)

## <a name="network-intermediary-device"></a>网络中介设备

如果我们检测到用户和 Microsoft 网络之间的设备可能会影响 Office 365 用户体验，将显示此见解。 对于发往 Microsoft 数据中心的特定 Microsoft 365 网络流量，建议绕过这些限制。 Microsoft [365](microsoft-365-network-connectivity-principles.md)网络连接原则中还介绍了此建议

### <a name="what-does-this-mean"></a>应用场景

代理服务器、VPN 和数据丢失防护设备等网络中介设备可能会影响中间流量的 Microsoft 365 客户端的性能和稳定性。

### <a name="what-should-i-do"></a>该怎么办？

配置检测到绕过 Microsoft 365 网络流量处理的网络中介设备。

## <a name="better-performance-detected-for-customers-near-you"></a>为附近客户检测到更好的性能

如果网络见解服务检测到您的都市地区的大量客户的性能优于位于此办公地点的组织中用户，将显示此见解。

在某些摘要视图中，此见解缩写为"对等"。

![相对网络性能](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>应用场景

此见解将检查 Microsoft 365 客户在此办公地点位于同一城市的总绩效。 如果用户的平均延迟比相邻租户的平均延迟高 10%，将显示此见解。

### <a name="what-should-i-do"></a>该怎么办？

此情况的原因可能有很多，包括企业网络或 ISP 中的延迟、瓶颈或体系结构设计问题。 检查 Office 网络与当前 Microsoft 365 前端之间的路由中每个跃点之间的延迟。 有关详细信息，请参阅 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)。

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>使用非最佳 Exchange Online 服务前端

如果网络见解服务检测到特定位置的用户未连接到最佳 Exchange Online 服务前端，将显示此见解。

在某些摘要视图中，此见解缩写为"路由"。

![非最佳 EXO 前端](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>应用场景

我们列出了适合从办公地点城市使用、性能良好的 Exchange Online 服务前端。 如果当前测试显示未在此列表中使用 Exchange Online 服务前端，则我们将调用此建议。

### <a name="what-should-i-do"></a>该怎么办？

使用非最佳 Exchange Online 服务前端可能是由于企业网络出口之前的网络回程所致，在这种情况下，我们建议使用本地和直接网络出口。 它还可能是由于使用远程 DNS 递归解析器服务器导致的，在这种情况下，我们建议将 DNS 递归解析器服务器与网络出口对齐。

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>使用非最佳 SharePoint Online 服务前端

如果网络见解服务检测到特定位置的用户未连接到最近的 SharePoint Online 服务前端，将显示此见解。

在某些摘要视图中，此见解缩写为"Afd"。

![非最佳 SPO 前端](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>应用场景

我们确定测试客户端连接到的 SharePoint Online 服务前端。 然后，对于办公地点城市，我们将该城市与预期的 SharePoint Online 服务前端进行比较。 如果不匹配，我们提出此建议。

### <a name="what-should-i-do"></a>该怎么办？

使用非最佳 SharePoint Online 服务前端可能是由于企业网络出口之前的网络回程所致，在这种情况下，我们建议使用本地和直接网络出口。 它还可能是由于使用远程 DNS 递归解析器服务器导致的，在这种情况下，我们建议将 DNS 递归解析器服务器与网络出口对齐。

## <a name="low-download-speed-from-sharepoint-front-door"></a>从 SharePoint 前端下载速度低

如果网络见解服务检测到特定办公地点与 SharePoint Online 之间的带宽小于 1 MBps，将显示此见解。

在某些摘要视图中，此见解缩写为"吞吐量"。

### <a name="what-does-this-mean"></a>应用场景

用户可以从 SharePoint Online 和 OneDrive for Business 服务前端门获取的下载速度以兆字节/ (MBps) 。 如果此值小于 1 MBps，我们将提供此见解。

### <a name="what-should-i-do"></a>该怎么办？

若要提高下载速度，可能需要增加带宽。 或者，办公室位置的用户计算机和 SharePoint Online 服务前端之间可能存在网络拥塞。 有时，这称为"连接丢失"，它限制了可供用户使用的下载速度，即使有足够的带宽可用。

## <a name="china-user-optimal-network-egress"></a>中国用户最佳网络出口

如果你的组织在中国有用户连接到其他地理位置的 Microsoft 365 租户，将显示此见解。 

### <a name="what-does-this-mean"></a>应用场景

如果您的组织具有专用 WAN 连接，我们建议从中国的办公室位置配置网络 WAN 线路，该线路具有以下任一位置的 Internet 网络出口：

- 香港特别行政区
- 日本
- Taiwan（台湾）
- 韩国
- 新加坡
- 马来西亚

与这些位置距离更远的用户的 Internet 出口将降低性能，并且由于跨界拥塞，中国出口可能会导致高延迟和连接问题。

### <a name="what-should-i-do"></a>该怎么办？

若要详细了解如何缓解与此见解相关的性能问题，请参阅针对中国用户的 [Microsoft 365 全局租户性能优化](microsoft-365-networking-china.md)。

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a>受连接问题影响的 Exchange 采样连接

此见解将显示 50% 或 50% 以上的采样连接何时受到影响。 Exchange 评估针对每个示例将影响定义为低于 60%。

### <a name="what-does-this-mean"></a>应用场景

这表示大多数用户可能遇到连接到 Exchange Online 的 Outlook 的用户体验问题。 样本百分比可能表示显示低于 60 分的用户百分比。  

### <a name="what-should-i-do"></a>该怎么办？

如果尚未启用，启用 Office 位置网络连接可见性。 要确定哪些办事处受影响 Exchange 的网络连接不佳的影响，并找到在将用户连接到 Microsoft 网络的每个办事处上改进网络外围的方法。

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a>受连接问题影响的 SharePoint 采样连接

此见解将显示 50% 或 50% 以上的采样连接何时受到影响。 影响由 SharePoint 评估定义，每个样本低于 40%。

### <a name="what-does-this-mean"></a>应用场景

这表示你的大多数用户可能会遇到 SharePoint 和 OneDrive 的用户体验问题。 样本百分比可能表示显示低于 40 分的用户百分比。  

### <a name="what-should-i-do"></a>该怎么办？

如果尚未启用，启用 Office 位置网络连接可见性。 要确定哪些办事处受影响 SharePoint 的网络连接不佳的影响，并找到改进将用户连接到 Microsoft 网络的每个办事处的网络外围的方法。

## <a name="related-topics"></a>相关主题

[Microsoft 365 管理中心中的网络连接 (预览版) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 网络评估 (预览) ](office-365-network-mac-perf-score.md)

[Microsoft 365 网络连接测试工具 (预览) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 网络连接位置服务 (预览) ](office-365-network-mac-location-services.md)
