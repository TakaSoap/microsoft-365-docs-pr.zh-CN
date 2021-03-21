---
title: Microsoft 365 网络连接概述
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: 讨论为什么网络优化对于 SaaS 服务很重要、Microsoft 365 网络的目标以及 SaaS 需要与其他工作负载不同的网络的方式。
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923178"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365 网络连接概述

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Microsoft 365 是一种分布式软件即服务 (SaaS) 云，它通过一组不同的微服务和应用程序提供生产力和协作方案。 Microsoft 365 的客户端组件（如 Outlook、Word 和 PowerPoint）在用户计算机上运行，并连接到在 Microsoft 数据中心中运行的其他 Microsoft 365 组件。 确定 Microsoft 365 最终用户体验质量最重要的因素是 Microsoft 365 客户端和 Microsoft 365 服务前端之间的网络可靠性和低延迟。

本文将介绍 Microsoft 365 网络的目标，以及为什么 Microsoft 365 网络需要不同于常规 Internet 流量的优化方法。

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 网络目标

Microsoft 365 网络的最终目标是通过使客户端和最近的 Microsoft 365 终结点之间的访问限制最小来优化最终用户体验。 最终用户体验的质量与用户使用的应用程序的性能和响应能力直接相关。 例如，Microsoft Teams 依赖于低延迟，以便用户电话呼叫、会议以及共享屏幕协作无故障，并且 Outlook 依靠出色的网络连接，实现利用服务器端索引和 AI 功能的即时搜索功能。

网络设计的主要目标是通过减少从客户端计算机到 Microsoft 全球网络的往返时间 (RTT) 来最大程度地减少延迟，Microsoft 的公共网络中枢，可将 Microsoft 的所有数据中心与分布于世界各地的低延迟、高可用性云应用程序入口点相互连接。 有关 Microsoft 全球网络的详细信息，请参阅 [Microsoft 构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)。

优化 Microsoft 365 网络性能并不复杂。 可以通过遵循一些关键原则获得最佳性能：

- 标识 Microsoft 365 网络流量
- 允许 Microsoft 365 网络流量的本地分支从用户连接到 Microsoft 365 的每个位置进入 Internet
- 允许 Microsoft 365 流量绕过代理和数据包检查设备

有关 Microsoft 365 网络连接原则详细信息，请参阅 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)。

## <a name="traditional-network-architectures-and-saas"></a>传统网络体系结构和 SaaS

客户端/服务器工作负载的传统网络体系结构原则围绕以下假设进行设计：客户端和终结点之间的流量不会扩展到企业网络外围之外。 此外，在许多企业网络中，所有出站 Internet 连接都遍历企业网络，并从中心位置出口。

在传统网络体系结构中，常规 Internet 流量的较高延迟是维护网络外围安全性的必要权衡，而 Internet 流量的性能优化通常涉及到在网络出口点升级或扩展设备。 但是，此方法不满足 SaaS 服务（如 Microsoft 365）的最佳网络性能的要求。

## <a name="identifying-microsoft-365-network-traffic"></a>标识 Microsoft 365 网络流量

我们正在简化标识 Microsoft 365 网络流量，并简化网络标识管理。

- 新类别的网络终结点，用于区分高度关键的网络流量和未受 Internet 延迟影响的网络流量。 在最重要的"优化"类别中，只有少数 URL 和支持 IP 地址。
- 用于脚本使用或 Microsoft 365 网络标识的直接设备配置和更改管理的 Web 服务。 可从 Web 服务、RSS 格式或使用 Microsoft Flow 模板的电子邮件中进行更改。
- [Office 365 网络合作伙伴](./microsoft-365-networking-partner-program.md) 计划与 Microsoft 合作伙伴合作，提供遵循 Microsoft 365 网络连接原则且配置简单的设备或服务。

## <a name="securing-microsoft-365-connections"></a>保护 Microsoft 365 连接

传统的网络安全的目标是强化公司网络外围，防范入侵和恶意漏洞。 大多数企业网络使用代理服务器、防火墙、SSL 中断和检查、深度数据包检查和数据丢失防护系统等技术对 Internet 流量实施网络安全。 这些技术为普通的 Internet 请求提供了重要的风险缓解，但在应用到 Microsoft 365 终结点时，可显著降低性能、可扩展性和最终用户体验。

Microsoft 365 通过专为 Microsoft 365 功能和工作负载设计的内置安全和调控功能，帮助满足组织对内容安全性和数据使用情况合规性的需求。 有关 Microsoft 365 安全性和合规性详细信息，请参阅 [Office 365 安全路线图](/office365/securitycompliance/security-roadmap)。 有关对 Microsoft 365 流量执行高级处理的高级网络解决方案的建议和支持位置的更多信息，请参阅在 [Office 365](https://support.microsoft.com/help/2690045)流量上使用第三方网络设备或解决方案。

## <a name="why-is-microsoft-365-networking-different"></a>为什么 Microsoft 365 网络不同？

Microsoft 365 旨在使用终结点安全性和加密网络连接实现最佳性能，从而减少外围安全实施需求。 Microsoft 365 数据中心位于世界各地，服务旨在使用多种方法将客户端连接到最佳可用服务终结点。 由于用户数据和处理分布在许多 Microsoft 数据中心之间，因此客户端计算机无法连接到任何一个网络终结点。 事实上，Microsoft 365 租户中的数据和服务由 Microsoft 全球网络动态优化，以适应最终用户从中访问这些数据和服务的地理位置。

Microsoft 365 流量受数据包检查和集中出口限制时，会创建一些常见的性能问题：

- 高延迟可能导致视频和音频流的性能极差，以及数据检索、搜索、实时协作、日历忙/闲信息、产品内内容和其他服务的响应缓慢
- 从中心位置出口连接会失败 Microsoft 365 全局网络的动态路由功能，增加延迟和往返时间
- 解密 SSL 保护的 Microsoft 365 网络流量并对其进行重新加密可能会导致协议错误并存在安全风险

通过允许客户端流量尽可能接近其地理位置来缩短到 Microsoft 365 入口点的网络路径，可以提高 Microsoft 365 中的连接性能和最终用户体验。 它还可以帮助减少对网络体系结构未来更改对 Microsoft 365 性能和可靠性的影响。 最佳连接模型始终在用户位置提供网络出口，无论该出口位于企业网络还是远程位置（如家庭、机场、咖啡店和机场）上。 通用 Internet 流量和基于 WAN 的企业网络流量将单独路由，并且不使用本地直接出口模型。 下图所示为所述的本地直接出口模型。

![本地出口网络体系结构](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

与传统模型相比，本地出口体系结构对 Microsoft 365 网络流量具有以下好处：
  
- 通过优化线路长度，提供最佳 Microsoft 365 性能。 最终用户连接通过 Microsoft 全球网络的分布式服务前端基础结构动态路由到最近的 Microsoft 365 入口点，然后通过 Microsoft 超低延迟高可用性光纤将流量内部路由到数据和服务终结点。
- 通过允许 Microsoft 365 流量的本地出口、绕过代理和流量检查设备，减少公司网络基础结构上的负载。
- 利用客户端终结点安全性和云安全功能保护两端连接，避免应用冗余网络安全技术。

> [!NOTE]
> 分布式 _服务前端_ 基础结构是 Microsoft 全球网络高度可用且可扩展的网络边缘，具有地理位置分散的位置。 它将终止最终用户连接，并有效地在 Microsoft 全球网络中路由这些连接。 有关 Microsoft 全球网络的详细信息，请参阅 [Microsoft 构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)。

有关了解和应用 Microsoft 365 网络连接原则详细信息，请参阅 Microsoft [365 网络连接原则](microsoft-365-network-connectivity-principles.md)。

## <a name="conclusion"></a>总结

优化 Microsoft 365 网络性能实际上要消除不必要的障碍。 通过将 Microsoft 365 连接视为受信任的流量，可以防止数据包检查引入延迟并竞争代理带宽。 允许客户端计算机和 Office 365 终结点之间的本地连接允许流量通过 Microsoft 全局网络动态路由。

## <a name="related-topics"></a>相关主题

[Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[管理 Office 365 终结点](managing-office-365-endpoints.md)

[Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)

[Office 365 IP 地址和 URL Web 服务](microsoft-365-ip-web-service.md)

[评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

[Microsoft 365 网络计划和性能优化](network-planning-and-performance.md)

[使用基线和性能历史记录优化 Office 365 性能](performance-tuning-using-baselines-and-history.md)

[Office 365 性能疑难解答计划](performance-troubleshooting-plan.md)

[内容分发网络](content-delivery-networks.md)

[Microsoft 365 连接测试](https://aka.ms/netonboard)

[Microsoft 如何构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 网络工作博客](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)