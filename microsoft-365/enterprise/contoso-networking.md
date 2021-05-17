---
title: Contoso Corporation 网络
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 网络基础结构，以及该公司如何使用 SD-WAN 技术实现最佳网络性能，Microsoft 365企业云服务。
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754010"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="08bac-103">Contoso Corporation 网络</span><span class="sxs-lookup"><span data-stu-id="08bac-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="08bac-104">为了采用包含云的基础结构，Contoso 对网络流量到云服务的传输方式进行根本转变。</span><span class="sxs-lookup"><span data-stu-id="08bac-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="08bac-105">它们将用户位置映射到本地 Internet 出口，将本地连接映射到 Internet 上最近的 Microsoft 365 网络位置，而不是专注于下一级别办公室层次结构的网络连接和流量的内部中心分支模型。</span><span class="sxs-lookup"><span data-stu-id="08bac-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="08bac-106">网络基础结构</span><span class="sxs-lookup"><span data-stu-id="08bac-106">Networking infrastructure</span></span>

<span data-ttu-id="08bac-107">这些网络元素将全球的 Contoso 办事处链接在一起：</span><span class="sxs-lookup"><span data-stu-id="08bac-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="08bac-108">多协议标签交换 (MPLS) WAN 网络</span><span class="sxs-lookup"><span data-stu-id="08bac-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="08bac-109">MPLS WAN 网络以分支中心配置将巴黎总部连接到区域办事处，将区域办事处连接到分支办事处。</span><span class="sxs-lookup"><span data-stu-id="08bac-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="08bac-110">网络使用户能够访问内部部署服务器，这些服务器是巴黎总部的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="08bac-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="08bac-111">它还将任何一般 Internet 流量路由到巴黎办事处，网络安全设备将清理请求。</span><span class="sxs-lookup"><span data-stu-id="08bac-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="08bac-112">在每个办公室中，路由器将流量路由到使用专用 IP 地址空间的子网上的有线主机或无线接入点。</span><span class="sxs-lookup"><span data-stu-id="08bac-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="08bac-113">本地直接 Internet 访问Microsoft 365流量</span><span class="sxs-lookup"><span data-stu-id="08bac-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="08bac-114">每个办事处都有一个软件定义的 WAN (SD-WAN) 设备，该设备具有一个或多个本地 Internet ISP 网络线路，通过代理服务器有自己的 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="08bac-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="08bac-115">这通常实现为指向同时提供公共 IP 地址和本地 DNS 服务器的本地 ISP 的 WAN 链接。</span><span class="sxs-lookup"><span data-stu-id="08bac-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="08bac-116">Internet 网站</span><span class="sxs-lookup"><span data-stu-id="08bac-116">Internet presence</span></span>

  <span data-ttu-id="08bac-117">Contoso 拥有 contoso \. com 公共域名。</span><span class="sxs-lookup"><span data-stu-id="08bac-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="08bac-118">用于订购产品的 Contoso 公共网站是巴黎园区中连接 Internet 的数据中心中的一组服务器。</span><span class="sxs-lookup"><span data-stu-id="08bac-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="08bac-119">Contoso 在 Internet 上使用 /24 公用 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="08bac-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="08bac-120">图 1 显示了 Contoso 网络基础结构及其与 Internet 的连接。</span><span class="sxs-lookup"><span data-stu-id="08bac-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Contoso 网络](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="08bac-122">**图 1：Contoso 网络**</span><span class="sxs-lookup"><span data-stu-id="08bac-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="08bac-123">使用 SD-WAN 与 Microsoft 建立最佳网络连接</span><span class="sxs-lookup"><span data-stu-id="08bac-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="08bac-124">Contoso 遵循了 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)：</span><span class="sxs-lookup"><span data-stu-id="08bac-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="08bac-125">标识并区分 Microsoft 365 网络流量</span><span class="sxs-lookup"><span data-stu-id="08bac-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="08bac-126">实现本地连接出口</span><span class="sxs-lookup"><span data-stu-id="08bac-126">Egress network connections locally</span></span>
- <span data-ttu-id="08bac-127">避免网络发卡</span><span class="sxs-lookup"><span data-stu-id="08bac-127">Avoid network hairpins</span></span>
- <span data-ttu-id="08bac-128">绕过重复的网络安全设备</span><span class="sxs-lookup"><span data-stu-id="08bac-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="08bac-129">有三种类别的网络通信 *Microsoft 365："优化\*\*"、"允许*"和"*默认"。*</span><span class="sxs-lookup"><span data-stu-id="08bac-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="08bac-130">"优化"和"允许"流量是受信任的网络流量，这些流量在终结点上经过加密和安全保护，并发往Microsoft 365网络。</span><span class="sxs-lookup"><span data-stu-id="08bac-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="08bac-131">Contoso 决定：</span><span class="sxs-lookup"><span data-stu-id="08bac-131">Contoso decided to:</span></span>

- <span data-ttu-id="08bac-132">对"优化"和"允许"类别流量使用直接 Internet 出口，将所有"默认"类别流量转发到巴黎的中央 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="08bac-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="08bac-133">在每个办公室部署 SD-WAN 设备是遵循这些原则并实现基于云的服务的最佳网络Microsoft 365一种简单方法。</span><span class="sxs-lookup"><span data-stu-id="08bac-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="08bac-134">SD-WAN 设备具有一个用于本地办事处网络的 LAN 端口和多个 WAN 端口。</span><span class="sxs-lookup"><span data-stu-id="08bac-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="08bac-135">一个 WAN 端口连接到其 MPLS 网络。</span><span class="sxs-lookup"><span data-stu-id="08bac-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="08bac-136">另一个连接到本地 ISP 线路。</span><span class="sxs-lookup"><span data-stu-id="08bac-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="08bac-137">SD-WAN 设备通过 ISP 链接路由“优化”和“允许”类别的网络流量。</span><span class="sxs-lookup"><span data-stu-id="08bac-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="08bac-138">Contoso 业务线应用基础结构</span><span class="sxs-lookup"><span data-stu-id="08bac-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="08bac-139">Contoso 针对以下内容构建了业务线应用程序和服务器 Intranet 基础结构：</span><span class="sxs-lookup"><span data-stu-id="08bac-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="08bac-140">附属办事处使用本地缓存服务器来存储经常访问的文档和内部网站。</span><span class="sxs-lookup"><span data-stu-id="08bac-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="08bac-p107">地区中心对地区办事处和附属办事处使用地区应用程序服务器。这些服务器与巴黎总部的服务器同步。</span><span class="sxs-lookup"><span data-stu-id="08bac-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="08bac-143">巴黎园区数据中心包含为整个组织服务的集中式应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="08bac-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="08bac-144">图 2 显示通过 Contoso Intranet 访问服务器时所使用的网络流量容量百分比。</span><span class="sxs-lookup"><span data-stu-id="08bac-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![内部应用程序的 Contoso 基础结构](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="08bac-146">**图 2：内部应用程序的 Contoso 基础结构**</span><span class="sxs-lookup"><span data-stu-id="08bac-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="08bac-147">对于附属办事处或区域中心办事处，员工所需的 60% 的资源都可以由附属办事处和区域中心办事处服务器提供。</span><span class="sxs-lookup"><span data-stu-id="08bac-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="08bac-148">其他 40% 的资源请求必须通过 WAN 链接转到巴黎园区。</span><span class="sxs-lookup"><span data-stu-id="08bac-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="08bac-149">企业版网络分析和Microsoft 365准备</span><span class="sxs-lookup"><span data-stu-id="08bac-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="08bac-150">Contoso Microsoft 365企业服务的成功采用取决于与 Internet 或直接到 Microsoft 云服务的高可用性和高效连接。</span><span class="sxs-lookup"><span data-stu-id="08bac-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="08bac-151">Contoso 执行以下步骤来计划和实现与企业云服务Microsoft 365优化的连接：</span><span class="sxs-lookup"><span data-stu-id="08bac-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="08bac-152">创建公司 WAN 网络图，帮助进行规划</span><span class="sxs-lookup"><span data-stu-id="08bac-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="08bac-153">为了开始网络规划，Contoso 创建了一个图表，显示其办公室位置、现有网络连接、现有网络外围设备以及网络上托管的服务类别。</span><span class="sxs-lookup"><span data-stu-id="08bac-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="08bac-154">他们在规划和实现网络连接的每个后续步骤中都使用了此图。</span><span class="sxs-lookup"><span data-stu-id="08bac-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="08bac-155">创建企业网络连接Microsoft 365规划</span><span class="sxs-lookup"><span data-stu-id="08bac-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="08bac-156">Contoso 使用[](microsoft-365-network-connectivity-principles.md)Microsoft 365准则和示例参考网络体系结构，将 SD-WAN 标识为其首选拓扑，Microsoft 365连接。</span><span class="sxs-lookup"><span data-stu-id="08bac-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="08bac-157">分析每个办事处的 Internet 连接利用率和 MPLS-WAN 带宽，并根据需要增加带宽</span><span class="sxs-lookup"><span data-stu-id="08bac-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="08bac-158">分析每个办事处的当前使用情况，并增加线路，以便预测Microsoft 365流量的平均未使用容量为 20%。</span><span class="sxs-lookup"><span data-stu-id="08bac-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="08bac-159">优化 Microsoft 网络服务的性能</span><span class="sxs-lookup"><span data-stu-id="08bac-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="08bac-160">Contoso 确定了一组 Office 365、Intune 和 Azure 终结点，并配置了 Internet 路径中的防火墙、安全设备和其他系统以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="08bac-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="08bac-161">"优化Office 365允许"类别流量的终结点已配置为 SD-WAN 设备，以便通过 ISP 电路进行路由。</span><span class="sxs-lookup"><span data-stu-id="08bac-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="08bac-162">配置内部 DNS</span><span class="sxs-lookup"><span data-stu-id="08bac-162">Configure internal DNS</span></span>

   <span data-ttu-id="08bac-163">DNS 必须能正常运行，才能查找本地 Microsoft 365 流量。</span><span class="sxs-lookup"><span data-stu-id="08bac-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="08bac-164">验证网络终结点和端口连接</span><span class="sxs-lookup"><span data-stu-id="08bac-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="08bac-165">Contoso 运行 Microsoft 网络连接测试工具，以验证企业云服务Microsoft 365连接性。</span><span class="sxs-lookup"><span data-stu-id="08bac-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="08bac-166">优化员工计算机以建立网络连接</span><span class="sxs-lookup"><span data-stu-id="08bac-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="08bac-167">检查了各个计算机以确保已安装最新的操作系统更新，并且终结点安全监视在所有客户端上处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="08bac-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="08bac-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="08bac-168">Next step</span></span>

<span data-ttu-id="08bac-169">了解 Contoso 如何利用云中的本地 [Active Directory 域](contoso-identity.md) 服务为员工和联合身份验证客户和业务合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="08bac-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="08bac-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08bac-170">See also</span></span>

[<span data-ttu-id="08bac-171">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08bac-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="08bac-172">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="08bac-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="08bac-173">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="08bac-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
