---
title: 针对中国用户的 Microsoft 365 全局租户性能优化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文提供了针对全球 Microsoft 365 租户中国用户优化网络性能的指导。
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923190"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a><span data-ttu-id="366e4-103">针对中国用户的 Microsoft 365 全局租户性能优化</span><span class="sxs-lookup"><span data-stu-id="366e4-103">Microsoft 365 global tenant performance optimization for China users</span></span>

>[!IMPORTANT]
><span data-ttu-id="366e4-104">本指南特定于位于中国的企业 **Microsoft 365** 用户连接到全局 **Microsoft 365 租户的使用方案**。</span><span class="sxs-lookup"><span data-stu-id="366e4-104">This guidance is specific to usage scenarios in which **enterprise Microsoft 365 users located in China** connect to a **global Microsoft 365 tenant**.</span></span> <span data-ttu-id="366e4-105">本指南不适用于 **由** 世纪通运营的 Office 365 中的租户。</span><span class="sxs-lookup"><span data-stu-id="366e4-105">This guidance does **not** apply to tenants in Office 365 operated by 21Vianet.</span></span>

<span data-ttu-id="366e4-106">对于具有全球 Microsoft 365 租户的企业以及在中国的企业，针对中国的用户的 Microsoft 365 客户端性能可能会因中国 Telco 的 Internet 体系结构的独特因素而变得复杂。</span><span class="sxs-lookup"><span data-stu-id="366e4-106">For enterprises with global Microsoft 365 tenants and a corporate presence in China, Microsoft 365 client performance for China-based users can be complicated by factors unique to China Telco's Internet architecture.</span></span>

<span data-ttu-id="366e4-107">中国 ISP 已监管全球公共 Internet 的接口连接，这些连接通过外围设备，这些设备容易出现高级别的跨边界网络拥塞。</span><span class="sxs-lookup"><span data-stu-id="366e4-107">China ISPs have regulated offshore connections to the global public Internet that go through perimeter devices which are prone to high-levels of cross-border network congestion.</span></span> <span data-ttu-id="366e4-108">此拥塞会为进入和离开中国的所有 Internet 流量造成数据包丢失和延迟。</span><span class="sxs-lookup"><span data-stu-id="366e4-108">This congestion creates packet loss and latency for all Internet traffic going into and out of China.</span></span>

![Microsoft 365 流量 - 未优化](../media/O365-networking/China-O365-unoptimized.png)

<span data-ttu-id="366e4-110">数据包丢失和延迟对网络服务的性能产生不利影响，尤其是需要大型数据交换 (的服务，如大型文件传输) 或需要近实时性能的 (音频和视频应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="366e4-110">Packet loss and latency is detrimental to the performance of network services, especially services that require large data exchanges (such as large file transfers) or requiring near real-time performance (audio and video applications).</span></span>

<span data-ttu-id="366e4-111">本主题旨在提供最佳实践，缓解中国跨边界网络拥塞对 Microsoft 365 服务的影响。</span><span class="sxs-lookup"><span data-stu-id="366e4-111">The goal of this topic is to provide best practices for mitigating the impact of China cross-border network congestion on Microsoft 365 services.</span></span> <span data-ttu-id="366e4-112">本主题不讨论其他常见的最后一英里性能问题，例如由于中国运营商内部路由复杂而导致数据包延迟高的问题。</span><span class="sxs-lookup"><span data-stu-id="366e4-112">This topic does not address other common last-mile performance issues such as issues of high packet latency due to complex routing within China carriers.</span></span>

## <a name="corporate-network-best-practices"></a><span data-ttu-id="366e4-113">企业网络最佳实践</span><span class="sxs-lookup"><span data-stu-id="366e4-113">Corporate network best practices</span></span>

<span data-ttu-id="366e4-114">许多在中国拥有全球 Microsoft 365 租户和用户的企业已实施专用网络，这些专用网络承载了中国办事处地点和世界各地的办公楼地点之间的公司网络流量。</span><span class="sxs-lookup"><span data-stu-id="366e4-114">Many enterprises with global Microsoft 365 tenants and users in China have implemented private networks that carry corporate network traffic between China office locations and offshore locations around the world.</span></span> <span data-ttu-id="366e4-115">这些企业可以利用此网络基础结构，以避免跨边界网络拥塞并优化其中国 Microsoft 365 服务性能。</span><span class="sxs-lookup"><span data-stu-id="366e4-115">These enterprises can leverage this network infrastructure to avoid cross-border network congestion and optimize their Microsoft 365 service performance in China.</span></span>

>[!IMPORTANT]
><span data-ttu-id="366e4-116">与所有专用 WAN 实施一样，您应始终咨询您国家/地区及/或地区的法规要求，以确保网络配置合规。</span><span class="sxs-lookup"><span data-stu-id="366e4-116">As with all private WAN implementations, you should always consult regulatory requirements for your country and/or region to ensure that your network configuration is in compliance.</span></span>

<span data-ttu-id="366e4-117">作为第一步，遵循 Microsoft [365](./network-planning-and-performance.md)的网络规划和性能优化中基准网络指南至关重要。</span><span class="sxs-lookup"><span data-stu-id="366e4-117">As a first step, it is crucial that you follow our benchmark network guidance at [Network planning and performance tuning for Microsoft 365](./network-planning-and-performance.md).</span></span> <span data-ttu-id="366e4-118">主要目标应该是尽可能避免从中国的 Internet 访问全球 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="366e4-118">The primary goal should be to avoid accessing global Microsoft 365 services from the Internet in China if possible.</span></span>

- <span data-ttu-id="366e4-119">利用现有专用网络，在中国办公网络和出口于中国以外的公共 Internet 上的出口位置之间传输 Microsoft 365 网络流量。</span><span class="sxs-lookup"><span data-stu-id="366e4-119">Leverage your existing private network to carry Microsoft 365 network traffic between China office networks and offshore locations that egress on the public Internet outside China.</span></span> <span data-ttu-id="366e4-120">中国以外的几乎任何位置都将提供明显的好处。</span><span class="sxs-lookup"><span data-stu-id="366e4-120">Almost any location outside China will provide a clear benefit.</span></span> <span data-ttu-id="366e4-121">网络管理员可以进一步优化，方法为在具有低延迟互连的区域与 [Microsoft 全球网络相互连接](/azure/networking/microsoft-global-network)。</span><span class="sxs-lookup"><span data-stu-id="366e4-121">Network administrators can further optimize by egressing in areas with low-latency interconnect with the [Microsoft global network](/azure/networking/microsoft-global-network).</span></span> <span data-ttu-id="366e4-122">例如，香港特别行政区、日本和韩国。</span><span class="sxs-lookup"><span data-stu-id="366e4-122">Hong Kong, Japan, and South Korea are examples.</span></span>
- <span data-ttu-id="366e4-123">配置用户设备以通过 VPN 连接访问企业网络，以允许 Microsoft 365 流量传输企业网络的专用链接。</span><span class="sxs-lookup"><span data-stu-id="366e4-123">Configure user devices to access the corporate network over a VPN connection to allow Microsoft 365 traffic to transit the corporate network's private offshore link.</span></span> <span data-ttu-id="366e4-124">确保 VPN 客户端未配置为使用拆分隧道，或者用户设备配置为忽略 Microsoft 365 流量的拆分隧道。</span><span class="sxs-lookup"><span data-stu-id="366e4-124">Ensure that VPN clients are either not configured to use split tunneling, or that user devices are configured to ignore split tunneling for Microsoft 365 traffic.</span></span>
- <span data-ttu-id="366e4-125">将网络配置为通过专用网链接路由所有 Microsoft 365 流量。</span><span class="sxs-lookup"><span data-stu-id="366e4-125">Configure your network to route all Microsoft 365 traffic across your private offshore link.</span></span> <span data-ttu-id="366e4-126">如果必须最大限度地减少专用链接上的流量，可以选择仅路由"优化"类别中的终结点，并允许对"允许"和"默认"终结点的请求传输Internet。 </span><span class="sxs-lookup"><span data-stu-id="366e4-126">If you must minimize the volume of traffic on your private link, you can choose to only route endpoints in the **Optimize** category, and allow requests to **Allow** and **Default** endpoints to transit the Internet.</span></span> <span data-ttu-id="366e4-127">这将通过将优化流量限制到对高延迟和数据包丢失最敏感的关键服务来提高性能并最大程度减少带宽消耗。</span><span class="sxs-lookup"><span data-stu-id="366e4-127">This will improve performance and minimize bandwidth consumption by limiting optimized traffic to critical services that are most sensitive to high latency and packet loss.</span></span>
- <span data-ttu-id="366e4-128">如果可能，请对实时媒体流通信（如 Teams）使用 UDP 而不是 TCP。</span><span class="sxs-lookup"><span data-stu-id="366e4-128">If possible, use UDP instead of TCP for live media streaming traffic, such as for Teams.</span></span> <span data-ttu-id="366e4-129">UDP 提供比 TCP 更好的实时媒体流性能。</span><span class="sxs-lookup"><span data-stu-id="366e4-129">UDP offers better live media streaming performance than TCP.</span></span>

<span data-ttu-id="366e4-130">若要了解如何选择性地路由 Microsoft 365 流量，请参阅 [管理 Office 365 终结点](managing-office-365-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="366e4-130">For information about how to selectively route Microsoft 365 traffic, see [Managing Office 365 endpoints](managing-office-365-endpoints.md).</span></span> <span data-ttu-id="366e4-131">有关全球所有 Office 365 URL 和 IP 地址的列表，请参阅 [Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="366e4-131">For a list of all worldwide Office 365 URLs and IP addresses, see [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>

![Microsoft 365 流量 - 优化](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a><span data-ttu-id="366e4-133">用户最佳做法</span><span class="sxs-lookup"><span data-stu-id="366e4-133">User best practices</span></span>

<span data-ttu-id="366e4-134">中国用户从远程位置（如家庭、咖啡店、酒店和分支机构）连接到全球 Microsoft 365 租户，而未连接到企业网络，则可能会遇到网络性能不佳的问题，因为其设备和 Microsoft 365 之间的流量必须经过中国拥堵的跨界网络线路。</span><span class="sxs-lookup"><span data-stu-id="366e4-134">Users in China who connect to global Microsoft 365 tenants from remote locations such as homes, coffee shops, hotels and branch offices with no connection to enterprise networks can experience poor network performance because traffic between their devices and Microsoft 365 must transit China's congested cross-border network circuits.</span></span>

<span data-ttu-id="366e4-135">如果无法选择跨边界专用网络和/或 VPN 访问企业网络，则仍可以通过培训基于中国的用户以遵循这些最佳做法来缓解每用户性能问题。</span><span class="sxs-lookup"><span data-stu-id="366e4-135">If cross-border private networks and/or VPN access into the corporate network are not an option, per-user performance issues can still be mitigated by training your China-based users to follow these best practices.</span></span>

- <span data-ttu-id="366e4-136">利用丰富的 Office 客户端支持缓存 (如 Outlook、Teams、OneDrive 等 ) ，并避免基于 Web 的客户端。</span><span class="sxs-lookup"><span data-stu-id="366e4-136">Utilize rich Office clients that support caching (e.g. Outlook, Teams, OneDrive, etc.), and avoid web-based clients.</span></span> <span data-ttu-id="366e4-137">Office 客户端缓存和脱机访问功能可以大大减少网络拥塞和延迟的影响。</span><span class="sxs-lookup"><span data-stu-id="366e4-137">Office client caching and offline access features can dramatically reduce the impact of network congestion and latency.</span></span>
- <span data-ttu-id="366e4-138">如果 Microsoft 365 租户已配置音频会议功能，则 Teams 用户可以通过公用电话交换网和 PSTN (加入) 。</span><span class="sxs-lookup"><span data-stu-id="366e4-138">If your Microsoft 365 tenant has been configured with the _Audio Conferencing_ feature, Teams users can join meetings via the public switched telephone network (PSTN).</span></span> <span data-ttu-id="366e4-139">有关详细信息，请参阅 [Office 365 中的音频会议](/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="366e4-139">For more information, see [Audio Conferencing in Office 365](/microsoftteams/audio-conferencing-in-office-365).</span></span>
- <span data-ttu-id="366e4-140">如果用户遇到网络性能问题，他们应报告给 IT 部门进行故障排除，如果怀疑 Microsoft 365 服务有问题，则上报给 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="366e4-140">If users experience network performance issues, they should report to their IT department for troubleshooting, and escalate to Microsoft support if trouble with Microsoft 365 services is suspected.</span></span> <span data-ttu-id="366e4-141">并非所有问题都由跨边界网络性能导致。</span><span class="sxs-lookup"><span data-stu-id="366e4-141">Not all issues are caused by cross-border network performance.</span></span>

<span data-ttu-id="366e4-142">Microsoft 一直在致力于在尽可能广泛的网络体系结构和特征范围内改进 Microsoft 365 用户体验和客户端性能。</span><span class="sxs-lookup"><span data-stu-id="366e4-142">Microsoft is continually working to improve the Microsoft 365 user experience and the performance of clients over the widest possible range of network architectures and characteristics.</span></span> <span data-ttu-id="366e4-143">访问 [Office 365](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) 技术社区以开始或加入对话、查找资源和提交功能请求和建议。</span><span class="sxs-lookup"><span data-stu-id="366e4-143">Visit the [Office 365 Tech Community](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) to start or join a conversation, find resources, and submit feature requests and suggestions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="366e4-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="366e4-144">Related topics</span></span>

[<span data-ttu-id="366e4-145">Microsoft 365 网络计划和性能优化</span><span class="sxs-lookup"><span data-stu-id="366e4-145">Network planning and performance tuning for Microsoft 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="366e4-146">Microsoft 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="366e4-146">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="366e4-147">管理 Office 365 终结点</span><span class="sxs-lookup"><span data-stu-id="366e4-147">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="366e4-148">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="366e4-148">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="366e4-149">Microsoft 全球网络</span><span class="sxs-lookup"><span data-stu-id="366e4-149">Microsoft global network</span></span>](/azure/networking/microsoft-global-network)