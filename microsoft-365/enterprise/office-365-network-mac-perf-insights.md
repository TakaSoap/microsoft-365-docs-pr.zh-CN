---
title: 'Microsoft 365 网络见解 (预览) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: a9d4dbde112c9b6c74e340824c63ce2b9749e80e
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948512"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="8391a-103">Microsoft 365 网络见解 (预览) </span><span class="sxs-lookup"><span data-stu-id="8391a-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="8391a-104">**网络见解** 是从 Microsoft 365 租户收集的性能指标，仅供租户中的管理用户查看。</span><span class="sxs-lookup"><span data-stu-id="8391a-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="8391a-105">Insights 显示在 Microsoft 365 管理中心的中 <https://portal.microsoft.com/adminportal/home#/networkperformance> 。</span><span class="sxs-lookup"><span data-stu-id="8391a-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="8391a-106">Insights 旨在帮助为你的办公室位置设计网络外围。</span><span class="sxs-lookup"><span data-stu-id="8391a-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="8391a-107">每个真知灼见都提供有关用户访问你的租户的每个地理位置的特定常见问题的性能特征的实时详细信息。</span><span class="sxs-lookup"><span data-stu-id="8391a-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="8391a-108">可以为每个办公室位置显示六个特定的网络见解：</span><span class="sxs-lookup"><span data-stu-id="8391a-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="8391a-109">Backhauled 网络出口</span><span class="sxs-lookup"><span data-stu-id="8391a-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="8391a-110">为附近的客户检测到更好的性能</span><span class="sxs-lookup"><span data-stu-id="8391a-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="8391a-111">使用非最佳 Exchange Online 服务前门</span><span class="sxs-lookup"><span data-stu-id="8391a-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="8391a-112">使用非最佳 SharePoint Online 服务前盖</span><span class="sxs-lookup"><span data-stu-id="8391a-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="8391a-113">SharePoint 前门的低下载速度</span><span class="sxs-lookup"><span data-stu-id="8391a-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="8391a-114">中国用户最佳网络出口</span><span class="sxs-lookup"><span data-stu-id="8391a-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="8391a-115">可以为租户显示两个租户级别的网络见解。</span><span class="sxs-lookup"><span data-stu-id="8391a-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="8391a-116">这些页面还会显示在 producvitivy 分数页面中：</span><span class="sxs-lookup"><span data-stu-id="8391a-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="8391a-117">由连接问题影响的 Exchange 抽样连接数</span><span class="sxs-lookup"><span data-stu-id="8391a-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="8391a-118">由连接问题影响的 SharePoint 抽样连接</span><span class="sxs-lookup"><span data-stu-id="8391a-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="8391a-119">网络洞察力、Microsoft 365 管理中心中的性能建议和评估当前处于预览状态，并且仅适用于已在功能预览计划中注册的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="8391a-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="8391a-120">Backhauled 网络出口</span><span class="sxs-lookup"><span data-stu-id="8391a-120">Backhauled network egress</span></span>

<span data-ttu-id="8391a-121">如果网络 insights 服务检测到网络传出的给定用户位置的距离大于500英里 (800 公里) （表示 Microsoft 365 流量正在被 backhauled 到公共 Internet 边缘设备或代理），将显示此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="8391a-122">在某些摘要视图中，这种洞察力缩写为 "出局"。</span><span class="sxs-lookup"><span data-stu-id="8391a-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Backhauled 网络出口](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-124">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-124">What does this mean?</span></span>

<span data-ttu-id="8391a-125">这表示办公地点和网络出口之间的距离 (800 公里) 的500英里以上。</span><span class="sxs-lookup"><span data-stu-id="8391a-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="8391a-126">办公室位置由模糊的客户端计算机位置标识，并且网络出口位置通过使用反向 IP 地址到 location 数据库来标识。</span><span class="sxs-lookup"><span data-stu-id="8391a-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="8391a-127">如果在计算机上禁用了 Windows 定位服务，则办公室位置可能不准确。</span><span class="sxs-lookup"><span data-stu-id="8391a-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="8391a-128">如果反向 IP 地址数据库信息不准确，则网络传出位置可能不准确。</span><span class="sxs-lookup"><span data-stu-id="8391a-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="8391a-129">此洞察力的详细信息包括办公地点、位置总数的租户用户总数、当前网络传出位置、传出位置的相关性、位置和当前出口点之间的距离、第一次检测条件的日期以及解决条件的日期。</span><span class="sxs-lookup"><span data-stu-id="8391a-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-130">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-130">What should I do?</span></span>

<span data-ttu-id="8391a-131">为此，我们建议网络出口离办公室位置更近，以便连接可以最佳路由到 Microsoft 的全局网络和最接近的 Microsoft 365 服务前盖。</span><span class="sxs-lookup"><span data-stu-id="8391a-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="8391a-132">由于 Microsoft 会在将来对用户的网络出口进行关闭，因此 Microsoft 会在将来对状态和 Microsoft 365 服务前端展开网络点和 Microsoft 服务之前提供改进的性能。</span><span class="sxs-lookup"><span data-stu-id="8391a-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="8391a-133">有关如何解决此问题的详细信息，请参阅[Office 365 网络连接原则](microsoft-365-network-connectivity-principles.md)中的[本地传出网络连接](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally)。</span><span class="sxs-lookup"><span data-stu-id="8391a-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="8391a-134">为附近的客户检测到更好的性能</span><span class="sxs-lookup"><span data-stu-id="8391a-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="8391a-135">如果网络 insights 服务检测到您的地铁区域中的大量客户具有比在此办公室位置的组织中的用户更好的性能，则会显示此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="8391a-136">在某些摘要视图中，这种洞察力缩写为 "对等方"。</span><span class="sxs-lookup"><span data-stu-id="8391a-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![相对网络性能](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-138">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-138">What does this mean?</span></span>

<span data-ttu-id="8391a-139">此真知灼见将检查与此办公室所在地在同一个城市中的 Microsoft 365 客户的聚合性能。</span><span class="sxs-lookup"><span data-stu-id="8391a-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="8391a-140">如果用户的平均延迟大于邻近租户平均延迟的10%，则会显示此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-141">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-141">What should I do?</span></span>

<span data-ttu-id="8391a-142">此条件的原因可能有多种，包括公司网络或 ISP 中的延迟、瓶颈或体系结构设计问题。</span><span class="sxs-lookup"><span data-stu-id="8391a-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="8391a-143">检查您的办公室网络和当前 Microsoft 365 前端之间路由中的每个跃点之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="8391a-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="8391a-144">有关详细信息，请参阅 [Office 365 网络连接原则](microsoft-365-network-connectivity-principles.md)。</span><span class="sxs-lookup"><span data-stu-id="8391a-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="8391a-145">使用非最佳 Exchange Online 服务前门</span><span class="sxs-lookup"><span data-stu-id="8391a-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="8391a-146">如果网络 insights 服务检测到特定位置中的用户未连接到最佳 Exchange Online 服务前盖，将显示此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="8391a-147">在某些摘要视图中，这种洞察力缩写为 "传送"。</span><span class="sxs-lookup"><span data-stu-id="8391a-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![非最佳前盖](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-149">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-149">What does this mean?</span></span>

<span data-ttu-id="8391a-150">我们列出了适用于办公室所在地城市的 Exchange Online 服务前盖，且具有出色的性能。</span><span class="sxs-lookup"><span data-stu-id="8391a-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="8391a-151">如果当前测试显示使用 Exchange Online 服务的前向不在此列表中，则我们称之为 "建议"。</span><span class="sxs-lookup"><span data-stu-id="8391a-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-152">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-152">What should I do?</span></span>

<span data-ttu-id="8391a-153">使用非最佳 Exchange Online 服务前盖可能是由于网络 backhaul 在公司网络出口前，在这种情况下，我们建议本地和直接网络出口。</span><span class="sxs-lookup"><span data-stu-id="8391a-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="8391a-154">也可能是由于使用远程 DNS 递归冲突解决服务器而导致的，在这种情况下，我们建议您将 DNS 递归解析器服务器与网络出口对齐。</span><span class="sxs-lookup"><span data-stu-id="8391a-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="8391a-155">使用非最佳 SharePoint Online 服务前盖</span><span class="sxs-lookup"><span data-stu-id="8391a-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="8391a-156">如果网络 insights 服务检测到特定位置中的用户未连接到最近的 SharePoint Online 服务前向，将显示此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="8391a-157">在某些摘要视图中，这种洞察力缩写为 "Afd"。</span><span class="sxs-lookup"><span data-stu-id="8391a-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![非最佳前盖](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-159">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-159">What does this mean?</span></span>

<span data-ttu-id="8391a-160">我们确定测试客户端连接到的 SharePoint Online 服务前向门。</span><span class="sxs-lookup"><span data-stu-id="8391a-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="8391a-161">然后，对于办公室所在地的城市，我们会将其与该城市的预期 SharePoint Online 服务前门进行比较。</span><span class="sxs-lookup"><span data-stu-id="8391a-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="8391a-162">如果不匹配，则建议这样做。</span><span class="sxs-lookup"><span data-stu-id="8391a-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-163">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-163">What should I do?</span></span>

<span data-ttu-id="8391a-164">使用非最佳的 SharePoint Online 服务前盖可能是由于网络 backhaul 在公司网络出口之前导致的，因此我们建议本地和直接网络出口。</span><span class="sxs-lookup"><span data-stu-id="8391a-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="8391a-165">也可能是由于使用远程 DNS 递归冲突解决服务器而导致的，在这种情况下，我们建议您将 DNS 递归解析器服务器与网络出口对齐。</span><span class="sxs-lookup"><span data-stu-id="8391a-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="8391a-166">SharePoint 前门的低下载速度</span><span class="sxs-lookup"><span data-stu-id="8391a-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="8391a-167">如果网络 insights 服务检测到特定的办公室位置和 SharePoint Online 之间的带宽小于 1 MBps，则会显示此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="8391a-168">在某些摘要视图中，这种洞察力缩写为 "吞吐量"。</span><span class="sxs-lookup"><span data-stu-id="8391a-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-169">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-169">What does this mean?</span></span>

<span data-ttu-id="8391a-170">用户可以从 SharePoint Online 和 OneDrive for business 服务前盖获取的下载速度以每秒 mb (MBps) 为单位计量。</span><span class="sxs-lookup"><span data-stu-id="8391a-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="8391a-171">如果此值小于 1 MBps，则提供此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-172">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-172">What should I do?</span></span>

<span data-ttu-id="8391a-173">为了提高下载速度，可能需要增加带宽。</span><span class="sxs-lookup"><span data-stu-id="8391a-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="8391a-174">或者，在办公室地点的用户计算机与 SharePoint Online service 前门之间可能存在网络拥塞。</span><span class="sxs-lookup"><span data-stu-id="8391a-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="8391a-175">这有时称为 congestive 丢失，它限制了用户可以使用的下载速度，即使有足够的带宽可用。</span><span class="sxs-lookup"><span data-stu-id="8391a-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="8391a-176">中国用户最佳网络出口</span><span class="sxs-lookup"><span data-stu-id="8391a-176">China user optimal network egress</span></span>

<span data-ttu-id="8391a-177">如果组织的用户在连接到你的 Microsoft 365 租户的其他地理位置，则会显示此洞察力。</span><span class="sxs-lookup"><span data-stu-id="8391a-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-178">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-178">What does this mean?</span></span>

<span data-ttu-id="8391a-179">如果您的组织具有专用 WAN 连接，我们建议您在中国的办公室位置配置网络 WAN 电路，在以下任一位置将网络出口到 Internet：</span><span class="sxs-lookup"><span data-stu-id="8391a-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="8391a-180">香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="8391a-180">Hong Kong</span></span>
- <span data-ttu-id="8391a-181">日本</span><span class="sxs-lookup"><span data-stu-id="8391a-181">Japan</span></span>
- <span data-ttu-id="8391a-182">中国台湾</span><span class="sxs-lookup"><span data-stu-id="8391a-182">Taiwan</span></span>
- <span data-ttu-id="8391a-183">韩国</span><span class="sxs-lookup"><span data-stu-id="8391a-183">South Korea</span></span>
- <span data-ttu-id="8391a-184">新加坡</span><span class="sxs-lookup"><span data-stu-id="8391a-184">Singapore</span></span>
- <span data-ttu-id="8391a-185">马来西亚</span><span class="sxs-lookup"><span data-stu-id="8391a-185">Malaysia</span></span>

<span data-ttu-id="8391a-186">远离用户的 Internet 出口与这些位置相比会降低性能，而在中国的出口可能导致由于交叉边界拥塞导致的高延迟和连接问题。</span><span class="sxs-lookup"><span data-stu-id="8391a-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-187">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-187">What should I do?</span></span>

<span data-ttu-id="8391a-188">有关如何缓解与此洞察力相关的性能问题的详细信息，请参阅 [适用于中国用户的 Office 365 全局租户性能优化](microsoft-365-networking-china.md)。</span><span class="sxs-lookup"><span data-stu-id="8391a-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="8391a-189">由连接问题影响的 Exchange 抽样连接数</span><span class="sxs-lookup"><span data-stu-id="8391a-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="8391a-190">此洞察力将显示何时有50% 或更多样本连接受到影响。</span><span class="sxs-lookup"><span data-stu-id="8391a-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="8391a-191">每个样本的 Exchange 评估为低于60% 的 Exchange 评估定义的影响。</span><span class="sxs-lookup"><span data-stu-id="8391a-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-192">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-192">What does this mean?</span></span>

<span data-ttu-id="8391a-193">这表明大多数用户可能会在连接到 Exchange Online 的 Outlook 中遇到用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="8391a-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="8391a-194">样本的百分比可能表示显示在60点以下的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="8391a-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-195">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-195">What should I do?</span></span>

<span data-ttu-id="8391a-196">启用 office location 网络连接可见性（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="8391a-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="8391a-197">您想要确定哪些分支机构受较差的网络连接 impactred 影响 Exchange 的信息，以及如何在将用户连接到 Microsoft 网络的情况中查找网络外围设备的方法。</span><span class="sxs-lookup"><span data-stu-id="8391a-197">You want to identify which offices are impactred by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="8391a-198">由连接问题影响的 SharePoint 抽样连接</span><span class="sxs-lookup"><span data-stu-id="8391a-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="8391a-199">此洞察力将显示何时有50% 或更多样本连接受到影响。</span><span class="sxs-lookup"><span data-stu-id="8391a-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="8391a-200">此影响由 SharePoint 评估定义，每个样本的低于40%。</span><span class="sxs-lookup"><span data-stu-id="8391a-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="8391a-201">应用场景</span><span class="sxs-lookup"><span data-stu-id="8391a-201">What does this mean?</span></span>

<span data-ttu-id="8391a-202">这表明大多数用户可能会遇到 SharePoint 和 OneDrive 的用户体验问题。</span><span class="sxs-lookup"><span data-stu-id="8391a-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="8391a-203">样本的百分比可能表示显示在40点以下的用户的百分比。</span><span class="sxs-lookup"><span data-stu-id="8391a-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="8391a-204">该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8391a-204">What should I do?</span></span>

<span data-ttu-id="8391a-205">启用 office location 网络连接可见性（如果尚未执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="8391a-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="8391a-206">您想要确定哪些分支机构受到影响 SharePoint 的网络连接的 impactred，并查找将用户连接到 Microsoft 网络的网络外围设备的方法。</span><span class="sxs-lookup"><span data-stu-id="8391a-206">You want to identify which offices are impactred by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8391a-207">相关主题</span><span class="sxs-lookup"><span data-stu-id="8391a-207">Related topics</span></span>

[<span data-ttu-id="8391a-208">Microsoft 365 管理中心中的网络性能建议 (preview) </span><span class="sxs-lookup"><span data-stu-id="8391a-208">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="8391a-209">Microsoft 365 网络评估 (预览版) </span><span class="sxs-lookup"><span data-stu-id="8391a-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="8391a-210">M365 管理中心中的 Microsoft 365 连接测试 (preview) </span><span class="sxs-lookup"><span data-stu-id="8391a-210">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="8391a-211">Microsoft 365 网络连接位置服务 (预览) </span><span class="sxs-lookup"><span data-stu-id="8391a-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
