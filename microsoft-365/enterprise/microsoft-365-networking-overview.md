---
title: Microsoft 365 网络连接概述
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/27/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: 讨论为什么网络优化对于 SaaS 服务很重要、Microsoft 365目标，以及 SaaS 需要与其他工作负载不同的网络。
ms.openlocfilehash: e5dcbae5a1fbac3b0b4fd4472fdcac2380b84382
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209701"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365网络连接概述

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft 365是一个分布式软件即服务 (SaaS) 云，它通过一组不同的微服务和应用程序提供生产力和协作方案。 客户端组件的Microsoft 365如 Outlook、Word 和 PowerPoint 在用户计算机上运行，并连接到在 Microsoft 数据中心Microsoft 365的其他组件。 决定最终用户体验质量的最重要的Microsoft 365是客户端与服务前端Microsoft 365之间的网络可靠性和Microsoft 365延迟。

本文将介绍网络目标Microsoft 365，以及为什么Microsoft 365网络需要不同于常规 Internet 流量的优化方法。

## <a name="microsoft-365-networking-goals"></a>Microsoft 365网络目标

建立网络Microsoft 365目标是通过启用客户端和最近的终结点之间限制最少的访问来优化最终用户Microsoft 365体验。 最终用户体验的质量与用户使用的应用程序的性能和响应能力直接相关。 例如，Microsoft Teams依赖于低延迟，以便用户电话呼叫、会议以及共享屏幕协作无故障，Outlook 依靠出色的网络连接实现应用服务器端索引和 AI 功能的即时搜索功能。

网络设计的主要目标是通过减少从客户端计算机到 Microsoft 全球网络的往返时间 (RTT) 来最大程度地减少延迟，Microsoft 的公共网络中枢，可将 Microsoft 的所有数据中心与分布于世界各地的低延迟、高可用性云应用程序入口点相互连接。 有关 Microsoft 全球网络的详细信息，请参阅 [Microsoft 构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)。

优化Microsoft 365网络性能并不复杂。 可以通过遵循一些关键原则获得最佳性能：

- 标识Microsoft 365网络流量
- 允许网络通信的本地Microsoft 365从用户连接到网络的每个位置的 Internet Microsoft 365
- 允许Microsoft 365流量绕过代理和数据包检查设备

有关网络连接原则Microsoft 365，请参阅Microsoft 365[网络连接原则。](microsoft-365-network-connectivity-principles.md)

## <a name="traditional-network-architectures-and-saas"></a>传统网络体系结构和 SaaS

客户端/服务器工作负载的传统网络体系结构原则围绕以下假设进行设计：客户端和终结点之间的流量不会扩展到企业网络外围之外。 此外，在许多企业网络中，所有出站 Internet 连接都遍历企业网络，并从中心位置出口。

在传统网络体系结构中，常规 Internet 流量的较高延迟是维护网络外围安全性的必要权衡，而 Internet 流量的性能优化通常涉及到在网络出口点升级或扩展设备。 但是，此方法无法满足 SaaS 服务（如 saaS 服务）的最佳性能Microsoft 365。

## <a name="identifying-microsoft-365-network-traffic"></a>标识Microsoft 365网络流量

我们正在简化网络通信Microsoft 365，并简化网络标识管理。

- 用于区分高度关键网络流量和未受 Internet 延迟影响的网络流量的新网络终结点类别。 在最重要的"优化"类别中，只有少数 URL 和支持 IP 地址。
- 用于脚本使用或直接设备配置的 Web 服务，以及用于Microsoft 365更改管理。 可从 Web 服务、RSS 格式或电子邮件（使用自定义模板）Microsoft Flow更改。
- [Office 365网络合作伙伴](./microsoft-365-networking-partner-program.md)计划与 Microsoft 合作伙伴合作，这些合作伙伴提供遵循网络连接Microsoft 365且配置简单的设备或服务。

## <a name="securing-microsoft-365-connections"></a>保护Microsoft 365连接

传统的网络安全的目标是强化公司网络外围，防范入侵和恶意漏洞。 大多数企业网络使用代理服务器、防火墙、SSL 中断和检查、深度数据包检查和数据丢失防护系统等技术对 Internet 流量实施网络安全。 这些技术为普通的 Internet 请求提供了重要的风险缓解，但在应用到 Microsoft 365 终结点时，可显著降低性能、可扩展性和最终用户体验。

Microsoft 365内置安全和治理功能（专为 Microsoft 365 功能和工作负载设计）帮助满足组织对内容安全性和数据使用情况合规性的需求。 有关安全性和合规性Microsoft 365，请参阅安全Office 365[路线图](/office365/securitycompliance/security-roadmap)。 有关 Microsoft 的建议和支持在对 Microsoft 365 流量执行高级处理的高级网络解决方案上的位置的更多信息，请参阅在 Office 365 流量上使用第三方网络设备或[解决方案](https://support.microsoft.com/help/2690045)。

## <a name="why-is-microsoft-365-networking-different"></a>为什么网络Microsoft 365不同？

Microsoft 365专为使用终结点安全性和加密网络连接实现最佳性能而设计的，从而减少了外围安全实施需求。 Microsoft 365数据中心位于全球，服务旨在使用多种方法将客户端连接到最佳可用服务终结点。 由于用户数据和处理分布在许多 Microsoft 数据中心之间，因此客户端计算机无法连接到任何一个网络终结点。 事实上，Microsoft 365租户中的数据和服务由 Microsoft 全球网络动态优化，以适应最终用户从中访问这些数据和服务所基于的地理位置。

当流量受到数据包检查Microsoft 365集中出口时，会创建一些常见的性能问题：

- 高延迟可能导致视频和音频流性能不佳，以及数据检索、搜索、实时协作、日历忙/闲信息、产品内内容和其他服务响应缓慢
- 从中央位置出口连接会与全局网络的动态路由Microsoft 365，增加延迟和往返时间
- 解密 SSL 安全Microsoft 365网络流量并对其进行重新加密可能会导致协议错误，并存在安全风险

通过允许客户端流量Microsoft 365尽可能靠近其地理位置来缩短到这些入口点的网络路径，可以提高连接性能和 Microsoft 365。 它还有助于减少网络体系结构未来更改对性能和可靠性Microsoft 365的影响。 最佳连接模型始终在用户位置提供网络出口，而不管它是在企业网络还是远程位置（如家庭、机场、咖啡店和机场）上。 通用 Internet 流量和基于 WAN 的企业网络流量将单独路由，并且不使用本地直接出口模型。 下图所示为所述的本地直接出口模型。

![本地出口网络体系结构。](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

针对 Microsoft 365 网络流量，与传统模型相比，本地出口体系结构具有以下优点：
  
- 通过优化线路长度，提供最佳 Microsoft 365 性能。 最终用户连接通过 Microsoft 全球网络的分布式服务前端基础结构动态路由到最近的 Microsoft 365 入口点，然后通过Microsoft 超低延迟高可用性光纤将流量内部路由到数据和服务终结点。
- 通过允许流量的本地出口、绕过代理和流量检查Microsoft 365公司网络基础结构上的负载。
- 通过应用客户端终结点安全性和云安全功能保护两端的连接，以避免应用冗余网络安全技术。

> [!NOTE]
> 分布式 _服务前端_ 基础结构是 Microsoft 全球网络高度可用且可扩展的网络边缘，具有地理位置分散的位置。 它将终止最终用户连接，并有效地在 Microsoft 全球网络中路由这些连接。 有关 Microsoft 全球网络的详细信息，请参阅 [Microsoft 构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)。

有关了解和应用网络连接Microsoft 365，请参阅网络连接Microsoft 365[准则](microsoft-365-network-connectivity-principles.md)。

## <a name="conclusion"></a>结论

优化Microsoft 365网络性能实际上要消除不必要的障碍。 通过将Microsoft 365视为受信任的流量，可以防止数据包检查引入延迟并竞争代理带宽。 允许客户端计算机和 Office 365 终结点之间的本地连接允许流量通过 Microsoft 全球网络动态路由。

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
