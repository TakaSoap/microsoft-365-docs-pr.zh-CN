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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 网络基础结构，以及公司如何使用其 SD WAN 技术实现最佳网络性能到 Microsoft 365 for enterprise 云服务。
ms.openlocfilehash: ca673e6dcbf0f3db4bde33d388598e5f4ffac914
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637183"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="695aa-103">Contoso Corporation 网络</span><span class="sxs-lookup"><span data-stu-id="695aa-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="695aa-p101">为了采用云包容的基础结构，Contoso 为云服务的网络通信的传播方式设计了一个根本性的转变。除了将网络连接和通信集中在 office 层次结构的下一级的内部中心辐射型模型中，它们还将用户位置映射到 internet 上最近的 Microsoft 365 网络位置的本地 internet 出口和本地连接。</span><span class="sxs-lookup"><span data-stu-id="695aa-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="695aa-106">网络基础结构</span><span class="sxs-lookup"><span data-stu-id="695aa-106">Networking infrastructure</span></span>

<span data-ttu-id="695aa-107">以下是链接到全球各地的 Contoso 办事处的网络元素：</span><span class="sxs-lookup"><span data-stu-id="695aa-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="695aa-108">多协议标签交换 (MPLS) WAN 网络</span><span class="sxs-lookup"><span data-stu-id="695aa-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="695aa-p102">MPLS WAN 网络将巴黎总部和区域办事处连接到分支和集线器配置中的卫星办公室。网络使用户能够访问在巴黎总部中组成业务线应用程序的本地服务器。它还会将任何常规 internet 流量路由到巴黎办事处，网络安全设备将擦除请求。在每个办公室中，路由器会将流量传递给有线主机或子网上的无线访问点，这将使用专用 IP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="695aa-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="695aa-113">Microsoft 365 流量的本地直接 internet 访问</span><span class="sxs-lookup"><span data-stu-id="695aa-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="695aa-p103">每个 office 都有一个软件定义的 WAN (SD WAN) 设备，该设备具有一个或多个本地 internet ISP 网络电路，通过代理服务器拥有自己的 internet 连接。这通常作为指向本地 ISP 的 WAN 链接实现，同时也提供公用 IP 地址和本地 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="695aa-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="695aa-116">Internet 网站</span><span class="sxs-lookup"><span data-stu-id="695aa-116">Internet presence</span></span>

  <span data-ttu-id="695aa-p104">Contoso 拥有 contoso \. com 公共域名称。Contoso 公共网站订购产品是在巴黎校园中连接到 internet 的数据中心中的一组服务器。Contoso 在 internet 上使用 a/24 公用 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="695aa-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="695aa-120">图1显示 Contoso 网络基础结构及其与 internet 的连接。</span><span class="sxs-lookup"><span data-stu-id="695aa-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Contoso 网络](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="695aa-122">**图1： Contoso 网络**</span><span class="sxs-lookup"><span data-stu-id="695aa-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="695aa-123">使用 SD-WAN 与 Microsoft 建立最佳网络连接</span><span class="sxs-lookup"><span data-stu-id="695aa-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="695aa-124">Contoso 遵循了 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)：</span><span class="sxs-lookup"><span data-stu-id="695aa-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="695aa-125">标识并区分 Microsoft 365 网络流量</span><span class="sxs-lookup"><span data-stu-id="695aa-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="695aa-126">实现本地连接出口</span><span class="sxs-lookup"><span data-stu-id="695aa-126">Egress network connections locally</span></span>
- <span data-ttu-id="695aa-127">避免网络发卡</span><span class="sxs-lookup"><span data-stu-id="695aa-127">Avoid network hairpins</span></span>
- <span data-ttu-id="695aa-128">绕过重复的网络安全设备</span><span class="sxs-lookup"><span data-stu-id="695aa-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="695aa-129">Microsoft 365 的网络流量有三种类别： " *优化*"、" *允许*" 和 " *默认*"。</span><span class="sxs-lookup"><span data-stu-id="695aa-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="695aa-130">优化和允许流量是在终结点进行加密和保护的受信任网络流量，它是面向 Microsoft 365 网络的。</span><span class="sxs-lookup"><span data-stu-id="695aa-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="695aa-131">Contoso 决定：</span><span class="sxs-lookup"><span data-stu-id="695aa-131">Contoso decided to:</span></span>

- <span data-ttu-id="695aa-132">使用直接 internet 出口以优化和允许类别流量，并将所有默认类别流量转发到基于巴黎的中央 internet 连接。</span><span class="sxs-lookup"><span data-stu-id="695aa-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="695aa-133">在每个办公室上部署 SD WAN 设备，以一种简单的方式来遵循这些原则，并实现 Microsoft 365 基于云的服务的最佳网络性能。</span><span class="sxs-lookup"><span data-stu-id="695aa-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="695aa-134">SD-WAN 设备具有一个用于本地办事处网络的 LAN 端口和多个 WAN 端口。</span><span class="sxs-lookup"><span data-stu-id="695aa-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="695aa-135">一个 WAN 端口连接到其 MPLS 网络。</span><span class="sxs-lookup"><span data-stu-id="695aa-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="695aa-136">另一个连接到本地 ISP 电路。</span><span class="sxs-lookup"><span data-stu-id="695aa-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="695aa-137">SD-WAN 设备通过 ISP 链接路由“优化”和“允许”类别的网络流量。</span><span class="sxs-lookup"><span data-stu-id="695aa-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="695aa-138">Contoso 业务线应用程序基础结构</span><span class="sxs-lookup"><span data-stu-id="695aa-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="695aa-139">Contoso 为以下各项构建业务线应用程序和服务器 intranet 基础结构：</span><span class="sxs-lookup"><span data-stu-id="695aa-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="695aa-140">附属办事处使用本地缓存服务器来存储经常访问的文档和内部网站。</span><span class="sxs-lookup"><span data-stu-id="695aa-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="695aa-p107">地区中心对地区办事处和附属办事处使用地区应用程序服务器。这些服务器与巴黎总部的服务器同步。</span><span class="sxs-lookup"><span data-stu-id="695aa-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="695aa-143">巴黎校园数据中心包含为整个组织提供服务的集中式应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="695aa-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="695aa-144">图2显示了跨 Contoso intranet 访问服务器时使用的网络流量容量百分比。</span><span class="sxs-lookup"><span data-stu-id="695aa-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![适用于内部应用程序的 Contoso 基础结构](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="695aa-146">**图2：适用于内部应用程序的 Contoso 基础结构**</span><span class="sxs-lookup"><span data-stu-id="695aa-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="695aa-147">对于附属或区域中心办公室，可以通过卫星和区域中心办公室服务器来处理员工所需的60% 的资源。</span><span class="sxs-lookup"><span data-stu-id="695aa-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="695aa-148">额外的40% 的资源请求必须通过 WAN 链接进入巴黎校园。</span><span class="sxs-lookup"><span data-stu-id="695aa-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="695aa-149">适用于企业的 Microsoft 365 的网络分析和准备工作</span><span class="sxs-lookup"><span data-stu-id="695aa-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="695aa-150">Contoso 用户成功采用了适用于企业服务的 Microsoft 365，这取决于与 internet 的高可用性和高性能连接，或直接连接到 Microsoft 云服务。</span><span class="sxs-lookup"><span data-stu-id="695aa-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="695aa-151">Contoso 采取以下步骤来规划和实施针对企业云服务的 Microsoft 365 的优化连接：</span><span class="sxs-lookup"><span data-stu-id="695aa-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="695aa-152">创建公司 WAN 网络图以协助规划</span><span class="sxs-lookup"><span data-stu-id="695aa-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="695aa-153">为了启动其网络规划，Contoso 创建了一个显示其办公室位置、现有网络连接、现有网络外围设备以及在网络上进行管理的服务类别的图表。</span><span class="sxs-lookup"><span data-stu-id="695aa-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="695aa-154">他们在规划和实现网络连接的每个后续步骤中使用此图。</span><span class="sxs-lookup"><span data-stu-id="695aa-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="695aa-155">为适用于企业网络连接的 Microsoft 365 创建计划</span><span class="sxs-lookup"><span data-stu-id="695aa-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="695aa-156">Contoso 使用 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md) 和示例参考网络体系结构，将 SD WAN 标识为 Microsoft 365 连接的首选拓扑。</span><span class="sxs-lookup"><span data-stu-id="695aa-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="695aa-157">在每个办公室分析 internet 连接利用率和 MPLS-WAN 带宽，并根据需要增加带宽</span><span class="sxs-lookup"><span data-stu-id="695aa-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="695aa-158">分析了每个 office 的当前使用情况，并增加了电路，以便预测的 Microsoft 365 基于云的流量将使用平均20% 的未使用容量。</span><span class="sxs-lookup"><span data-stu-id="695aa-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="695aa-159">优化 Microsoft 网络服务的性能</span><span class="sxs-lookup"><span data-stu-id="695aa-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="695aa-160">Contoso 确定了 Office 365、Intune 和 Azure 终结点集以及 internet 路径中配置的防火墙、安全设备和其他系统，以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="695aa-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="695aa-161">Office 365 的终结点优化并允许类别流量配置为 SD-WAN 设备，以通过 ISP 电路进行路由。</span><span class="sxs-lookup"><span data-stu-id="695aa-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="695aa-162">配置内部 DNS</span><span class="sxs-lookup"><span data-stu-id="695aa-162">Configure internal DNS</span></span>

   <span data-ttu-id="695aa-163">DNS 必须能正常运行，才能查找本地 Microsoft 365 流量。</span><span class="sxs-lookup"><span data-stu-id="695aa-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="695aa-164">验证网络终结点和端口连接性</span><span class="sxs-lookup"><span data-stu-id="695aa-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="695aa-165">Contoso 已运行 Microsoft 网络连接测试工具，以验证适用于企业云服务的 Microsoft 365 的连接。</span><span class="sxs-lookup"><span data-stu-id="695aa-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="695aa-166">优化员工计算机以实现网络连接</span><span class="sxs-lookup"><span data-stu-id="695aa-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="695aa-167">检查了单个计算机以确保安装了最新的操作系统更新，并且所有客户端上的终结点安全监视处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="695aa-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="695aa-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="695aa-168">Next step</span></span>

<span data-ttu-id="695aa-169">[了解](contoso-identity.md) Contoso 如何利用云中面向员工的本地 Active Directory 域服务 (AD DS)，以及如何利用面向客户和业务合作伙伴的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="695aa-169">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="695aa-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="695aa-170">See also</span></span>

[<span data-ttu-id="695aa-171">Microsoft 365 的网络路线图</span><span class="sxs-lookup"><span data-stu-id="695aa-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="695aa-172">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="695aa-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="695aa-173">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="695aa-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
