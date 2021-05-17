---
title: Microsoft 365网络连接概述
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
description: 讨论为什么网络优化对于 SaaS 服务很重要、Microsoft 365目标，以及 SaaS 需要与其他工作负载不同的网络的方式。
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923178"
---
# <a name="microsoft-365-network-connectivity-overview"></a><span data-ttu-id="cda83-103">Microsoft 365 网络连接概述</span><span class="sxs-lookup"><span data-stu-id="cda83-103">Microsoft 365 network connectivity overview</span></span>

<span data-ttu-id="cda83-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="cda83-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cda83-105">Microsoft 365是一种分布式软件即服务 (SaaS) 云，它通过一组不同的微服务和应用程序提供生产力和协作方案。</span><span class="sxs-lookup"><span data-stu-id="cda83-105">Microsoft 365 is a distributed Software-as-a-Service (SaaS) cloud that provides productivity and collaboration scenarios through a diverse set of micro-services and applications.</span></span> <span data-ttu-id="cda83-106">客户端组件的Microsoft 365如 Outlook、Word 和 PowerPoint 在用户计算机上运行，并连接到 Microsoft 365 在 Microsoft 数据中心中运行的其他组件。</span><span class="sxs-lookup"><span data-stu-id="cda83-106">Client components of Microsoft 365 such as Outlook, Word and PowerPoint run on user computers and connect to other components of Microsoft 365 that run in Microsoft datacenters.</span></span> <span data-ttu-id="cda83-107">决定最终用户体验质量的最重要的Microsoft 365是客户端与 Microsoft 365 前端Microsoft 365之间的网络可靠性和低延迟。</span><span class="sxs-lookup"><span data-stu-id="cda83-107">The most significant factor that determines the quality of the Microsoft 365 end user experience is network reliability and low latency between Microsoft 365 clients and Microsoft 365 service front doors.</span></span>

<span data-ttu-id="cda83-108">本文将介绍网络目标Microsoft 365，以及为什么Microsoft 365网络需要不同于常规 Internet 流量的优化方法。</span><span class="sxs-lookup"><span data-stu-id="cda83-108">In this article, you will learn about the goals of Microsoft 365 networking, and why Microsoft 365 networking requires a different approach to optimization than generic Internet traffic.</span></span>

## <a name="microsoft-365-networking-goals"></a><span data-ttu-id="cda83-109">Microsoft 365网络目标</span><span class="sxs-lookup"><span data-stu-id="cda83-109">Microsoft 365 networking goals</span></span>

<span data-ttu-id="cda83-110">建立网络Microsoft 365目标是通过启用客户端和最近的终结点之间限制最少的访问来优化最终用户Microsoft 365体验。</span><span class="sxs-lookup"><span data-stu-id="cda83-110">The ultimate goal of Microsoft 365 networking is to optimize the end user experience by enabling the least restrictive access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="cda83-111">最终用户体验的质量与用户使用的应用程序的性能和响应能力直接相关。</span><span class="sxs-lookup"><span data-stu-id="cda83-111">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="cda83-112">例如，Microsoft Teams依赖于低延迟，以便用户电话呼叫、会议以及共享屏幕协作无故障，Outlook 依靠出色的网络连接实现利用服务器端索引和 AI 功能的即时搜索功能。</span><span class="sxs-lookup"><span data-stu-id="cda83-112">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free, and Outlook relies on great networking connectivity for instant search features that leverage server-side indexing and AI capabilities.</span></span>

<span data-ttu-id="cda83-113">网络设计的主要目标是通过减少从客户端计算机到 Microsoft 全球网络的往返时间 (RTT) 来最大程度地减少延迟，Microsoft 的公共网络中枢，可将 Microsoft 的所有数据中心与分布于世界各地的低延迟、高可用性云应用程序入口点相互连接。</span><span class="sxs-lookup"><span data-stu-id="cda83-113">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client machines to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points spread around the world.</span></span> <span data-ttu-id="cda83-114">有关 Microsoft 全球网络的详细信息，请参阅 [Microsoft 构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)。</span><span class="sxs-lookup"><span data-stu-id="cda83-114">You can learn more about the Microsoft Global Network at [How Microsoft builds its fast and reliable global network](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span></span>

<span data-ttu-id="cda83-115">优化Microsoft 365网络性能并不复杂。</span><span class="sxs-lookup"><span data-stu-id="cda83-115">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="cda83-116">可以通过遵循一些关键原则获得最佳性能：</span><span class="sxs-lookup"><span data-stu-id="cda83-116">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="cda83-117">标识Microsoft 365网络流量</span><span class="sxs-lookup"><span data-stu-id="cda83-117">Identify Microsoft 365 network traffic</span></span>
- <span data-ttu-id="cda83-118">允许网络通信的本地Microsoft 365从用户连接到网络的每个位置的 Internet Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cda83-118">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365</span></span>
- <span data-ttu-id="cda83-119">允许Microsoft 365流量绕过代理和数据包检查设备</span><span class="sxs-lookup"><span data-stu-id="cda83-119">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices</span></span>

<span data-ttu-id="cda83-120">有关网络连接原则Microsoft 365，请参阅Microsoft 365[网络连接原则](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="cda83-120">For more information on Microsoft 365 network connectivity principles, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="traditional-network-architectures-and-saas"></a><span data-ttu-id="cda83-121">传统网络体系结构和 SaaS</span><span class="sxs-lookup"><span data-stu-id="cda83-121">Traditional network architectures and SaaS</span></span>

<span data-ttu-id="cda83-122">客户端/服务器工作负载的传统网络体系结构原则围绕以下假设进行设计：客户端和终结点之间的流量不会扩展到企业网络外围之外。</span><span class="sxs-lookup"><span data-stu-id="cda83-122">Traditional network architecture principles for client/server workloads are designed around the assumption that traffic between clients and endpoints does not extend outside the corporate network perimeter.</span></span> <span data-ttu-id="cda83-123">此外，在许多企业网络中，所有出站 Internet 连接都遍历企业网络，并从中心位置出口。</span><span class="sxs-lookup"><span data-stu-id="cda83-123">Also, in many enterprise networks, all outbound Internet connections traverse the corporate network, and egress from a central location.</span></span>

<span data-ttu-id="cda83-124">在传统网络体系结构中，常规 Internet 流量的较高延迟是维护网络外围安全性的必要权衡，而 Internet 流量的性能优化通常涉及到在网络出口点升级或扩展设备。</span><span class="sxs-lookup"><span data-stu-id="cda83-124">In traditional network architectures, higher latency for generic Internet traffic is a necessary tradeoff in order to maintain network perimeter security, and performance optimization for Internet traffic typically involves upgrading or scaling out the equipment at network egress points.</span></span> <span data-ttu-id="cda83-125">但是，此方法不满足 SaaS 服务（如 Microsoft 365）的最佳网络性能的要求。</span><span class="sxs-lookup"><span data-stu-id="cda83-125">However, this approach does not address the requirements for optimum network performance of SaaS services such as Microsoft 365.</span></span>

## <a name="identifying-microsoft-365-network-traffic"></a><span data-ttu-id="cda83-126">标识Microsoft 365网络流量</span><span class="sxs-lookup"><span data-stu-id="cda83-126">Identifying Microsoft 365 network traffic</span></span>

<span data-ttu-id="cda83-127">我们正在简化网络通信Microsoft 365，并简化网络标识管理。</span><span class="sxs-lookup"><span data-stu-id="cda83-127">We're making it easier to identify Microsoft 365 network traffic and making it simpler to manage the network identification.</span></span>

- <span data-ttu-id="cda83-128">新类别的网络终结点，用于区分高度关键的网络流量和未受 Internet 延迟影响的网络流量。</span><span class="sxs-lookup"><span data-stu-id="cda83-128">New categories of network endpoints to differentiate highly critical network traffic from network traffic which is not impacted by Internet latencies.</span></span> <span data-ttu-id="cda83-129">在最重要的"优化"类别中，只有少数 URL 和支持 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="cda83-129">There are just a handful of URLs and supporting IP Addresses in the most critical “Optimize” category.</span></span>
- <span data-ttu-id="cda83-130">用于脚本使用或直接设备配置的 Web 服务，以及用于Microsoft 365更改管理。</span><span class="sxs-lookup"><span data-stu-id="cda83-130">Web services for script usage or direct device configuration and change management of Microsoft 365 network identification.</span></span> <span data-ttu-id="cda83-131">可从 Web 服务、RSS 格式或电子邮件（使用自定义模板）Microsoft Flow更改。</span><span class="sxs-lookup"><span data-stu-id="cda83-131">Changes are available from the web service, or in RSS format, or on email using a Microsoft Flow template.</span></span>
- <span data-ttu-id="cda83-132">[Office 365网络合作伙伴](./microsoft-365-networking-partner-program.md)计划与 Microsoft 合作伙伴合作，这些合作伙伴提供遵循网络连接Microsoft 365且配置简单的设备或服务。</span><span class="sxs-lookup"><span data-stu-id="cda83-132">[Office 365 Network partner program](./microsoft-365-networking-partner-program.md) with Microsoft partners who provide devices or services that follow Microsoft 365 network connectivity principles and have simple configuration.</span></span>

## <a name="securing-microsoft-365-connections"></a><span data-ttu-id="cda83-133">保护Microsoft 365连接</span><span class="sxs-lookup"><span data-stu-id="cda83-133">Securing Microsoft 365 connections</span></span>

<span data-ttu-id="cda83-134">传统的网络安全的目标是强化公司网络外围，防范入侵和恶意漏洞。</span><span class="sxs-lookup"><span data-stu-id="cda83-134">The goal of traditional network security is to harden the corporate network perimeter against intrusion and malicious exploits.</span></span> <span data-ttu-id="cda83-135">大多数企业网络使用代理服务器、防火墙、SSL 中断和检查、深度数据包检查和数据丢失防护系统等技术对 Internet 流量实施网络安全。</span><span class="sxs-lookup"><span data-stu-id="cda83-135">Most enterprise networks enforce network security for Internet traffic using technologies like proxy servers, firewalls, SSL break and inspect, deep packet inspection, and data loss prevention systems.</span></span> <span data-ttu-id="cda83-136">这些技术为普通的 Internet 请求提供了重要的风险缓解，但在应用到 Microsoft 365 终结点时，可显著降低性能、可扩展性和最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="cda83-136">These technologies provide important risk mitigation for generic Internet requests but can dramatically reduce performance, scalability, and the quality of end user experience when applied to Microsoft 365 endpoints.</span></span>

<span data-ttu-id="cda83-137">Microsoft 365内置安全和治理功能（专为 Microsoft 365 功能和工作负载设计）帮助满足组织对内容安全性和数据使用情况合规性的需求。</span><span class="sxs-lookup"><span data-stu-id="cda83-137">Microsoft 365 helps meet your organization's needs for content security and data usage compliance with built-in security and governance features designed specifically for Microsoft 365 features and workloads.</span></span> <span data-ttu-id="cda83-138">有关安全与合规性Microsoft 365，请参阅安全Office 365[路线图](/office365/securitycompliance/security-roadmap)。</span><span class="sxs-lookup"><span data-stu-id="cda83-138">For more information about Microsoft 365 security and compliance, see the [Office 365 security roadmap](/office365/securitycompliance/security-roadmap).</span></span> <span data-ttu-id="cda83-139">有关 Microsoft 的建议和支持在对 Microsoft 365 流量执行高级处理的高级网络解决方案上的位置的更多信息，请参阅在 Office 365 流量上使用第三方网络设备或[解决方案](https://support.microsoft.com/help/2690045)。</span><span class="sxs-lookup"><span data-stu-id="cda83-139">For more information about Microsoft’s recommendations and support position on advanced network solutions that perform advanced-level processing on Microsoft 365 traffic, see [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045).</span></span>

## <a name="why-is-microsoft-365-networking-different"></a><span data-ttu-id="cda83-140">为什么网络Microsoft 365不同？</span><span class="sxs-lookup"><span data-stu-id="cda83-140">Why is Microsoft 365 networking different?</span></span>

<span data-ttu-id="cda83-141">Microsoft 365是专为使用终结点安全性和加密网络连接实现最佳性能而设计的，从而减少了外围安全实施需求。</span><span class="sxs-lookup"><span data-stu-id="cda83-141">Microsoft 365 is designed for optimal performance using endpoint security and encrypted network connections, reducing the need for perimeter security enforcement.</span></span> <span data-ttu-id="cda83-142">Microsoft 365数据中心位于全球，服务旨在使用多种方法将客户端连接到最佳可用服务终结点。</span><span class="sxs-lookup"><span data-stu-id="cda83-142">Microsoft 365 datacenters are located across the world and the service is designed to use various methods for connecting clients to best available service endpoints.</span></span> <span data-ttu-id="cda83-143">由于用户数据和处理分布在许多 Microsoft 数据中心之间，因此客户端计算机无法连接到任何一个网络终结点。</span><span class="sxs-lookup"><span data-stu-id="cda83-143">Since user data and processing is distributed between many Microsoft datacenters, there is no single network endpoint to which client machines can connect.</span></span> <span data-ttu-id="cda83-144">事实上，Microsoft 365租户中的数据和服务由 Microsoft 全球网络动态优化，以适应最终用户从中访问这些数据和服务所基于的地理位置。</span><span class="sxs-lookup"><span data-stu-id="cda83-144">In fact, data and services in your Microsoft 365 tenant are dynamically optimized by the Microsoft Global Network to adapt to the geographic locations from which they are accessed by end users.</span></span>

<span data-ttu-id="cda83-145">当流量受到数据包检查Microsoft 365集中出口时，会创建一些常见的性能问题：</span><span class="sxs-lookup"><span data-stu-id="cda83-145">Certain common performance issues are created when Microsoft 365 traffic is subject to packet inspection and centralized egress:</span></span>

- <span data-ttu-id="cda83-146">高延迟可能导致视频和音频流的性能极差，以及数据检索、搜索、实时协作、日历忙/闲信息、产品内内容和其他服务的响应缓慢</span><span class="sxs-lookup"><span data-stu-id="cda83-146">High latency can cause extremely poor performance of video and audio streams, and slow response of data retrieval, searches, real-time collaboration, calendar free/busy information, in-product content and other services</span></span>
- <span data-ttu-id="cda83-147">从中心位置出口连接会失败全球网络的动态路由Microsoft 365，增加延迟和往返时间</span><span class="sxs-lookup"><span data-stu-id="cda83-147">Egressing connections from a central location defeats the dynamic routing capabilities of the Microsoft 365 global network, adding latency and round-trip time</span></span>
- <span data-ttu-id="cda83-148">解密安全 SSL Microsoft 365网络流量并对其进行重新加密可能会导致协议错误，并存在安全风险</span><span class="sxs-lookup"><span data-stu-id="cda83-148">Decrypting SSL secured Microsoft 365 network traffic and re-encrypting it can cause protocol errors and has security risk</span></span>

<span data-ttu-id="cda83-149">通过允许客户端流量尽可能靠近其地理位置来缩短Microsoft 365入口点的网络路径，可以提高连接性能和最终用户在 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="cda83-149">Shortening the network path to Microsoft 365 entry points by allowing client traffic to egress as close as possible to their geographic location can improve connectivity performance and the end user experience in Microsoft 365.</span></span> <span data-ttu-id="cda83-150">它还有助于减少网络体系结构未来更改对性能和可靠性Microsoft 365的影响。</span><span class="sxs-lookup"><span data-stu-id="cda83-150">It can also help to reduce the impact of future changes to the network architecture on Microsoft 365 performance and reliability.</span></span> <span data-ttu-id="cda83-151">最佳连接模型始终在用户位置提供网络出口，无论该出口位于企业网络还是远程位置（如家庭、机场、咖啡店和机场）上。</span><span class="sxs-lookup"><span data-stu-id="cda83-151">The optimum connectivity model is to always provide network egress at the user's location, regardless of whether this is on the corporate network or remote locations such as home, hotels, coffee shops and airports.</span></span> <span data-ttu-id="cda83-152">通用 Internet 流量和基于 WAN 的企业网络流量将单独路由，并且不使用本地直接出口模型。</span><span class="sxs-lookup"><span data-stu-id="cda83-152">Generic Internet traffic and WAN based corporate network traffic would be separately routed and not use the local direct egress model.</span></span> <span data-ttu-id="cda83-153">下图所示为所述的本地直接出口模型。</span><span class="sxs-lookup"><span data-stu-id="cda83-153">This local direct egress model is represented in the diagram below.</span></span>

![本地出口网络体系结构](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

<span data-ttu-id="cda83-155">针对 Microsoft 365 网络流量，与传统模型相比，本地出口体系结构具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="cda83-155">The local egress architecture has the following benefits for Microsoft 365 network traffic over the traditional model:</span></span>
  
- <span data-ttu-id="cda83-156">通过优化线路长度，提供最佳 Microsoft 365 性能。</span><span class="sxs-lookup"><span data-stu-id="cda83-156">Provides optimal Microsoft 365 performance by optimizing route length.</span></span> <span data-ttu-id="cda83-157">最终用户连接通过 Microsoft 全球网络的分布式服务前端基础结构动态路由到最近的 Microsoft 365 入口点，然后通过Microsoft 超低延迟高可用性光纤将流量内部路由到数据和服务终结点。</span><span class="sxs-lookup"><span data-stu-id="cda83-157">End user connections are dynamically routed to the nearest Microsoft 365 entry point by the Microsoft Global Network's _Distributed Service Front Door_ infrastructure, and traffic is then routed internally to data and service endpoints over Microsoft's ultra-low latency high availability fiber.</span></span>
- <span data-ttu-id="cda83-158">通过允许流量的本地出口、绕过代理和流量检查设备Microsoft 365公司网络基础结构上的负载。</span><span class="sxs-lookup"><span data-stu-id="cda83-158">Reduces the load on corporate network infrastructure by allowing local egress for Microsoft 365 traffic, bypassing proxies and traffic inspection devices.</span></span>
- <span data-ttu-id="cda83-159">利用客户端终结点安全性和云安全功能保护两端连接，避免应用冗余网络安全技术。</span><span class="sxs-lookup"><span data-stu-id="cda83-159">Secures connections on both ends by leveraging client endpoint security and cloud security features, avoiding application of redundant network security technologies.</span></span>

> [!NOTE]
> <span data-ttu-id="cda83-160">分布式 _服务前端_ 基础结构是 Microsoft 全球网络高度可用且可扩展的网络边缘，具有地理位置分散的位置。</span><span class="sxs-lookup"><span data-stu-id="cda83-160">The _Distributed Service Front Door_ infrastructure is the Microsoft Global Network's highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="cda83-161">它将终止最终用户连接，并有效地在 Microsoft 全球网络中路由这些连接。</span><span class="sxs-lookup"><span data-stu-id="cda83-161">It terminates end user connections and efficiently routes them within the Microsoft Global Network.</span></span> <span data-ttu-id="cda83-162">有关 Microsoft 全球网络的详细信息，请参阅 [Microsoft 构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)。</span><span class="sxs-lookup"><span data-stu-id="cda83-162">You can learn more about the Microsoft Global Network at [How Microsoft builds its fast and reliable global network](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).</span></span>

<span data-ttu-id="cda83-163">有关了解和应用网络连接Microsoft 365，请参阅Microsoft 365[网络连接原则](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="cda83-163">For more information on understanding and applying Microsoft 365 network connectivity principles, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="conclusion"></a><span data-ttu-id="cda83-164">结束语</span><span class="sxs-lookup"><span data-stu-id="cda83-164">Conclusion</span></span>

<span data-ttu-id="cda83-165">优化Microsoft 365性能实际上要消除不必要的障碍。</span><span class="sxs-lookup"><span data-stu-id="cda83-165">Optimizing Microsoft 365 network performance really comes down to removing unnecessary impediments.</span></span> <span data-ttu-id="cda83-166">通过将Microsoft 365视为受信任的流量，可以防止数据包检查引入延迟并竞争代理带宽。</span><span class="sxs-lookup"><span data-stu-id="cda83-166">By treating Microsoft 365 connections as trusted traffic, you can prevent latency from being introduced by packet inspection and competition for proxy bandwidth.</span></span> <span data-ttu-id="cda83-167">允许客户端计算机和 Office 365 终结点之间的本地连接允许流量通过 Microsoft 全球网络动态路由。</span><span class="sxs-lookup"><span data-stu-id="cda83-167">Allowing local connections between client machines and Office 365 endpoints enables traffic to be dynamically routed through the Microsoft Global Network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cda83-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="cda83-168">Related Topics</span></span>

[<span data-ttu-id="cda83-169">Microsoft 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="cda83-169">Microsoft 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="cda83-170">管理 Office 365 终结点</span><span class="sxs-lookup"><span data-stu-id="cda83-170">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="cda83-171">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="cda83-171">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="cda83-172">Office 365 IP 地址和 URL Web 服务</span><span class="sxs-lookup"><span data-stu-id="cda83-172">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="cda83-173">评估 Microsoft 365 网络连接</span><span class="sxs-lookup"><span data-stu-id="cda83-173">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="cda83-174">Microsoft 365 网络计划和性能优化</span><span class="sxs-lookup"><span data-stu-id="cda83-174">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="cda83-175">使用基线和性能历史记录优化 Office 365 性能</span><span class="sxs-lookup"><span data-stu-id="cda83-175">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="cda83-176">Office 365 性能疑难解答计划</span><span class="sxs-lookup"><span data-stu-id="cda83-176">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="cda83-177">内容分发网络</span><span class="sxs-lookup"><span data-stu-id="cda83-177">Content Delivery Networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="cda83-178">Microsoft 365 连接测试</span><span class="sxs-lookup"><span data-stu-id="cda83-178">Microsoft 365 connectivity test</span></span>](https://aka.ms/netonboard)

[<span data-ttu-id="cda83-179">Microsoft 如何构建其快速可靠的全球网络</span><span class="sxs-lookup"><span data-stu-id="cda83-179">How Microsoft builds its fast and reliable global network</span></span>](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[<span data-ttu-id="cda83-180">Office 365 网络工作博客</span><span class="sxs-lookup"><span data-stu-id="cda83-180">Office 365 Networking blog</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)