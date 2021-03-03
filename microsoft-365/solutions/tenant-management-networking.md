---
title: 步骤 2. Microsoft 365 企业租户的最佳网络
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 优化对 Microsoft 365 租户的网络访问。
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407188"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="c9194-104">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="c9194-104">Step 2.</span></span> <span data-ttu-id="c9194-105">Microsoft 365 企业租户的最佳网络</span><span class="sxs-lookup"><span data-stu-id="c9194-105">Optimal networking for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="c9194-106">Microsoft 365 企业版包括云生产力应用（如 Teams 和 Exchange Online）和 Microsoft Intune，以及 Microsoft Azure 的许多标识和安全服务。</span><span class="sxs-lookup"><span data-stu-id="c9194-106">Microsoft 365 for enterprise includes cloud productivity apps such as Teams and Exchange Online, and Microsoft Intune, along with many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="c9194-107">所有这些基于云的服务都依赖于来自本地网络或 Internet 上任何位置的客户端设备的连接的安全性、性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="c9194-107">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices on your on-premises network or any location on the Internet.</span></span> 

<span data-ttu-id="c9194-108">若要优化租户的网络访问，需要：</span><span class="sxs-lookup"><span data-stu-id="c9194-108">To optimize network access for your tenant, you need to:</span></span>

- <span data-ttu-id="c9194-109">优化本地用户与 Microsoft 全局网络最近的位置之间的路径。</span><span class="sxs-lookup"><span data-stu-id="c9194-109">Optimize the path between your on-premises users and the closest location to the Microsoft Global Network.</span></span>
- <span data-ttu-id="c9194-110">为使用远程访问 VPN 解决方案的远程用户优化对 Microsoft 全局网络的访问。</span><span class="sxs-lookup"><span data-stu-id="c9194-110">Optimize access to the Microsoft Global Network for your remote users that are using a remote access VPN solution.</span></span>
- <span data-ttu-id="c9194-111">使用 Network Insights 设计办公地点的网络外围。</span><span class="sxs-lookup"><span data-stu-id="c9194-111">Use Network Insights to design the network perimeter for your office locations.</span></span>
- <span data-ttu-id="c9194-112">使用 Office 365 CDN 优化对 SharePoint 网站上承载的特定资产的访问。</span><span class="sxs-lookup"><span data-stu-id="c9194-112">Optimize access to specific assets hosted on SharePoint sites with the Office 365 CDN.</span></span>
- <span data-ttu-id="c9194-113">配置代理和网络边缘设备以绕过对包含终结点列表的 Microsoft 365 受信任流量的处理，并随着更改而自动更新列表。</span><span class="sxs-lookup"><span data-stu-id="c9194-113">Configure proxy and network edge devices to bypass processing for Microsoft 365 trusted traffic with the list of endpoints and automate the updating of the list as changes are made.</span></span>

## <a name="enterprise-on-premises-workers"></a><span data-ttu-id="c9194-114">企业内部部署工作人员</span><span class="sxs-lookup"><span data-stu-id="c9194-114">Enterprise on-premises workers</span></span>

<span data-ttu-id="c9194-115">对于企业网络，您应在客户端和最近的 Microsoft 365 终结点之间启用性能最高的网络访问，从而优化最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="c9194-115">For enterprise networks, you should optimize the end user experience by enabling the highest-performing network access between clients and the closest Microsoft 365 endpoints.</span></span> <span data-ttu-id="c9194-116">最终用户体验的质量与用户使用的应用程序的性能和响应能力直接相关。</span><span class="sxs-lookup"><span data-stu-id="c9194-116">The quality of end user experience is directly related to the performance and responsiveness of the application that the user is using.</span></span> <span data-ttu-id="c9194-117">例如，Microsoft Teams 依赖于低延迟，以便用户电话呼叫、会议以及共享屏幕协作无故障。</span><span class="sxs-lookup"><span data-stu-id="c9194-117">For example, Microsoft Teams relies on low latency so that user phone calls, conferences and shared screen collaborations are glitch-free.</span></span>

<span data-ttu-id="c9194-118">网络设计的主要目标是通过减少从客户端设备到 Microsoft 全球网络的往返时间 (RTT) 来最大程度地减少延迟，Microsoft 的公共网络主干网可将 Microsoft 的所有数据中心与低延迟、高可用性云应用程序入口点（称为"前端"）相互连接。</span><span class="sxs-lookup"><span data-stu-id="c9194-118">The primary goal in the network design should be to minimize latency by reducing the round-trip time (RTT) from client devices to the Microsoft Global Network, Microsoft's public network backbone that interconnects all of Microsoft's datacenters with low latency, high availability cloud application entry points, known as front doors, spread around the world.</span></span>

<span data-ttu-id="c9194-119">下面是传统企业网络的示例。</span><span class="sxs-lookup"><span data-stu-id="c9194-119">Here is an example of a traditional enterprise network.</span></span>

![具有中央 Internet 访问权的传统企业网络](../media/tenant-management-overview/tenant-management-networking-traditional.png)

<span data-ttu-id="c9194-121">在此图中，分支机构通过广域网连接到中央办公室， (WAN) WAN 主干网。</span><span class="sxs-lookup"><span data-stu-id="c9194-121">In this illustration, branch offices connect to a central office through wide area network (WAN) devices and a WAN backbone.</span></span> <span data-ttu-id="c9194-122">Internet 访问通过位于中央办公室网络边缘的安全或代理设备以及 ISP (服务提供商) 。</span><span class="sxs-lookup"><span data-stu-id="c9194-122">Internet access is through a security or proxy device at the network edge of the central office and an Internet service provider (ISP).</span></span> <span data-ttu-id="c9194-123">在 Internet 上，Microsoft 全球网络在全球的一些地区具有一系列正面门。</span><span class="sxs-lookup"><span data-stu-id="c9194-123">On the Internet, the Microsoft Global Network has a series of front doors in regions around the world.</span></span> <span data-ttu-id="c9194-124">组织还可以将中间位置用于额外的数据包处理和安全通信。</span><span class="sxs-lookup"><span data-stu-id="c9194-124">Organizations can also use intermediate locations for additional packet processing and security for traffic.</span></span> <span data-ttu-id="c9194-125">组织的 Microsoft 365 租户位于 Microsoft 全球网络内。</span><span class="sxs-lookup"><span data-stu-id="c9194-125">An organization's Microsoft 365 tenant is located within the Microsoft Global Network.</span></span>

<span data-ttu-id="c9194-126">Microsoft 365 云服务的此配置存在以下问题：</span><span class="sxs-lookup"><span data-stu-id="c9194-126">The problems with this configuration for Microsoft 365 cloud services are:</span></span>

- <span data-ttu-id="c9194-127">对于分支机构中的用户，流量会发送到非本地前端门，从而增加延迟。</span><span class="sxs-lookup"><span data-stu-id="c9194-127">For users in branch offices, traffic gets sent to non-local front doors, increasing latency.</span></span>
- <span data-ttu-id="c9194-128">将流量发送到中间位置将创建对受信任流量执行重复数据包处理的网络发夹，从而增加延迟。</span><span class="sxs-lookup"><span data-stu-id="c9194-128">Sending traffic to intermediate locations create network hairpins that perform duplicate packet processing on trusted traffic, increasing latency.</span></span>
- <span data-ttu-id="c9194-129">网络边缘设备对受信任的流量执行不需要的重复数据包处理，从而增加延迟。</span><span class="sxs-lookup"><span data-stu-id="c9194-129">Network edge devices perform unneeded and duplicate packet processing on trusted traffic, increasing latency.</span></span>

<span data-ttu-id="c9194-130">优化 Microsoft 365 网络性能不需要很复杂。</span><span class="sxs-lookup"><span data-stu-id="c9194-130">Optimizing Microsoft 365 network performance doesn't need to be complicated.</span></span> <span data-ttu-id="c9194-131">可以通过遵循一些关键原则来获得最佳性能：</span><span class="sxs-lookup"><span data-stu-id="c9194-131">You can get the best possible performance by following a few key principles:</span></span>

- <span data-ttu-id="c9194-132">标识 Microsoft 365 网络流量，这是发往 Microsoft 云服务的受信任流量。</span><span class="sxs-lookup"><span data-stu-id="c9194-132">Identify Microsoft 365 network traffic, which is trusted traffic destined to Microsoft cloud services.</span></span>
- <span data-ttu-id="c9194-133">允许 Microsoft 365 网络流量的本地分支从用户连接到 Microsoft 365 的每个位置进入 Internet。</span><span class="sxs-lookup"><span data-stu-id="c9194-133">Allow local branch egress of Microsoft 365 network traffic to the internet from each location where users connect to Microsoft 365.</span></span>
- <span data-ttu-id="c9194-134">避免网络发夹。</span><span class="sxs-lookup"><span data-stu-id="c9194-134">Avoid network hairpins.</span></span>
- <span data-ttu-id="c9194-135">允许 Microsoft 365 流量绕过代理和数据包检查设备。</span><span class="sxs-lookup"><span data-stu-id="c9194-135">Allow Microsoft 365 traffic to bypass proxies and packet inspection devices.</span></span>

<span data-ttu-id="c9194-136">如果实现这些原则，则得到针对 Microsoft 365 优化的企业网络。</span><span class="sxs-lookup"><span data-stu-id="c9194-136">If you implement these principles, you get an enterprise network optimized for Microsoft 365.</span></span>

![针对 Microsoft 365 优化的企业网络](../media/tenant-management-overview/tenant-management-networking-optimized.png)

<span data-ttu-id="c9194-138">在此图中，分支机构通过软件定义的 WAN 设备 (SDWAN) 设备有自己的 Internet 连接，该设备将受信任的 Microsoft 365 流量发送到区域最近的前端。</span><span class="sxs-lookup"><span data-stu-id="c9194-138">In this illustration, branch offices have their own Internet connection through a software-defined WAN device (SDWAN) device, which sends trusted Microsoft 365 traffic to the regionally closest front door.</span></span> <span data-ttu-id="c9194-139">在中央办公室，受信任的 Microsoft 365 流量绕过安全或代理设备，不再使用中间设备。</span><span class="sxs-lookup"><span data-stu-id="c9194-139">At the central office, trusted Microsoft 365 traffic bypasses the security or proxy device and intermediate devices are no longer used.</span></span>

<span data-ttu-id="c9194-140">下面是优化的配置如何解决传统企业网络的延迟问题：</span><span class="sxs-lookup"><span data-stu-id="c9194-140">Here's are how the optimized configuration solves the latency issues of a traditional enterprise network:</span></span>

- <span data-ttu-id="c9194-141">受信任的 Microsoft 365 流量跳过 WAN 主干网，并发送到所有办公室的本地前端，从而减少延迟。</span><span class="sxs-lookup"><span data-stu-id="c9194-141">Trusted Microsoft 365 traffic skips the WAN backbone and is sent to local front doors for all offices, decreasing latency.</span></span>
- <span data-ttu-id="c9194-142">对于 Microsoft 365 受信任流量，将跳过执行重复数据包处理的网络发夹，从而减少延迟。</span><span class="sxs-lookup"><span data-stu-id="c9194-142">Network hairpins that perform duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>
- <span data-ttu-id="c9194-143">对于 Microsoft 365 受信任流量，将跳过执行不需要和重复数据包处理的网络边缘设备，从而减少延迟。</span><span class="sxs-lookup"><span data-stu-id="c9194-143">Network edge devices that perform unneeded and duplicate packet processing are skipped for Microsoft 365 trusted traffic, decreasing latency.</span></span>

<span data-ttu-id="c9194-144">有关详细信息，请参阅 [Microsoft 365 网络连接概述](../enterprise/microsoft-365-networking-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c9194-144">For more information, see [Microsoft 365 network connectivity overview](../enterprise/microsoft-365-networking-overview.md).</span></span>

## <a name="remote-workers"></a><span data-ttu-id="c9194-145">远程工作人员</span><span class="sxs-lookup"><span data-stu-id="c9194-145">Remote workers</span></span>

<span data-ttu-id="c9194-146">如果远程工作者正在使用传统的 VPN 客户端来获取对组织网络的远程访问权限，请验证该 VPN 客户端是否支持拆分隧道。</span><span class="sxs-lookup"><span data-stu-id="c9194-146">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span> <span data-ttu-id="c9194-147">如果没有拆分隧道，所有远程工作通信都将通过 VPN 连接发送。在这种情况下，必须将其转发到组织的边缘设备、进行处理，然后在 Internet 上发送。</span><span class="sxs-lookup"><span data-stu-id="c9194-147">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span> <span data-ttu-id="c9194-148">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="c9194-148">Here is an example.</span></span>

![来自无隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="c9194-150">在此图中，Microsoft 365 流量必须通过组织采取间接路由，该路由可以转发到远离 VPN 客户端物理位置的 Microsoft 全局网络前端。</span><span class="sxs-lookup"><span data-stu-id="c9194-150">In this illustration, Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft Global Network front door far away from the VPN client’s physical location.</span></span> <span data-ttu-id="c9194-151">此间接路径会增加网络流量的延迟并降低整体性能。</span><span class="sxs-lookup"><span data-stu-id="c9194-151">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="c9194-152">借助拆分隧道，你可以将 VPN 客户端配置为排除通过 VPN 连接发送到组织网络的特定类型的通信。</span><span class="sxs-lookup"><span data-stu-id="c9194-152">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="c9194-153">要优化 Microsoft 365 云资源的访问权限，请将拆分隧道 VPN 客户端配置为排除通过 VPN 连接的流向 **优化** 类别 Microsoft 365 终结点的流量。</span><span class="sxs-lookup"><span data-stu-id="c9194-153">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="c9194-154">有关详细信息，请参阅[Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)终结点类别[](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)和用于拆分隧道的"优化"类别终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="c9194-154">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) and [the lists](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) of Optimize category endpoints for split tunneling.</span></span>

<span data-ttu-id="c9194-155">下面是拆分隧道产生的流量，其中大部分到 Microsoft 365 云应用的流量都绕过 VPN 连接。</span><span class="sxs-lookup"><span data-stu-id="c9194-155">Here is the resulting traffic flow for split tunneling, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![来自有隧道的 VPN 客户端的网络流量](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="c9194-157">在此图中，VPN 客户端直接通过 Internet 发送和接收关键的 Microsoft 365 云服务流量，并发送到 Microsoft 全球网络最近的前端。</span><span class="sxs-lookup"><span data-stu-id="c9194-157">In this illustration, the VPN client sends and receives crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest front door into the Microsoft Global Network.</span></span>

<span data-ttu-id="c9194-158">有关更多信息和指导，请参阅[使用 VPN 拆分隧道为远程用户优化 Office 365 连接](../enterprise/microsoft-365-vpn-split-tunnel.md)。</span><span class="sxs-lookup"><span data-stu-id="c9194-158">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="using-network-insights-preview"></a><span data-ttu-id="c9194-159">使用 Network Insights (预览) </span><span class="sxs-lookup"><span data-stu-id="c9194-159">Using Network Insights (preview)</span></span>

<span data-ttu-id="c9194-160">网络见解是从 Microsoft 365 租户收集的性能指标，可帮助你为办公室位置设计网络外围。</span><span class="sxs-lookup"><span data-stu-id="c9194-160">Network insights are performance metrics collected from your Microsoft 365 tenant that help you design network perimeters for your office locations.</span></span> <span data-ttu-id="c9194-161">每个见解提供有关本地用户访问租户的每个地理位置的指定问题的性能特征的实时详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9194-161">Each insight provides live details about the performance characteristics for a specified issue for each geographic location where on-premises users are accessing your tenant.</span></span>

<span data-ttu-id="c9194-162">可能会为租户显示两个租户级别的网络见解：</span><span class="sxs-lookup"><span data-stu-id="c9194-162">There are two tenant level network insights that may be shown for the tenant:</span></span>

- [<span data-ttu-id="c9194-163">受连接问题影响的 Exchange 采样连接</span><span class="sxs-lookup"><span data-stu-id="c9194-163">Exchange sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="c9194-164">受连接问题影响的 SharePoint 采样连接</span><span class="sxs-lookup"><span data-stu-id="c9194-164">SharePoint sampled connections impacted by connectivity issues</span></span>](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

<span data-ttu-id="c9194-165">这些是每个办公室位置的特定网络见解：</span><span class="sxs-lookup"><span data-stu-id="c9194-165">These are the specific network insights for each office location:</span></span>

- [<span data-ttu-id="c9194-166">回程网络出口</span><span class="sxs-lookup"><span data-stu-id="c9194-166">Backhauled network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [<span data-ttu-id="c9194-167">为附近客户检测到更好的性能</span><span class="sxs-lookup"><span data-stu-id="c9194-167">Better performance detected for customers near you</span></span>](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="c9194-168">使用非最佳 Exchange Online 服务前端</span><span class="sxs-lookup"><span data-stu-id="c9194-168">Use of a non-optimal Exchange Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="c9194-169">使用非最佳 SharePoint Online 服务前端</span><span class="sxs-lookup"><span data-stu-id="c9194-169">Use of a non-optimal SharePoint Online service front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="c9194-170">从 SharePoint 前端下载速度较低</span><span class="sxs-lookup"><span data-stu-id="c9194-170">Low download speed from SharePoint front door</span></span>](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="c9194-171">中国用户最佳网络出口</span><span class="sxs-lookup"><span data-stu-id="c9194-171">China user optimal network egress</span></span>](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
><span data-ttu-id="c9194-172">Microsoft 365 管理中心中的网络见解、性能建议和评估当前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="c9194-172">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status.</span></span> <span data-ttu-id="c9194-173">它仅适用于已在功能预览计划中注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="c9194-173">It is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

<span data-ttu-id="c9194-174">有关详细信息，请参阅 [Microsoft 365 网络见解](../enterprise/office-365-network-mac-perf-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="c9194-174">For more information, see [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).</span></span>

## <a name="sharepoint-performance-with-the-office-365-cdn"></a><span data-ttu-id="c9194-175">使用 Office 365 CDN 的 SharePoint 性能</span><span class="sxs-lookup"><span data-stu-id="c9194-175">SharePoint performance with the Office 365 CDN</span></span>

<span data-ttu-id="c9194-176">基于云的内容交付网络 (CDN) 允许你减少加载时间、节省带宽和加快响应速度。</span><span class="sxs-lookup"><span data-stu-id="c9194-176">A cloud-based Content Delivery Network (CDN) allows you to reduce load times, save bandwidth, and speed responsiveness.</span></span> <span data-ttu-id="c9194-177">CDN 通过缓存静态资产（如图形或视频文件）来提高性能，这些资产更接近请求它们浏览器的浏览器，这有助于加快下载速度并减少延迟。</span><span class="sxs-lookup"><span data-stu-id="c9194-177">A CDN improves performance by caching static assets such as graphic or video files closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="c9194-178">可以使用内置的 Office 365 内容交付网络 (CDN) （包含在 Microsoft 365 E3 和 E5 中的 SharePoint 中）来托管静态资产，以提供更好的 SharePoint 页面性能。</span><span class="sxs-lookup"><span data-stu-id="c9194-178">You can use the built-in Office 365 Content Delivery Network (CDN), included with SharePoint in Microsoft 365 E3 and E5, to host static assets to provide better performance for your SharePoint pages.</span></span>

<span data-ttu-id="c9194-179">Office 365 CDN 由多个 CDN 组成，用户可以在多个位置（即 _源_）托管静态资产，并从全局高速网络提供这些资产。</span><span class="sxs-lookup"><span data-stu-id="c9194-179">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="c9194-180">根据你想要在 Office 365 CDN 中托管的内容类型，可以添加公共源、专用源或两者。</span><span class="sxs-lookup"><span data-stu-id="c9194-180">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins, or both.</span></span>

<span data-ttu-id="c9194-181">部署和配置后，Office 365 CDN 将上载来自公用源和专用源的资产，并使它们可供通过 Internet 访问的用户快速访问。</span><span class="sxs-lookup"><span data-stu-id="c9194-181">When deployed and configured, the Office 365 CDN uploads assets from public and private origins and makes them available for fast access to users located across the Internet.</span></span>

<span data-ttu-id="c9194-182">![为用户部署的 Office 365 CDN](../media/O365-CDN/o365-cdn-flow-transparent.svg "为用户部署的 Office 365 CDN")</span><span class="sxs-lookup"><span data-stu-id="c9194-182">![Office 365 CDN deployed for users](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN deployed for users")</span></span>

<span data-ttu-id="c9194-183">有关详细信息，请参阅将 [Office 365 CDN 与 SharePoint Online 一同使用](../enterprise/use-microsoft-365-cdn-with-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="c9194-183">For more information, see [Use the Office 365 CDN with SharePoint Online](../enterprise/use-microsoft-365-cdn-with-spo.md).</span></span>

## <a name="automated-endpoint-listing"></a><span data-ttu-id="c9194-184">自动化终结点列表</span><span class="sxs-lookup"><span data-stu-id="c9194-184">Automated endpoint listing</span></span>

<span data-ttu-id="c9194-185">若要让本地客户端、边缘设备和基于云的数据包分析服务跳过对受信任的 Microsoft 365 流量的处理，必须使用与 Microsoft 365 服务对应的终结点 (IP 地址范围和 DNS 名称) 来配置它们。</span><span class="sxs-lookup"><span data-stu-id="c9194-185">To have your on-premises clients, edge devices, and cloud-based packet analysis services skip processing of trusted Microsoft 365 traffic, you must configure them with the set of endpoints (IP address ranges and DNS names) corresponding to Microsoft 365 services.</span></span> <span data-ttu-id="c9194-186">可以在防火墙和其他边缘安全设备、客户端计算机的 PAC 文件以绕过代理或分支机构的 SD-WAN 设备中手动配置这些终结点。</span><span class="sxs-lookup"><span data-stu-id="c9194-186">These endpoints can be manually configured in firewalls and other edge security devices, PAC files for client computers to bypass proxies, or SD-WAN devices at branch offices.</span></span> <span data-ttu-id="c9194-187">但是，终结点会随着时间的推移而发生变化，因此需要在这些位置持续手动维护终结点列表。</span><span class="sxs-lookup"><span data-stu-id="c9194-187">However, the endpoints change over time, requiring ongoing manual maintenance of the endpoint lists in these locations.</span></span>

<span data-ttu-id="c9194-188">若要自动化客户端 PAC 文件和网络设备中 Microsoft 365 终结点的一览和更改管理，请使用 [Office 365 IP 地址和基于 URL REST 的 Web 服务](../enterprise/microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="c9194-188">To automate the listing and change management for Microsoft 365 endpoints in your client PAC files and network devices, use the [Office 365 IP Address and URL REST-based web service](../enterprise/microsoft-365-ip-web-service.md).</span></span> <span data-ttu-id="c9194-189">此服务可帮助你更好地识别和区分 Microsoft 365 网络流量，从而更轻松地评估、配置和了解最新更改。</span><span class="sxs-lookup"><span data-stu-id="c9194-189">This service helps you better identify and differentiate Microsoft 365 network traffic, making it easier for you to evaluate, configure, and stay current with the latest changes.</span></span>

<span data-ttu-id="c9194-190">可以使用 PowerShell、Python 或其他语言来确定终结点在一段时间的变化，并配置 PAC 文件和边缘网络设备。</span><span class="sxs-lookup"><span data-stu-id="c9194-190">You can use PowerShell, Python, or other languages to determine the changes to endpoints over time and configure your PAC files and edge network devices.</span></span>

<span data-ttu-id="c9194-191">基本过程为：</span><span class="sxs-lookup"><span data-stu-id="c9194-191">The basic process is:</span></span>

1. <span data-ttu-id="c9194-192">使用 Office 365 IP 地址和 URL Web 服务和您所选择的配置机制，使用当前的 Microsoft 365 终结点集配置 PAC 文件和网络设备。</span><span class="sxs-lookup"><span data-stu-id="c9194-192">Use the Office 365 IP Address and URL web service and the configuration mechanism of your choice to configure your PAC files and network devices with the current set of Microsoft 365 endpoints.</span></span>
2. <span data-ttu-id="c9194-193">运行每日定期检查终结点中的更改或使用通知方法。</span><span class="sxs-lookup"><span data-stu-id="c9194-193">Run a daily recurring to check for changes in the endpoints or use a notification method.</span></span>
3. <span data-ttu-id="c9194-194">检测到更改时，重新生成并重新分发客户端计算机的 PAC 文件，并更改网络设备。</span><span class="sxs-lookup"><span data-stu-id="c9194-194">When changes are detected, regenerate and redistribute the PAC file for client computers and make the changes to your network devices.</span></span>

<span data-ttu-id="c9194-195">有关详细信息，请参阅 [Office 365 IP 地址和 URL Web 服务](../enterprise/microsoft-365-ip-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="c9194-195">For more information, see [Office 365 IP Address and URL web service](../enterprise/microsoft-365-ip-web-service.md).</span></span>

## <a name="results-of-step-2"></a><span data-ttu-id="c9194-196">步骤 2 的结果</span><span class="sxs-lookup"><span data-stu-id="c9194-196">Results of Step 2</span></span>

<span data-ttu-id="c9194-197">对于具有最佳网络连接的 Microsoft 365 租户，你已确定：</span><span class="sxs-lookup"><span data-stu-id="c9194-197">For your Microsoft 365 tenant with optimal networking, you have determined:</span></span>

- <span data-ttu-id="c9194-198">如何通过添加到所有分支机构的 Internet 连接并消除网络发夹来优化本地用户的网络性能。</span><span class="sxs-lookup"><span data-stu-id="c9194-198">How to optimize network performance for on-premises users by adding Internet connections to all branch offices and eliminating network hairpins.</span></span>
- <span data-ttu-id="c9194-199">如何为基于客户端的 PAC 文件和网络设备和服务实现自动化的受信任终结点列表，包括最适合企业网络 (更新) 。</span><span class="sxs-lookup"><span data-stu-id="c9194-199">How to implement automated trusted endpoint listing for your client-based PAC files and your network devices and services, including ongoing updates (most suitable for enterprise networks).</span></span>
- <span data-ttu-id="c9194-200">如何支持远程工作者访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="c9194-200">How to support the access of remote workers to on-premises resources.</span></span>
- <span data-ttu-id="c9194-201">如何使用网络见解</span><span class="sxs-lookup"><span data-stu-id="c9194-201">How to use Network Insights</span></span>
- <span data-ttu-id="c9194-202">如何部署 Office 365 CDN。</span><span class="sxs-lookup"><span data-stu-id="c9194-202">How to deploy the Office 365 CDN.</span></span>

<span data-ttu-id="c9194-203">下面是具有最佳网络的企业组织及其租户的示例。</span><span class="sxs-lookup"><span data-stu-id="c9194-203">Here is an example of an enterprise organization and its tenant with optimal networking.</span></span>

![具有最佳网络租户的示例](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[<span data-ttu-id="c9194-205">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="c9194-205">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

<span data-ttu-id="c9194-206">在此图中，此企业组织的租户具有：</span><span class="sxs-lookup"><span data-stu-id="c9194-206">In this illustration, the tenant for this enterprise organization has:</span></span>

- <span data-ttu-id="c9194-207">使用 SDWAN 设备将受信任的 Microsoft 365 流量转发到本地前端的每个分支机构的本地 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="c9194-207">Local internet access for each branch office with an SDWAN device that forwards trusted Microsoft 365 traffic to a local front door.</span></span>
- <span data-ttu-id="c9194-208">无网络发夹。</span><span class="sxs-lookup"><span data-stu-id="c9194-208">No network hairpins.</span></span>
- <span data-ttu-id="c9194-209">将 Microsoft 365 受信任流量转发到本地前端的中央办公室安全性和代理边缘设备。</span><span class="sxs-lookup"><span data-stu-id="c9194-209">Central office security and proxy edge devices that forward Microsoft 365 trusted traffic to a local front door.</span></span>

## <a name="ongoing-maintenance-for-optimal-networking"></a><span data-ttu-id="c9194-210">持续维护以实现最佳网络</span><span class="sxs-lookup"><span data-stu-id="c9194-210">Ongoing maintenance for optimal networking</span></span>

<span data-ttu-id="c9194-211">你可能需要持续：</span><span class="sxs-lookup"><span data-stu-id="c9194-211">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="c9194-212">更新边缘设备和已部署的 PAC 文件以更改终结点，或验证自动化进程是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="c9194-212">Update your edge devices and deployed PAC files for changes in endpoints or verify that your automated process works properly.</span></span>
- <span data-ttu-id="c9194-213">在 Office 365 CDN 中管理资产。</span><span class="sxs-lookup"><span data-stu-id="c9194-213">Manage your assets in the Office 365 CDN.</span></span>
- <span data-ttu-id="c9194-214">更新 VPN 客户端中的拆分隧道配置，以更改终结点。</span><span class="sxs-lookup"><span data-stu-id="c9194-214">Update the split tunneling configuration in your VPN clients for changes in endpoints.</span></span>

## <a name="next-step"></a><span data-ttu-id="c9194-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c9194-215">Next step</span></span>

<span data-ttu-id="c9194-216">[![步骤 3.同步标识并强制执行安全登录](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span><span class="sxs-lookup"><span data-stu-id="c9194-216">[![Step 3. Synchronize your identities and enforce secure sign-ins](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)</span></span>

<span data-ttu-id="c9194-217">继续使用 [标识](tenant-management-identity.md) 同步本地帐户和组，并强制执行安全用户登录。</span><span class="sxs-lookup"><span data-stu-id="c9194-217">Continue with [identity](tenant-management-identity.md) to synchronize your on-premises accounts and groups and enforce secure user sign-ins.</span></span>
