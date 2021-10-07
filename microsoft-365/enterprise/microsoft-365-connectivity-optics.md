---
title: Microsoft 365连接光学
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 本文包含有关连接Microsoft 365的信息。
ms.openlocfilehash: c1ee14966f13ff50ff809ebbdf4c578bf949e956
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150541"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365连接光学

本文档介绍 Microsoft 通常从客户设备收集的一些连接光学镜头，并介绍 Microsoft 使用此类数据分析和优化服务交付以及评估和确保最佳最终用户体验的一些方法。

连接光学镜头通常从 Microsoft 应用程序收集，这些光学组件可以安装在最终用户设备上，也可以从浏览器访问。 与 Microsoft 365 中的可选数据收集不同，此处介绍的许多连接光学镜头对于确保 Microsoft 满足我们与客户的可用性和性能承诺是不可或缺的。 这些光学镜头使 Microsoft 可以快速检测和响应最终用户与 Microsoft 服务终结点之间的连接路径中的任何问题。 其中一些光学镜头还用于启用网络中心中的网络连接[Microsoft 365 管理功能](office-365-network-mac-perf-overview.md)。

## <a name="optics-collected-from-microsoft-365-applications"></a>从应用程序收集的Microsoft 365

目前，在所有设备上使用不频繁采样收集光学镜头。 一般来说，特定光学镜头和目标 (服务终结点) 它们要通过特定迭代进行测量）由 Microsoft 根据服务要求进行配置，并出于采样目的进行随机化。
在每个光学系统收集间隔，可能会使用最终用户设备作为测量源和一个 Microsoft 365 服务终结点作为测量目标收集以下一个或多个测量：

| 度量 | 说明 |
| --- | --- |
| 延迟 | 通过 HTTP 检索小文件所花时间 |
| 吞吐量 | 通过 HTTP 检索较大文件所花时间（很少测量）以避免过多的带宽消耗 |
| RTT (往返)  | ICMP ping |
| Traceroute | ICMP traceroute |

每个度量通常与其他信息相关联，其中可能包括以下项目：

| 项目 | 说明 |
| --- | --- |
| 租户 ID | 与最终用户设备关联的Azure Active Directory租户的唯一标识符。 |
| 监视器 ID | 生成请求请求的应用程序的标识符 (如 Outlook、OneDrive 等 ) ，由执行测量的客户端应用程序提供。 |
| 请求 ID | Microsoft 提供的度量配置中指定的度量请求的标识符。 |
| 远程 IP | 与从客户端到服务终结点的请求关联的掩码源 IP，由接收测量请求的服务器提供，并且根据对 Microsoft 可见的客户端源 IP 地址计算。 IP 地址被屏蔽到 IPv4 地址的 /24 子网或 IPv6 地址的 /48 子网，以确保 Microsoft 无法识别单个设备或用户。 |
| 前端 | Microsoft 365服务前端标识符，由接收测量请求的服务器提供。 |
| 端点 | Microsoft 365由接收测量请求的服务器提供的服务终结点位置。 |
| 证书颁发者 | 连接到服务终结点时呈现的 SSL 证书的"证书颁发者"属性，指示将证书颁发给服务终结点的证书颁发机构。 |
| 证书指纹 | 连接到服务终结点时呈现的 SSL 证书的"证书指纹"属性，服务终结点是证书的可公开访问的唯一标识符。 |
| 纬度/经度 | 最终用户设备的抽象纬度和经度。 仅针对在最终用户设备上启用了 Windows 定位服务的租户，并且还启用了在 Microsoft 365 管理门户[中收集此信息](office-365-network-mac-perf-overview.md#1-enable-windows-location-services)。 |

## <a name="measurement-process"></a>度量过程

对于已安装的应用程序) ，每个最终用户设备通常会按计划执行 (或基于为基于 Web 的应用程序 (加载浏览器页面的操作) 。 度量活动作为后台操作执行，不会影响用户的应用程序体验。 由于将用于此过程的特定迭代的度量类型和目标是随机的，因此客户可能会注意到，客户可能注意到针对其地区的 Microsoft 服务终结点的请求与最终用户设备针对正常应用程序连接发出的典型请求类似。 此外，客户可能会注意到对位于其本地区域之外的 Microsoft 服务终结点的请求。 这些度量通常用于确保客户请求以最佳方式路由到最佳服务终结点，因为对客户和 ISP 基础结构的更改可能要求 Microsoft 持续更改我们的请求路由策略。 若要详细了解 Microsoft 如何将流量路由到最佳服务终结点，以及如何优化与 Microsoft 365 服务的连接，Microsoft 365[网络连接概述。](microsoft-365-networking-overview.md)

## <a name="service-endpoints"></a>服务终结点

用作这些度量目标的 Microsoft 服务终结点包含在已发布的 url 和 IP Office 365[范围内](urls-and-ip-address-ranges.md)。 对于这些连接光学镜头的集合，不需要访问其他服务终结点。
