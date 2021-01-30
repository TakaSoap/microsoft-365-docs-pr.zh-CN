---
title: 'Microsoft 365 网络见解 (预览) '
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
description: 'Microsoft 365 网络见解 (预览) '
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055469"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="ab413-103">Microsoft 365 网络见解 (预览) </span><span class="sxs-lookup"><span data-stu-id="ab413-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="ab413-104">**网络见解** 是从 Microsoft 365 租户收集的性能指标，仅可供租户中的管理用户查看。</span><span class="sxs-lookup"><span data-stu-id="ab413-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="ab413-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="ab413-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="ab413-106">见解旨在帮助您设计办公地点的网络外围。</span><span class="sxs-lookup"><span data-stu-id="ab413-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="ab413-107">每个见解都提供有关用户访问租户的每个地理位置的特定常见问题的性能特征的实时详细信息。</span><span class="sxs-lookup"><span data-stu-id="ab413-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="ab413-108">每个办公室位置可能会显示六个特定的网络见解：</span><span class="sxs-lookup"><span data-stu-id="ab413-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="ab413-109">回程网络出口</span><span class="sxs-lookup"><span data-stu-id="ab413-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="ab413-110">网络中介设备</span><span class="sxs-lookup"><span data-stu-id="ab413-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="ab413-111">为附近客户检测到更好的性能</span><span class="sxs-lookup"><span data-stu-id="ab413-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="ab413-112">使用非最佳 Exchange Online 服务前端</span><span class="sxs-lookup"><span data-stu-id="ab413-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="ab413-113">使用非最佳 SharePoint Online 服务前端</span><span class="sxs-lookup"><span data-stu-id="ab413-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="ab413-114">从 SharePoint 前端下载速度较低</span><span class="sxs-lookup"><span data-stu-id="ab413-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="ab413-115">中国用户最佳网络出口</span><span class="sxs-lookup"><span data-stu-id="ab413-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="ab413-116">可能会为租户显示两个租户级别的网络见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="ab413-117">这些也显示在 producvitivy 分数页面中：</span><span class="sxs-lookup"><span data-stu-id="ab413-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="ab413-118">受连接问题影响的 Exchange 采样连接</span><span class="sxs-lookup"><span data-stu-id="ab413-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="ab413-119">受连接问题影响的 SharePoint 采样连接</span><span class="sxs-lookup"><span data-stu-id="ab413-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="ab413-120">Microsoft 365 管理中心中的网络见解、性能建议和评估目前处于预览状态，仅适用于已在功能预览计划注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="ab413-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="ab413-121">回程网络出口</span><span class="sxs-lookup"><span data-stu-id="ab413-121">Backhauled network egress</span></span>

<span data-ttu-id="ab413-122">如果网络见解服务检测到从给定用户位置到网络出口的距离大于 500 英里 (800 千米) ，则将显示此见解，指示 Microsoft 365 流量正在回流到常见的 Internet 边缘设备或代理。</span><span class="sxs-lookup"><span data-stu-id="ab413-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="ab413-123">在某些摘要视图中，此见解缩写为"出口"。</span><span class="sxs-lookup"><span data-stu-id="ab413-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![回程网络出口](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-125">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-125">What does this mean?</span></span>

<span data-ttu-id="ab413-126">这标识了办公室位置和网络出口之间的距离超过 500 英里 (800 千米) 。</span><span class="sxs-lookup"><span data-stu-id="ab413-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="ab413-127">办公室位置由混淆的客户端计算机位置标识，网络出口位置使用反向 IP 地址标识到位置数据库。</span><span class="sxs-lookup"><span data-stu-id="ab413-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="ab413-128">如果计算机上禁用了 Windows Location Services，则办公地点可能不准确。</span><span class="sxs-lookup"><span data-stu-id="ab413-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="ab413-129">如果反向 IP 地址数据库信息不准确，则网络出口位置可能不准确。</span><span class="sxs-lookup"><span data-stu-id="ab413-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="ab413-130">此见解的详细信息包括办公室位置、位置中租户用户总数的估计百分比、当前网络出口位置、出口位置的相关性、位置与当前出口点之间的距离、首次检测到条件的日期以及解决条件的日期。</span><span class="sxs-lookup"><span data-stu-id="ab413-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-131">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-131">What should I do?</span></span>

<span data-ttu-id="ab413-132">为获得此见解，我们建议网络出口更接近办公地点，以便连接性可以最佳地路由到 Microsoft 的全局网络和最近的 Microsoft 365 服务前端。</span><span class="sxs-lookup"><span data-stu-id="ab413-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="ab413-133">通过关闭到用户办公室位置的网络出口，还可以在未来提高性能，因为 Microsoft 未来将同时扩展网络接入点和 Microsoft 365 服务前端入口。</span><span class="sxs-lookup"><span data-stu-id="ab413-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="ab413-134">若要详细了解如何解决此问题，请参阅[Office 365](microsoft-365-network-connectivity-principles.md)网络连接原则中的本地出口网络连接。 [](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)</span><span class="sxs-lookup"><span data-stu-id="ab413-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="ab413-135">网络中介设备</span><span class="sxs-lookup"><span data-stu-id="ab413-135">Network intermediary device</span></span>

<span data-ttu-id="ab413-136">如果我们检测到用户和 Microsoft 网络之间的设备可能会影响 Office 365 用户体验，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="ab413-137">对于发往 Microsoft 数据中心的特定 Microsoft 365 网络流量，建议绕过这些限制。</span><span class="sxs-lookup"><span data-stu-id="ab413-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="ab413-138">Microsoft [365](microsoft-365-network-connectivity-principles.md)网络连接原则中还介绍了此建议</span><span class="sxs-lookup"><span data-stu-id="ab413-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-139">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-139">What does this mean?</span></span>

<span data-ttu-id="ab413-140">代理服务器、VPN 和数据丢失防护设备等网络中介设备可能会影响中间流量的 Microsoft 365 客户端的性能和稳定性。</span><span class="sxs-lookup"><span data-stu-id="ab413-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-141">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-141">What should I do?</span></span>

<span data-ttu-id="ab413-142">配置检测到绕过 Microsoft 365 网络流量处理的网络中介设备。</span><span class="sxs-lookup"><span data-stu-id="ab413-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="ab413-143">为附近客户检测到更好的性能</span><span class="sxs-lookup"><span data-stu-id="ab413-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="ab413-144">如果网络见解服务检测到您的都市地区的大量客户的性能优于位于此办公地点的组织中用户，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="ab413-145">在某些摘要视图中，此见解缩写为"对等"。</span><span class="sxs-lookup"><span data-stu-id="ab413-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![相对网络性能](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-147">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-147">What does this mean?</span></span>

<span data-ttu-id="ab413-148">此见解将检查 Microsoft 365 客户在此办公地点位于同一城市的总绩效。</span><span class="sxs-lookup"><span data-stu-id="ab413-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="ab413-149">如果用户的平均延迟比相邻租户的平均延迟高 10%，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-150">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-150">What should I do?</span></span>

<span data-ttu-id="ab413-151">此情况的原因可能有很多，包括企业网络或 ISP 中的延迟、瓶颈或体系结构设计问题。</span><span class="sxs-lookup"><span data-stu-id="ab413-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="ab413-152">检查 Office 网络与当前 Microsoft 365 前端之间的路由中每个跃点之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="ab413-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="ab413-153">有关详细信息，请参阅 [Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="ab413-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="ab413-154">使用非最佳 Exchange Online 服务前端</span><span class="sxs-lookup"><span data-stu-id="ab413-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="ab413-155">如果网络见解服务检测到特定位置的用户未连接到最佳 Exchange Online 服务前端，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="ab413-156">在某些摘要视图中，此见解缩写为"路由"。</span><span class="sxs-lookup"><span data-stu-id="ab413-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![非最佳 EXO 前端](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-158">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-158">What does this mean?</span></span>

<span data-ttu-id="ab413-159">我们列出了适合从办公地点城市使用、性能良好的 Exchange Online 服务前端。</span><span class="sxs-lookup"><span data-stu-id="ab413-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="ab413-160">如果当前测试显示未在此列表中使用 Exchange Online 服务前端，则我们将调用此建议。</span><span class="sxs-lookup"><span data-stu-id="ab413-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-161">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-161">What should I do?</span></span>

<span data-ttu-id="ab413-162">使用非最佳 Exchange Online 服务前端可能是由于企业网络出口之前的网络回程所致，在这种情况下，我们建议使用本地和直接网络出口。</span><span class="sxs-lookup"><span data-stu-id="ab413-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ab413-163">它还可能是由于使用远程 DNS 递归解析器服务器导致的，在这种情况下，我们建议将 DNS 递归解析器服务器与网络出口对齐。</span><span class="sxs-lookup"><span data-stu-id="ab413-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="ab413-164">使用非最佳 SharePoint Online 服务前端</span><span class="sxs-lookup"><span data-stu-id="ab413-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="ab413-165">如果网络见解服务检测到特定位置的用户未连接到最近的 SharePoint Online 服务前端，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="ab413-166">在某些摘要视图中，此见解缩写为"Afd"。</span><span class="sxs-lookup"><span data-stu-id="ab413-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![非最佳 SPO 前端](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-168">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-168">What does this mean?</span></span>

<span data-ttu-id="ab413-169">我们确定测试客户端连接到的 SharePoint Online 服务前端。</span><span class="sxs-lookup"><span data-stu-id="ab413-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="ab413-170">然后，对于办公地点城市，我们将该城市与预期的 SharePoint Online 服务前端进行比较。</span><span class="sxs-lookup"><span data-stu-id="ab413-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="ab413-171">如果不匹配，我们提出此建议。</span><span class="sxs-lookup"><span data-stu-id="ab413-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-172">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-172">What should I do?</span></span>

<span data-ttu-id="ab413-173">使用非最佳 SharePoint Online 服务前端可能是由于企业网络出口之前的网络回程所致，在这种情况下，我们建议使用本地和直接网络出口。</span><span class="sxs-lookup"><span data-stu-id="ab413-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="ab413-174">它还可能是由于使用远程 DNS 递归解析器服务器导致的，在这种情况下，我们建议将 DNS 递归解析器服务器与网络出口对齐。</span><span class="sxs-lookup"><span data-stu-id="ab413-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="ab413-175">从 SharePoint 前端下载速度低</span><span class="sxs-lookup"><span data-stu-id="ab413-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="ab413-176">如果网络见解服务检测到特定办公地点与 SharePoint Online 之间的带宽小于 1 MBps，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="ab413-177">在某些摘要视图中，此见解缩写为"吞吐量"。</span><span class="sxs-lookup"><span data-stu-id="ab413-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-178">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-178">What does this mean?</span></span>

<span data-ttu-id="ab413-179">用户可以从 SharePoint Online 和 OneDrive for Business 服务前端门获取的下载速度以兆字节/ (MBps) 。</span><span class="sxs-lookup"><span data-stu-id="ab413-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="ab413-180">如果此值小于 1 MBps，我们将提供此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-181">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-181">What should I do?</span></span>

<span data-ttu-id="ab413-182">若要提高下载速度，可能需要增加带宽。</span><span class="sxs-lookup"><span data-stu-id="ab413-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="ab413-183">或者，办公室位置的用户计算机和 SharePoint Online 服务前端之间可能存在网络拥塞。</span><span class="sxs-lookup"><span data-stu-id="ab413-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="ab413-184">有时，这称为"连接丢失"，它限制了可供用户使用的下载速度，即使有足够的带宽可用。</span><span class="sxs-lookup"><span data-stu-id="ab413-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="ab413-185">中国用户最佳网络出口</span><span class="sxs-lookup"><span data-stu-id="ab413-185">China user optimal network egress</span></span>

<span data-ttu-id="ab413-186">如果你的组织在中国有用户连接到其他地理位置的 Microsoft 365 租户，将显示此见解。</span><span class="sxs-lookup"><span data-stu-id="ab413-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-187">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-187">What does this mean?</span></span>

<span data-ttu-id="ab413-188">如果您的组织具有专用 WAN 连接，我们建议从中国的办公室位置配置网络 WAN 线路，该线路具有以下任一位置的 Internet 网络出口：</span><span class="sxs-lookup"><span data-stu-id="ab413-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="ab413-189">香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="ab413-189">Hong Kong</span></span>
- <span data-ttu-id="ab413-190">日本</span><span class="sxs-lookup"><span data-stu-id="ab413-190">Japan</span></span>
- <span data-ttu-id="ab413-191">Taiwan（台湾）</span><span class="sxs-lookup"><span data-stu-id="ab413-191">Taiwan</span></span>
- <span data-ttu-id="ab413-192">韩国</span><span class="sxs-lookup"><span data-stu-id="ab413-192">South Korea</span></span>
- <span data-ttu-id="ab413-193">新加坡</span><span class="sxs-lookup"><span data-stu-id="ab413-193">Singapore</span></span>
- <span data-ttu-id="ab413-194">马来西亚</span><span class="sxs-lookup"><span data-stu-id="ab413-194">Malaysia</span></span>

<span data-ttu-id="ab413-195">与这些位置距离更远的用户的 Internet 出口将降低性能，并且由于跨界拥塞，中国出口可能会导致高延迟和连接问题。</span><span class="sxs-lookup"><span data-stu-id="ab413-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-196">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-196">What should I do?</span></span>

<span data-ttu-id="ab413-197">若要详细了解如何缓解与此见解相关的性能问题，请参阅针对中国用户的 [Microsoft 365 全局租户性能优化](microsoft-365-networking-china.md)。</span><span class="sxs-lookup"><span data-stu-id="ab413-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="ab413-198">受连接问题影响的 Exchange 采样连接</span><span class="sxs-lookup"><span data-stu-id="ab413-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="ab413-199">此见解将显示 50% 或 50% 以上的采样连接何时受到影响。</span><span class="sxs-lookup"><span data-stu-id="ab413-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="ab413-200">Exchange 评估针对每个示例将影响定义为低于 60%。</span><span class="sxs-lookup"><span data-stu-id="ab413-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-201">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-201">What does this mean?</span></span>

<span data-ttu-id="ab413-202">这表示大多数用户可能遇到连接到 Exchange Online 的 Outlook 的用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="ab413-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="ab413-203">样本百分比可能表示显示低于 60 分的用户百分比。</span><span class="sxs-lookup"><span data-stu-id="ab413-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-204">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-204">What should I do?</span></span>

<span data-ttu-id="ab413-205">如果尚未启用，启用 Office 位置网络连接可见性。</span><span class="sxs-lookup"><span data-stu-id="ab413-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="ab413-206">要确定哪些办事处受影响 Exchange 的网络连接不佳的影响，并找到在将用户连接到 Microsoft 网络的每个办事处上改进网络外围的方法。</span><span class="sxs-lookup"><span data-stu-id="ab413-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="ab413-207">受连接问题影响的 SharePoint 采样连接</span><span class="sxs-lookup"><span data-stu-id="ab413-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="ab413-208">此见解将显示 50% 或 50% 以上的采样连接何时受到影响。</span><span class="sxs-lookup"><span data-stu-id="ab413-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="ab413-209">影响由 SharePoint 评估定义，每个样本低于 40%。</span><span class="sxs-lookup"><span data-stu-id="ab413-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="ab413-210">应用场景</span><span class="sxs-lookup"><span data-stu-id="ab413-210">What does this mean?</span></span>

<span data-ttu-id="ab413-211">这表示你的大多数用户可能会遇到 SharePoint 和 OneDrive 的用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="ab413-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="ab413-212">样本百分比可能表示显示低于 40 分的用户百分比。</span><span class="sxs-lookup"><span data-stu-id="ab413-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="ab413-213">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ab413-213">What should I do?</span></span>

<span data-ttu-id="ab413-214">如果尚未启用，启用 Office 位置网络连接可见性。</span><span class="sxs-lookup"><span data-stu-id="ab413-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="ab413-215">要确定哪些办事处受影响 SharePoint 的网络连接不佳的影响，并找到改进将用户连接到 Microsoft 网络的每个办事处的网络外围的方法。</span><span class="sxs-lookup"><span data-stu-id="ab413-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab413-216">相关主题</span><span class="sxs-lookup"><span data-stu-id="ab413-216">Related topics</span></span>

[<span data-ttu-id="ab413-217">Microsoft 365 管理中心中的网络连接 (预览版) </span><span class="sxs-lookup"><span data-stu-id="ab413-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="ab413-218">Microsoft 365 网络评估 (预览) </span><span class="sxs-lookup"><span data-stu-id="ab413-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="ab413-219">Microsoft 365 网络连接测试工具 (预览) </span><span class="sxs-lookup"><span data-stu-id="ab413-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="ab413-220">Microsoft 365 网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="ab413-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
