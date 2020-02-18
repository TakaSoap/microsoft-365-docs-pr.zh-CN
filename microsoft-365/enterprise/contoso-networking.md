---
title: Contoso Corporation 网络
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 网络基础结构以及如何使用其 SD-WAN 技术为 Microsoft 365 企业版云服务提供最佳网络性能。
ms.openlocfilehash: 20279ac0aed1b7ad86e1fc8e1d78a412230eba52
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068331"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="81454-103">Contoso Corporation 网络</span><span class="sxs-lookup"><span data-stu-id="81454-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="81454-p101">为了采用云包容性基础结构，Contoso 的网络工程师从根本上改变了网络流量流向云服务的方式。他们没有采用内部中心和辐射模型（专注于下一级 Contoso 办事处层次结构的网络连接和流量），而是尽力将用户位置映射到本地 Internet 出口，并将本地连接映射到 Internet 上的最近 Microsoft 365 网络位置。</span><span class="sxs-lookup"><span data-stu-id="81454-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="81454-106">Contoso 网络基础结构</span><span class="sxs-lookup"><span data-stu-id="81454-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="81454-107">关联自己在世界各地办事处的 Contoso 网络包括以下要素：</span><span class="sxs-lookup"><span data-stu-id="81454-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="81454-108">多协议标签交换 (MPLS) WAN 网络</span><span class="sxs-lookup"><span data-stu-id="81454-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="81454-p102">在中心辐射型配置中，MPLS WAN 网络将巴黎总部连接到地区办事处，并将地区办事处连接到附属办事处。这样便于用户访问构成巴黎办事处业务线应用程序的本地服务器。它还会将任何通用 Internet 流量路由到网络安全设备会擦除请求的巴黎办事处。在每个办事处内，路由器将流量路由到子网上的有线主机或无线接入点（使用专用 IP 地址空间）。</span><span class="sxs-lookup"><span data-stu-id="81454-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="81454-113">Microsoft 365 流量的本地直接 Internet 访问</span><span class="sxs-lookup"><span data-stu-id="81454-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="81454-p103">每个办事处都有内含一条或多条本地 Internet ISP 网络线路的软件定义 WAN (SD-WAN) 设备，可通过代理服务器自行连接 Internet。这通常实现为与本地 ISP 的 WAN 链接，本地 ISP 提供公共 IP 地址和本地 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="81454-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="81454-116">Internet 网站</span><span class="sxs-lookup"><span data-stu-id="81454-116">Internet presence</span></span>

  <span data-ttu-id="81454-p104">Contoso 拥有 contoso.com 公共域名。用于订购产品的 Contoso 公共网站是一组服务器，位于巴黎园区中连接到 Internet 的数据中心内。Contoso 在 Internet 上使用 /24 公用 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="81454-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="81454-120">图 1 显示 Contoso 的网络基础结构及其 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="81454-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Contoso 网络](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="81454-122">**图 1：Contoso 网络**</span><span class="sxs-lookup"><span data-stu-id="81454-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="81454-123">使用 SD-WAN 与 Microsoft 建立最佳网络连接</span><span class="sxs-lookup"><span data-stu-id="81454-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="81454-124">Contoso 遵循了 [Office 365 网络连接原则](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)：</span><span class="sxs-lookup"><span data-stu-id="81454-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) to:</span></span>

1. <span data-ttu-id="81454-125">标识并区分 Office 365 网络流量</span><span class="sxs-lookup"><span data-stu-id="81454-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="81454-126">实现本地连接出口</span><span class="sxs-lookup"><span data-stu-id="81454-126">Egress network connections locally</span></span>
3. <span data-ttu-id="81454-127">避免网络发卡</span><span class="sxs-lookup"><span data-stu-id="81454-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="81454-128">绕过重复的网络安全设备</span><span class="sxs-lookup"><span data-stu-id="81454-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="81454-129">Office 365 的网络流量分为三个类别：优化、允许和默认。</span><span class="sxs-lookup"><span data-stu-id="81454-129">There are three categories of network traffic for Office 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="81454-130">“优化”流量和“允许”流量是受信任的网络流量，其在终结点上加密并得到保护，并发送到 Microsoft 365 网络。</span><span class="sxs-lookup"><span data-stu-id="81454-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="81454-131">Contoso 决定：</span><span class="sxs-lookup"><span data-stu-id="81454-131">Contoso decided to:</span></span>

- <span data-ttu-id="81454-132">对“优化”和“允许”类别流量使用直接 Internet 出口，并将所有“默认”类别流量转发到巴黎总部的中央 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="81454-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="81454-133">在每个办事处位置都部署 SD-WAN 设备，以轻松遵循这些原则，并实现 Microsoft 365 基于云的服务的最佳网络性能。</span><span class="sxs-lookup"><span data-stu-id="81454-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="81454-134">SD-WAN 设备具有一个用于本地办事处网络的 LAN 端口和多个 WAN 端口。</span><span class="sxs-lookup"><span data-stu-id="81454-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="81454-135">一个 WAN 端口连接到其 MPLS 网络，另一个 WAN 端口连接到本地 ISP 线路。</span><span class="sxs-lookup"><span data-stu-id="81454-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="81454-136">SD-WAN 设备通过 ISP 链接路由“优化”和“允许”类别的网络流量。</span><span class="sxs-lookup"><span data-stu-id="81454-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="81454-137">Contoso 业务线应用程序基础结构</span><span class="sxs-lookup"><span data-stu-id="81454-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="81454-138">Contoso 针对以下方案构建了业务线应用程序和服务器 Intranet 基础结构：</span><span class="sxs-lookup"><span data-stu-id="81454-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="81454-139">附属办事处使用本地缓存服务器来存储经常访问的文档和内部网站。</span><span class="sxs-lookup"><span data-stu-id="81454-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="81454-p107">地区中心对地区办事处和附属办事处使用地区应用程序服务器。这些服务器与巴黎总部的服务器同步。</span><span class="sxs-lookup"><span data-stu-id="81454-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="81454-142">巴黎园区的数据中心包含为整个组织提供服务的集中式应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="81454-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="81454-143">图 2 展示了跨 Contoso Intranet 访问服务器时的网络流量百分比。</span><span class="sxs-lookup"><span data-stu-id="81454-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Contoso 内部应用程序的基础结构](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="81454-145">**图 2：Contoso 内部应用程序的基础结构**</span><span class="sxs-lookup"><span data-stu-id="81454-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="81454-p108">对于分支办事处或区域中心办事处的用户，员工所需资源的 60% 可由分支办事处和区域中心办事处服务器提供。其他 40% 的资源请求则必须通过 WAN 链接到巴黎园区。</span><span class="sxs-lookup"><span data-stu-id="81454-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="81454-148">Contoso 分析并准备网络以连接到 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="81454-148">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="81454-p109">Contoso 用户能否成功采用 Microsoft 365 企业版服务，取决于与 Internet 或直接与 Microsoft 云服务建立高度可用的高性能连接。Contoso 采取了下面这些步骤，以计划并实现与 Microsoft 365 企业版云服务的优化连接：</span><span class="sxs-lookup"><span data-stu-id="81454-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="81454-151">绘制了公司 WAN 网络图来协助计划</span><span class="sxs-lookup"><span data-stu-id="81454-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="81454-p110">Contoso 首先执行了网络计划，具体是绘制了显示办事处位置、现有网络连接、现有网络外围设备和网络上托管的各类服务的网络图。他们在计划和实现网络连接过程中的每个后续步骤都参考了此图。</span><span class="sxs-lookup"><span data-stu-id="81454-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="81454-154">制定了 Microsoft 365 企业版网络连接计划</span><span class="sxs-lookup"><span data-stu-id="81454-154">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="81454-155">Contoso 根据 [Office 365 网络连接原则](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)，提供了参考网络体系结构，将 SD-WAN 确定为 Office 365 连接的首选拓扑。</span><span class="sxs-lookup"><span data-stu-id="81454-155">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD-WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="81454-156">分析了每个办事处的 Internet 连接利用率和 MPLS WAN 带宽，并根据需要增加了带宽</span><span class="sxs-lookup"><span data-stu-id="81454-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="81454-157">Contoso 分析了每个办事处的当前使用情况，并增加了线路，以便预测 Microsoft 365 基于云的流量平均有 20% 未用容量。</span><span class="sxs-lookup"><span data-stu-id="81454-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="81454-158">优化了 Microsoft 网络服务性能</span><span class="sxs-lookup"><span data-stu-id="81454-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="81454-159">Contoso 确定了 Office 365、Intune 和 Azure 终结点的集合，并在 Internet 路径中配置了防火墙、安全设备和其他系统，以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="81454-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="81454-160">Office 365“优化”和“允许”类别流量的终结点已配置到 SD-WAN 设备，以便通过 ISP 线路进行路由。</span><span class="sxs-lookup"><span data-stu-id="81454-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="81454-161">配置了内部 DNS</span><span class="sxs-lookup"><span data-stu-id="81454-161">Configured internal DNS</span></span>

   <span data-ttu-id="81454-162">DNS 必须能正常运行，才能查找本地 Office 365 流量。</span><span class="sxs-lookup"><span data-stu-id="81454-162">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="81454-163">验证了网络终结点和端口连接</span><span class="sxs-lookup"><span data-stu-id="81454-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="81454-164">Contoso 运行了 Microsoft 提供的网络连接测试工具，以验证 Microsoft 365 企业版云服务的连接性。</span><span class="sxs-lookup"><span data-stu-id="81454-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="81454-165">优化了员工计算机的网络连接</span><span class="sxs-lookup"><span data-stu-id="81454-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="81454-166">Contoso 检查了个人计算机，以确保最新操作系统更新已安装，且终结点安全监视在所有客户端上都有效。</span><span class="sxs-lookup"><span data-stu-id="81454-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="81454-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="81454-167">Next step</span></span>

<span data-ttu-id="81454-168">[了解](contoso-identity.md) Contoso 如何利用云中面向员工的本地 Active Directory 域服务 (AD DS)，以及如何利用面向客户和业务合作伙伴的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="81454-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="81454-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81454-169">See also</span></span>

[<span data-ttu-id="81454-170">Microsoft 365 企业版网络</span><span class="sxs-lookup"><span data-stu-id="81454-170">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="81454-171">部署指南</span><span class="sxs-lookup"><span data-stu-id="81454-171">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="81454-172">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="81454-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
