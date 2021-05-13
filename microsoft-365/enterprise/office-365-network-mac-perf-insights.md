---
title: Microsoft 365Network Insights
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
description: Microsoft 365Network Insights
ms.openlocfilehash: 10b1c66a8f9aae555c2841b2b290f341bec3c7ec
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470535"
---
# <a name="microsoft-365-network-insights"></a><span data-ttu-id="fb6c3-103">Microsoft 365Network Insights</span><span class="sxs-lookup"><span data-stu-id="fb6c3-103">Microsoft 365 Network Insights</span></span>

<span data-ttu-id="fb6c3-104">**网络见解** 是从 Microsoft 365 租户收集的性能指标，可供租户中的管理用户查看。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="fb6c3-105">Insights are displayed in the Microsoft 365 Center at <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="fb6c3-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="fb6c3-106">见解旨在帮助您设计办公地点的网络外围。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="fb6c3-107">每个见解提供有关用户正在访问租户的每个地理位置的特定常见问题的性能特征的实时详细信息。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="fb6c3-108">可能会针对每个办公室位置显示六个特定的网络见解：</span><span class="sxs-lookup"><span data-stu-id="fb6c3-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="fb6c3-109">回程网络出口</span><span class="sxs-lookup"><span data-stu-id="fb6c3-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="fb6c3-110">网络中介设备</span><span class="sxs-lookup"><span data-stu-id="fb6c3-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="fb6c3-111">为附近客户检测到更好的性能</span><span class="sxs-lookup"><span data-stu-id="fb6c3-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="fb6c3-112">使用非最佳Exchange Online服务前端</span><span class="sxs-lookup"><span data-stu-id="fb6c3-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="fb6c3-113">使用非最佳联机SharePoint联机服务前端</span><span class="sxs-lookup"><span data-stu-id="fb6c3-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="fb6c3-114">从前端SharePoint下载速度</span><span class="sxs-lookup"><span data-stu-id="fb6c3-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="fb6c3-115">中国用户最佳网络出口</span><span class="sxs-lookup"><span data-stu-id="fb6c3-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="fb6c3-116">可能会为租户显示两个租户级别的网络见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="fb6c3-117">这些也显示在工作效率分数页面中：</span><span class="sxs-lookup"><span data-stu-id="fb6c3-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="fb6c3-118">Exchange连接问题影响的已采样连接</span><span class="sxs-lookup"><span data-stu-id="fb6c3-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="fb6c3-119">SharePoint连接问题影响的已采样连接</span><span class="sxs-lookup"><span data-stu-id="fb6c3-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="fb6c3-120">Microsoft 365 管理中心中的网络见解、性能建议和评估目前处于预览状态，仅适用于已在功能预览计划中注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="fb6c3-121">回程网络出口</span><span class="sxs-lookup"><span data-stu-id="fb6c3-121">Backhauled network egress</span></span>

<span data-ttu-id="fb6c3-122">如果网络见解服务检测到从给定用户位置到网络出口的距离大于 500 英里 (800 千米) ，则将显示此见解，指示 Microsoft 365 流量正回流到常见的 Internet 边缘设备或代理。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="fb6c3-123">在某些摘要视图中，此见解缩写为"出口"。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb6c3-124">![回程网络出口](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="fb6c3-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-125">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-125">What does this mean?</span></span>

<span data-ttu-id="fb6c3-126">这标识了办公地点和网络出口之间的距离超过 500 英里 (800 千米) 。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="fb6c3-127">办公室位置由模糊处理客户端计算机位置标识，网络出口位置使用反向 IP 地址到位置数据库进行标识。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="fb6c3-128">如果计算机上禁用了 Windows，则办公地点可能不准确。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="fb6c3-129">如果反向 IP 地址数据库信息不准确，则网络出口位置可能不准确。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="fb6c3-130">此见解的详细信息包括办公室位置、估计的租户用户总数在位置中的百分比、当前网络出口位置、出口位置的相关性、位置与当前出口点之间的距离、首次检测到条件的日期以及解决条件的日期。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-131">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-131">What should I do?</span></span>

<span data-ttu-id="fb6c3-132">为获得此见解，我们建议网络出口距离办公地点更近，以便连接可以最佳方式路由到 Microsoft 的全局网络和最近的 Microsoft 365 服务前端。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="fb6c3-133">关闭网络出口到用户办公地点还可以在未来提高性能，因为 Microsoft 未来将同时扩展网络接入点和Microsoft 365前端服务。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="fb6c3-134">若要详细了解如何解决此问题，请参阅[Network](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) Connectivity Principles 中的本地[Office 365出口](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="fb6c3-135">网络中介设备</span><span class="sxs-lookup"><span data-stu-id="fb6c3-135">Network intermediary device</span></span>

<span data-ttu-id="fb6c3-136">如果我们检测到你的用户和 Microsoft 网络之间的设备可能会影响你的用户体验，将显示Office 365信息。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="fb6c3-137">建议对发往 Microsoft 数据中心Microsoft 365网络通信绕过这些限制。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="fb6c3-138">Network Connectivity Principles 中Microsoft 365[进一步描述了这一建议](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="fb6c3-139">我们展示的一个网络中介见解是，当网络中介设备截获和解密 Exchange、SharePoint 和 Teams 的关键 Office 365 网络终结点时，SSL 中断和检查。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-140">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-140">What does this mean?</span></span>

<span data-ttu-id="fb6c3-141">网络中介设备（如代理服务器、VPN 和数据丢失防护设备）可能会影响流量Microsoft 365客户端的性能和稳定性。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-142">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-142">What should I do?</span></span>

<span data-ttu-id="fb6c3-143">配置检测到绕过对网络通信的处理的网络Microsoft 365设备。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="fb6c3-144">为附近客户检测到更好的性能</span><span class="sxs-lookup"><span data-stu-id="fb6c3-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="fb6c3-145">如果网络见解服务检测到您的开发区中的大量客户的性能优于此办公地点的组织中用户的性能，则将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="fb6c3-146">在某些摘要视图中，此见解缩写为"对等"。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb6c3-147">![相对网络性能](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="fb6c3-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-148">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-148">What does this mean?</span></span>

<span data-ttu-id="fb6c3-149">此见解将分析客户在此Microsoft 365同一城市的总绩效。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="fb6c3-150">如果用户的平均延迟比相邻租户的平均延迟高 10%，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-151">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-151">What should I do?</span></span>

<span data-ttu-id="fb6c3-152">此情况可能有很多原因，包括公司网络或 ISP 中的延迟、瓶颈或体系结构设计问题。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="fb6c3-153">检查办公室网络与当前网络之间的路由中每个跃点Microsoft 365延迟。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="fb6c3-154">有关详细信息，请参阅Microsoft 365[网络连接原则](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="fb6c3-155">使用非最佳Exchange Online服务前端</span><span class="sxs-lookup"><span data-stu-id="fb6c3-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="fb6c3-156">如果网络见解服务检测到特定位置的用户未连接到最佳服务前端，将显示Exchange Online见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="fb6c3-157">此见解在一些摘要视图中缩写为"路由"。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb6c3-158">![非最佳 EXO 前端](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="fb6c3-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-159">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-159">What does this mean?</span></span>

<span data-ttu-id="fb6c3-160">我们Exchange Online适合从办公地点城市使用、性能良好的服务前端门。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="fb6c3-161">如果当前测试显示是否Exchange Online服务前端未在此列表中，那么我们将提出此建议。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-162">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-162">What should I do?</span></span>

<span data-ttu-id="fb6c3-163">使用非最佳Exchange Online服务前端可能是由于企业网络出口前面的网络回程所致，在这种情况下，我们建议使用本地和直接网络出口。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="fb6c3-164">它还可能是由于使用远程 DNS 递归解析程序服务器所致，在这种情况下，我们建议将 DNS 递归解析器服务器与网络出口对齐。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="fb6c3-165">使用非最佳联机SharePoint联机服务前端</span><span class="sxs-lookup"><span data-stu-id="fb6c3-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="fb6c3-166">如果网络见解服务检测到特定位置的用户未连接到最近的 SharePoint Online 服务前端，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="fb6c3-167">此见解在一些摘要视图中缩写为"Afd"。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb6c3-168">![非最佳 SPO 前端](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="fb6c3-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-169">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-169">What does this mean?</span></span>

<span data-ttu-id="fb6c3-170">我们SharePoint客户端连接到的联机服务前端。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="fb6c3-171">然后，对于办公地点城市，我们将它SharePoint该城市的预期联机服务前端。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="fb6c3-172">如果不匹配，我们提出此建议。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-173">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-173">What should I do?</span></span>

<span data-ttu-id="fb6c3-174">使用非最佳 SharePoint Online 服务前端可能是由于企业网络出口前面的网络回程所致，在这种情况下，我们建议使用本地和直接网络出口。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="fb6c3-175">它还可能是由于使用远程 DNS 递归解析程序服务器所致，在这种情况下，我们建议将 DNS 递归解析器服务器与网络出口对齐。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="fb6c3-176">从前端SharePoint下载速度</span><span class="sxs-lookup"><span data-stu-id="fb6c3-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="fb6c3-177">如果网络见解服务检测到特定办公地点与 SharePoint Online 之间的带宽小于 1 MBps，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="fb6c3-178">在某些摘要视图中，此见解缩写为"吞吐量"。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-179">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-179">What does this mean?</span></span>

<span data-ttu-id="fb6c3-180">用户可以从 SharePoint Online 和 OneDrive for Business 服务前端门获取的下载速度以每秒兆字节 (MBps) 。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="fb6c3-181">如果此值小于 1 MBps，我们将提供此见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-182">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-182">What should I do?</span></span>

<span data-ttu-id="fb6c3-183">若要提高下载速度，可能需要增加带宽。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="fb6c3-184">或者，办公地点的用户计算机和 SharePoint Online 服务前端之间可能存在网络拥塞。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="fb6c3-185">这有时称为"连接丢失"，即使有足够的带宽可用，它也会限制可供用户使用的下载速度。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="fb6c3-186">中国用户最佳网络出口</span><span class="sxs-lookup"><span data-stu-id="fb6c3-186">China user optimal network egress</span></span>

<span data-ttu-id="fb6c3-187">如果你的组织在中国有用户连接到位于其他地理位置的 Microsoft 365 租户，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-188">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-188">What does this mean?</span></span>

<span data-ttu-id="fb6c3-189">如果您的组织具有专用 WAN 连接，我们建议您从位于中国的办公地点配置网络 WAN 线路，该线路具有网络出口到以下任一位置的 Internet：</span><span class="sxs-lookup"><span data-stu-id="fb6c3-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="fb6c3-190">香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="fb6c3-190">Hong Kong</span></span>
- <span data-ttu-id="fb6c3-191">日本</span><span class="sxs-lookup"><span data-stu-id="fb6c3-191">Japan</span></span>
- <span data-ttu-id="fb6c3-192">Taiwan（台湾）</span><span class="sxs-lookup"><span data-stu-id="fb6c3-192">Taiwan</span></span>
- <span data-ttu-id="fb6c3-193">韩国</span><span class="sxs-lookup"><span data-stu-id="fb6c3-193">South Korea</span></span>
- <span data-ttu-id="fb6c3-194">新加坡</span><span class="sxs-lookup"><span data-stu-id="fb6c3-194">Singapore</span></span>
- <span data-ttu-id="fb6c3-195">马来西亚</span><span class="sxs-lookup"><span data-stu-id="fb6c3-195">Malaysia</span></span>

<span data-ttu-id="fb6c3-196">与这些位置距离用户更远的 Internet 出口将降低性能，并且由于跨界拥塞，中国出口可能会导致高延迟和连接问题。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-197">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-197">What should I do?</span></span>

<span data-ttu-id="fb6c3-198">若要详细了解如何缓解与此见解相关的性能问题，请参阅Microsoft 365中国用户的全局[租户性能优化](microsoft-365-networking-china.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="fb6c3-199">Exchange连接问题影响的已采样连接</span><span class="sxs-lookup"><span data-stu-id="fb6c3-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="fb6c3-200">此见解将说明 50% 或 50% 以上的采样连接何时受到影响。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="fb6c3-201">该影响由评估Exchange样本低于 60%。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-202">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-202">What does this mean?</span></span>

<span data-ttu-id="fb6c3-203">这表示你的大多数用户在连接到 Outlook 时可能会遇到Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="fb6c3-204">样本百分比可能表示显示低于 60 分的用户百分比。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-205">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-205">What should I do?</span></span>

<span data-ttu-id="fb6c3-206">启用 Office 位置网络连接可见性（如果尚未启用）。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="fb6c3-207">您希望确定哪些办事处受到影响 Exchange且网络连接不佳的影响，并找到改进将用户连接到 Microsoft 网络的每个办事处的网络外围的方法。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="fb6c3-208">SharePoint连接问题影响的已采样连接</span><span class="sxs-lookup"><span data-stu-id="fb6c3-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="fb6c3-209">此见解将说明 50% 或 50% 以上的采样连接何时受到影响。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="fb6c3-210">该影响由评估SharePoint样本低于 40%。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="fb6c3-211">这意味着什么?</span><span class="sxs-lookup"><span data-stu-id="fb6c3-211">What does this mean?</span></span>

<span data-ttu-id="fb6c3-212">这表示你的大多数用户可能遇到与用户或用户SharePoint OneDrive。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="fb6c3-213">样本百分比可能表示显示低于 40 分的用户百分比。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="fb6c3-214">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fb6c3-214">What should I do?</span></span>

<span data-ttu-id="fb6c3-215">启用 Office 位置网络连接可见性（如果尚未启用）。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="fb6c3-216">您希望确定哪些办事处受影响 SharePoint且网络连接不佳的影响，并找到改进将用户连接到 Microsoft 网络的每个办事处的网络外围的方法。</span><span class="sxs-lookup"><span data-stu-id="fb6c3-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fb6c3-217">相关主题</span><span class="sxs-lookup"><span data-stu-id="fb6c3-217">Related topics</span></span>

[<span data-ttu-id="fb6c3-218">Microsoft 365 管理中心 (预览) </span><span class="sxs-lookup"><span data-stu-id="fb6c3-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="fb6c3-219">Microsoft 365网络评估 (预览) </span><span class="sxs-lookup"><span data-stu-id="fb6c3-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="fb6c3-220">Microsoft 365预览版 (网络连接测试) </span><span class="sxs-lookup"><span data-stu-id="fb6c3-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="fb6c3-221">Microsoft 365网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="fb6c3-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
