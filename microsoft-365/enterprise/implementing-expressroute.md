---
title: 实现适用于 Office 365 的 ExpressRoute
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: 了解如何实现 ExpressRoute for Office 365，这将提供许多面向 Internet 的 Office 365 路径。
ms.openlocfilehash: d75fe3a6dab4926babeef61fc14894566ff819b0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051362"
---
# <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="e1263-103">实现适用于 Office 365 的 ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="e1263-103">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="e1263-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="e1263-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e1263-105">ExpressRoute for Office 365 提供了一个指向许多面向 Internet 的 Office 365 路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-105">ExpressRoute for Office 365 provides an alternate routing path to many internet facing Office 365 services.</span></span> <span data-ttu-id="e1263-106">适用于 Office 365 的 ExpressRoute 的体系结构基于将已可通过 Internet 访问的 Office 365 服务的公共 IP 前缀公布到已预配的 ExpressRoute 电路中，以后续重新分发到网络中。</span><span class="sxs-lookup"><span data-stu-id="e1263-106">The architecture of ExpressRoute for Office 365 is based on advertising public IP prefixes of Office 365 services that are already accessible over the Internet into your provisioned ExpressRoute circuits for subsequent redistribution of those IP prefixes into your network.</span></span> <span data-ttu-id="e1263-107">使用 ExpressRoute，您可以有效地启用多个不同的路由路径，通过 Internet 和 ExpressRoute 为许多 Office 365服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-107">With ExpressRoute you effectively enable several different routing paths, through the internet and through ExpressRoute, for many Office 365 services.</span></span> <span data-ttu-id="e1263-108">网络上路由的这种状态可能会显著改变内部网络拓扑的设计方法。</span><span class="sxs-lookup"><span data-stu-id="e1263-108">This state of routing on your network may represent a significant change to how your internal network topology is designed.</span></span>
  
 <span data-ttu-id="e1263-109">**状态：** 完整指南 v2</span><span class="sxs-lookup"><span data-stu-id="e1263-109">**Status:** Complete Guide v2</span></span>
  
<span data-ttu-id="e1263-110">必须仔细规划 ExpressRoute Office 365实现，以适应网络复杂性，即通过专用电路（路由注入核心网络和 Internet）提供路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-110">You must carefully plan your ExpressRoute for Office 365 implementation to accommodate for the network complexities of having routing available via both a dedicated circuit with routes injected into your core network and the internet.</span></span> <span data-ttu-id="e1263-111">如果你和团队不执行本指南中的详细规划和测试，则当启用 ExpressRoute 电路时，你可能会遇到间歇性或完全中断与 Office 365 服务的连接的高风险。</span><span class="sxs-lookup"><span data-stu-id="e1263-111">If you and your team don't perform the detailed planning and testing in this guide, there is a high risk you'll experience intermittent or a total loss of connectivity to Office 365 services when the ExpressRoute circuit is enabled.</span></span>
  
<span data-ttu-id="e1263-112">若要成功实施，你需要分析基础结构要求，完成详细的网络评估和设计，以分步和受控的方式仔细规划部署，并构建详细的验证和测试计划。</span><span class="sxs-lookup"><span data-stu-id="e1263-112">To have a successful implementation, you will need to analyze your infrastructure requirements, go through detailed network assessment and design, carefully plan the rollout in a staged and controlled manner, and build a detailed validation and testing plan.</span></span> <span data-ttu-id="e1263-113">对于大型的分布式环境，实现跨越几个月的情况很常见。</span><span class="sxs-lookup"><span data-stu-id="e1263-113">For a large, distributed environment it's not uncommon to see implementations span several months.</span></span> <span data-ttu-id="e1263-114">本指南旨在帮助你提前规划。</span><span class="sxs-lookup"><span data-stu-id="e1263-114">This guide is designed to help you plan ahead.</span></span>
  
<span data-ttu-id="e1263-115">大型成功部署可能需要六个月的规划时间，并且通常包括组织中多个领域的团队成员，包括网络、防火墙和代理服务器管理员、Office 365 管理员、安全、最终用户支持、项目管理和管理层支持。</span><span class="sxs-lookup"><span data-stu-id="e1263-115">Large successful deployments may take six months in planning and often include team members from many areas in the organization including networking, Firewall and Proxy server administrators, Office 365 administrators, security, end-user support, project management, and executive sponsorship.</span></span> <span data-ttu-id="e1263-116">对规划过程的投资将降低您遇到部署失败导致停机或复杂且成本高昂的故障排除的可能性。</span><span class="sxs-lookup"><span data-stu-id="e1263-116">Your investment in the planning process will reduce the likelihood that you'll experience deployment failures resulting in downtime or complex and expensive troubleshooting.</span></span>
  
<span data-ttu-id="e1263-117">我们希望在本指南启动之前完成以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1263-117">We expect the following pre-requisites to be completed before this implementation guide is started.</span></span>
  
1. <span data-ttu-id="e1263-118">你已完成网络评估，以确定是否推荐并批准 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="e1263-118">You've completed a network assessment to determine if ExpressRoute is recommended and approved.</span></span>

2. <span data-ttu-id="e1263-119">你已选择 ExpressRoute 网络服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e1263-119">You've selected an ExpressRoute network service provider.</span></span> <span data-ttu-id="e1263-120">查找有关 [ExpressRoute 合作伙伴和对等位置的详细信息](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="e1263-120">Find details about the [ExpressRoute partners and peering locations](/azure/expressroute/expressroute-locations).</span></span>

3. <span data-ttu-id="e1263-121">你已阅读并了解 [ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) 文档，并且你的内部网络能够端到端满足 ExpressRoute 先决条件。</span><span class="sxs-lookup"><span data-stu-id="e1263-121">You've already read and understand the [ExpressRoute documentation](https://azure.microsoft.com/documentation/services/expressroute/) and your internal network is able to meet ExpressRoute pre-requisites end to end.</span></span>

4. <span data-ttu-id="e1263-122">团队已阅读 、 的所有公共指南和文档，并观看第 9 频道上的 [https://aka.ms/expressrouteoffice365](./azure-expressroute.md) [https://aka.ms/ert](https://aka.ms/ert) Azure [ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer)系列，了解关键技术详细信息，包括：</span><span class="sxs-lookup"><span data-stu-id="e1263-122">Your team has read all of the public guidance and documentation at [https://aka.ms/expressrouteoffice365](./azure-expressroute.md), [https://aka.ms/ert](https://aka.ms/ert), and watched the [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to gain an understanding of critical technical details including:</span></span>

      - <span data-ttu-id="e1263-123">SaaS 服务的 Internet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="e1263-123">The internet dependencies of SaaS services.</span></span>

      - <span data-ttu-id="e1263-124">如何避免非对称路由和处理复杂的路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-124">How to avoid asymmetric routes and handle complex routing.</span></span>

      - <span data-ttu-id="e1263-125">如何合并外围安全、可用性和应用程序级别控件。</span><span class="sxs-lookup"><span data-stu-id="e1263-125">How to incorporate perimeter security, availability, and application level controls.</span></span>

## <a name="begin-by-gathering-requirements"></a><span data-ttu-id="e1263-126">首先收集要求</span><span class="sxs-lookup"><span data-stu-id="e1263-126">Begin by gathering requirements</span></span>
<span data-ttu-id="e1263-127"><a name="requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-127"><a name="requirements"> </a></span></span>

<span data-ttu-id="e1263-128">首先确定计划在你的组织中采用哪些功能和服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-128">Start by determining which features and services you plan to adopt within your organization.</span></span> <span data-ttu-id="e1263-129">您需要确定将使用不同的 Office 365服务的功能，以及网络上哪些位置将承载使用这些功能的人。</span><span class="sxs-lookup"><span data-stu-id="e1263-129">You need to determine which features of the different Office 365 services will be used and which locations on your network will host people using those features.</span></span> <span data-ttu-id="e1263-130">使用方案目录，需要添加其中每个方案所需的网络属性;例如入站和出站网络流量，以及Office 365终结点是否通过 ExpressRoute 提供。</span><span class="sxs-lookup"><span data-stu-id="e1263-130">With the catalog of scenarios, you need to add the network attributes that each of those scenarios require; such as inbound and outbound network traffic flows and if the Office 365 endpoints are available over ExpressRoute or not.</span></span>
  
<span data-ttu-id="e1263-131">收集组织的要求：</span><span class="sxs-lookup"><span data-stu-id="e1263-131">To gather your organization's requirements:</span></span>
  
- <span data-ttu-id="e1263-132">为组织使用的服务编录入站Office 365出站网络流量。</span><span class="sxs-lookup"><span data-stu-id="e1263-132">Catalog the inbound and outbound network traffic for the Office 365 services your organization is using.</span></span> <span data-ttu-id="e1263-133">请参阅Office 365 URL 和 IP 地址范围页面，查看不同方案Office 365流的说明。</span><span class="sxs-lookup"><span data-stu-id="e1263-133">Consult Office 365 URLs and IP address ranges page for the description of flows that different Office 365 scenarios require.</span></span>

- <span data-ttu-id="e1263-134">收集现有网络拓扑的文档，其中显示内部 WAN 主干和拓扑、附属站点连接、最后一英里用户连接、网络外围出口点路由和代理服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1263-134">Gather documentation of existing network topology showing details of your internal WAN backbone and topology, connectivity of satellite sites, last mile user connectivity, routing to network perimeter egress points, and proxy services.</span></span>

  - <span data-ttu-id="e1263-135">标识要连接到的网络图上的入站服务Office 365和其他Microsoft 服务，同时显示 Internet 和建议的 ExpressRoute 连接路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-135">Identify inbound service endpoints on the network diagrams that Office 365 and other Microsoft services will connect to, showing both internet and proposed ExpressRoute connection paths.</span></span>

  - <span data-ttu-id="e1263-136">确定位置之间的所有地理用户位置和 WAN 连接，以及当前具有 Internet 出口的位置以及建议哪些位置具有 ExpressRoute 对等位置的出口。</span><span class="sxs-lookup"><span data-stu-id="e1263-136">Identify all geographic user locations and WAN connectivity between locations along with which locations currently have an egress to the internet and which locations are proposed to have an egress to an ExpressRoute peering location.</span></span>

  - <span data-ttu-id="e1263-137">标识所有边缘设备（如代理、防火墙等）并编录它们的关系以通过 Internet 和 ExpressRoute 流动。</span><span class="sxs-lookup"><span data-stu-id="e1263-137">Identify all edge devices, such as proxies, firewalls, and so on and catalog their relationship to flows going over the Internet and ExpressRoute.</span></span>

  - <span data-ttu-id="e1263-138">记录最终用户是否将Office 365 Internet 和 ExpressRoute 流的直接路由或间接应用程序代理访问服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-138">Document whether end users will access Office 365 services via direct routing or indirect application proxy for both Internet and ExpressRoute flows.</span></span>

- <span data-ttu-id="e1263-139">将租户的位置和"会议"位置添加到网络图。</span><span class="sxs-lookup"><span data-stu-id="e1263-139">Add the location of your tenant and meet-me locations to your network diagram.</span></span>

- <span data-ttu-id="e1263-140">估计从主要用户位置到其他用户位置的预期和观察到的网络Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1263-140">Estimate the expected and observed network performance and latency characteristics from major user locations to Office 365.</span></span> <span data-ttu-id="e1263-141">请记住，Office 365是一组全局和分布式服务，用户将连接到可能不同于其租户位置的位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-141">Keep in mind that Office 365 is a global and distributed set of services and users will be connecting to locations that may be different from the location of their tenant.</span></span> <span data-ttu-id="e1263-142">因此，建议通过 ExpressRoute 和 Internet 连接测量和优化用户与 Microsoft 全球网络的最近边缘之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="e1263-142">For this reason, it is recommended to measure and optimize for latency between the user and the closest edge of Microsoft global network over ExpressRoute and Internet connections.</span></span> <span data-ttu-id="e1263-143">可以使用网络评估中的结果帮助完成此任务。</span><span class="sxs-lookup"><span data-stu-id="e1263-143">You can use your findings from the network assessment to aid with this task.</span></span>

- <span data-ttu-id="e1263-144">列出新 ExpressRoute 连接需要满足的公司网络安全和高可用性要求。</span><span class="sxs-lookup"><span data-stu-id="e1263-144">List company network security and high availability requirements that need to be met with the new ExpressRoute connection.</span></span> <span data-ttu-id="e1263-145">例如，在 Internet 出口或 ExpressRoute 电路故障Office 365，用户如何继续获得对连接的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e1263-145">For example, how do users continue to get access to Office 365 in the event of the Internet egress or ExpressRoute circuit failure.</span></span>

- <span data-ttu-id="e1263-146">记录哪些入站和出Office 365网络流将使用 Internet 路径，哪些将使用 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="e1263-146">Document which inbound and outbound Office 365 network flows will use the Internet path and which will use ExpressRoute.</span></span> <span data-ttu-id="e1263-147">用户地理位置的具体信息以及本地网络拓扑的详细信息可能要求计划不同于不同用户位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-147">The specifics of geographical locations of your users and details of your on-premises network topology may require the plan to be different from one user location to another.</span></span>

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a><span data-ttu-id="e1263-148">编录出站和入站网络流量</span><span class="sxs-lookup"><span data-stu-id="e1263-148">Catalog your outbound and inbound network traffic</span></span>
<span data-ttu-id="e1263-149"><a name="trafficCatalog"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-149"><a name="trafficCatalog"> </a></span></span>

<span data-ttu-id="e1263-150">为了最大程度地降低路由和其他网络复杂性，我们建议你仅对因法规要求或由于网络评估结果而需要通过专用连接的网络通信流使用适用于 Office 365 的 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="e1263-150">To minimize routing and other network complexities, we recommend that you only use ExpressRoute for Office 365 for the network traffic flows that are required to go over a dedicated connection due to regulatory requirements or as the result of the network assessment.</span></span> <span data-ttu-id="e1263-151">此外，建议将 ExpressRoute 路由的范围进行阶段化，将出站和入站网络流量作为实施项目的不同且不同的阶段流动。</span><span class="sxs-lookup"><span data-stu-id="e1263-151">Additionally, we recommend that you stage the scope of ExpressRoute routing and approach outbound and inbound network traffic flows as different and distinct stages of the implementation project.</span></span> <span data-ttu-id="e1263-152">部署 ExpressRoute for Office 365 仅针对用户启动的出站网络流量，并保留入站网络流量通过 Internet，可以帮助控制引入其他非对称路由可能性的拓扑复杂性和风险增加。</span><span class="sxs-lookup"><span data-stu-id="e1263-152">Deploy ExpressRoute for Office 365 for just user initiated outbound network traffic flows and leave inbound network traffic flows across the Internet can help to control the increase in topological complexity and risks of introducing additional asymmetric routing possibilities.</span></span>
  
<span data-ttu-id="e1263-153">网络流量目录应包含本地网络和 Microsoft 之间所有入站和出站网络连接列表。</span><span class="sxs-lookup"><span data-stu-id="e1263-153">Your network traffic catalog should contain listings of all the inbound and outbound network connections that you'll have between your on-premises network and Microsoft.</span></span>
  
- <span data-ttu-id="e1263-154">出站网络流量流是任何从本地环境启动连接（如从内部客户端或服务器启动连接，目标为 Microsoft 服务）。</span><span class="sxs-lookup"><span data-stu-id="e1263-154">Outbound network traffic flows are any scenarios where a connection is initiated from your on-premises environment, such as from internal clients or servers, with a destination of the Microsoft services.</span></span> <span data-ttu-id="e1263-155">这些连接可能直接Office 365间接连接，例如当连接通过代理服务器、防火墙或其他网络设备连接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1263-155">These connections may be direct to Office 365 or indirect, such as when the connection goes through proxy servers, firewalls, or other networking devices on the path to Office 365.</span></span>

- <span data-ttu-id="e1263-156">入站网络流量是任何从 Microsoft 云启动到本地主机的连接的方案。</span><span class="sxs-lookup"><span data-stu-id="e1263-156">Inbound network traffic flows are any scenarios where a connection is initiated from the Microsoft cloud to an on-premises host.</span></span> <span data-ttu-id="e1263-157">这些连接通常需要通过防火墙和客户安全策略为外部来源的流所需的其他安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="e1263-157">These connections typically need to go through firewall and other security infrastructure that customer security policy requires for externally originated flows.</span></span>

<span data-ttu-id="e1263-158">阅读文章Routing [with ExpressRoute for Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)中的确保路由对称部分，以确定将发送入站通信的服务，并查找 Office 365 终结点参考文章中标记为 **ExpressRoute for** [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)的列，以确定连接信息的其余部分。</span><span class="sxs-lookup"><span data-stu-id="e1263-158">Read the **Ensuring route symmetry** section of the article [Routing with ExpressRoute for Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) to determine which services will send inbound traffic and look for the column marked **ExpressRoute for Office 365** in the [Office 365 endpoints](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) reference article to determine the rest of the connectivity information.</span></span>
  
<span data-ttu-id="e1263-159">对于需要出站连接的每个服务，您需要描述服务的计划连接，包括网络路由、代理配置、数据包检查和带宽需求。</span><span class="sxs-lookup"><span data-stu-id="e1263-159">For each service that requires an outbound connection, you'll want to describe the planned connectivity for the service including network routing, proxy configuration, packet inspection, and bandwidth needs.</span></span>
  
<span data-ttu-id="e1263-160">对于需要入站连接的每项服务，你将需要一些其他信息。</span><span class="sxs-lookup"><span data-stu-id="e1263-160">For each service that requires an inbound connection, you'll need some additional information.</span></span> <span data-ttu-id="e1263-161">Microsoft 云中的服务器将建立与本地网络的连接。</span><span class="sxs-lookup"><span data-stu-id="e1263-161">Servers in the Microsoft cloud will establish connections to your on-premises network.</span></span> <span data-ttu-id="e1263-162">为了确保正确建立连接，您需要描述此连接的各个方面，包括;接受这些入站连接的服务的公用 DNS 条目、CIDR 格式的 IPv4 IP 地址、涉及的 ISP 设备，以及如何处理这些连接的入站 NAT 或源 NAT。</span><span class="sxs-lookup"><span data-stu-id="e1263-162">to ensure the connections are made correctly, you'll want to describe all aspects of this connectivity, including; the public DNS entries for the services that will accept these inbound connections, the CIDR formatted IPv4 IP addresses, which ISP equipment is involved, and how inbound NAT or source NAT is handled for these connections.</span></span>
  
<span data-ttu-id="e1263-163">应检查入站连接，而不管它们是否通过 Internet 或 ExpressRoute 进行连接，以确保尚未引入非对称路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-163">Inbound connections should be reviewed regardless of whether they're connecting over the internet or ExpressRoute to ensure asymmetric routing hasn't been introduced.</span></span> <span data-ttu-id="e1263-164">在某些情况下，允许服务启动入站Office 365本地终结点可能还需要由其他 Microsoft 和非 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-164">In some cases, on-premises endpoints that Office 365 services initiate inbound connections to may also need to be accessed by other Microsoft and non-Microsoft services.</span></span> <span data-ttu-id="e1263-165">出于其他目的启用 ExpressRoute 路由到这些服务Office 365不会中断其他方案，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="e1263-165">It is paramount that enabling ExpressRoute routing to these services for Office 365 purposes doesn't break other scenarios.</span></span> <span data-ttu-id="e1263-166">在许多情况下，客户可能需要对内部网络（如基于源的 NAT）进行特定更改，以确保来自 Microsoft 的入站流在启用 ExpressRoute 后保持对称。</span><span class="sxs-lookup"><span data-stu-id="e1263-166">In many cases, customers may need to implement specific changes to their internal network, such as source based NAT, to ensure that inbound flows from Microsoft remain symmetric after ExpressRoute is enabled.</span></span>
  
<span data-ttu-id="e1263-167">下面是所需详细级别的示例。</span><span class="sxs-lookup"><span data-stu-id="e1263-167">Here's a sample of the level of detail required.</span></span> <span data-ttu-id="e1263-168">在这种情况下，Exchange混合会通过 ExpressRoute 路由到本地系统。</span><span class="sxs-lookup"><span data-stu-id="e1263-168">In this case Exchange Hybrid would route to the on-premises system over ExpressRoute.</span></span>

|<span data-ttu-id="e1263-169">**Connection 属性**</span><span class="sxs-lookup"><span data-stu-id="e1263-169">**Connection property**</span></span>|<span data-ttu-id="e1263-170">**值**</span><span class="sxs-lookup"><span data-stu-id="e1263-170">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1263-171">**网络流量方向**</span><span class="sxs-lookup"><span data-stu-id="e1263-171">**Network traffic direction**</span></span> <br/> |<span data-ttu-id="e1263-172">入站</span><span class="sxs-lookup"><span data-stu-id="e1263-172">Inbound</span></span>  <br/> |
|<span data-ttu-id="e1263-173">**服务**</span><span class="sxs-lookup"><span data-stu-id="e1263-173">**Service**</span></span> <br/> |<span data-ttu-id="e1263-174">Exchange 混合</span><span class="sxs-lookup"><span data-stu-id="e1263-174">Exchange Hybrid</span></span>  <br/> |
|<span data-ttu-id="e1263-175">**公共Office 365终结点 (源)**</span><span class="sxs-lookup"><span data-stu-id="e1263-175">**Public Office 365 endpoint (source)**</span></span> <br/> |<span data-ttu-id="e1263-176">Exchange Online (IP 地址) </span><span class="sxs-lookup"><span data-stu-id="e1263-176">Exchange Online (IP addresses)</span></span>  <br/> |
|<span data-ttu-id="e1263-177">**公共本地终结点 (目标)**</span><span class="sxs-lookup"><span data-stu-id="e1263-177">**Public On-Premises Endpoint (destination)**</span></span> <br/> |<span data-ttu-id="e1263-178">5.5.5.5</span><span class="sxs-lookup"><span data-stu-id="e1263-178">5.5.5.5</span></span>  <br/> |
|<span data-ttu-id="e1263-179">**公用 (Internet) DNS 条目**</span><span class="sxs-lookup"><span data-stu-id="e1263-179">**Public (Internet) DNS entry**</span></span> <br/> |<span data-ttu-id="e1263-180">Autodiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e1263-180">Autodiscover.contoso.com</span></span>  <br/> |
|<span data-ttu-id="e1263-181">**此本地终结点将供其他非 (使用Office 365) Microsoft 服务**</span><span class="sxs-lookup"><span data-stu-id="e1263-181">**Will this on-premises endpoint be used for by other (non-Office 365) Microsoft services**</span></span> <br/> |<span data-ttu-id="e1263-182">否</span><span class="sxs-lookup"><span data-stu-id="e1263-182">No</span></span>  <br/> |
|<span data-ttu-id="e1263-183">**Internet 上的用户/系统会使用此本地终结点吗**</span><span class="sxs-lookup"><span data-stu-id="e1263-183">**Will this on-premises endpoint be used by users/systems on the Internet**</span></span> <br/> |<span data-ttu-id="e1263-184">是</span><span class="sxs-lookup"><span data-stu-id="e1263-184">Yes</span></span>  <br/> |
|<span data-ttu-id="e1263-185">**通过公共终结点发布的内部系统**</span><span class="sxs-lookup"><span data-stu-id="e1263-185">**Internal systems published through public endpoints**</span></span> <br/> |<span data-ttu-id="e1263-186">Exchange Server客户端访问角色 (本地) 192.168.101、192.168.102、192.168.103</span><span class="sxs-lookup"><span data-stu-id="e1263-186">Exchange Server client access role (on-premises) 192.168.101, 192.168.102, 192.168.103</span></span>  <br/> |
|<span data-ttu-id="e1263-187">**公共终结点的 IP 播发**</span><span class="sxs-lookup"><span data-stu-id="e1263-187">**IP advertisement of the public endpoint**</span></span> <br/> |<span data-ttu-id="e1263-188">**到 Internet**：5.5.0.0/16</span><span class="sxs-lookup"><span data-stu-id="e1263-188">**To Internet**: 5.5.0.0/16</span></span>  <br/> <span data-ttu-id="e1263-189">**To ExpressRoute**： 5.5.5.0/24</span><span class="sxs-lookup"><span data-stu-id="e1263-189">**To ExpressRoute**: 5.5.5.0/24</span></span>  <br/> |
|<span data-ttu-id="e1263-190">**安全/外围控件**</span><span class="sxs-lookup"><span data-stu-id="e1263-190">**Security/Perimeter Controls**</span></span> <br/> |<span data-ttu-id="e1263-191">**Internet 路径**： DeviceID_002</span><span class="sxs-lookup"><span data-stu-id="e1263-191">**Internet path**: DeviceID_002</span></span>  <br/> <span data-ttu-id="e1263-192">**ExpressRoute 路径**： DeviceID_003</span><span class="sxs-lookup"><span data-stu-id="e1263-192">**ExpressRoute path**: DeviceID_003</span></span>  <br/> |
|<span data-ttu-id="e1263-193">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="e1263-193">**High Availability**</span></span> <br/> |<span data-ttu-id="e1263-194">跨 2 个地理位置冗余的活动/活动</span><span class="sxs-lookup"><span data-stu-id="e1263-194">Active/Active across 2 geo-redundant</span></span>  <br/> <span data-ttu-id="e1263-195">ExpressRoute 电路 - 芝加哥和 Dallas</span><span class="sxs-lookup"><span data-stu-id="e1263-195">ExpressRoute circuits - Chicago and Dallas</span></span>  <br/> |
|<span data-ttu-id="e1263-196">**路径对称控制**</span><span class="sxs-lookup"><span data-stu-id="e1263-196">**Path symmetry control**</span></span> <br/> |<span data-ttu-id="e1263-197">**方法**：源 NAT</span><span class="sxs-lookup"><span data-stu-id="e1263-197">**Method**: Source NAT</span></span>  <br/> <span data-ttu-id="e1263-198">**Internet 路径**：源 NAT 到 192.168.5.5 的入站连接</span><span class="sxs-lookup"><span data-stu-id="e1263-198">**Internet path**: Source NAT inbound connections to 192.168.5.5</span></span>  <br/> |<span data-ttu-id="e1263-199">**ExpressRoute 路径**：到 Dallas) 192.168.1.0 (和 192.168.2.0 (NAT) </span><span class="sxs-lookup"><span data-stu-id="e1263-199">**ExpressRoute path**: Source NAT connections to 192.168.1.0 (Chicago) and 192.168.2.0 (Dallas)</span></span>  <br/> |

<span data-ttu-id="e1263-200">下面是仅出站服务的示例：</span><span class="sxs-lookup"><span data-stu-id="e1263-200">Here's a sample of a service that is outbound only:</span></span>

|<span data-ttu-id="e1263-201">**Connection 属性**</span><span class="sxs-lookup"><span data-stu-id="e1263-201">**Connection property**</span></span>|<span data-ttu-id="e1263-202">**值**</span><span class="sxs-lookup"><span data-stu-id="e1263-202">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1263-203">**网络流量方向**</span><span class="sxs-lookup"><span data-stu-id="e1263-203">**Network traffic direction**</span></span> <br/> |<span data-ttu-id="e1263-204">出站</span><span class="sxs-lookup"><span data-stu-id="e1263-204">Outbound</span></span>  <br/> |
|<span data-ttu-id="e1263-205">**服务**</span><span class="sxs-lookup"><span data-stu-id="e1263-205">**Service**</span></span> <br/> |<span data-ttu-id="e1263-206">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e1263-206">SharePoint Online</span></span>  <br/> |
|<span data-ttu-id="e1263-207">**内部部署终结点 (源)**</span><span class="sxs-lookup"><span data-stu-id="e1263-207">**On-premises endpoint (source)**</span></span> <br/> |<span data-ttu-id="e1263-208">用户工作站</span><span class="sxs-lookup"><span data-stu-id="e1263-208">User workstation</span></span>  <br/> |
|<span data-ttu-id="e1263-209">**公用Office 365终结点 (目标)**</span><span class="sxs-lookup"><span data-stu-id="e1263-209">**Public Office 365 endpoint (destination)**</span></span> <br/> |<span data-ttu-id="e1263-210">SharePoint联机 (IP 地址) </span><span class="sxs-lookup"><span data-stu-id="e1263-210">SharePoint Online (IP addresses)</span></span>  <br/> |
|<span data-ttu-id="e1263-211">**公用 (Internet) DNS 条目**</span><span class="sxs-lookup"><span data-stu-id="e1263-211">**Public (Internet) DNS entry**</span></span> <br/> |<span data-ttu-id="e1263-212">\*.sharepoint.com (和其他 FQDN) </span><span class="sxs-lookup"><span data-stu-id="e1263-212">\*.sharepoint.com (and additional FQDNs)</span></span>  <br/> |
|<span data-ttu-id="e1263-213">**CDN引荐**</span><span class="sxs-lookup"><span data-stu-id="e1263-213">**CDN Referrals**</span></span> <br/> |<span data-ttu-id="e1263-214">cdn.sharepointonline.com (FQN 和其他 FQDN) - 由服务提供商CDN的 IP) </span><span class="sxs-lookup"><span data-stu-id="e1263-214">cdn.sharepointonline.com (and additional FQDNs) - IP addresses maintained by CDN providers)</span></span>  <br/> |
|<span data-ttu-id="e1263-215">**使用的 IP 播发和 NAT**</span><span class="sxs-lookup"><span data-stu-id="e1263-215">**IP advertisement and NAT in use**</span></span> <br/> |<span data-ttu-id="e1263-216">**Internet 路径/源 NAT**：1.1.1.0/24</span><span class="sxs-lookup"><span data-stu-id="e1263-216">**Internet path/Source NAT**: 1.1.1.0/24</span></span>  <br/> <span data-ttu-id="e1263-217">**ExpressRoute 路径/** 源 NAT：1.1.2.0/24 (芝加哥) 和 1.1.3.0/24 (Dallas) </span><span class="sxs-lookup"><span data-stu-id="e1263-217">**ExpressRoute path/Source NAT**: 1.1.2.0/24 (Chicago) and 1.1.3.0/24 (Dallas)</span></span>  <br/> |
|<span data-ttu-id="e1263-218">**Connectivity 方法**</span><span class="sxs-lookup"><span data-stu-id="e1263-218">**Connectivity method**</span></span> <br/> |<span data-ttu-id="e1263-219">**Internet：** 通过第 7 层代理 (.pac) </span><span class="sxs-lookup"><span data-stu-id="e1263-219">**Internet**: via layer 7 proxy (.pac file)</span></span>  <br/> <span data-ttu-id="e1263-220">**ExpressRoute：** 无代理 (直接路由) </span><span class="sxs-lookup"><span data-stu-id="e1263-220">**ExpressRoute**: direct routing (no proxy)</span></span>  <br/> |
|<span data-ttu-id="e1263-221">**安全/外围控件**</span><span class="sxs-lookup"><span data-stu-id="e1263-221">**Security/Perimeter Controls**</span></span> <br/> |<span data-ttu-id="e1263-222">**Internet 路径**： DeviceID_002</span><span class="sxs-lookup"><span data-stu-id="e1263-222">**Internet path**: DeviceID_002</span></span>  <br/> <span data-ttu-id="e1263-223">**ExpressRoute 路径**： DeviceID_003</span><span class="sxs-lookup"><span data-stu-id="e1263-223">**ExpressRoute path**: DeviceID_003</span></span>  <br/> |
|<span data-ttu-id="e1263-224">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="e1263-224">**High Availability**</span></span> <br/> |<span data-ttu-id="e1263-225">**Internet 路径**：冗余 Internet 出口</span><span class="sxs-lookup"><span data-stu-id="e1263-225">**Internet path**: Redundant internet egress</span></span>  <br/> <span data-ttu-id="e1263-226">**ExpressRoute 路径**：跨 2 个地理位置冗余 ExpressRoute 电路的主动/主动"热槽"路由 - 芝加哥和 Dallas</span><span class="sxs-lookup"><span data-stu-id="e1263-226">**ExpressRoute path**: Active/Active 'hot potato' routing across 2 geo-redundant ExpressRoute circuits - Chicago and Dallas</span></span>  <br/> |
|<span data-ttu-id="e1263-227">**路径对称控制**</span><span class="sxs-lookup"><span data-stu-id="e1263-227">**Path symmetry control**</span></span> <br/> |<span data-ttu-id="e1263-228">**方法**：所有连接的源 NAT</span><span class="sxs-lookup"><span data-stu-id="e1263-228">**Method**: Source NAT for all connections</span></span>  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a><span data-ttu-id="e1263-229">具有区域连接的网络拓扑设计</span><span class="sxs-lookup"><span data-stu-id="e1263-229">Your network topology design with regional connectivity</span></span>
<span data-ttu-id="e1263-230"><a name="topology"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-230"><a name="topology"> </a></span></span>

<span data-ttu-id="e1263-231">了解服务及其关联的网络流量流后，您可以创建一个网络图，该图表包含这些新的连接要求，并说明了使用 ExpressRoute for Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1263-231">Once you understand the services and their associated network traffic flows, you can create a network diagram that incorporates these new connectivity requirements and illustrates the changes you'll make to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="e1263-232">您的图表应包括：</span><span class="sxs-lookup"><span data-stu-id="e1263-232">Your diagram should include:</span></span>
  
1. <span data-ttu-id="e1263-233">将访问Office 365服务的所有用户位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-233">All user locations where Office 365 and other services will be accessed from.</span></span>

2. <span data-ttu-id="e1263-234">所有 Internet 和 ExpressRoute 出口点。</span><span class="sxs-lookup"><span data-stu-id="e1263-234">All internet and ExpressRoute egress points.</span></span>

3. <span data-ttu-id="e1263-235">管理网络内连接的所有出站和入站设备，包括路由器、防火墙、应用程序代理服务器和入侵检测/防护。</span><span class="sxs-lookup"><span data-stu-id="e1263-235">All outbound and inbound devices that manage connectivity in and out of the network, including routers, firewalls, application proxy servers, and intrusion detection/prevention.</span></span>

4. <span data-ttu-id="e1263-236">所有入站流量的内部目标，例如接受来自 ADFS Web 应用程序代理服务器的连接的内部 ADFS 服务器。</span><span class="sxs-lookup"><span data-stu-id="e1263-236">Internal destinations for all inbound traffic, such as internal ADFS servers that accept connections from the ADFS web application proxy servers.</span></span>

5. <span data-ttu-id="e1263-237">将公布的所有 IP 子网的目录</span><span class="sxs-lookup"><span data-stu-id="e1263-237">Catalog of all IP subnets that will be advertised</span></span>

6. <span data-ttu-id="e1263-238">确定用户将访问Office 365的位置，并列出将用于 ExpressRoute 的"会面我"位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-238">Identify each location where people will access Office 365 from and list the meet-me locations that will be used for ExpressRoute.</span></span>

7. <span data-ttu-id="e1263-239">内部网络拓扑的位置和部分，其中将接受、筛选和传播从 ExpressRoute 中学习的 Microsoft IP 前缀。</span><span class="sxs-lookup"><span data-stu-id="e1263-239">Locations and portions of your internal network topology, where Microsoft IP prefixes learned from ExpressRoute will be accepted, filtered and propagated to.</span></span>

8. <span data-ttu-id="e1263-240">网络拓扑应说明每个网段的地理位置，以及它如何通过 ExpressRoute 和/或 Internet 连接到 Microsoft 网络。</span><span class="sxs-lookup"><span data-stu-id="e1263-240">The network topology should illustrate the geographic location of each network segment and how it connects to the Microsoft network over ExpressRoute and/or the Internet.</span></span>

<span data-ttu-id="e1263-241">下图显示了用户将在其中使用 Office 365以及入站和出站路由广告到邮件的每个Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1263-241">The diagram below shows each location where people will be using Office 365 from along with the inbound and outbound routing advertisements to Office 365.</span></span>
  
![ExpressRoute regional geographic meet-me](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
<span data-ttu-id="e1263-243">对于出站流量，人们Office 365以下三种方式之一：</span><span class="sxs-lookup"><span data-stu-id="e1263-243">For outbound traffic, the people access Office 365 in one of three ways:</span></span>
  
1. <span data-ttu-id="e1263-244">通过北美为加利福尼亚人的会面位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-244">Through a meet-me location in North America for the people in California.</span></span>

2. <span data-ttu-id="e1263-245">通过香港与香港居民的会面地点。</span><span class="sxs-lookup"><span data-stu-id="e1263-245">Through a meet-me location in Hong Kong for the people in Hong Kong.</span></span>

3. <span data-ttu-id="e1263-246">通过孟加拉国的 Internet，用户较少且未设置 ExpressRoute 电路。</span><span class="sxs-lookup"><span data-stu-id="e1263-246">Through the internet in Bangladesh where there are fewer people and no ExpressRoute circuit provisioned.</span></span>

![区域图表的出站连接](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
<span data-ttu-id="e1263-248">同样，来自 Office 365的入站网络流量以以下三种方式之一返回：</span><span class="sxs-lookup"><span data-stu-id="e1263-248">Similarly, the inbound network traffic from Office 365 returns in one of three ways:</span></span>
  
1. <span data-ttu-id="e1263-249">通过北美为加利福尼亚人的会面位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-249">Through a meet-me location in North America for the people in California.</span></span>

2. <span data-ttu-id="e1263-250">通过香港与香港居民的会面地点。</span><span class="sxs-lookup"><span data-stu-id="e1263-250">Through a meet-me location in Hong Kong for the people in Hong Kong.</span></span>

3. <span data-ttu-id="e1263-251">通过孟加拉国的 Internet，用户较少且未设置 ExpressRoute 电路。</span><span class="sxs-lookup"><span data-stu-id="e1263-251">Through the internet in Bangladesh where there are fewer people and no ExpressRoute circuit provisioned.</span></span>

![区域图的入站连接](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a><span data-ttu-id="e1263-253">确定适当的会面位置</span><span class="sxs-lookup"><span data-stu-id="e1263-253">Determine the appropriate meet-me location</span></span>

<span data-ttu-id="e1263-254">选择"联系我"位置（即 ExpressRoute 电路将网络连接到 Microsoft 网络的物理位置）受用户从其中访问Office 365影响。</span><span class="sxs-lookup"><span data-stu-id="e1263-254">The selection of meet-me locations, which are the physical location where your ExpressRoute circuit connects your network to the Microsoft network, is influenced by the locations where people will access Office 365 from.</span></span> <span data-ttu-id="e1263-255">作为 SaaS 产品，Office 365在 IaaS 或 PaaS 区域模型下运行的方式与 Azure 不同。</span><span class="sxs-lookup"><span data-stu-id="e1263-255">As a SaaS offering, Office 365 does not operate under the IaaS or PaaS regional model in the same way Azure does.</span></span> <span data-ttu-id="e1263-256">相反，Office 365是一组分布式协作服务，其中用户可能需要跨多个数据中心和地区连接到终结点，这些终结点不一定位于托管用户租户的同一位置或区域。</span><span class="sxs-lookup"><span data-stu-id="e1263-256">Instead, Office 365 is a distributed set of collaboration services, where users may need to connect to endpoints across multiple datacenters and regions, which may not necessarily be in the same location or region where the user's tenant is hosted.</span></span>
  
<span data-ttu-id="e1263-257">这意味着在选择 ExpressRoute for Office 365 的"联系我"位置时，需要考虑的最重要的注意事项是组织中人员将进行连接的位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-257">This means the most important consideration you need to make when selecting meet-me locations for ExpressRoute for Office 365 is where the people in your organization will be connecting from.</span></span> <span data-ttu-id="e1263-258">最佳 Office 365 连接的一般建议是实施路由，以便用户对 Office 365 服务的请求通过最短网络路径提交到 Microsoft 网络中，这通常也称为"热路由"路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-258">The general recommendation for optimal Office 365 connectivity is implement routing, so that user requests to Office 365 services are handed off into the Microsoft network over the shortest network path, this is also often being referred to as 'hot potato' routing.</span></span> <span data-ttu-id="e1263-259">例如，如果大多数 Office 365用户位于一个或两个位置，则选择与这些用户的位置最接近的"会面我"位置将创建最佳设计。</span><span class="sxs-lookup"><span data-stu-id="e1263-259">For example, if most of the Office 365 users are in one or two locations, selecting meet-me locations that are in the closest proximity to the location of those users will create the optimal design.</span></span> <span data-ttu-id="e1263-260">如果您的公司在许多不同区域具有大量用户，您可能需要考虑拥有多个 ExpressRoute 电路和"会面我"位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-260">If your company has large user populations in many different regions, you may want to consider having multiple ExpressRoute circuits and meet-me locations.</span></span> <span data-ttu-id="e1263-261">对于一些用户位置，进入 Microsoft 网络和 Office 365 的最短/最佳路径可能不是通过内部 WAN 和 ExpressRoute 会议点，而是通过 Internet。</span><span class="sxs-lookup"><span data-stu-id="e1263-261">For some of your user locations, the shortest/most optimal path into Microsoft network and Office 365, may not be through your internal WAN and ExpressRoute meet-me points, but via the Internet.</span></span>
  
<span data-ttu-id="e1263-262">通常，可以在与用户相对接近的一个区域内选择多个"我开会"位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-262">Often times, there are multiple meet-me locations that could be selected within a region with relative proximity to your users.</span></span> <span data-ttu-id="e1263-263">填写下表以指导您的决策。</span><span class="sxs-lookup"><span data-stu-id="e1263-263">Fill out the following table to guide your decisions.</span></span>

|<span data-ttu-id="e1263-264">**在加利福尼亚和纽约计划的 ExpressRoute 会面位置**</span><span class="sxs-lookup"><span data-stu-id="e1263-264">**Planned ExpressRoute meet-me locations in California and New York**</span></span>||
|:-----|:-----|
|<span data-ttu-id="e1263-265">位置</span><span class="sxs-lookup"><span data-stu-id="e1263-265">Location</span></span>  <br/> |<span data-ttu-id="e1263-266">人员数</span><span class="sxs-lookup"><span data-stu-id="e1263-266">Number of people</span></span>  <br/> |<span data-ttu-id="e1263-267">Microsoft 网络通过 Internet 出口的预期延迟</span><span class="sxs-lookup"><span data-stu-id="e1263-267">Expected latency to Microsoft network over Internet egress</span></span>  <br/> |<span data-ttu-id="e1263-268">通过 ExpressRoute 对 Microsoft 网络的预期延迟</span><span class="sxs-lookup"><span data-stu-id="e1263-268">Expected latency to Microsoft network over ExpressRoute</span></span>  <br/> |
|<span data-ttu-id="e1263-269">Los Angeles</span><span class="sxs-lookup"><span data-stu-id="e1263-269">Los Angeles</span></span>  <br/> |<span data-ttu-id="e1263-270">10,000</span><span class="sxs-lookup"><span data-stu-id="e1263-270">10,000</span></span>  <br/> |<span data-ttu-id="e1263-271">~15ms</span><span class="sxs-lookup"><span data-stu-id="e1263-271">~15ms</span></span>  <br/> |<span data-ttu-id="e1263-272">大约 10 毫秒 (通过位于) </span><span class="sxs-lookup"><span data-stu-id="e1263-272">~10ms (via Silicon Valley)</span></span>  <br/> |
|<span data-ttu-id="e1263-273">华盛顿州</span><span class="sxs-lookup"><span data-stu-id="e1263-273">Washington DC</span></span>  <br/> |<span data-ttu-id="e1263-274">15,000</span><span class="sxs-lookup"><span data-stu-id="e1263-274">15,000</span></span>  <br/> |<span data-ttu-id="e1263-275">~20 毫秒</span><span class="sxs-lookup"><span data-stu-id="e1263-275">~20ms</span></span>  <br/> |<span data-ttu-id="e1263-276">通过纽约 (大约 10 毫秒) </span><span class="sxs-lookup"><span data-stu-id="e1263-276">~10ms (via New York)</span></span>  <br/> |
|<span data-ttu-id="e1263-277">Dallas</span><span class="sxs-lookup"><span data-stu-id="e1263-277">Dallas</span></span>  <br/> |<span data-ttu-id="e1263-278">5,000</span><span class="sxs-lookup"><span data-stu-id="e1263-278">5,000</span></span>  <br/> |<span data-ttu-id="e1263-279">~15ms</span><span class="sxs-lookup"><span data-stu-id="e1263-279">~15ms</span></span>  <br/> |<span data-ttu-id="e1263-280">通过纽约 (大约 40 毫秒) </span><span class="sxs-lookup"><span data-stu-id="e1263-280">~40ms (via New York)</span></span>  <br/> |

<span data-ttu-id="e1263-281">在显示 Office 365 区域、ExpressRoute 网络服务提供商"联系我"位置和按位置显示人员数量的全局网络体系结构之后，它可用于标识能否进行任何优化。</span><span class="sxs-lookup"><span data-stu-id="e1263-281">Once the global network architecture showing the Office 365 region, ExpressRoute network service provider meet-me locations, and the quantity of people by location has been developed, it can be used to identify if any optimizations can be made.</span></span> <span data-ttu-id="e1263-282">它也可能显示全局发夹网络连接，其中流量将路由到较远的位置，以便获取"我开会"位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-282">It may also show global hairpin network connections where traffic routes to a distant location in order to get the meet-me location.</span></span> <span data-ttu-id="e1263-283">如果发现全局网络上有一个发夹，则应该先修正该发夹，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="e1263-283">If a hairpin on the global network is discovered it should be remediated before continuing.</span></span> <span data-ttu-id="e1263-284">查找另一个会议位置，或使用选择性 Internet 出口点来避免发夹。</span><span class="sxs-lookup"><span data-stu-id="e1263-284">Either find another meet-me location, or use selective Internet breakout egress points to avoid the hairpin.</span></span>
  
<span data-ttu-id="e1263-285">第一个图表显示了一个北美具有两个物理位置的客户示例。</span><span class="sxs-lookup"><span data-stu-id="e1263-285">The first diagram, shows an example of a customer with two physical locations in North America.</span></span> <span data-ttu-id="e1263-286">你可以查看有关 Office 位置、Office 365位置的信息，以及 ExpressRoute 会议-我位置的一些选择。</span><span class="sxs-lookup"><span data-stu-id="e1263-286">You can see the information about office locations, Office 365 tenant locations, and several choices for ExpressRoute meet-me locations.</span></span> <span data-ttu-id="e1263-287">在此例中，客户已基于两个原则选择了会议地点，顺序为：</span><span class="sxs-lookup"><span data-stu-id="e1263-287">In this example, the customer has selected the meet-me location based on two principles, in order:</span></span>
  
1. <span data-ttu-id="e1263-288">最接近其组织中人员的位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-288">Closest proximity to the people in their organization.</span></span>

2. <span data-ttu-id="e1263-289">最接近托管主机的 Microsoft 数据中心Office 365位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-289">Closest in proximity to a Microsoft datacenter where Office 365 is hosted.</span></span>

![ExpressRoute 美国地理-我](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
<span data-ttu-id="e1263-291">第二个图稍微进一步扩展了此概念，显示了一个使用类似信息和决策制定的国家/客户面临的示例。</span><span class="sxs-lookup"><span data-stu-id="e1263-291">Expanding this concept slightly further, the second diagram shows an example multi-national customer faced with similar information and decision making.</span></span> <span data-ttu-id="e1263-292">此客户在孟加拉国有一家小型办公室，只有一个十人的小组，专注于扩大他们在地区的业务。</span><span class="sxs-lookup"><span data-stu-id="e1263-292">This customer has a small office in Bangladesh with only a small team of ten people focused on growing their footprint in the region.</span></span> <span data-ttu-id="e1263-293">在金那有一个"会面"位置和一个 Microsoft 数据中心，Office 365在金纳尼托管，因此"会面我"位置有意义;但是，对于十个人来说，附加电路的费用是一项很重的负担。</span><span class="sxs-lookup"><span data-stu-id="e1263-293">There is a meet-me location in Chennai and a Microsoft datacenter with Office 365 hosted in Chennai so a meet-me location would make sense; however, for ten people, the expense of the additional circuit is burdensome.</span></span> <span data-ttu-id="e1263-294">在查看网络时，需要确定跨网络发送网络流量所涉及的延迟是否比花费资金获取另一个 ExpressRoute 电路更有效。</span><span class="sxs-lookup"><span data-stu-id="e1263-294">As you look at your network, you'll need to determine if the latency involved in sending your network traffic across your network is more effective than spending the capital to acquire another ExpressRoute circuit.</span></span>
  
<span data-ttu-id="e1263-295">此外，在孟加拉国的十个人，其网络流量通过 Internet 发送到 Microsoft 网络的性能可能会比他们在内部网络上路由的性能更好，如我们在介绍性图表中介绍并在下面复制所示。</span><span class="sxs-lookup"><span data-stu-id="e1263-295">Alternatively, the ten people in Bangladesh may experience better performance with their network traffic sent over the internet to the Microsoft network than they would routing on their internal network as we showed in the introductory diagrams and reproduced below.</span></span>
  
![区域图表的出站连接](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a><span data-ttu-id="e1263-297">创建 ExpressRoute for Office 365实施计划</span><span class="sxs-lookup"><span data-stu-id="e1263-297">Create your ExpressRoute for Office 365 implementation plan</span></span>
<span data-ttu-id="e1263-298"><a name="implementation"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-298"><a name="implementation"> </a></span></span>

<span data-ttu-id="e1263-299">实现计划应包含配置 ExpressRoute 的技术详细信息，以及网络上配置所有其他基础结构的详细信息，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e1263-299">Your implementation plan should encompass both the technical details of configuring ExpressRoute as well as the details of configuring all the other infrastructure on your network, such as the following.</span></span>
  
- <span data-ttu-id="e1263-300">规划在 ExpressRoute 和 Internet 之间拆分哪些服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-300">Plan which services split between ExpressRoute and Internet.</span></span>

- <span data-ttu-id="e1263-301">规划带宽、安全性、高可用性和故障转移。</span><span class="sxs-lookup"><span data-stu-id="e1263-301">Plan for bandwidth, security, high availability and failover.</span></span>

- <span data-ttu-id="e1263-302">设计入站和出站路由，包括针对不同位置的正确路由路径优化</span><span class="sxs-lookup"><span data-stu-id="e1263-302">Design inbound and outbound routing, including proper routing path optimizations for different locations</span></span>

- <span data-ttu-id="e1263-303">确定 ExpressRoute 路由将在你的网络中播发多远，以及客户端选择 Internet 或 ExpressRoute 路径的机制是什么;例如，直接路由或应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="e1263-303">Decide how far ExpressRoute routes will be advertised into your network and what is the mechanism for clients to select Internet or ExpressRoute path; for example, direct routing or application proxy.</span></span>

- <span data-ttu-id="e1263-304">规划 DNS 记录更改，包括 [发件人策略框架](../security/defender-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md) 条目。</span><span class="sxs-lookup"><span data-stu-id="e1263-304">Plan DNS record changes, including [Sender Policy Framework](../security/defender-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md) entries.</span></span>

- <span data-ttu-id="e1263-305">规划 NAT 策略，包括出站和入站源 NAT。</span><span class="sxs-lookup"><span data-stu-id="e1263-305">Plan NAT strategy including outbound and inbound source NAT.</span></span>

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a><span data-ttu-id="e1263-306">使用 Internet 和 ExpressRoute 网络路径规划路由</span><span class="sxs-lookup"><span data-stu-id="e1263-306">Plan your routing with both internet and ExpressRoute network paths</span></span>
<span data-ttu-id="e1263-307"><a name="paths"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-307"><a name="paths"> </a></span></span>

- <span data-ttu-id="e1263-308">对于初始部署，建议使用 Internet 使用所有入站服务，如入站电子邮件或混合连接。</span><span class="sxs-lookup"><span data-stu-id="e1263-308">For your initial deployment, all inbound services, such as inbound email or hybrid connectivity, are recommended to use the internet.</span></span>

- <span data-ttu-id="e1263-309">规划最终用户客户端 LAN 路由，例如配置 [PAC/WPAD](./managing-office-365-endpoints.md)文件、默认路由、代理服务器和 BGP 路由广告。</span><span class="sxs-lookup"><span data-stu-id="e1263-309">Plan end user client LAN routing, such as [configuring a PAC/WPAD file](./managing-office-365-endpoints.md), default route, proxy servers, and BGP route advertisements.</span></span>

- <span data-ttu-id="e1263-310">规划外围路由，包括代理服务器、防火墙和云代理。</span><span class="sxs-lookup"><span data-stu-id="e1263-310">Plan perimeter routing, including proxy servers, firewalls, and cloud proxies.</span></span>

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a><span data-ttu-id="e1263-311">规划带宽、安全性、高可用性和故障转移</span><span class="sxs-lookup"><span data-stu-id="e1263-311">Plan your bandwidth, security, high availability and failover</span></span>
<span data-ttu-id="e1263-312"><a name="availability"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-312"><a name="availability"> </a></span></span>

<span data-ttu-id="e1263-313">创建每个主要工作负荷所需的带宽Office 365计划。</span><span class="sxs-lookup"><span data-stu-id="e1263-313">Create a plan for bandwidth required for each major Office 365 workload.</span></span> <span data-ttu-id="e1263-314">单独估计Exchange Online、SharePoint Online 和 Skype for Business Online 带宽要求。</span><span class="sxs-lookup"><span data-stu-id="e1263-314">Separately estimate Exchange Online, SharePoint Online, and Skype for Business Online bandwidth requirements.</span></span> <span data-ttu-id="e1263-315">你可以将我们提供的估算计算器用于Exchange Online Skype for Business和估计计算器;但是，需要具有用户配置文件和位置的代表性示例的试点测试才能完全了解组织的带宽需求。</span><span class="sxs-lookup"><span data-stu-id="e1263-315">You can use the estimation calculators we've provided for Exchange Online and Skype for Business as a starting place; however, a pilot test with a representative sample of the user profiles and locations is required to fully understand the bandwidth needs of your organization.</span></span>
  
<span data-ttu-id="e1263-316">将每个 Internet 和 ExpressRoute 出口位置的安全性处理方式添加到计划中，请记住与 Office 365 的所有 ExpressRoute 连接都使用公共对等，并且仍必须按照连接到外部网络的公司的安全策略进行保护。</span><span class="sxs-lookup"><span data-stu-id="e1263-316">Add how security is handled at each internet and ExpressRoute egress location to your plan, remember all ExpressRoute connections to Office 365 use public peering and must still be secured in accordance with your company security policies of connecting to external networks.</span></span>
  
<span data-ttu-id="e1263-317">将有关哪些人员受哪种类型的中断的影响以及这些人员如何以最简单的方式以最大能力执行他们的工作的详细信息添加到您的计划中。</span><span class="sxs-lookup"><span data-stu-id="e1263-317">Add details to your plan about which people will be affected by what type of outage and how those people will be able to perform their work at full capacity in the simplest manner.</span></span>
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a><span data-ttu-id="e1263-318">规划带宽要求，Skype for Business抖动、延迟、拥塞和空位的带宽要求</span><span class="sxs-lookup"><span data-stu-id="e1263-318">Plan bandwidth requirements including Skype for Business requirements on Jitter, Latency, Congestion, and Headroom</span></span>
  
<span data-ttu-id="e1263-319">Skype for BusinessOnline 还有特定的其他网络要求，如 Skype for Business Online 中的媒体质量和网络连接性能[一文所详细介绍](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)。</span><span class="sxs-lookup"><span data-stu-id="e1263-319">Skype for Business Online also has specific additional network requirements which are detailed in the article [Media Quality and Network Connectivity Performance in Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).</span></span>
  
<span data-ttu-id="e1263-320">阅读 Network [planning with ExpressRoute for Office 365 中的 Azure ExpressRoute 带宽Office 365。](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd) </span><span class="sxs-lookup"><span data-stu-id="e1263-320">Read the section **Bandwidth planning for Azure ExpressRoute** in [Network planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).</span></span>
  
<span data-ttu-id="e1263-321">与试点用户执行带宽评估时，可以使用我们的指南;[Office 365基线和性能历史记录来优化性能](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)。</span><span class="sxs-lookup"><span data-stu-id="e1263-321">When performing a bandwidth assessment with your pilot users, you can use our guide; [Office 365 performance tuning using baselines and performance history](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).</span></span>
  
#### <a name="plan-for-high-availability-requirements"></a><span data-ttu-id="e1263-322">规划高可用性要求</span><span class="sxs-lookup"><span data-stu-id="e1263-322">Plan for high availability requirements</span></span>
  
<span data-ttu-id="e1263-323">创建高可用性计划以满足您的需求，并将其合并到更新的网络拓扑图中。</span><span class="sxs-lookup"><span data-stu-id="e1263-323">Create a plan for high availability to meet your needs and incorporate this into your updated network topology diagram.</span></span> <span data-ttu-id="e1263-324">阅读 Network [planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的 Azure **ExpressRoute** 高可用性和Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1263-324">Read the section **High availability and failover with Azure ExpressRoute** in [Network planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).</span></span>
  
#### <a name="plan-for-network-security-requirements"></a><span data-ttu-id="e1263-325">规划网络安全要求</span><span class="sxs-lookup"><span data-stu-id="e1263-325">Plan for network security requirements</span></span>
  
<span data-ttu-id="e1263-326">创建满足网络安全要求的计划，并将其纳入更新的网络拓扑图。</span><span class="sxs-lookup"><span data-stu-id="e1263-326">Create a plan to meet your network security requirements and incorporate this into your updated network topology diagram.</span></span> <span data-ttu-id="e1263-327">阅读 Network [planning with ExpressRoute for Office 365 for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的将安全控件应用于 Azure **ExpressRoute** 一节。</span><span class="sxs-lookup"><span data-stu-id="e1263-327">Read the section **Applying security controls to Azure ExpressRoute for Office 365 scenarios** in [Network planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).</span></span>
  
### <a name="design-outbound-service-connectivity"></a><span data-ttu-id="e1263-328">设计出站服务连接</span><span class="sxs-lookup"><span data-stu-id="e1263-328">Design outbound service connectivity</span></span>
<span data-ttu-id="e1263-329"><a name="outbound"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-329"><a name="outbound"> </a></span></span>

<span data-ttu-id="e1263-330">ExpressRoute for Office 365具有 *可能不熟悉的* 出站网络要求。</span><span class="sxs-lookup"><span data-stu-id="e1263-330">ExpressRoute for Office 365 has  *outbound*  network requirements that may be unfamiliar.</span></span> <span data-ttu-id="e1263-331">具体而言，表示要连接到的用户和网络Office 365并充当到 Microsoft 的出站网络连接的源终结点的 IP 地址必须遵循下面列出的特定要求。</span><span class="sxs-lookup"><span data-stu-id="e1263-331">Specifically, the IP addresses that represent your users and networks to Office 365 and act as the source endpoints for outbound network connections to Microsoft must follow specific requirements outlined below.</span></span>
  
1. <span data-ttu-id="e1263-332">终结点必须是注册到贵公司或为您提供 ExpressRoute 连接的运营商的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e1263-332">The endpoints must be public IP addresses, that are registered to your company or to carrier providing ExpressRoute connectivity to you.</span></span>

2. <span data-ttu-id="e1263-333">终结点必须公布给 Microsoft，并且由 ExpressRoute 验证/接受。</span><span class="sxs-lookup"><span data-stu-id="e1263-333">The endpoints must be advertised to Microsoft and validated/accepted by ExpressRoute.</span></span>

3. <span data-ttu-id="e1263-334">终结点不得使用相同或更首选的路由指标播发到 Internet。</span><span class="sxs-lookup"><span data-stu-id="e1263-334">The endpoints must not be advertised to the Internet with the same or more preferred routing metric.</span></span>

4. <span data-ttu-id="e1263-335">终结点不能用于连接到未通过 ExpressRoute Microsoft 服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="e1263-335">The endpoints must not be used for connectivity to Microsoft services that are not configured over ExpressRoute.</span></span>

<span data-ttu-id="e1263-336">如果网络设计不满足这些要求，则由于路由黑色全息或非对称路由，你的用户将面临连接到 Office 365 和其他 Microsoft 服务 的高风险。</span><span class="sxs-lookup"><span data-stu-id="e1263-336">If your network design doesn't meet these requirements, there is a high risk your users will experience connectivity failures to Office 365 and other Microsoft services due to route black holing or asymmetric routing.</span></span> <span data-ttu-id="e1263-337">当对 Microsoft 服务 的请求通过 ExpressRoute 路由时，会出现此情况，但响应会通过 Internet 路由回，反之亦然，并且有状态网络设备（如防火墙）会丢弃响应。</span><span class="sxs-lookup"><span data-stu-id="e1263-337">This occurs when requests to Microsoft services are routed over ExpressRoute, but responses are routed back across the internet, or vice versa, and the responses are dropped by stateful network devices such as firewalls.</span></span>
  
<span data-ttu-id="e1263-338">满足上述要求的最常见方法是使用源 NAT，方法是作为网络的一部分实现，或由 ExpressRoute 运营商提供。</span><span class="sxs-lookup"><span data-stu-id="e1263-338">The most common method you can use to meet the above requirements is to use source NAT, either implemented as a part of your network or provided by your ExpressRoute carrier.</span></span> <span data-ttu-id="e1263-339">源 NAT 允许你从 ExpressRoute 和 提取 Internet 网络的详细信息和专用 IP 寻址;与正确的 IP 路由广告结合，提供一种简单的机制来确保路径对称。</span><span class="sxs-lookup"><span data-stu-id="e1263-339">Source NAT allows you to abstract the details and private IP addressing of your internet network from ExpressRoute and; coupled with proper IP route advertisements, provide an easy mechanism to ensure path symmetry.</span></span> <span data-ttu-id="e1263-340">如果你使用的是特定于 ExpressRoute 对等位置的有状态网络设备，则必须针对每个 ExpressRoute 对等实现单独的 NAT 池以确保路径对称。</span><span class="sxs-lookup"><span data-stu-id="e1263-340">If you're using stateful network devices that are specific to ExpressRoute peering locations, you must implement separate NAT pools for each ExpressRoute peering to ensure path symmetry.</span></span>
  
<span data-ttu-id="e1263-341">阅读有关 [ExpressRoute NAT 要求的更多信息](/azure/expressroute/expressroute-nat)。</span><span class="sxs-lookup"><span data-stu-id="e1263-341">Read more about the [ExpressRoute NAT requirements](/azure/expressroute/expressroute-nat).</span></span>
  
<span data-ttu-id="e1263-342">将出站连接更改添加到网络拓扑图。</span><span class="sxs-lookup"><span data-stu-id="e1263-342">Add the changes for the outbound connectivity to the network topology diagram.</span></span>
  
### <a name="design-inbound-service-connectivity"></a><span data-ttu-id="e1263-343">设计入站服务连接</span><span class="sxs-lookup"><span data-stu-id="e1263-343">Design inbound service connectivity</span></span>
<span data-ttu-id="e1263-344"><a name="inbound"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-344"><a name="inbound"> </a></span></span>

<span data-ttu-id="e1263-345">大多数企业 Office 365 部署都假定某种形式的入站连接从 Office 365 到本地服务，例如 Exchange、SharePoint 和 Skype for Business 混合方案、邮箱迁移以及使用 ADFS 基础结构的身份验证。</span><span class="sxs-lookup"><span data-stu-id="e1263-345">The majority of enterprise Office 365 deployments assume some form of inbound connectivity from Office 365 to on-premises services, such as for Exchange, SharePoint, and Skype for Business hybrid scenarios, mailbox migrations, and authentication using ADFS infrastructure.</span></span> <span data-ttu-id="e1263-346">当 ExpressRoute 为出站连接启用本地网络和 Microsoft 之间的其他路由路径时，这些入站连接可能会无意中受到非对称路由的影响，即使打算让这些流继续使用 Internet。</span><span class="sxs-lookup"><span data-stu-id="e1263-346">When ExpressRoute you enable an additional routing path between your on-premises network and Microsoft for outbound connectivity, these inbound connections may inadvertently be impacted by asymmetric routing, even if you intend to have those flows continue to use the Internet.</span></span> <span data-ttu-id="e1263-347">建议采用下面所述的一些预防措施，以确保对从内部部署系统到本地系统的基于 Internet Office 365流没有影响。</span><span class="sxs-lookup"><span data-stu-id="e1263-347">A few precautions described below are recommended to ensure there is no impact to Internet based inbound flows from Office 365 to on-premises systems.</span></span>
  
<span data-ttu-id="e1263-348">为了最大限度地降低入站网络流量流非对称路由的风险，所有入站连接都应在路由到具有 ExpressRoute 路由可见性的网络分段之前，使用源 NAT。</span><span class="sxs-lookup"><span data-stu-id="e1263-348">To minimize the risks of asymmetric routing for inbound network traffic flows, all of the inbound connections should use source NAT before they're routed into segments of your network which have routing visibility into ExpressRoute.</span></span> <span data-ttu-id="e1263-349">如果允许传入连接到达具有路由可见性且没有源 NAT 的 ExpressRoute 的网络段上，来自 Office 365 的请求将从 Internet 进入，但返回到 Office 365 的响应将首选 ExpressRoute 网络路径返回到 Microsoft 网络，从而导致非对称路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-349">If the incoming connections are allowed onto a network segment with routing visibility into ExpressRoute without source NAT, requests originating from Office 365 will enter from the internet, but the response going back to Office 365 will prefer the ExpressRoute network path back to the Microsoft network, causing asymmetric routing.</span></span>
  
<span data-ttu-id="e1263-350">你可以考虑以下实现模式之一来满足此要求：</span><span class="sxs-lookup"><span data-stu-id="e1263-350">You may consider one of the following implementation patterns to satisfy this requirement:</span></span>
  
1. <span data-ttu-id="e1263-351">使用网络设备（如防火墙或负载平衡器）将请求从 Internet 路由到内部部署系统之前，先执行源 NAT。</span><span class="sxs-lookup"><span data-stu-id="e1263-351">Perform source NAT before requests are routed into your internal network using networking equipment such as firewalls or load balancers on the path from the Internet to your on-premises systems.</span></span>

2. <span data-ttu-id="e1263-352">确保 ExpressRoute 路由不会传播到处理 Internet 连接的入站服务（如前端服务器或反向代理系统）所在的网络段。</span><span class="sxs-lookup"><span data-stu-id="e1263-352">Ensure that ExpressRoute routes are not propagated to the network segments where inbound services, such as front end servers or reverse proxy systems, handling Internet connections reside.</span></span>

<span data-ttu-id="e1263-353">明确计算网络中这些方案并保留所有入站网络流量通过 Internet 有助于最大程度地降低非对称路由的部署和操作风险。</span><span class="sxs-lookup"><span data-stu-id="e1263-353">Explicitly accounting for these scenarios in your network and keeping all inbound network traffic flows over the Internet helps to minimize deployment and operational risk of asymmetric routing.</span></span>
  
<span data-ttu-id="e1263-354">在某些情况下，你可以选择通过 ExpressRoute 连接引导某些入站流。</span><span class="sxs-lookup"><span data-stu-id="e1263-354">There may be cases where you may choose to direct some inbound flows over ExpressRoute connections.</span></span> <span data-ttu-id="e1263-355">对于这些方案，应考虑以下其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="e1263-355">For these scenarios, take the following additional considerations into account.</span></span>
  
1. <span data-ttu-id="e1263-356">Office 365只能面向使用公共 IP 的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="e1263-356">Office 365 can only target on-premises endpoints that use public IPs.</span></span> <span data-ttu-id="e1263-357">这意味着，即使内部部署入站终结点仅通过 ExpressRoute Office 365，它仍然需要与公用 IP 关联。</span><span class="sxs-lookup"><span data-stu-id="e1263-357">This means that even if the on-premises inbound endpoint is only exposed to Office 365 over ExpressRoute, it still needs to have public IP associated with it.</span></span>

2. <span data-ttu-id="e1263-358">所有 DNS 名称解析Office 365使用公共 DNS 解析本地终结点。</span><span class="sxs-lookup"><span data-stu-id="e1263-358">All DNS name resolution that Office 365 services perform to resolve on-premises endpoints happen using public DNS.</span></span> <span data-ttu-id="e1263-359">这意味着您必须在 Internet 上注册入站服务终结点的 FQDN 到 IP 的映射。</span><span class="sxs-lookup"><span data-stu-id="e1263-359">This means that you must register inbound service endpoints' FQDN to IP mappings on the Internet.</span></span>

3. <span data-ttu-id="e1263-360">为了通过 ExpressRoute 接收入站网络连接，必须通过 ExpressRoute 向 Microsoft 播发这些终结点的公共 IP 子网。</span><span class="sxs-lookup"><span data-stu-id="e1263-360">In order to receive inbound network connections over ExpressRoute, the public IP subnets for these endpoints must to be advertised to Microsoft over ExpressRoute.</span></span>

4. <span data-ttu-id="e1263-361">仔细评估这些入站网络流量流，以确保根据公司安全和网络策略对它们应用适当的安全和网络控制。</span><span class="sxs-lookup"><span data-stu-id="e1263-361">Carefully evaluate these inbound network traffic flows to ensure that proper security and network controls are applied to them in accordance with your company security and network policies.</span></span>

5. <span data-ttu-id="e1263-362">通过 ExpressRoute 向 Microsoft 公布内部部署入站终结点后，ExpressRoute 将有效地成为所有 Microsoft 服务（包括 Office 365）的这些终结点的首选路由路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-362">Once your on-premises inbound endpoints are advertised to Microsoft over ExpressRoute, ExpressRoute will effectively become the preferred routing path to those endpoints for all Microsoft services, including Office 365.</span></span> <span data-ttu-id="e1263-363">这意味着这些终结点子网只能用于与 Office 365 服务的通信，而不要用于 Microsoft 网络的其他服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-363">This means that those endpoint subnets must only be used for communications with Office 365 services and no other services on the Microsoft network.</span></span> <span data-ttu-id="e1263-364">否则，你的设计将导致非对称路由，其中来自Microsoft 服务的入站连接倾向于通过 ExpressRoute 路由入站，而返回路径将使用 Internet。</span><span class="sxs-lookup"><span data-stu-id="e1263-364">Otherwise, your design will cause asymmetric routing where inbound connections from other Microsoft services prefer to route inbound over ExpressRoute, while the return path will use the Internet.</span></span>

6. <span data-ttu-id="e1263-365">如果 ExpressRoute 电路或会议位置关闭，你将需要确保本地入站终结点仍然可用于接受通过单独网络路径的请求。</span><span class="sxs-lookup"><span data-stu-id="e1263-365">In the event an ExpressRoute circuit or meet-me location is down, you'll need to ensure the on-premises inbound endpoints are still available to accept requests over a separate network path.</span></span> <span data-ttu-id="e1263-366">这可能意味着通过多个 ExpressRoute 电路为这些终结点发布子网。</span><span class="sxs-lookup"><span data-stu-id="e1263-366">This may mean advertising subnets for those endpoints through multiple ExpressRoute circuits.</span></span>

7. <span data-ttu-id="e1263-367">我们建议对通过 ExpressRoute 进入网络的所有入站网络流量应用源 NAT，尤其是在这些流跨有状态网络设备（如防火墙）时。</span><span class="sxs-lookup"><span data-stu-id="e1263-367">We recommend applying source NAT for all inbound network traffic flows entering your network through ExpressRoute, especially when these flows cross stateful network devices such as firewalls.</span></span>

8. <span data-ttu-id="e1263-368">某些本地服务（如 ADFS 代理或 Exchange自动发现）可能同时接收来自 Office 365 服务和 Internet 用户的入站请求。</span><span class="sxs-lookup"><span data-stu-id="e1263-368">Some on-premises services, such as ADFS proxy or Exchange autodiscover, may receive inbound requests from both Office 365 services and users from the Internet.</span></span> <span data-ttu-id="e1263-369">对于这些请求Office 365将面向与用户通过 Internet 请求相同的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e1263-369">For these requests Office 365 will target the same FQDN as user requests over the Internet.</span></span> <span data-ttu-id="e1263-370">允许从 Internet 到这些本地终结点的入站用户连接，同时强制Office 365连接使用 ExpressRoute，这表示路由的复杂性很大。</span><span class="sxs-lookup"><span data-stu-id="e1263-370">Allowing inbound user connections from the internet to those on-premises endpoints, while forcing Office 365 connections to use ExpressRoute, represents significant routing complexity.</span></span> <span data-ttu-id="e1263-371">对于绝大多数客户，出于操作考虑，不建议通过 ExpressRoute 实现此类复杂方案。</span><span class="sxs-lookup"><span data-stu-id="e1263-371">For the vast majority of customers implementing such complex scenarios over ExpressRoute is not recommended due to operational considerations.</span></span> <span data-ttu-id="e1263-372">此额外开销包括管理非对称路由的风险，并且需要你仔细管理跨多个维度的路由广告和策略。</span><span class="sxs-lookup"><span data-stu-id="e1263-372">This additional overhead includes, managing risks of asymmetric routing and will require you to carefully manage routing advertisements and policies across multiple dimensions.</span></span>

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a><span data-ttu-id="e1263-373">更新网络拓扑计划以显示如何避免非对称路由</span><span class="sxs-lookup"><span data-stu-id="e1263-373">Update your network topology plan to show how you would avoid asymmetric routes</span></span>
<span data-ttu-id="e1263-374"><a name="asymmetric"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-374"><a name="asymmetric"> </a></span></span>

<span data-ttu-id="e1263-375">您希望避免非对称路由，以确保组织成员可以无缝地Office 365 Internet 上的其他重要服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-375">You want to avoid asymmetric routing to ensure people in your organization can seamlessly use Office 365 as well as other important services on the internet.</span></span> <span data-ttu-id="e1263-376">客户具有两种导致非对称路由的常见配置。</span><span class="sxs-lookup"><span data-stu-id="e1263-376">There are two common configurations customers have that cause asymmetric routing.</span></span> <span data-ttu-id="e1263-377">现在是查看计划使用的网络配置并检查是否存在其中一种非对称路由方案的良好时间。</span><span class="sxs-lookup"><span data-stu-id="e1263-377">Now's a good time to review the network configuration you're planning to use and check if one of these asymmetric routing scenarios could exist.</span></span>
  
<span data-ttu-id="e1263-378">首先，我们将检查一些与以下网络图相关的不同情况。</span><span class="sxs-lookup"><span data-stu-id="e1263-378">To begin, we'll examine a few different situations associated with the following network diagram.</span></span> <span data-ttu-id="e1263-379">在此图中，接收入站请求的所有服务器（如 ADFS 或本地混合服务器）都位于 New Jersey 数据中心，并公布给 Internet。</span><span class="sxs-lookup"><span data-stu-id="e1263-379">In this diagram, all servers that receive inbound requests, such as ADFS or on-premises hybrid servers are in the New Jersey data center and are advertised to the internet.</span></span>
  
1. <span data-ttu-id="e1263-380">外围网络是安全的，但没有源 NAT 可用于传入请求。</span><span class="sxs-lookup"><span data-stu-id="e1263-380">While the perimeter network is secure, there is no Source NAT available for incoming requests.</span></span>

2. <span data-ttu-id="e1263-381">New Jersey 数据中心中的服务器能够查看 Internet 和 ExpressRoute 路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-381">The servers in the New Jersey data center are able to see both internet and ExpressRoute routes.</span></span>

![ExpressRoute 连接概述](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
<span data-ttu-id="e1263-383">我们还提供如何修复它们的建议。</span><span class="sxs-lookup"><span data-stu-id="e1263-383">We also have suggestions on how to fix them.</span></span>
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a><span data-ttu-id="e1263-384">问题 1：通过 Internet 从云到本地连接</span><span class="sxs-lookup"><span data-stu-id="e1263-384">Problem 1: Cloud to on-premises connection over the Internet</span></span>
  
<span data-ttu-id="e1263-385">下图说明了当网络配置未为来自 Microsoft 云的 Internet 入站请求提供 NAT 时采用的非对称网络路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-385">The following diagram illustrates the asymmetric network path taken when your network configuration doesn't provide NAT for inbound requests from the Microsoft cloud over the internet.</span></span>
  
1. <span data-ttu-id="e1263-386">来自 Office 365的入站请求从公共 DNS 检索内部部署终结点的 IP 地址，并将请求发送到外围网络。</span><span class="sxs-lookup"><span data-stu-id="e1263-386">The inbound request from Office 365 retrieves the IP address of the on-premises endpoint from public DNS and sends the request to your perimeter network.</span></span>

2. <span data-ttu-id="e1263-387">在此错误配置中，在发送流量的外围网络中没有配置或可用的源 NAT，从而导致将实际源 IP 地址用作返回目标。</span><span class="sxs-lookup"><span data-stu-id="e1263-387">In this faulty configuration, there is no Source NAT configured or available at the perimeter network where the traffic is sent resulting in the actual source IP address being used as the return destination.</span></span>

  - <span data-ttu-id="e1263-388">您网络上服务器通过任何可用的 ExpressRoute 网络连接将Office 365流量路由到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="e1263-388">The server on your network routes the return traffic to Office 365 through any available ExpressRoute network connection.</span></span>

  - <span data-ttu-id="e1263-389">结果是该流到非对称Office 365，从而导致连接断开。</span><span class="sxs-lookup"><span data-stu-id="e1263-389">The result is an Asymmetric path for that flow to Office 365, resulting in a broken connection.</span></span>

![ExpressRoute 等长路由问题 1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a><span data-ttu-id="e1263-391">解决方案 1a：源 NAT</span><span class="sxs-lookup"><span data-stu-id="e1263-391">Solution 1a: Source NAT</span></span>
  
<span data-ttu-id="e1263-392">只需将源 NAT 添加到入站请求，可解决此错误配置的网络。</span><span class="sxs-lookup"><span data-stu-id="e1263-392">Simply adding a source NAT to the inbound request resolves this misconfigured network.</span></span> <span data-ttu-id="e1263-393">在此图中：</span><span class="sxs-lookup"><span data-stu-id="e1263-393">In this diagram:</span></span>
  
1. <span data-ttu-id="e1263-394">传入的请求将继续通过 New Jersey 数据中心的外围网络输入。</span><span class="sxs-lookup"><span data-stu-id="e1263-394">The incoming request continues to enter through the New Jersey data center's perimeter network.</span></span> <span data-ttu-id="e1263-395">此时源 NAT 可用。</span><span class="sxs-lookup"><span data-stu-id="e1263-395">This time Source NAT is available.</span></span>

2. <span data-ttu-id="e1263-396">来自服务器的响应将路由回与源 NAT 关联的 IP，而不是原始 IP 地址，从而导致响应沿同一网络路径返回。</span><span class="sxs-lookup"><span data-stu-id="e1263-396">The response from the server routes back toward the IP associated with the Source NAT instead of the original IP address, resulting in the response returning along the same network path.</span></span>

![ExpressRoute 等长路由解决方案 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a><span data-ttu-id="e1263-398">解决方案 1b：路由范围</span><span class="sxs-lookup"><span data-stu-id="e1263-398">Solution 1b: Route Scoping</span></span>
  
<span data-ttu-id="e1263-399">或者，你可以选择不允许播发 ExpressRoute BGP 前缀，从而删除这些计算机的备用网络路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-399">Alternatively, you can choose to not allow the ExpressRoute BGP prefixes to be advertised, removing the alternate network path for those computers.</span></span> <span data-ttu-id="e1263-400">在此图中：</span><span class="sxs-lookup"><span data-stu-id="e1263-400">In this diagram:</span></span>
  
1. <span data-ttu-id="e1263-401">传入的请求将继续通过 New Jersey 数据中心的外围网络输入。</span><span class="sxs-lookup"><span data-stu-id="e1263-401">The incoming request continues to enter through the New Jersey data center's perimeter network.</span></span> <span data-ttu-id="e1263-402">这一次，通过 ExpressRoute 电路从 Microsoft 播发的前缀对 New Jersey 数据中心不可用。</span><span class="sxs-lookup"><span data-stu-id="e1263-402">This time the prefixes advertised from Microsoft over the ExpressRoute circuit are not available to the New Jersey data center.</span></span>

2. <span data-ttu-id="e1263-403">来自服务器的响应通过唯一可用的路由向与原始 IP 地址关联的 IP 路由返回，从而导致响应沿同一网络路径返回。</span><span class="sxs-lookup"><span data-stu-id="e1263-403">The response from the server routes back toward the IP associated with the original IP address over the only route available, resulting in the response returning along the same network path.</span></span>

![ExpressRoute 等长路由解决方案 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a><span data-ttu-id="e1263-405">问题 2：通过 ExpressRoute 从云到本地连接</span><span class="sxs-lookup"><span data-stu-id="e1263-405">Problem 2: Cloud to on-premises connection over ExpressRoute</span></span>
  
<span data-ttu-id="e1263-406">下图说明了当网络配置未通过 ExpressRoute 为来自 Microsoft 云的入站请求提供 NAT 时采用的非对称网络路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-406">The following diagram illustrates the asymmetric network path taken when your network configuration doesn't provide NAT for inbound requests from the Microsoft cloud over ExpressRoute.</span></span>
  
1. <span data-ttu-id="e1263-407">来自 DNS 的入站Office 365从 DNS 检索 IP 地址，并将请求发送到外围网络。</span><span class="sxs-lookup"><span data-stu-id="e1263-407">The inbound request from Office 365 retrieves the IP address from DNS and sends the request to your perimeter network.</span></span>

2. <span data-ttu-id="e1263-408">在此错误配置中，在发送流量的外围网络中没有配置或可用的源 NAT，从而导致将实际源 IP 地址用作返回目标。</span><span class="sxs-lookup"><span data-stu-id="e1263-408">In this faulty configuration, there is no Source NAT configured or available at the perimeter network where the traffic is sent resulting in the actual source IP address being used as the return destination.</span></span>

  - <span data-ttu-id="e1263-409">网络上计算机通过任何可用的 ExpressRoute 网络连接将Office 365流量路由到其他位置。</span><span class="sxs-lookup"><span data-stu-id="e1263-409">The computer on your network routes the return traffic to Office 365 through any available ExpressRoute network connection.</span></span>

  - <span data-ttu-id="e1263-410">结果是非对称连接与Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1263-410">The result is an Asymmetric connection to Office 365.</span></span>

![ExpressRoute 等长路由问题 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a><span data-ttu-id="e1263-412">解决方案 2：源 NAT</span><span class="sxs-lookup"><span data-stu-id="e1263-412">Solution 2: Source NAT</span></span>
  
<span data-ttu-id="e1263-413">只需将源 NAT 添加到入站请求，可解决此错误配置的网络。</span><span class="sxs-lookup"><span data-stu-id="e1263-413">Simply adding a source NAT to the inbound request resolves this misconfigured network.</span></span> <span data-ttu-id="e1263-414">在此图中：</span><span class="sxs-lookup"><span data-stu-id="e1263-414">In this diagram:</span></span>
  
1. <span data-ttu-id="e1263-415">传入的请求将继续通过纽约数据中心的外围网络输入。</span><span class="sxs-lookup"><span data-stu-id="e1263-415">The incoming request continues to enter through the New York data center's perimeter network.</span></span> <span data-ttu-id="e1263-416">此时源 NAT 可用。</span><span class="sxs-lookup"><span data-stu-id="e1263-416">This time Source NAT is available.</span></span>

2. <span data-ttu-id="e1263-417">来自服务器的响应将路由回与源 NAT 关联的 IP，而不是原始 IP 地址，从而导致响应沿同一网络路径返回。</span><span class="sxs-lookup"><span data-stu-id="e1263-417">The response from the server routes back toward the IP associated with the Source NAT instead of the original IP address, resulting in the response returning along the same network path.</span></span>

![ExpressRoute 等长路由解决方案 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a><span data-ttu-id="e1263-419">白皮书验证网络设计是否具有路径对称</span><span class="sxs-lookup"><span data-stu-id="e1263-419">Paper verify that the network design has path symmetry</span></span>

<span data-ttu-id="e1263-420">此时，你需要在纸张上验证你的实施计划是否为你将使用网络部署的不同方案提供Office 365。</span><span class="sxs-lookup"><span data-stu-id="e1263-420">At this point, you need to verify on paper that your implementation plan offers route symmetry for the different scenarios in which you'll be using Office 365.</span></span> <span data-ttu-id="e1263-421">你将确定当某人使用服务的不同功能时预期采用的特定网络路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-421">You'll identify the specific network route that is expected to be taken when a person uses different features of the service.</span></span> <span data-ttu-id="e1263-422">从本地网络和 WAN 路由到外围设备，到连接路径;ExpressRoute 或 Internet，并连接到联机终结点。</span><span class="sxs-lookup"><span data-stu-id="e1263-422">From the on-premises network and WAN routing, to the perimeter devices, to the connectivity path; ExpressRoute or the internet, and on to the connection to the online endpoint.</span></span>
  
<span data-ttu-id="e1263-423">你需要为之前标识为组织将采用的所有 Office 365网络服务执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e1263-423">You'll need to do this for all of the Office 365 network services that were previously identified as services that your organization will adopt.</span></span>
  
<span data-ttu-id="e1263-424">本白皮书通过第二个人浏览路线会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="e1263-424">It helps to do this paper walk through of routes with a second person.</span></span> <span data-ttu-id="e1263-425">向他们解释每个网络跃点应从何处获取其下一个路由，并确保你熟悉路由路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-425">Explain to them where each network hop is expected to get its next route from and ensure that you're familiar with the routing paths.</span></span> <span data-ttu-id="e1263-426">请记住，ExpressRoute 将始终向 Microsoft 服务器 IP 地址提供范围更广的路由，从而提供比 Internet 默认路由更低的路由成本。</span><span class="sxs-lookup"><span data-stu-id="e1263-426">Remember that ExpressRoute will always provide a more scoped route to Microsoft server IP addresses giving it lower route cost than an Internet default route.</span></span>
  
### <a name="design-client-connectivity-configuration"></a><span data-ttu-id="e1263-427">设计客户端连接配置</span><span class="sxs-lookup"><span data-stu-id="e1263-427">Design Client Connectivity Configuration</span></span>
<span data-ttu-id="e1263-428"><a name="asymmetric"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-428"><a name="asymmetric"> </a></span></span>

![将 PAC 文件与 ExpressRoute 一同使用](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
<span data-ttu-id="e1263-430">如果将代理服务器用于 Internet 绑定流量，则需要调整任何 PAC 或客户端配置文件，以确保网络上的客户端计算机已正确配置为将所需的 ExpressRoute 流量发送到 Office 365 而无需传输代理服务器，其余流量（包括一些 Office 365 流量）将发送到相关代理。</span><span class="sxs-lookup"><span data-stu-id="e1263-430">If you're using a proxy server for internet bound traffic then you need to adjust any PAC or client configuration files to ensure client computers on your network are correctly configured to send the ExpressRoute traffic you desire to Office 365 without transiting your proxy server, and the remaining traffic, including some Office 365 traffic, is sent to the relevant proxy.</span></span> <span data-ttu-id="e1263-431">阅读我们有关管理[OFFICE 365 终结点](./managing-office-365-endpoints.md)（例如 PAC 文件）的指南。</span><span class="sxs-lookup"><span data-stu-id="e1263-431">Read our guide on [managing Office 365 endpoints](./managing-office-365-endpoints.md) for example PAC files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1263-432">终结点会频繁更改，频率为每周一次。</span><span class="sxs-lookup"><span data-stu-id="e1263-432">The endpoints change frequently, as often as weekly.</span></span> <span data-ttu-id="e1263-433">只应基于组织采用的服务和功能进行更改，以减少需要所做的更改数，使其保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="e1263-433">You should only make changes based on the services and features your organization has adopted to reduce the number of changes you'll need to make to stay current.</span></span> <span data-ttu-id="e1263-434">请密切注意 RSS源中的"有效日期"，其中将公布更改，并保留所有过去更改的记录，在到达生效日期之前，可能不会公布宣布的 IP 地址，也可以将其从广告中删除。</span><span class="sxs-lookup"><span data-stu-id="e1263-434">Pay close attention to the **Effective Date** in the RSS feed where the changes are announced and a record is kept of all past changes, IP addresses that are announced may not be advertised, or removed from advertisement, until the effective date is reached.</span></span>
  
## <a name="build-your-deployment-and-testing-procedures"></a><span data-ttu-id="e1263-435">构建部署和测试过程</span><span class="sxs-lookup"><span data-stu-id="e1263-435">Build your deployment and testing procedures</span></span>
<span data-ttu-id="e1263-436"><a name="testing"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-436"><a name="testing"> </a></span></span>

<span data-ttu-id="e1263-437">您的实施计划应包括测试和回滚规划。</span><span class="sxs-lookup"><span data-stu-id="e1263-437">Your implementation plan should include both testing and rollback planning.</span></span> <span data-ttu-id="e1263-438">如果你的实现未如预期运行，则计划应设计为在发现问题之前影响最少人数。</span><span class="sxs-lookup"><span data-stu-id="e1263-438">If your implementation isn't functioning as expected, the plan should be designed to affect the least number of people before problems are discovered.</span></span> <span data-ttu-id="e1263-439">以下是计划应考虑的一些高级别原则。</span><span class="sxs-lookup"><span data-stu-id="e1263-439">The following are some high level principles your plan should consider.</span></span>
  
1. <span data-ttu-id="e1263-440">分段网络段和用户服务载入，以最大限度地减少中断。</span><span class="sxs-lookup"><span data-stu-id="e1263-440">Stage the network segment and user service onboarding to minimize disruption.</span></span>

2. <span data-ttu-id="e1263-441">规划从单独的 Internet 连接主机使用 traceroute 和 TCP 连接测试路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-441">Plan for testing routes with traceroute and TCP connect from a separate internet connected host.</span></span>

3. <span data-ttu-id="e1263-442">最好在具有测试租户的隔离测试网络上测试入站和出Office 365服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-442">Preferably, testing of inbound and outbound services should be done on an isolated test network with a test Office 365 tenant.</span></span>

      - <span data-ttu-id="e1263-443">或者，如果客户尚未使用或正在试用，可在生产Office 365进行测试。</span><span class="sxs-lookup"><span data-stu-id="e1263-443">Alternatively, testing can be performed on a production network if the customer is not yet using Office 365 or is in pilot.</span></span>

      - <span data-ttu-id="e1263-444">或者，在生产中断期间（仅为测试和监控留出）可以执行测试。</span><span class="sxs-lookup"><span data-stu-id="e1263-444">Alternatively, testing can be performed during a production outage that is set aside for test and monitoring only.</span></span>

      - <span data-ttu-id="e1263-445">或者，可以通过检查每个第 3 层路由器节点上每个服务的路由来进行测试。</span><span class="sxs-lookup"><span data-stu-id="e1263-445">Alternatively, testing can be done by checking routes for each service on each layer 3 router node.</span></span> <span data-ttu-id="e1263-446">只有在无法进行其他测试时，才应使用这种回退，因为缺少物理测试会带来风险。</span><span class="sxs-lookup"><span data-stu-id="e1263-446">This fall back should only be used if no other testing is possible since a lack of physical testing introduces risk.</span></span>

### <a name="build-your-deployment-procedures"></a><span data-ttu-id="e1263-447">构建部署过程</span><span class="sxs-lookup"><span data-stu-id="e1263-447">Build your deployment procedures</span></span>

<span data-ttu-id="e1263-448">部署过程应分阶段向小型人员组推出，以允许先进行测试，然后再部署到更大的人员组。</span><span class="sxs-lookup"><span data-stu-id="e1263-448">Your deployment procedures should roll out to small groups of people in stages to allow for testing before deploying to larger groups of people.</span></span> <span data-ttu-id="e1263-449">以下是分步部署 ExpressRoute 的几种方法。</span><span class="sxs-lookup"><span data-stu-id="e1263-449">The following are several ways to stage the deployment of ExpressRoute.</span></span>
  
1. <span data-ttu-id="e1263-450">使用 Microsoft 对等设置 ExpressRoute，并仅出于分步测试目的将路由广告转发到单个主机。</span><span class="sxs-lookup"><span data-stu-id="e1263-450">Set up ExpressRoute with Microsoft peering and have the route advertisements forwarded to a single host only for staged testing purposes.</span></span>

2. <span data-ttu-id="e1263-451">首先将路由播发到 ExpressRoute 网络到单个网段，然后按网络段或区域展开路由广告。</span><span class="sxs-lookup"><span data-stu-id="e1263-451">Advertise routes to the ExpressRoute network to a single network segment at first and expand route advertisements by network segment or region.</span></span>

3. <span data-ttu-id="e1263-452">如果是首次Office 365部署，请使用 ExpressRoute 网络部署作为一小部分人的试点。</span><span class="sxs-lookup"><span data-stu-id="e1263-452">If deploying Office 365 for the first time, use the ExpressRoute network deployment as a pilot for a small number of people.</span></span>

4. <span data-ttu-id="e1263-453">如果使用代理服务器，也可以配置测试 PAC 文件，在添加更多内容之前，通过测试和反馈将少量用户引导到 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="e1263-453">If using proxy servers, you can alternatively configure a test PAC file to direct a small number of people to ExpressRoute with testing and feedback before adding more.</span></span>

<span data-ttu-id="e1263-454">您的实现计划应列出必须执行的每个部署过程或部署网络配置所需的命令。</span><span class="sxs-lookup"><span data-stu-id="e1263-454">Your implementation plan should list each of the deployment procedures that must be taken or commands that need to be used to deploy the networking configuration.</span></span> <span data-ttu-id="e1263-455">网络中断时间到达时，进行的所有更改都应来自预先编写并经过对等审查的写入部署计划。</span><span class="sxs-lookup"><span data-stu-id="e1263-455">When the network outage time arrives all of the changes being made should be from the written deployment plan which was written in advance and peer reviewed.</span></span> <span data-ttu-id="e1263-456">请参阅我们的 ExpressRoute 技术配置指南。</span><span class="sxs-lookup"><span data-stu-id="e1263-456">See our guidance on the technical configuration of ExpressRoute.</span></span>
  
- <span data-ttu-id="e1263-457">如果已更改将继续发送电子邮件的任何本地服务器的 IP 地址，则更新 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="e1263-457">Updating your SPF TXT records if you've changed IP addresses for any on-premises servers that will continue to send email.</span></span>

- <span data-ttu-id="e1263-458">如果已更改 IP 地址以适应新的 NAT 配置，则更新内部部署服务器的任何 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="e1263-458">Updating any DNS entries for on-premises servers if you've changed IP addresses to accommodate a new NAT configuration.</span></span>

- <span data-ttu-id="e1263-459">确保你已订阅 RSS 源，Office 365终结点通知以维护任何路由或代理配置。</span><span class="sxs-lookup"><span data-stu-id="e1263-459">Ensure you've subscribed to the RSS feed for Office 365 endpoint notifications to maintain any routing or proxy configurations.</span></span>

<span data-ttu-id="e1263-460">完成 ExpressRoute 部署后，应执行测试计划中的过程。</span><span class="sxs-lookup"><span data-stu-id="e1263-460">After your ExpressRoute deployment is complete the procedures in the test plan should be executed.</span></span> <span data-ttu-id="e1263-461">应记录每个过程的结果。</span><span class="sxs-lookup"><span data-stu-id="e1263-461">Results for each procedure should be logged.</span></span> <span data-ttu-id="e1263-462">如果测试计划结果指示实现未成功，则必须包括回滚到原始生产环境的过程。</span><span class="sxs-lookup"><span data-stu-id="e1263-462">You must include procedures for rolling back to the original production environment in the event the test plan results indicate the implementation was not successful.</span></span>
  
### <a name="build-your-test-procedures"></a><span data-ttu-id="e1263-463">构建测试过程</span><span class="sxs-lookup"><span data-stu-id="e1263-463">Build your test procedures</span></span>

<span data-ttu-id="e1263-464">测试过程应包含针对每个出站和入站网络服务的测试Office 365使用 ExpressRoute 和不会使用 ExpressRoute 的网络服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-464">Your testing procedures should include tests for each outbound and inbound network service for Office 365 both that will be using ExpressRoute and ones that will not.</span></span> <span data-ttu-id="e1263-465">这些过程应包括从每个唯一网络位置进行测试，包括不在企业 LAN 中的用户。</span><span class="sxs-lookup"><span data-stu-id="e1263-465">The procedures should include testing from each unique network location including users who are not on-premises in the corporate LAN.</span></span>
  
<span data-ttu-id="e1263-466">测试活动的一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="e1263-466">Some examples of test activities include the following.</span></span>
  
1. <span data-ttu-id="e1263-467">从本地路由器 Ping 到网络运营商路由器。</span><span class="sxs-lookup"><span data-stu-id="e1263-467">Ping from your on-premises router to your network operator router.</span></span>

2. <span data-ttu-id="e1263-468">验证本地路由器Office 365 500 及以上的 IP 地址和 CRM Online IP 地址广告。</span><span class="sxs-lookup"><span data-stu-id="e1263-468">Validate the 500+ Office 365 and CRM Online IP address advertisements are received by your on-premises router.</span></span>

3. <span data-ttu-id="e1263-469">验证入站和出站 NAT 是否正在 ExpressRoute 和内部网络之间运行。</span><span class="sxs-lookup"><span data-stu-id="e1263-469">Validate your inbound and outbound NAT is operating between ExpressRoute and the internal network.</span></span>

4. <span data-ttu-id="e1263-470">验证到 NAT 的路由是否正在从路由器公布。</span><span class="sxs-lookup"><span data-stu-id="e1263-470">Validate that routes to your NAT are being advertised from your router.</span></span>

5. <span data-ttu-id="e1263-471">验证 ExpressRoute 是否接受你播发的前缀。</span><span class="sxs-lookup"><span data-stu-id="e1263-471">Validate that ExpressRoute has accepted your advertised prefixes.</span></span>

      - <span data-ttu-id="e1263-472">使用以下 cmdlet 验证对等广告：</span><span class="sxs-lookup"><span data-stu-id="e1263-472">Use the following cmdlet to verify peering advertisements:</span></span>

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. <span data-ttu-id="e1263-473">验证公共 NAT IP 范围是否未通过任何其他 ExpressRoute 或公共 Internet 网络线路向 Microsoft 公布，除非它是较大范围的特定子集（如上例所示）。</span><span class="sxs-lookup"><span data-stu-id="e1263-473">Validate your public NAT IP range is not advertised to Microsoft through any other ExpressRoute or public Internet network circuit unless it is a specific subset of a larger range as in the previous example.</span></span>

7. <span data-ttu-id="e1263-474">ExpressRoute 电路已配对，验证这两个 BGP 会话是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="e1263-474">ExpressRoute circuits are paired, validate that both BGP sessions are running.</span></span>

8. <span data-ttu-id="e1263-475">在 NAT 内部设置单个主机，并使用 ping、tracert 和 tcpping 测试跨新电路与主机连接 outlook.office365.com。</span><span class="sxs-lookup"><span data-stu-id="e1263-475">Set up a single host on the inside of your NAT and use ping, tracert, and tcpping to test connectivity across the new circuit to the host outlook.office365.com.</span></span> <span data-ttu-id="e1263-476">或者，可以在镜像端口上使用 Wireshark 或 Microsoft Network Monitor 3.4 等工具连接到 MSEE，以验证能否连接到与 outlook.office365.com 关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e1263-476">Alternatively, you could use a tool such as Wireshark or Microsoft Network Monitor 3.4 on a mirrored port to the MSEE to validate you're able to connect to the IP address associated with outlook.office365.com.</span></span>

9. <span data-ttu-id="e1263-477">测试应用程序应用程序级别的Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e1263-477">Test application level functionality for Exchange Online.</span></span>

  - <span data-ttu-id="e1263-478">测试Outlook用户能否连接到Exchange Online发送/接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1263-478">Test Outlook is able to connect to Exchange Online and send/receive email.</span></span>

  - <span data-ttu-id="e1263-479">测试Outlook能否使用联机模式。</span><span class="sxs-lookup"><span data-stu-id="e1263-479">Test Outlook is able to use online-mode.</span></span>

  - <span data-ttu-id="e1263-480">测试智能手机连接和发送/接收功能。</span><span class="sxs-lookup"><span data-stu-id="e1263-480">Test smartphone connectivity and send/receive capability.</span></span>

10. <span data-ttu-id="e1263-481">测试 SharePoint Online 的应用程序级别功能</span><span class="sxs-lookup"><span data-stu-id="e1263-481">Test application level functionality for SharePoint Online</span></span>

  - <span data-ttu-id="e1263-482">测试OneDrive for Business客户端。</span><span class="sxs-lookup"><span data-stu-id="e1263-482">Test OneDrive for Business sync client.</span></span>

  - <span data-ttu-id="e1263-483">测试 SharePoint Online Web 访问。</span><span class="sxs-lookup"><span data-stu-id="e1263-483">Test SharePoint Online web access.</span></span>

11. <span data-ttu-id="e1263-484">测试用于以下调用Skype for Business应用程序级别功能：</span><span class="sxs-lookup"><span data-stu-id="e1263-484">Test application level functionality for Skype for Business calling scenarios:</span></span>

  - <span data-ttu-id="e1263-485">以经过身份验证的用户身份加入电话会议 [最终用户发起的邀请]。</span><span class="sxs-lookup"><span data-stu-id="e1263-485">Join to conference call as authenticated user [invite initiated by end user].</span></span>

  - <span data-ttu-id="e1263-486">邀请用户加入电话会议 [从 MCU 发送的邀请]。</span><span class="sxs-lookup"><span data-stu-id="e1263-486">Invite user to conference call [invite sent from MCU].</span></span>

  - <span data-ttu-id="e1263-487">使用 Web 应用程序以匿名Skype for Business加入会议。</span><span class="sxs-lookup"><span data-stu-id="e1263-487">Join conference as anonymous user using the Skype for Business web application.</span></span>

  - <span data-ttu-id="e1263-488">从有线电脑连接、IP 电话和移动设备加入呼叫。</span><span class="sxs-lookup"><span data-stu-id="e1263-488">Join call from your wired PC connection, IP phone, and mobile device.</span></span>

  - <span data-ttu-id="e1263-489">呼叫联盟用户 o 呼叫 PSTN 验证：呼叫已完成，呼叫质量可接受，连接时间可接受。</span><span class="sxs-lookup"><span data-stu-id="e1263-489">Call to federated user o Call to PSTN Validation: call is completed, call quality is acceptable, connection time is acceptable.</span></span>

  - <span data-ttu-id="e1263-490">验证租户成员和联盟用户是否更新了联系人的状态。</span><span class="sxs-lookup"><span data-stu-id="e1263-490">Verify presence status for contacts is updated for both members of the tenant and federated users.</span></span>

### <a name="common-problems"></a><span data-ttu-id="e1263-491">常见问题</span><span class="sxs-lookup"><span data-stu-id="e1263-491">Common problems</span></span>

<span data-ttu-id="e1263-492">非对称路由是最常见的实现问题。</span><span class="sxs-lookup"><span data-stu-id="e1263-492">Asymmetric routing is the most common implementation problem.</span></span> <span data-ttu-id="e1263-493">以下是要查找的一些常见源：</span><span class="sxs-lookup"><span data-stu-id="e1263-493">Here are some common sources to look for:</span></span>
  
- <span data-ttu-id="e1263-494">使用没有源 NAT 的开放或平面网络路由拓扑。</span><span class="sxs-lookup"><span data-stu-id="e1263-494">Using an open or flat network routing topology without source NAT in place.</span></span>

- <span data-ttu-id="e1263-495">未使用 SNAT 通过 Internet 和 ExpressRoute 连接路由到入站服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-495">Not using SNAT to route to inbound services through both the internet and ExpressRoute connections.</span></span>

- <span data-ttu-id="e1263-496">在广泛部署之前，不在测试网络上测试 ExpressRoute 上的入站服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-496">Not testing inbound services on ExpressRoute on a test network prior to deploying broadly.</span></span>

## <a name="deploying-expressroute-connectivity-through-your-network"></a><span data-ttu-id="e1263-497">通过网络部署 ExpressRoute 连接</span><span class="sxs-lookup"><span data-stu-id="e1263-497">Deploying ExpressRoute connectivity through your network</span></span>
<span data-ttu-id="e1263-498"><a name="testing"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-498"><a name="testing"> </a></span></span>

<span data-ttu-id="e1263-499">将部署一次分步部署到一个网络段，逐步推出到不同网络部分的连接，并计划回滚每个新网段。</span><span class="sxs-lookup"><span data-stu-id="e1263-499">Stage your deployment to one segment of the network at a time, progressively rolling out the connectivity to different parts of the network with a plan to roll back for each new network segment.</span></span> <span data-ttu-id="e1263-500">如果你的部署与部署Office 365一致，请首先部署到Office 365试点用户，然后从试点用户开始扩展。</span><span class="sxs-lookup"><span data-stu-id="e1263-500">If your deployment is aligned with an Office 365 deployment, deploy to your Office 365 pilot users first and extend from there.</span></span>
  
<span data-ttu-id="e1263-501">首先用于测试，然后用于生产：</span><span class="sxs-lookup"><span data-stu-id="e1263-501">First for your test and then for production:</span></span>
  
- <span data-ttu-id="e1263-502">运行部署步骤以启用 ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="e1263-502">Run the deployment steps to enable ExpressRoute.</span></span>

- <span data-ttu-id="e1263-503">测试网络路由是否如预期一样。</span><span class="sxs-lookup"><span data-stu-id="e1263-503">Test your seeing the network routes are as expected.</span></span>

- <span data-ttu-id="e1263-504">在每个入站和出站服务上执行测试。</span><span class="sxs-lookup"><span data-stu-id="e1263-504">Perform testing on each inbound and outbound service.</span></span>

- <span data-ttu-id="e1263-505">如果发现任何问题，回滚。</span><span class="sxs-lookup"><span data-stu-id="e1263-505">Rollback if you discover any issues.</span></span>

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a><span data-ttu-id="e1263-506">设置与具有测试网段的 ExpressRoute 的测试连接</span><span class="sxs-lookup"><span data-stu-id="e1263-506">Set up a test connection to ExpressRoute with a test network segment</span></span>

<span data-ttu-id="e1263-507">现在，你已完成的白皮书计划，是时候进行小规模测试了。</span><span class="sxs-lookup"><span data-stu-id="e1263-507">Now that you have the completed plan on paper it is time to test at a small scale.</span></span> <span data-ttu-id="e1263-508">在此测试中，你将建立与 Microsoft 对等到本地网络测试子网的单个 ExpressRoute 连接。</span><span class="sxs-lookup"><span data-stu-id="e1263-508">In this test you will establish a single ExpressRoute connection with Microsoft Peering to a test subnet on your on-premises network.</span></span> <span data-ttu-id="e1263-509">可以配置[与测试子网](https://go.microsoft.com/fwlink/p/?LinkID=403802)Office 365外部连接的试用租户，并包括将在测试子网的生产中使用的所有出站和入站服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-509">You can configure a [trial Office 365 tenant](https://go.microsoft.com/fwlink/p/?LinkID=403802) with connectivity to and from the test subnet and include all outbound and inbound services that you will be using in production in the test subnet.</span></span> <span data-ttu-id="e1263-510">为测试网络段设置 DNS，并建立所有入站和出站服务。</span><span class="sxs-lookup"><span data-stu-id="e1263-510">Set up DNS for the test network segment and establish all inbound and outbound services.</span></span> <span data-ttu-id="e1263-511">执行测试计划，并确保熟悉每个服务的路由和路由传播。</span><span class="sxs-lookup"><span data-stu-id="e1263-511">Execute your test plan and ensure that you are familiar with the routing for each service and the route propagation.</span></span>
  
### <a name="execute-the-deployment-and-test-plans"></a><span data-ttu-id="e1263-512">执行部署和测试计划</span><span class="sxs-lookup"><span data-stu-id="e1263-512">Execute the deployment and test plans</span></span>

<span data-ttu-id="e1263-513">完成上述项目后，请查看已完成的区域，并确保你和团队在执行部署和测试计划之前已查看这些方面。</span><span class="sxs-lookup"><span data-stu-id="e1263-513">As you complete the items described above, check off the areas you've completed and ensure you and your team have reviewed them before executing your deployment and testing plans.</span></span>
  
- <span data-ttu-id="e1263-514">网络更改中涉及的出站和入站服务的列表。</span><span class="sxs-lookup"><span data-stu-id="e1263-514">List of outbound and inbound services that are involved in the network change.</span></span>

- <span data-ttu-id="e1263-515">显示 Internet 出口和 ExpressRoute meet-me 位置的全局网络体系结构图。</span><span class="sxs-lookup"><span data-stu-id="e1263-515">Global network architecture diagram showing both internet egress and ExpressRoute meet-me locations.</span></span>

- <span data-ttu-id="e1263-516">网络路由图，演示部署的每个服务所使用的不同网络路径。</span><span class="sxs-lookup"><span data-stu-id="e1263-516">Network routing diagram demonstrating the different network paths used for each service deployed.</span></span>

- <span data-ttu-id="e1263-517">具有实现更改和回滚的步骤（如果需要）的部署计划。</span><span class="sxs-lookup"><span data-stu-id="e1263-517">A deployment plan with steps to implement the changes and rollback if needed.</span></span>

- <span data-ttu-id="e1263-518">测试每个服务和网络Office 365测试计划。</span><span class="sxs-lookup"><span data-stu-id="e1263-518">A test plan for testing each Office 365 and network service.</span></span>

- <span data-ttu-id="e1263-519">已完成入站和出站服务的生产路由的纸张验证。</span><span class="sxs-lookup"><span data-stu-id="e1263-519">Completed paper validation of production routes for inbound and outbound services.</span></span>

- <span data-ttu-id="e1263-520">跨测试网络段完成的测试，包括可用性测试。</span><span class="sxs-lookup"><span data-stu-id="e1263-520">A completed test across a test network segment including availability testing.</span></span>

<span data-ttu-id="e1263-521">选择一个足以运行整个部署计划和测试计划的中断时段，有一些时间可用于故障排除和回滚（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="e1263-521">Choose an outage window that is long enough to run through the entire deployment plan and the test plan, has some time available for troubleshooting and time for rolling back if required.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e1263-522">由于通过 Internet 和 ExpressRoute 进行路由的复杂性质，建议向此窗口添加额外的缓冲区时间以处理复杂路由的疑难解答。</span><span class="sxs-lookup"><span data-stu-id="e1263-522">Due to the complex nature of routing over both the internet and ExpressRoute, it is recommended that additional buffer time is added to this window to handle troubleshooting complex routing.</span></span>
  
### <a name="configure-qos-for-skype-for-business-online"></a><span data-ttu-id="e1263-523">为 Skype for Business Online 配置 QoS</span><span class="sxs-lookup"><span data-stu-id="e1263-523">Configure QoS for Skype for Business Online</span></span>

<span data-ttu-id="e1263-524">QoS 是获得联机语音和会议Skype for Business所必需的。</span><span class="sxs-lookup"><span data-stu-id="e1263-524">QoS is necessary to obtain voice and meeting benefits for Skype for Business Online.</span></span> <span data-ttu-id="e1263-525">You can configure QoS after you have ensure that the ExpressRoute network connection does not block any of your other Office 365 service access.</span><span class="sxs-lookup"><span data-stu-id="e1263-525">You can configure QoS after you have ensured that the ExpressRoute network connection does not block any of your other Office 365 service access.</span></span> <span data-ttu-id="e1263-526">Skype for Business Online 中的[ExpressRoute 和 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)一文介绍了 QoS 的配置。</span><span class="sxs-lookup"><span data-stu-id="e1263-526">Configuration for QoS is described in the article [ExpressRoute and QoS in Skype for Business Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) .</span></span>
  
## <a name="troubleshooting-your-implementation"></a><span data-ttu-id="e1263-527">实现疑难解答</span><span class="sxs-lookup"><span data-stu-id="e1263-527">Troubleshooting your implementation</span></span>
<span data-ttu-id="e1263-528"><a name="troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="e1263-528"><a name="troubleshooting"> </a></span></span>

<span data-ttu-id="e1263-529">首先查看此实施指南中的步骤，实施计划中是否遗漏了任何步骤？</span><span class="sxs-lookup"><span data-stu-id="e1263-529">The first place to look is at the steps in this implementation guide, were any missed in your implementation plan?</span></span> <span data-ttu-id="e1263-530">如果可能，请返回并运行进一步的小网络测试，以复制错误并在那里调试它。</span><span class="sxs-lookup"><span data-stu-id="e1263-530">Go back and run further small network testing if possible to replicate the error and debug it there.</span></span>
  
<span data-ttu-id="e1263-531">确定测试期间哪些入站或出站服务失败。</span><span class="sxs-lookup"><span data-stu-id="e1263-531">Identify which inbound or outbound services failed during testing.</span></span> <span data-ttu-id="e1263-532">专门获取失败的每个服务的 IP 地址和子网。</span><span class="sxs-lookup"><span data-stu-id="e1263-532">Get specifically the IP addresses and subnets for each of the services which failed.</span></span> <span data-ttu-id="e1263-533">继续操作，在纸张上演示网络拓扑图并验证路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-533">Go ahead and walk the network topology diagram on paper and validate the routing.</span></span> <span data-ttu-id="e1263-534">请专门验证 ExpressRoute 路由播发到何处，如有可能，请通过跟踪在中断期间测试该路由。</span><span class="sxs-lookup"><span data-stu-id="e1263-534">Validate specifically where the ExpressRoute routing is advertised to, Test that routing during the outage if possible with traces.</span></span>
  
<span data-ttu-id="e1263-535">将带网络跟踪的 PSPing 运行到每个客户终结点，并评估源 IP 地址和目标 IP 地址，以验证它们是否符合预期。</span><span class="sxs-lookup"><span data-stu-id="e1263-535">Run PSPing with a network trace to each customer endpoint and evaluate source and destination IP addresses to validate that they are as expected.</span></span> <span data-ttu-id="e1263-536">对端口 25 上公开的任何邮件主机运行 telnet，并验证 SNAT 是否隐藏原始源 IP 地址（如果预期）。</span><span class="sxs-lookup"><span data-stu-id="e1263-536">Run telnet to any mail host that you expose on port 25 and verify that SNAT is hiding the original source IP address if this is expected.</span></span>
  
<span data-ttu-id="e1263-537">请记住，在通过 ExpressRoute 连接部署 Office 365 时，需要确保 ExpressRoute 的网络配置设计最佳，并且还优化了网络上的其他组件（如客户端计算机）。</span><span class="sxs-lookup"><span data-stu-id="e1263-537">Keep in mind that while deploying Office 365 with an ExpressRoute connection you'll need to ensure both the network configuration for ExpressRoute is optimally designed and you've also optimized the other components on your network such as client computers.</span></span> <span data-ttu-id="e1263-538">除了使用此规划指南对您可能错过的步骤进行疑难解答之外，我们还为 Office 365 编写性能疑难解答[计划](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c)。</span><span class="sxs-lookup"><span data-stu-id="e1263-538">In addition to using this planning guide to troubleshoot the steps you may have missed, we also have written a [Performance troubleshooting plan for Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .</span></span>
  
<span data-ttu-id="e1263-539">以下是可以用于返回的简短链接：[https://aka.ms/implementexpressroute365]()</span><span class="sxs-lookup"><span data-stu-id="e1263-539">Here's a short link you can use to come back: [https://aka.ms/implementexpressroute365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e1263-540">相关主题</span><span class="sxs-lookup"><span data-stu-id="e1263-540">Related Topics</span></span>

[<span data-ttu-id="e1263-541">评估 Office 365 网络连接</span><span class="sxs-lookup"><span data-stu-id="e1263-541">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="e1263-542">适用于 Office 365 的 Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="e1263-542">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
  
[<span data-ttu-id="e1263-543">管理 ExpressRoute for Office 365 连接</span><span class="sxs-lookup"><span data-stu-id="e1263-543">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)
  
[<span data-ttu-id="e1263-544">使用 ExpressRoute for Office 365 路由</span><span class="sxs-lookup"><span data-stu-id="e1263-544">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
  
[<span data-ttu-id="e1263-545">ExpressRoute for Office 365 网络计划</span><span class="sxs-lookup"><span data-stu-id="e1263-545">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
  
[<span data-ttu-id="e1263-546">在 ExpressRoute 中将 BGP 社区用于Office 365方案</span><span class="sxs-lookup"><span data-stu-id="e1263-546">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)
  
[<span data-ttu-id="e1263-547">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="e1263-547">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="e1263-548">优化 Skype for Business Online 网络</span><span class="sxs-lookup"><span data-stu-id="e1263-548">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[<span data-ttu-id="e1263-549">Skype for Business Online 中的 ExpressRoute 和 QoS</span><span class="sxs-lookup"><span data-stu-id="e1263-549">ExpressRoute and QoS in Skype for Business Online</span></span>](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[<span data-ttu-id="e1263-550">使用 ExpressRoute 的呼叫流</span><span class="sxs-lookup"><span data-stu-id="e1263-550">Call flow using ExpressRoute</span></span>](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[<span data-ttu-id="e1263-551">使用基线和性能历史记录优化 Office 365 性能</span><span class="sxs-lookup"><span data-stu-id="e1263-551">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
[<span data-ttu-id="e1263-552">Office 365 性能疑难解答计划</span><span class="sxs-lookup"><span data-stu-id="e1263-552">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)
  
[<span data-ttu-id="e1263-553">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="e1263-553">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="e1263-554">Office 365 网络和性能优化</span><span class="sxs-lookup"><span data-stu-id="e1263-554">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)